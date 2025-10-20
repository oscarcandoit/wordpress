---
url: https://developer.wordpress.org/reference/functions/get_date_from_gmt
scraped_at: 2025-10-20T03:22:58.297Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_date\_from\_gmt()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_date\_from\_gmt()

Search

# get\_date\_from\_gmt( string$date\_string, string$format = 'Y-m-d H:i:s' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#wp--skip-link--target)

Given a date in UTC or GMT timezone, returns that date in the timezone of the site.

## [Description](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#description)

Requires a date in the Y-m-d H:i:s format.

Default return format of ‘Y-m-d H:i:s’ can be overridden using the `$format` parameter.

## [Parameters](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#parameters)

`$date_string` stringrequired

The date to be converted, in UTC or GMT timezone.

`$format` stringoptional

The format string for the returned date. Default ‘Y-m-d H:i:s’.

Default: `'Y-m-d H:i:s'`

## [Return](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#return)

string Formatted version of the date, in the site’s timezone.

## [Source](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#source)

`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#)

```php
function get_date_from_gmt( $date_string, $format = 'Y-m-d H:i:s' ) {
	$datetime = date_create( $date_string, new DateTimeZone( 'UTC' ) );

	if ( false === $datetime ) {
		return gmdate( $format, 0 );
	}

	return $datetime->setTimezone( wp_timezone() )->format( $format );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L3683) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L3683-L3691)

## [Related](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#related)

| Uses | Description |
| --- | --- |
| [wp\_timezone()](https://developer.wordpress.org/reference/functions/wp_timezone/) `wp-includes/functions.php` | Retrieves the timezone of the site as a `DateTimeZone` object. |

| Used by | Description |
| --- | --- |
| [wp\_resolve\_post\_date()](https://developer.wordpress.org/reference/functions/wp_resolve_post_date/) `wp-includes/post.php` | Uses wp\_checkdate to return a valid Gregorian-calendar value for post\_date. |
| [WP\_Customize\_Manager::save\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Saves the post for the loaded changeset. |
| [rest\_get\_date\_with\_gmt()](https://developer.wordpress.org/reference/functions/rest_get_date_with_gmt/) `wp-includes/rest-api.php` | Parses a date into both its local and UTC equivalent, in MySQL datetime format. |
| [wp\_xmlrpc\_server::wp\_editComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a comment. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_date_from_gmt/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#comment-content-5119)



[get\_date\_from\_gmt()](https://developer.wordpress.org/reference/functions/get_date_from_gmt/) does not accept a Unix Timestamp because date\_create() doesn’t.



If you need to provide a Unix Timestamp, you will need to convert it to a different format first like the following example:





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#)




```php
<?php

$utc_timestamp = 1623096269;

// This is a format that date_create() will accept
$utc_timestamp_converted = date( 'Y-m-d H:i:s', $utc_timestamp );

$output_format = 'Y-m-d H:i:s';

// Now we can use our timestamp with get_date_from_gmt()
$local_timestamp = get_date_from_gmt( $utc_timestamp_converted, $output_format );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_date_from_gmt%2F%3Freplytocom%3D5119%23feedback-editor-5119)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_date_from_gmt/#comment-content-7048)



The inverse function is [get\_gmt\_from\_date](https://developer.wordpress.org/reference/functions/get_gmt_from_date/).





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_date_from_gmt%2F%3Freplytocom%3D7048%23feedback-editor-7048)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_date_from_gmt%2F) before being able to contribute a note or feedback.

Notifications