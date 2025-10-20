---
url: https://developer.wordpress.org/reference/functions/current_user_can_for_site
scraped_at: 2025-10-20T03:18:25.401Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

current\_user\_can\_for\_site()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)current\_user\_can\_for\_site()

Search

# current\_user\_can\_for\_site( int$site\_id, string$capability, mixed$args ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#return)
- [Source](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#source)
- [Related](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#wp--skip-link--target)

Returns whether the current user has the specified capability for a given site.

## [Description](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#description)

This function also accepts an ID of an object to check against if the capability is a meta capability. Meta capabilities such as `edit_post` and `edit_user` are capabilities used by the `map_meta_cap()` function to map to primitive capabilities that a user or role has, such as `edit_posts` and `edit_others_posts`.

This function replaces the [current\_user\_can\_for\_blog()](https://developer.wordpress.org/reference/functions/current_user_can_for_blog/) function.

Example usage:

`wp-includes/capabilities.php`
[Copy](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#)

```php
current_user_can_for_site( $site_id, 'edit_posts' );
current_user_can_for_site( $site_id, 'edit_post', $post->ID );
current_user_can_for_site( $site_id, 'edit_post_meta', $post->ID, $meta_key );
```

## [Parameters](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#parameters)

`$site_id` intrequired

Site ID.

`$capability` stringrequired

Capability name.

`$args` mixedoptional

Optional further parameters, typically starting with an object ID.

## [Return](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#return)

bool Whether the user has the given capability.

## [Source](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#source)

`wp-includes/capabilities.php`
[Copy](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#)

```php
function current_user_can_for_site( $site_id, $capability, ...$args ) {
	$switched = is_multisite() ? switch_to_blog( $site_id ) : false;

	$can = current_user_can( $capability, ...$args );

	if ( $switched ) {
		restore_current_blog();
	}

	return $can;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/capabilities.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/capabilities.php#L936) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/capabilities.php#L936-L946)

## [Related](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#related)

| Uses | Description |
| --- | --- |
| [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) `wp-includes/ms-blogs.php` | Switches the current blog. |
| [restore\_current\_blog()](https://developer.wordpress.org/reference/functions/restore_current_blog/) `wp-includes/ms-blogs.php` | Restores the current blog, after calling [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) . |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [is\_multisite()](https://developer.wordpress.org/reference/functions/is_multisite/) `wp-includes/load.php` | Determines whether Multisite is enabled. |

[Show 2 more](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#) [Show less](https://developer.wordpress.org/reference/functions/current_user_can_for_site/#)

| Used by | Description |
| --- | --- |
| [current\_user\_can\_for\_blog()](https://developer.wordpress.org/reference/functions/current_user_can_for_blog/) `wp-includes/deprecated.php` | Returns whether the current user has the specified capability for a given site. |

## [Changelog](https://developer.wordpress.org/reference/functions/current_user_can_for_site/\#changelog)

| Version | Description |
| --- | --- |
| [6.7.0](https://developer.wordpress.org/reference/since/6.7.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcurrent_user_can_for_site%2F) before being able to contribute a note or feedback.

Notifications