---
url: https://developer.wordpress.org/reference/functions/get_password_reset_key
scraped_at: 2025-10-20T03:18:06.854Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_password_reset_key/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_password\_reset\_key()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_password\_reset\_key()

Search

# get\_password\_reset\_key( WP\_User$user ): string\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_password_reset_key/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_password_reset_key/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_password_reset_key/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_password_reset_key/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_password_reset_key/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_password_reset_key/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_password_reset_key/#wp--skip-link--target)

Creates, stores, then returns a password reset key for user.

## [Parameters](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#parameters)

`$user` [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)required

User to retrieve password reset key for.

## [Return](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#return)

string\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) Password reset key on success. [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on error.

## [Source](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#source)

`wp-includes/user.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_password_reset_key/#)

[Copy](https://developer.wordpress.org/reference/functions/get_password_reset_key/#)

```php
function get_password_reset_key( $user ) {
	if ( ! ( $user instanceof WP_User ) ) {
		return new WP_Error( 'invalidcombo', __( '<strong>Error:</strong> There is no account with that username or email address.' ) );
	}

	/**
	 * Fires before a new password is retrieved.
	 *
	 * Use the 'retrieve_password' hook instead.
	 *
	 * @since 1.5.0
	 * @deprecated 1.5.1 Misspelled. Use 'retrieve_password' hook instead.
	 *
	 * @param string $user_login The user login name.
	 */
	do_action_deprecated( 'retreive_password', array( $user->user_login ), '1.5.1', 'retrieve_password' );

	/**
	 * Fires before a new password is retrieved.
	 *
	 * @since 1.5.1
	 *
	 * @param string $user_login The user login name.
	 */
	do_action( 'retrieve_password', $user->user_login );

	$password_reset_allowed = wp_is_password_reset_allowed_for_user( $user );
	if ( ! $password_reset_allowed ) {
		return new WP_Error( 'no_password_reset', __( 'Password reset is not allowed for this user' ) );
	} elseif ( is_wp_error( $password_reset_allowed ) ) {
		return $password_reset_allowed;
	}

	// Generate something random for a password reset key.
	$key = wp_generate_password( 20, false );

	/**
	 * Fires when a password reset key is generated.
	 *
	 * @since 2.5.0
	 *
	 * @param string $user_login The username for the user.
	 * @param string $key        The generated password reset key.
	 */
	do_action( 'retrieve_password_key', $user->user_login, $key );

	$hashed = time() . ':' . wp_fast_hash( $key );

	$key_saved = wp_update_user(
		array(
			'ID'                  => $user->ID,
			'user_activation_key' => $hashed,
		)
	);

	if ( is_wp_error( $key_saved ) ) {
		return $key_saved;
	}

	return $key;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/user.php#L3010) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/user.php#L3010-L3070)

## [Hooks](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#hooks)

[do\_action\_deprecated( ‘retreive\_password’, string$user\_login )](https://developer.wordpress.org/reference/hooks/retreive_password/)

Fires before a new password is retrieved.

[do\_action( ‘retrieve\_password’, string$user\_login )](https://developer.wordpress.org/reference/hooks/retrieve_password/)

Fires before a new password is retrieved.

[do\_action( ‘retrieve\_password\_key’, string$user\_login, string$key )](https://developer.wordpress.org/reference/hooks/retrieve_password_key/)

Fires when a password reset key is generated.

## [Related](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#related)

| Uses | Description |
| --- | --- |
| [wp\_fast\_hash()](https://developer.wordpress.org/reference/functions/wp_fast_hash/) `wp-includes/functions.php` | Returns a cryptographically secure hash of a message using a fast generic hash function. |
| [wp\_is\_password\_reset\_allowed\_for\_user()](https://developer.wordpress.org/reference/functions/wp_is_password_reset_allowed_for_user/) `wp-includes/user.php` | Checks if password reset is allowed for a specific user. |
| [do\_action\_deprecated()](https://developer.wordpress.org/reference/functions/do_action_deprecated/) `wp-includes/plugin.php` | Fires functions attached to a deprecated action hook. |
| [wp\_generate\_password()](https://developer.wordpress.org/reference/functions/wp_generate_password/) `wp-includes/pluggable.php` | Generates a random password drawn from the defined set of characters. |
| [wp\_update\_user()](https://developer.wordpress.org/reference/functions/wp_update_user/) `wp-includes/user.php` | Updates a user in the database. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_password_reset_key/#) [Show less](https://developer.wordpress.org/reference/functions/get_password_reset_key/#)

| Used by | Description |
| --- | --- |
| [retrieve\_password()](https://developer.wordpress.org/reference/functions/retrieve_password/) `wp-includes/user.php` | Handles sending a password retrieval email to a user. |
| [wp\_new\_user\_notification()](https://developer.wordpress.org/reference/functions/wp_new_user_notification/) `wp-includes/pluggable.php` | Emails login credentials to a newly-registered user. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_password_reset_key/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_password_reset_key%2F) before being able to contribute a note or feedback.

Notifications