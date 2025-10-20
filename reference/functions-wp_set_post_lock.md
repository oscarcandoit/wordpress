---
url: https://developer.wordpress.org/reference/functions/wp_set_post_lock
scraped_at: 2025-10-20T03:20:36.716Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_set\_post\_lock()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_set\_post\_lock()

Search

# wp\_set\_post\_lock( int\|WP\_Post$post ): array\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#wp--skip-link--target)

Marks the post as currently being edited by the current user.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_set_post_lock/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)required

ID or object of the post being edited.

## [Return](https://developer.wordpress.org/reference/functions/wp_set_post_lock/\#return)

array\|false Array of the lock time and user ID. False if the post does not exist, or there is no current user.

- `0` int
The current time as a Unix timestamp.

- `1` int
The ID of the current user.


## [Source](https://developer.wordpress.org/reference/functions/wp_set_post_lock/\#source)

`wp-admin/includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#)

```php
function wp_set_post_lock( $post ) {
	$post = get_post( $post );

	if ( ! $post ) {
		return false;
	}

	$user_id = get_current_user_id();

	if ( 0 === $user_id ) {
		return false;
	}

	$now  = time();
	$lock = "$now:$user_id";

	update_post_meta( $post->ID, '_edit_lock', $lock );

	return array( $now, $user_id );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/post.php#L1757) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/post.php#L1757-L1776)

## [Related](https://developer.wordpress.org/reference/functions/wp_set_post_lock/\#related)

| Uses | Description |
| --- | --- |
| [update\_post\_meta()](https://developer.wordpress.org/reference/functions/update_post_meta/) `wp-includes/post.php` | Updates a post meta field based on the given post ID. |
| [get\_current\_user\_id()](https://developer.wordpress.org/reference/functions/get_current_user_id/) `wp-includes/user.php` | Gets the current user’s ID. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#) [Show less](https://developer.wordpress.org/reference/functions/wp_set_post_lock/#)

| Used by | Description |
| --- | --- |
| [wp\_refresh\_post\_lock()](https://developer.wordpress.org/reference/functions/wp_refresh_post_lock/) `wp-admin/includes/misc.php` | Checks lock status on the New/Edit Post screen and refresh the lock. |
| [wp\_write\_post()](https://developer.wordpress.org/reference/functions/wp_write_post/) `wp-admin/includes/post.php` | Creates a new post from the “Write Post” form using `$_POST` information. |
| [edit\_post()](https://developer.wordpress.org/reference/functions/edit_post/) `wp-admin/includes/post.php` | Updates an existing post with values provided in `$_POST`. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_set_post_lock/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_set_post_lock%2F) before being able to contribute a note or feedback.

Notifications