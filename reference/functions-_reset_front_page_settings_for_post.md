---
url: https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post
scraped_at: 2025-10-20T03:22:00.740Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_reset\_front\_page\_settings\_for\_post()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_reset\_front\_page\_settings\_for\_post()

Search

# \_reset\_front\_page\_settings\_for\_post( int$post\_id )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#source)
- [Related](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Resets the page\_on\_front, show\_on\_front, and page\_for\_post settings when a linked page is deleted or trashed.

## [Description](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/\#description)

Also ensures the post is no longer sticky.

## [Parameters](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/\#parameters)

`$post_id` intrequired

Post ID.

## [Source](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#)

[Copy](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#)

```php
function _reset_front_page_settings_for_post( $post_id ) {
	$post = get_post( $post_id );

	if ( 'page' === $post->post_type ) {
		/*
		 * If the page is defined in option page_on_front or post_for_posts,
		 * adjust the corresponding options.
		 */
		if ( (int) get_option( 'page_on_front' ) === $post->ID ) {
			update_option( 'show_on_front', 'posts' );
			update_option( 'page_on_front', 0 );
		}
		if ( (int) get_option( 'page_for_posts' ) === $post->ID ) {
			update_option( 'page_for_posts', 0 );
		}
	}

	unstick_post( $post->ID );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L3901) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L3901-L3919)

## [Related](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/\#related)

| Uses | Description |
| --- | --- |
| [unstick\_post()](https://developer.wordpress.org/reference/functions/unstick_post/) `wp-includes/post.php` | Un-sticks a post. |
| [update\_option()](https://developer.wordpress.org/reference/functions/update_option/) `wp-includes/option.php` | Updates the value of an option that was already added. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

[Show 2 more](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#) [Show less](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/#)

## [Changelog](https://developer.wordpress.org/reference/functions/_reset_front_page_settings_for_post/\#changelog)

| Version | Description |
| --- | --- |
| [3.7.0](https://developer.wordpress.org/reference/since/3.7.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_reset_front_page_settings_for_post%2F) before being able to contribute a note or feedback.

Notifications