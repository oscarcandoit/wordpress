---
url: https://developer.wordpress.org/reference/functions/get_post_timestamp
scraped_at: 2025-10-20T03:20:25.347Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_post_timestamp/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_post\_timestamp()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_post\_timestamp()

Search

# get\_post\_timestamp( int\|WP\_Post$post = null, string$field = 'date' ): int\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_post_timestamp/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_post_timestamp/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_post_timestamp/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_post_timestamp/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_post_timestamp/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_post_timestamp/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_timestamp/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_post_timestamp/#wp--skip-link--target)

Retrieves post published or modified time as a Unix timestamp.

## [Description](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#description)

Note that this function returns a true Unix timestamp, not summed with timezone offset like older WP functions.

## [Parameters](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Post ID or post object. Default is global `$post` object.

Default: `null`

`$field` stringoptional

Published or modified time to use from database. Accepts `'date'` or `'modified'`.

Default `'date'`.

Default: `'date'`

## [Return](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#return)

int\|false Unix timestamp on success, false on failure.

## [Source](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#source)

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_timestamp/#)

```php
function get_post_timestamp( $post = null, $field = 'date' ) {
	$datetime = get_post_datetime( $post, $field );

	if ( false === $datetime ) {
		return false;
	}

	return $datetime->getTimestamp();
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L2979) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L2979-L2987)

## [Related](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#related)

| Uses | Description |
| --- | --- |
| [get\_post\_datetime()](https://developer.wordpress.org/reference/functions/get_post_datetime/) `wp-includes/general-template.php` | Retrieves post published or modified time as a `DateTimeImmutable` object instance. |

| Used by | Description |
| --- | --- |
| [WP\_Posts\_List\_Table::column\_date()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_date/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the post date column output. |
| [WP\_Media\_List\_Table::column\_date()](https://developer.wordpress.org/reference/classes/wp_media_list_table/column_date/) `wp-admin/includes/class-wp-media-list-table.php` | Handles the date column output. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#changelog)

| Version | Description |
| --- | --- |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_timestamp/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/get_post_timestamp/#comment-content-5252)



How to get the published and modified date with `get_post_timestamp()` and then convert it into a readable format.





`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_post_timestamp/#)

[Copy](https://developer.wordpress.org/reference/functions/get_post_timestamp/#)




```php
<?php
function published_modified_date() {

   	// UNIX published date
   	$unix_published_date = get_post_timestamp( '', 'date' );

   	// UNIX modified date
   	$unix_modified_date = get_post_timestamp( '', 'modified' );

       // Convert from UNIX timestamp into readable date
       // Reference: https://developer.wordpress.org/reference/functions/date_i18n
   	$published_date = date_i18n( get_option( 'date_format' ), $unix_published_date );
   	$modified_date = date_i18n( get_option( 'date_format' ), $unix_modified_date );

       // Convert from UNIX timestamp into full date/time (ISO)
       // Reference: https://wordpress.org/support/article/formatting-date-and-time
   	$full_published_date = date_i18n( 'c', $unix_published_date );
   	$full_modified_date = date_i18n( 'c', $unix_modified_date );

       ?>

   	<span class="published"><time datetime="<?php echo $full_published_date; ?>"><?php echo $published_date; ?></time></span>

       <?php
       // If modified date is greater than published date by 1 day
       if ( $unix_modified_date > $unix_published_date + 86400 ) { ?>
   		<span class="modified">Modified on: <time datetime="<?php echo $full_modified_date; ?>"><?php echo $modified_date; ?></time></span>
   	    <?php
       }

}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_timestamp%2F%3Freplytocom%3D5252%23feedback-editor-5252)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_timestamp%2F) before being able to contribute a note or feedback.

Notifications