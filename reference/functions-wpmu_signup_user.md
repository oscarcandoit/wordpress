---
url: https://developer.wordpress.org/reference/functions/wpmu_signup_user
scraped_at: 2025-10-20T03:22:34.996Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wpmu\_signup\_user()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wpmu\_signup\_user()

Search

# wpmu\_signup\_user( string$user, string$user\_email, array$meta = array() )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#wp--skip-link--target)

Records user signup information for future activation.

## [Description](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#description)

This function is used when user registration is open but new site registration is not.

## [Parameters](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#parameters)

`$user` stringrequired

The user’s requested login name.

`$user_email` stringrequired

The user’s email address.

`$meta` arrayoptional

Signup meta data.

Default: `array()`

## [Source](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#source)

`wp-includes/ms-functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#)

[Copy](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#)

```php
function wpmu_signup_user( $user, $user_email, $meta = array() ) {
	global $wpdb;

	// Format data.
	$user       = preg_replace( '/\s+/', '', sanitize_user( $user, true ) );
	$user_email = sanitize_email( $user_email );
	$key        = substr( md5( time() . wp_rand() . $user_email ), 0, 16 );

	/**
	 * Filters the metadata for a user signup.
	 *
	 * The metadata will be serialized prior to storing it in the database.
	 *
	 * @since 4.8.0
	 *
	 * @param array  $meta       Signup meta data. Default empty array.
	 * @param string $user       The user's requested login name.
	 * @param string $user_email The user's email address.
	 * @param string $key        The user's activation key.
	 */
	$meta = apply_filters( 'signup_user_meta', $meta, $user, $user_email, $key );

	$wpdb->insert(
		$wpdb->signups,
		array(
			'domain'         => '',
			'path'           => '',
			'title'          => '',
			'user_login'     => $user,
			'user_email'     => $user_email,
			'registered'     => current_time( 'mysql', true ),
			'activation_key' => $key,
			'meta'           => serialize( $meta ),
		)
	);

	/**
	 * Fires after a user's signup information has been written to the database.
	 *
	 * @since 4.4.0
	 *
	 * @param string $user       The user's requested login name.
	 * @param string $user_email The user's email address.
	 * @param string $key        The user's activation key.
	 * @param array  $meta       Signup meta data. Default empty array.
	 */
	do_action( 'after_signup_user', $user, $user_email, $key, $meta );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/ms-functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/ms-functions.php#L867) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/ms-functions.php#L867-L914)

## [Hooks](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#hooks)

[do\_action( ‘after\_signup\_user’, string$user, string$user\_email, string$key, array$meta )](https://developer.wordpress.org/reference/hooks/after_signup_user/)

Fires after a user’s signup information has been written to the database.

[apply\_filters( ‘signup\_user\_meta’, array$meta, string$user, string$user\_email, string$key )](https://developer.wordpress.org/reference/hooks/signup_user_meta/)

Filters the metadata for a user signup.

## [Related](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#related)

| Uses | Description |
| --- | --- |
| [sanitize\_email()](https://developer.wordpress.org/reference/functions/sanitize_email/) `wp-includes/formatting.php` | Strips out all characters that are not allowable in an email. |
| [sanitize\_user()](https://developer.wordpress.org/reference/functions/sanitize_user/) `wp-includes/formatting.php` | Sanitizes a username, stripping out unsafe characters. |
| [wp\_rand()](https://developer.wordpress.org/reference/functions/wp_rand/) `wp-includes/pluggable.php` | Generates a random non-negative number. |
| [current\_time()](https://developer.wordpress.org/reference/functions/current_time/) `wp-includes/functions.php` | Retrieves the current time based on specified type. |
| [wpdb::insert()](https://developer.wordpress.org/reference/classes/wpdb/insert/) `wp-includes/class-wpdb.php` | Inserts a row into the table. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#) [Show less](https://developer.wordpress.org/reference/functions/wpmu_signup_user/#)

| Used by | Description |
| --- | --- |
| [validate\_user\_signup()](https://developer.wordpress.org/reference/functions/validate_user_signup/) `wp-signup.php` | Validates the new user sign-up. |

## [Changelog](https://developer.wordpress.org/reference/functions/wpmu_signup_user/\#changelog)

| Version | Description |
| --- | --- |
| [MU (3.0.0)](https://developer.wordpress.org/reference/since/mu.3.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwpmu_signup_user%2F) before being able to contribute a note or feedback.

Notifications