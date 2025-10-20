---
url: https://developer.wordpress.org/reference/functions/do_action_deprecated
scraped_at: 2025-10-20T03:26:13.875Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/do_action_deprecated/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

do\_action\_deprecated()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)do\_action\_deprecated()

Search

# do\_action\_deprecated( string$hook\_name, array$args, string$version, string$replacement = '', string$message = '' )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/do_action_deprecated/#description)
  - [See also](https://developer.wordpress.org/reference/functions/do_action_deprecated/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/do_action_deprecated/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/do_action_deprecated/#source)
- [Related](https://developer.wordpress.org/reference/functions/do_action_deprecated/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/do_action_deprecated/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/do_action_deprecated/#wp--skip-link--target)

Fires functions attached to a deprecated action hook.

## [Description](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#description)

When an action hook is deprecated, the [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) call is replaced with [do\_action\_deprecated()](https://developer.wordpress.org/reference/functions/do_action_deprecated/) , which triggers a deprecation notice and then fires the original hook.

### [See also](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#see-also)

- [\_deprecated\_hook()](https://developer.wordpress.org/reference/functions/_deprecated_hook)

## [Parameters](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#parameters)

`$hook_name` stringrequired

The name of the action hook.

`$args` arrayrequired

Array of additional function arguments to be passed to [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) .

`$version` stringrequired

The version of WordPress that deprecated the hook.

`$replacement` stringoptional

The hook that should have been used.

Default: `''`

`$message` stringoptional

A message regarding the change.

Default: `''`

## [Source](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#source)

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/do_action_deprecated/#)

```php
function do_action_deprecated( $hook_name, $args, $version, $replacement = '', $message = '' ) {
	if ( ! has_action( $hook_name ) ) {
		return;
	}

	_deprecated_hook( $hook_name, $version, $replacement, $message );

	do_action_ref_array( $hook_name, $args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L739) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L739-L747)

## [Related](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#related)

| Uses | Description |
| --- | --- |
| [\_deprecated\_hook()](https://developer.wordpress.org/reference/functions/_deprecated_hook/) `wp-includes/functions.php` | Marks a deprecated action or filter hook as deprecated and throws a notice. |
| [has\_action()](https://developer.wordpress.org/reference/functions/has_action/) `wp-includes/plugin.php` | Checks if any action has been registered for a hook. |
| [do\_action\_ref\_array()](https://developer.wordpress.org/reference/functions/do_action_ref_array/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook, specifying arguments in an array. |

| Used by | Description |
| --- | --- |
| [wp\_check\_comment\_disallowed\_list()](https://developer.wordpress.org/reference/functions/wp_check_comment_disallowed_list/) `wp-includes/comment.php` | Checks if a comment contains disallowed characters or words. |
| [wp\_insert\_site()](https://developer.wordpress.org/reference/functions/wp_insert_site/) `wp-includes/ms-site.php` | Inserts a new site into the database. |
| [wp\_delete\_site()](https://developer.wordpress.org/reference/functions/wp_delete_site/) `wp-includes/ms-site.php` | Deletes a site from the database. |
| [register\_and\_do\_post\_meta\_boxes()](https://developer.wordpress.org/reference/functions/register_and_do_post_meta_boxes/) `wp-admin/includes/meta-boxes.php` | Registers the default post meta boxes, and runs the `do_meta_boxes` actions. |
| [get\_password\_reset\_key()](https://developer.wordpress.org/reference/functions/get_password_reset_key/) `wp-includes/user.php` | Creates, stores, then returns a password reset key for user. |
| [wpmu\_delete\_blog()](https://developer.wordpress.org/reference/functions/wpmu_delete_blog/) `wp-admin/includes/ms.php` | Deletes a site. |
| [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/) `wp-includes/option.php` | Sets/updates the value of a site transient. |
| [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/) `wp-includes/option.php` | Sets/updates the value of a transient. |
| [\_transition\_post\_status()](https://developer.wordpress.org/reference/functions/_transition_post_status/) `wp-includes/post.php` | Hook for managing future post transitions to published. |
| [clean\_blog\_cache()](https://developer.wordpress.org/reference/functions/clean_blog_cache/) `wp-includes/ms-site.php` | Clean the blog cache |

[Show 5 more](https://developer.wordpress.org/reference/functions/do_action_deprecated/#) [Show less](https://developer.wordpress.org/reference/functions/do_action_deprecated/#)

## [Changelog](https://developer.wordpress.org/reference/functions/do_action_deprecated/\#changelog)

| Version | Description |
| --- | --- |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_action_deprecated%2F) before being able to contribute a note or feedback.

Notifications