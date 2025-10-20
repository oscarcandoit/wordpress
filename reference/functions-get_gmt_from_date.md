---
url: https://developer.wordpress.org/reference/functions/get_gmt_from_date
scraped_at: 2025-10-20T03:25:31.890Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_gmt\_from\_date()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_gmt\_from\_date()

Search

# get\_gmt\_from\_date( string$date\_string, string$format = 'Y-m-d H:i:s' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#wp--skip-link--target)

Given a date in the timezone of the site, returns that date in UTC.

## [Description](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#description)

Requires and returns a date in the Y-m-d H:i:s format.

Return format can be overridden using the $format parameter.

## [Parameters](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#parameters)

`$date_string` stringrequired

The date to be converted, in the timezone of the site.

`$format` stringoptional

The format string for the returned date. Default ‘Y-m-d H:i:s’.

Default: `'Y-m-d H:i:s'`

## [Return](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#return)

string Formatted version of the date, in UTC.

## [Source](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#source)

`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#)

```php
function get_gmt_from_date( $date_string, $format = 'Y-m-d H:i:s' ) {
	$datetime = date_create( $date_string, wp_timezone() );

	if ( false === $datetime ) {
		return gmdate( $format, 0 );
	}

	return $datetime->setTimezone( new DateTimeZone( 'UTC' ) )->format( $format );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L3661) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L3661-L3669)

## [Related](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#related)

| Uses | Description |
| --- | --- |
| [wp\_timezone()](https://developer.wordpress.org/reference/functions/wp_timezone/) `wp-includes/functions.php` | Retrieves the timezone of the site as a `DateTimeZone` object. |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post output for response. |
| [rest\_get\_date\_with\_gmt()](https://developer.wordpress.org/reference/functions/rest_get_date_with_gmt/) `wp-includes/rest-api.php` | Parses a date into both its local and UTC equivalent, in MySQL datetime format. |
| [\_wp\_translate\_postdata()](https://developer.wordpress.org/reference/functions/_wp_translate_postdata/) `wp-admin/includes/post.php` | Renames `$_POST` data from form names to DB post columns. |
| [WP\_Customize\_Manager::save()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save/) `wp-includes/class-wp-customize-manager.php` | Handles customize\_save WP Ajax request to save/update a changeset. |
| [\_future\_post\_hook()](https://developer.wordpress.org/reference/functions/_future_post_hook/) `wp-includes/post.php` | Hook used to schedule publication for a post marked for the future. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wp\_xmlrpc\_server::\_convert\_date\_gmt()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_convert_date_gmt/) `wp-includes/class-wp-xmlrpc-server.php` | Converts a WordPress GMT date string to an [IXR\_Date](https://developer.wordpress.org/reference/classes/ixr_date/) object. |
| [wp\_update\_comment()](https://developer.wordpress.org/reference/functions/wp_update_comment/) `wp-includes/comment.php` | Updates an existing comment in the database. |
| [wp\_insert\_comment()](https://developer.wordpress.org/reference/functions/wp_insert_comment/) `wp-includes/comment.php` | Inserts a comment into the database. |

[Show 4 more](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#) [Show less](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_gmt_from_date/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/get_gmt_from_date/#comment-content-3934)



The inverse of this is get\_date\_from\_gmt



[https://developer.wordpress.org/reference/functions/get\_date\_from\_gmt/](https://developer.wordpress.org/reference/functions/get_date_from_gmt/)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_gmt_from_date%2F%3Freplytocom%3D3934%23feedback-editor-3934)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_gmt_from_date%2F) before being able to contribute a note or feedback.

Notifications