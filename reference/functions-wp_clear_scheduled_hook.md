---
url: https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook
scraped_at: 2025-10-20T03:23:12.171Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_clear\_scheduled\_hook()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_clear\_scheduled\_hook()

Search

# wp\_clear\_scheduled\_hook( string$hook, array$args = array(), bool$wp\_error = false ): int\|false\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#wp--skip-link--target)

Unschedules all events attached to the hook with the specified arguments.

## [Description](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#description)

Warning: This function may return boolean false, but may also return a non-boolean value which evaluates to false. For information about casting to booleans see the [PHP documentation](https://www.php.net/manual/en/language.types.boolean.php). Use the `===` operator for testing the return value of this function.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#parameters)

`$hook` stringrequired

Action hook, the execution of which will be unscheduled.

`$args` arrayoptional

Array containing each separate argument to pass to the hook’s callback function.

Although not passed to a callback, these arguments are used to uniquely identify the event, so they should be the same as those used when originally scheduling the event.

Default: `array()`

`$wp_error` booloptional

Whether to return a [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on failure.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#return)

int\|false\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) On success an integer indicating number of events unscheduled (0 indicates no events were registered with the hook and arguments combination), false or [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) if unscheduling one or more events fail.

## [More Information](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#more-information)

If you created a scheduled job using a hook and arguments, you cannot delete it by supplying only the hook. Similarly, if you created a set of scheduled jobs that share a hook but have different arguments, you cannot delete them using only the hook name, you have to delete them all individually using the hook name and arguments.

## [Source](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#source)

`wp-includes/cron.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#)

```php
function wp_clear_scheduled_hook( $hook, $args = array(), $wp_error = false ) {
	/*
	 * Backward compatibility.
	 * Previously, this function took the arguments as discrete vars rather than an array like the rest of the API.
	 */
	if ( ! is_array( $args ) ) {
		_deprecated_argument(
			__FUNCTION__,
			'3.0.0',
			__( 'This argument has changed to an array to match the behavior of the other cron functions.' )
		);

		$args     = array_slice( func_get_args(), 1 ); // phpcs:ignore PHPCompatibility.FunctionUse.ArgumentFunctionsReportCurrentValue.NeedsInspection
		$wp_error = false;
	}

	/**
	 * Filter to override clearing a scheduled hook.
	 *
	 * Returning a non-null value will short-circuit the normal unscheduling
	 * process, causing the function to return the filtered value instead.
	 *
	 * For plugins replacing wp-cron, return the number of events successfully
	 * unscheduled (zero if no events were registered with the hook) or false
	 * or a WP_Error if unscheduling one or more events fails.
	 *
	 * @since 5.1.0
	 * @since 5.7.0 The `$wp_error` parameter was added, and a `WP_Error` object can now be returned.
	 *
	 * @param null|int|false|WP_Error $pre      Value to return instead. Default null to continue unscheduling the event.
	 * @param string                  $hook     Action hook, the execution of which will be unscheduled.
	 * @param array                   $args     Arguments to pass to the hook's callback function.
	 * @param bool                    $wp_error Whether to return a WP_Error on failure.
	 */
	$pre = apply_filters( 'pre_clear_scheduled_hook', null, $hook, $args, $wp_error );

	if ( null !== $pre ) {
		if ( $wp_error && false === $pre ) {
			return new WP_Error(
				'pre_clear_scheduled_hook_false',
				__( 'A plugin prevented the hook from being cleared.' )
			);
		}

		if ( ! $wp_error && is_wp_error( $pre ) ) {
			return false;
		}

		return $pre;
	}

	/*
	 * This logic duplicates wp_next_scheduled().
	 * It's required due to a scenario where wp_unschedule_event() fails due to update_option() failing,
	 * and, wp_next_scheduled() returns the same schedule in an infinite loop.
	 */
	$crons = _get_cron_array();
	if ( empty( $crons ) ) {
		return 0;
	}

	$results = array();
	$key     = md5( serialize( $args ) );

	foreach ( $crons as $timestamp => $cron ) {
		if ( isset( $cron[ $hook ][ $key ] ) ) {
			$results[] = wp_unschedule_event( $timestamp, $hook, $args, true );
		}
	}

	$errors = array_filter( $results, 'is_wp_error' );
	$error  = new WP_Error();

	if ( $errors ) {
		if ( $wp_error ) {
			array_walk( $errors, array( $error, 'merge_from' ) );

			return $error;
		}

		return false;
	}

	return count( $results );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/cron.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/cron.php#L549) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/cron.php#L549-L633)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#hooks)

[apply\_filters( ‘pre\_clear\_scheduled\_hook’, null\|int\|false\|WP\_Error$pre, string$hook, array$args, bool$wp\_error )](https://developer.wordpress.org/reference/hooks/pre_clear_scheduled_hook/)

Filter to override clearing a scheduled hook.

## [Related](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#related)

| Uses | Description |
| --- | --- |
| [\_get\_cron\_array()](https://developer.wordpress.org/reference/functions/_get_cron_array/) `wp-includes/cron.php` | Retrieves cron info array option. |
| [wp\_unschedule\_event()](https://developer.wordpress.org/reference/functions/wp_unschedule_event/) `wp-includes/cron.php` | Unschedules a previously scheduled event. |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 4 more](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#) [Show less](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#)

| Used by | Description |
| --- | --- |
| [populate\_network()](https://developer.wordpress.org/reference/functions/populate_network/) `wp-admin/includes/schema.php` | Populate network settings. |
| [\_transition\_post\_status()](https://developer.wordpress.org/reference/functions/_transition_post_status/) `wp-includes/post.php` | Hook for managing future post transitions to published. |
| [\_future\_post\_hook()](https://developer.wordpress.org/reference/functions/_future_post_hook/) `wp-includes/post.php` | Hook used to schedule publication for a post marked for the future. |
| [check\_and\_publish\_future\_post()](https://developer.wordpress.org/reference/functions/check_and_publish_future_post/) `wp-includes/post.php` | Publishes future post and make sure post ID has future post status. |
| [wp\_delete\_post()](https://developer.wordpress.org/reference/functions/wp_delete_post/) `wp-includes/post.php` | Trashes or deletes a post or page. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#changelog)

| Version | Description |
| --- | --- |
| [5.7.0](https://developer.wordpress.org/reference/since/5.7.0/) | The `$wp_error` parameter was added. |
| [5.1.0](https://developer.wordpress.org/reference/since/5.1.0/) | Return value modified to indicate success or failure, ['pre\_clear\_scheduled\_hook'](https://developer.wordpress.org/reference/hooks/pre_clear_scheduled_hook/) filter added to short-circuit the function. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#comment-content-1141)



**Basic Example**



Clear a scheduled event





`wp-includes/cron.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/#)




```php
// If you previously added for example
// wp_schedule_single_event( time() + 3600, 'my_new_event' );

wp_clear_scheduled_hook( 'my_new_event' );

// or this if you created something like
// wp_schedule_single_event( time() + 3600, 'my_new_event', array( 'some_arg' ) );

wp_clear_scheduled_hook( 'my_new_event', array( 'some_arg' ) );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_clear_scheduled_hook%2F%3Freplytocom%3D1141%23feedback-editor-1141)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_clear_scheduled_hook%2F) before being able to contribute a note or feedback.

Notifications