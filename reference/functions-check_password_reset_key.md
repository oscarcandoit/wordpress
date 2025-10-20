---
url: https://developer.wordpress.org/reference/functions/check_password_reset_key
scraped_at: 2025-10-20T03:27:30.983Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/check_password_reset_key/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

check\_password\_reset\_key()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)check\_password\_reset\_key()

Search

# check\_password\_reset\_key( string$key, string$login ): [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) \| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/check_password_reset_key/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/check_password_reset_key/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/check_password_reset_key/#return)
- [Source](https://developer.wordpress.org/reference/functions/check_password_reset_key/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/check_password_reset_key/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/check_password_reset_key/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/check_password_reset_key/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/check_password_reset_key/#wp--skip-link--target)

Retrieves a user row based on password reset key and login.

## [Description](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#description)

A key is considered ‘expired’ if it exactly matches the value of the user\_activation\_key field, rather than being matched after going through the hashing process. This field is now hashed; old values are no longer accepted but have a different [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) code so good user feedback can be provided.

## [Parameters](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#parameters)

`$key` stringrequired

The password reset key.

`$login` stringrequired

The user login.

## [Return](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#return)

[WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) \| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object on success, [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) object for invalid or expired keys.

## [Source](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#source)

`wp-includes/user.php`
[Expand code](https://developer.wordpress.org/reference/functions/check_password_reset_key/#)

[Copy](https://developer.wordpress.org/reference/functions/check_password_reset_key/#)

```php
function check_password_reset_key(
	#[\SensitiveParameter]
	$key,
	$login
) {
	$key = preg_replace( '/[^a-z0-9]/i', '', $key );

	if ( empty( $key ) || ! is_string( $key ) ) {
		return new WP_Error( 'invalid_key', __( 'Invalid key.' ) );
	}

	if ( empty( $login ) || ! is_string( $login ) ) {
		return new WP_Error( 'invalid_key', __( 'Invalid key.' ) );
	}

	$user = get_user_by( 'login', $login );

	if ( ! $user ) {
		return new WP_Error( 'invalid_key', __( 'Invalid key.' ) );
	}

	/**
	 * Filters the expiration time of password reset keys.
	 *
	 * @since 4.3.0
	 *
	 * @param int $expiration The expiration time in seconds.
	 */
	$expiration_duration = apply_filters( 'password_reset_expiration', DAY_IN_SECONDS );

	if ( str_contains( $user->user_activation_key, ':' ) ) {
		list( $pass_request_time, $pass_key ) = explode( ':', $user->user_activation_key, 2 );
		$expiration_time                      = $pass_request_time + $expiration_duration;
	} else {
		$pass_key        = $user->user_activation_key;
		$expiration_time = false;
	}

	if ( ! $pass_key ) {
		return new WP_Error( 'invalid_key', __( 'Invalid key.' ) );
	}

	$hash_is_correct = wp_verify_fast_hash( $key, $pass_key );

	if ( $hash_is_correct && $expiration_time && time() < $expiration_time ) {
		return $user;
	} elseif ( $hash_is_correct && $expiration_time ) {
		// Key has an expiration time that's passed.
		return new WP_Error( 'expired_key', __( 'Invalid key.' ) );
	}

	if ( hash_equals( $user->user_activation_key, $key ) || ( $hash_is_correct && ! $expiration_time ) ) {
		$return  = new WP_Error( 'expired_key', __( 'Invalid key.' ) );
		$user_id = $user->ID;

		/**
		 * Filters the return value of check_password_reset_key() when an
		 * old-style key or an expired key is used.
		 *
		 * @since 3.7.0 Previously plain-text keys were stored in the database.
		 * @since 4.3.0 Previously key hashes were stored without an expiration time.
		 *
		 * @param WP_Error $return  A WP_Error object denoting an expired key.
		 *                          Return a WP_User object to validate the key.
		 * @param int      $user_id The matched user ID.
		 */
		return apply_filters( 'password_reset_key_expired', $return, $user_id );
	}

	return new WP_Error( 'invalid_key', __( 'Invalid key.' ) );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/user.php#L3086) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/user.php#L3086-L3156)

## [Hooks](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#hooks)

[apply\_filters( ‘password\_reset\_expiration’, int$expiration )](https://developer.wordpress.org/reference/hooks/password_reset_expiration/)

Filters the expiration time of password reset keys.

[apply\_filters( ‘password\_reset\_key\_expired’, WP\_Error$return, int$user\_id )](https://developer.wordpress.org/reference/hooks/password_reset_key_expired/)

Filters the return value of [check\_password\_reset\_key()](https://developer.wordpress.org/reference/functions/check_password_reset_key/) when an old-style key or an expired key is used.

## [Related](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#related)

| Uses | Description |
| --- | --- |
| [wp\_verify\_fast\_hash()](https://developer.wordpress.org/reference/functions/wp_verify_fast_hash/) `wp-includes/functions.php` | Checks whether a plaintext message matches the hashed value. Used to verify values hashed via [wp\_fast\_hash()](https://developer.wordpress.org/reference/functions/wp_fast_hash/) . |
| [get\_user\_by()](https://developer.wordpress.org/reference/functions/get_user_by/) `wp-includes/pluggable.php` | Retrieves user info by a given field. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 2 more](https://developer.wordpress.org/reference/functions/check_password_reset_key/#) [Show less](https://developer.wordpress.org/reference/functions/check_password_reset_key/#)

## [Changelog](https://developer.wordpress.org/reference/functions/check_password_reset_key/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcheck_password_reset_key%2F) before being able to contribute a note or feedback.

Notifications