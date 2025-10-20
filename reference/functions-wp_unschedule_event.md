---
url: https://developer.wordpress.org/reference/functions/wp_unschedule_event
scraped_at: 2025-10-20T03:23:02.367Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_unschedule\_event()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_unschedule\_event()

Search

# wp\_unschedule\_event( int$timestamp, string$hook, array$args = array(), bool$wp\_error = false ): bool\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#wp--skip-link--target)

Unschedules a previously scheduled event.

## [Description](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#description)

The `$timestamp` and `$hook` parameters are required so that the event can be identified.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#parameters)

`$timestamp` intrequired

Unix timestamp (UTC) of the event.

`$hook` stringrequired

Action hook of the event.

`$args` arrayoptional

Array containing each separate argument to pass to the hook’s callback function.

Although not passed to a callback, these arguments are used to uniquely identify the event, so they should be the same as those used when originally scheduling the event.

Default: `array()`

`$wp_error` booloptional

Whether to return a [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on failure.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#return)

bool\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) True if event successfully unscheduled. False or [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on failure.

## [More Information](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#more-information)

Note that you need to know the exact time of the next occurrence when scheduled hook was set to run, and the function arguments it was supposed to have, in order to unschedule it. All future occurrences are unscheduled by calling this function.

## [Source](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#source)

`wp-includes/cron.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#)

```php
function wp_unschedule_event( $timestamp, $hook, $args = array(), $wp_error = false ) {
	// Make sure timestamp is a positive integer.
	if ( ! is_numeric( $timestamp ) || $timestamp <= 0 ) {
		if ( $wp_error ) {
			return new WP_Error(
				'invalid_timestamp',
				__( 'Event timestamp must be a valid Unix timestamp.' )
			);
		}

		return false;
	}

	/**
	 * Filter to override unscheduling of events.
	 *
	 * Returning a non-null value will short-circuit the normal unscheduling
	 * process, causing the function to return the filtered value instead.
	 *
	 * For plugins replacing wp-cron, return true if the event was successfully
	 * unscheduled, false or a WP_Error if not.
	 *
	 * @since 5.1.0
	 * @since 5.7.0 The `$wp_error` parameter was added, and a `WP_Error` object can now be returned.
	 *
	 * @param null|bool|WP_Error $pre       Value to return instead. Default null to continue unscheduling the event.
	 * @param int                $timestamp Unix timestamp (UTC) for when to run the event.
	 * @param string             $hook      Action hook, the execution of which will be unscheduled.
	 * @param array              $args      Arguments to pass to the hook's callback function.
	 * @param bool               $wp_error  Whether to return a WP_Error on failure.
	 */
	$pre = apply_filters( 'pre_unschedule_event', null, $timestamp, $hook, $args, $wp_error );

	if ( null !== $pre ) {
		if ( $wp_error && false === $pre ) {
			return new WP_Error(
				'pre_unschedule_event_false',
				__( 'A plugin prevented the event from being unscheduled.' )
			);
		}

		if ( ! $wp_error && is_wp_error( $pre ) ) {
			return false;
		}

		return $pre;
	}

	$crons = _get_cron_array();
	$key   = md5( serialize( $args ) );

	unset( $crons[ $timestamp ][ $hook ][ $key ] );

	if ( empty( $crons[ $timestamp ][ $hook ] ) ) {
		unset( $crons[ $timestamp ][ $hook ] );
	}

	if ( empty( $crons[ $timestamp ] ) ) {
		unset( $crons[ $timestamp ] );
	}

	return _set_cron_array( $crons, $wp_error );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/cron.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/cron.php#L462) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/cron.php#L462-L524)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#hooks)

[apply\_filters( ‘pre\_unschedule\_event’, null\|bool\|WP\_Error$pre, int$timestamp, string$hook, array$args, bool$wp\_error )](https://developer.wordpress.org/reference/hooks/pre_unschedule_event/)

Filter to override unscheduling of events.

## [Related](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#related)

| Uses | Description |
| --- | --- |
| [\_get\_cron\_array()](https://developer.wordpress.org/reference/functions/_get_cron_array/) `wp-includes/cron.php` | Retrieves cron info array option. |
| [\_set\_cron\_array()](https://developer.wordpress.org/reference/functions/_set_cron_array/) `wp-includes/cron.php` | Updates the cron option with the new cron array. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 3 more](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#) [Show less](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#)

| Used by | Description |
| --- | --- |
| [wp\_clear\_scheduled\_hook()](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/) `wp-includes/cron.php` | Unschedules all events attached to the hook with the specified arguments. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#changelog)

| Version | Description |
| --- | --- |
| [5.7.0](https://developer.wordpress.org/reference/since/5.7.0/) | The `$wp_error` parameter was added. |
| [5.1.0](https://developer.wordpress.org/reference/since/5.1.0/) | Return value modified to boolean indicating success or failure, ['pre\_unschedule\_event'](https://developer.wordpress.org/reference/hooks/pre_unschedule_event/) filter added to short-circuit the function. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_unschedule_event/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#comment-content-5588)



You can also use `wp_clear_scheduled_hook()`, which calls `wp_unschedule_event()`. It will similarly clear all future events and save you from calling `wp_next_scheduled()` yourself.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unschedule_event%2F%3Freplytocom%3D5588%23feedback-editor-5588)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#comment-content-1356)



**Example**





`wp-includes/cron.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_unschedule_event/#)




```php
// Get the timestamp for the next event.
$timestamp = wp_next_scheduled( 'my_schedule_hook' );

// If this event was created with any special arguments, you need to get those too.
$original_args = array();

wp_unschedule_event( $timestamp, 'my_schedule_hook', $original_args );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unschedule_event%2F%3Freplytocom%3D1356%23feedback-editor-1356)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unschedule_event%2F) before being able to contribute a note or feedback.

Notifications