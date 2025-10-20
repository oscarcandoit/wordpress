---
url: https://developer.wordpress.org/reference/functions/_deprecated_hook
scraped_at: 2025-10-20T03:24:12.828Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_deprecated_hook/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_deprecated\_hook()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_deprecated\_hook()

Search

# \_deprecated\_hook( string$hook, string$version, string$replacement = '', string$message = '' )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/_deprecated_hook/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/_deprecated_hook/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/_deprecated_hook/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/_deprecated_hook/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/_deprecated_hook/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/_deprecated_hook/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_deprecated_hook/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Marks a deprecated action or filter hook as deprecated and throws a notice.

## [Description](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#description)

Use the [‘deprecated\_hook\_run’](https://developer.wordpress.org/reference/hooks/deprecated_hook_run/) action to get the backtrace describing where the deprecated hook was called.

Default behavior is to trigger a user error if `WP_DEBUG` is true.

This function is called by the [do\_action\_deprecated()](https://developer.wordpress.org/reference/functions/do_action_deprecated/) and [apply\_filters\_deprecated()](https://developer.wordpress.org/reference/functions/apply_filters_deprecated/) functions, and so generally does not need to be called directly.

## [Parameters](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#parameters)

`$hook` stringrequired

The hook that was used.

`$version` stringrequired

The version of WordPress that deprecated the hook.

`$replacement` stringoptional

The hook that should have been used.

Default: `''`

`$message` stringoptional

A message regarding the change.

Default: `''`

## [Source](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/_deprecated_hook/#)

[Copy](https://developer.wordpress.org/reference/functions/_deprecated_hook/#)

```php
function _deprecated_hook( $hook, $version, $replacement = '', $message = '' ) {
	/**
	 * Fires when a deprecated hook is called.
	 *
	 * @since 4.6.0
	 *
	 * @param string $hook        The hook that was called.
	 * @param string $replacement The hook that should be used as a replacement.
	 * @param string $version     The version of WordPress that deprecated the argument used.
	 * @param string $message     A message regarding the change.
	 */
	do_action( 'deprecated_hook_run', $hook, $replacement, $version, $message );

	/**
	 * Filters whether to trigger deprecated hook errors.
	 *
	 * @since 4.6.0
	 *
	 * @param bool $trigger Whether to trigger deprecated hook errors. Requires
	 *                      `WP_DEBUG` to be defined true.
	 */
	if ( WP_DEBUG && apply_filters( 'deprecated_hook_trigger_error', true ) ) {
		$message = empty( $message ) ? '' : ' ' . $message;

		if ( $replacement ) {
			$message = sprintf(
				/* translators: 1: WordPress hook name, 2: Version number, 3: Alternative hook name. */
				__( 'Hook %1$s is <strong>deprecated</strong> since version %2$s! Use %3$s instead.' ),
				$hook,
				$version,
				$replacement
			) . $message;
		} else {
			$message = sprintf(
				/* translators: 1: WordPress hook name, 2: Version number. */
				__( 'Hook %1$s is <strong>deprecated</strong> since version %2$s with no alternative available.' ),
				$hook,
				$version
			) . $message;
		}

		wp_trigger_error( '', $message, E_USER_DEPRECATED );
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L5939) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L5939-L5982)

## [Hooks](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#hooks)

[do\_action( ‘deprecated\_hook\_run’, string$hook, string$replacement, string$version, string$message )](https://developer.wordpress.org/reference/hooks/deprecated_hook_run/)

Fires when a deprecated hook is called.

[apply\_filters( ‘deprecated\_hook\_trigger\_error’, bool$trigger )](https://developer.wordpress.org/reference/hooks/deprecated_hook_trigger_error/)

Filters whether to trigger deprecated hook errors.

## [Related](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#related)

| Uses | Description |
| --- | --- |
| [wp\_trigger\_error()](https://developer.wordpress.org/reference/functions/wp_trigger_error/) `wp-includes/functions.php` | Generates a user-level error/warning/notice/deprecation message. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 1 more](https://developer.wordpress.org/reference/functions/_deprecated_hook/#) [Show less](https://developer.wordpress.org/reference/functions/_deprecated_hook/#)

| Used by | Description |
| --- | --- |
| [apply\_filters\_deprecated()](https://developer.wordpress.org/reference/functions/apply_filters_deprecated/) `wp-includes/plugin.php` | Fires functions attached to a deprecated filter hook. |
| [do\_action\_deprecated()](https://developer.wordpress.org/reference/functions/do_action_deprecated/) `wp-includes/plugin.php` | Fires functions attached to a deprecated action hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/_deprecated_hook/\#changelog)

| Version | Description |
| --- | --- |
| [5.4.0](https://developer.wordpress.org/reference/since/5.4.0/) | The error type is now classified as E\_USER\_DEPRECATED (used to default to E\_USER\_NOTICE). |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_deprecated_hook%2F) before being able to contribute a note or feedback.

Notifications