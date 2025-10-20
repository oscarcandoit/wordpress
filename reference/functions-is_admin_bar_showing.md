---
url: https://developer.wordpress.org/reference/functions/is_admin_bar_showing
scraped_at: 2025-10-20T03:15:49.728Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_admin\_bar\_showing()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_admin\_bar\_showing()

Search

# is\_admin\_bar\_showing(): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#description)
- [Return](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#return)
- [Source](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#wp--skip-link--target)

Determines whether the admin bar should be showing.

## [Description](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#description)

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Return](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#return)

bool Whether the admin bar should be showing.

## [Source](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#source)

`wp-includes/admin-bar.php`
[Expand code](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#)

[Copy](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#)

```php
function is_admin_bar_showing() {
	global $show_admin_bar, $pagenow;

	// For all these types of requests, we never want an admin bar.
	if ( defined( 'XMLRPC_REQUEST' ) || defined( 'DOING_AJAX' ) || defined( 'IFRAME_REQUEST' ) || wp_is_json_request() ) {
		return false;
	}

	if ( is_embed() ) {
		return false;
	}

	// Integrated into the admin.
	if ( is_admin() ) {
		return true;
	}

	if ( ! isset( $show_admin_bar ) ) {
		if ( ! is_user_logged_in() || 'wp-login.php' === $pagenow ) {
			$show_admin_bar = false;
		} else {
			$show_admin_bar = _get_admin_bar_pref();
		}
	}

	/**
	 * Filters whether to show the admin bar.
	 *
	 * Returning false to this hook is the recommended way to hide the admin bar.
	 * The user's display preference is used for logged in users.
	 *
	 * @since 3.1.0
	 *
	 * @param bool $show_admin_bar Whether the admin bar should be shown. Default false.
	 */
	$show_admin_bar = apply_filters( 'show_admin_bar', $show_admin_bar );

	return $show_admin_bar;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/admin-bar.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/admin-bar.php#L1338) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/admin-bar.php#L1338-L1376)

## [Hooks](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#hooks)

[apply\_filters( ‘show\_admin\_bar’, bool$show\_admin\_bar )](https://developer.wordpress.org/reference/hooks/show_admin_bar/)

Filters whether to show the admin bar.

## [Related](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#related)

| Uses | Description |
| --- | --- |
| [wp\_is\_json\_request()](https://developer.wordpress.org/reference/functions/wp_is_json_request/) `wp-includes/load.php` | Checks whether current request is a JSON request, or is expecting a JSON response. |
| [is\_embed()](https://developer.wordpress.org/reference/functions/is_embed/) `wp-includes/query.php` | Is the query for an embedded post? |
| [is\_user\_logged\_in()](https://developer.wordpress.org/reference/functions/is_user_logged_in/) `wp-includes/pluggable.php` | Determines whether the current visitor is a logged in user. |
| [\_get\_admin\_bar\_pref()](https://developer.wordpress.org/reference/functions/_get_admin_bar_pref/) `wp-includes/admin-bar.php` | Retrieves the admin bar display preference of a user. |
| [is\_admin()](https://developer.wordpress.org/reference/functions/is_admin/) `wp-includes/load.php` | Determines whether the current request is for an administrative interface page. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#) [Show less](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#)

| Used by | Description |
| --- | --- |
| [\_wp\_admin\_html\_begin()](https://developer.wordpress.org/reference/functions/_wp_admin_html_begin/) `wp-admin/includes/template.php` | Prints out the beginning of the admin HTML header. |
| [\_wp\_admin\_bar\_init()](https://developer.wordpress.org/reference/functions/_wp_admin_bar_init/) `wp-includes/admin-bar.php` | Instantiates the admin bar object and set it up as a global for access elsewhere. |
| [wp\_admin\_bar\_render()](https://developer.wordpress.org/reference/functions/wp_admin_bar_render/) `wp-includes/admin-bar.php` | Renders the admin bar to the page based on the $wp\_admin\_bar->menu member var. |
| [get\_body\_class()](https://developer.wordpress.org/reference/functions/get_body_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the body element. |

## [Changelog](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#comment-content-1200)



**Basic Example**





`wp-includes/admin-bar.php`
[Copy](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/#)




```php
if ( is_admin_bar_showing() ) {
       // do something
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_admin_bar_showing%2F%3Freplytocom%3D1200%23feedback-editor-1200)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_admin_bar_showing%2F) before being able to contribute a note or feedback.

Notifications