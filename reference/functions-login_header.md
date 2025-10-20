---
url: https://developer.wordpress.org/reference/functions/login_header
scraped_at: 2025-10-20T03:15:34.814Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/login_header/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

login\_header()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)login\_header()

Search

# login\_header( string\|null$title = null, string$message = '', WP\_Error\|null$wp\_error = null )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/login_header/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/login_header/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/login_header/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/login_header/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/login_header/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/login_header/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/login_header/#wp--skip-link--target)

Outputs the login page header.

## [Parameters](https://developer.wordpress.org/reference/functions/login_header/\#parameters)

`$title` string\|nulloptional

WordPress login page title to display in the `<title>` element.

Defaults to ‘Log In’.

Default: `null`

`$message` stringoptional

Message to display in header.

Default: `''`

`$wp_error` [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)\|nulloptional

The error to pass. Defaults to a [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) instance.

Default: `null`

## [Source](https://developer.wordpress.org/reference/functions/login_header/\#source)

`wp-login.php`
[Expand code](https://developer.wordpress.org/reference/functions/login_header/#)

[Copy](https://developer.wordpress.org/reference/functions/login_header/#)

```php
function login_header( $title = null, $message = '', $wp_error = null ) {
	global $error, $interim_login, $action;

	if ( null === $title ) {
		$title = __( 'Log In' );
	}

	// Don't index any of these forms.
	add_filter( 'wp_robots', 'wp_robots_sensitive_page' );
	add_action( 'login_head', 'wp_strict_cross_origin_referrer' );

	add_action( 'login_head', 'wp_login_viewport_meta' );

	if ( ! is_wp_error( $wp_error ) ) {
		$wp_error = new WP_Error();
	}

	// Shake it!
	$shake_error_codes = array( 'empty_password', 'empty_email', 'invalid_email', 'invalidcombo', 'empty_username', 'invalid_username', 'incorrect_password', 'retrieve_password_email_failure' );
	/**
	 * Filters the error codes array for shaking the login form.
	 *
	 * @since 3.0.0
	 *
	 * @param string[] $shake_error_codes Error codes that shake the login form.
	 */
	$shake_error_codes = apply_filters( 'shake_error_codes', $shake_error_codes );

	if ( $shake_error_codes && $wp_error->has_errors() && in_array( $wp_error->get_error_code(), $shake_error_codes, true ) ) {
		add_action( 'login_footer', 'wp_shake_js', 12 );
	}

	$login_title = get_bloginfo( 'name', 'display' );

	/* translators: Login screen title. 1: Login screen name, 2: Network or site name. */
	$login_title = sprintf( __( '%1$s &lsaquo; %2$s &#8212; WordPress' ), $title, $login_title );

	if ( wp_is_recovery_mode() ) {
		/* translators: %s: Login screen title. */
		$login_title = sprintf( __( 'Recovery Mode &#8212; %s' ), $login_title );
	}

	/**
	 * Filters the title tag content for login page.
	 *
	 * @since 4.9.0
	 *
	 * @param string $login_title The page title, with extra context added.
	 * @param string $title       The original page title.
	 */
	$login_title = apply_filters( 'login_title', $login_title, $title );

	?><!DOCTYPE html>
	<html <?php language_attributes(); ?>>
	<head>
	<meta http-equiv="Content-Type" content="<?php bloginfo( 'html_type' ); ?>; charset=<?php bloginfo( 'charset' ); ?>" />
	<title><?php echo $login_title; ?></title>
	<?php

	wp_enqueue_style( 'login' );

	/*
	 * Remove all stored post data on logging out.
	 * This could be added by add_action('login_head'...) like wp_shake_js(),
	 * but maybe better if it's not removable by plugins.
	 */
	if ( 'loggedout' === $wp_error->get_error_code() ) {
		ob_start();
		?>
		<script>if("sessionStorage" in window){try{for(var key in sessionStorage){if(key.indexOf("wp-autosave-")!=-1){sessionStorage.removeItem(key)}}}catch(e){}};</script>
		<?php
		wp_print_inline_script_tag( wp_remove_surrounding_empty_script_tags( ob_get_clean() ) );
	}

	/**
	 * Enqueues scripts and styles for the login page.
	 *
	 * @since 3.1.0
	 */
	do_action( 'login_enqueue_scripts' );

	/**
	 * Fires in the login page header after scripts are enqueued.
	 *
	 * @since 2.1.0
	 */
	do_action( 'login_head' );

	$login_header_url = __( 'https://wordpress.org/' );

	/**
	 * Filters link URL of the header logo above login form.
	 *
	 * @since 2.1.0
	 *
	 * @param string $login_header_url Login header logo URL.
	 */
	$login_header_url = apply_filters( 'login_headerurl', $login_header_url );

	$login_header_title = '';

	/**
	 * Filters the title attribute of the header logo above login form.
	 *
	 * @since 2.1.0
	 * @deprecated 5.2.0 Use 'login_headertext' instead.
	 *
	 * @param string $login_header_title Login header logo title attribute.
	 */
	$login_header_title = apply_filters_deprecated(
		'login_headertitle',
		array( $login_header_title ),
		'5.2.0',
		'login_headertext',
		__( 'Usage of the title attribute on the login logo is not recommended for accessibility reasons. Use the link text instead.' )
	);

	$login_header_text = empty( $login_header_title ) ? __( 'Powered by WordPress' ) : $login_header_title;

	/**
	 * Filters the link text of the header logo above the login form.
	 *
	 * @since 5.2.0
	 *
	 * @param string $login_header_text The login header logo link text.
	 */
	$login_header_text = apply_filters( 'login_headertext', $login_header_text );

	$classes = array( 'login-action-' . $action, 'wp-core-ui' );

	if ( is_rtl() ) {
		$classes[] = 'rtl';
	}

	if ( $interim_login ) {
		$classes[] = 'interim-login';

		?>
		<style type="text/css">html{background-color: transparent;}</style>
		<?php

		if ( 'success' === $interim_login ) {
			$classes[] = 'interim-login-success';
		}
	}

	$classes[] = ' locale-' . sanitize_html_class( strtolower( str_replace( '_', '-', get_locale() ) ) );

	/**
	 * Filters the login page body classes.
	 *
	 * @since 3.5.0
	 *
	 * @param string[] $classes An array of body classes.
	 * @param string   $action  The action that brought the visitor to the login page.
	 */
	$classes = apply_filters( 'login_body_class', $classes, $action );

	?>
	</head>
	<body class="login no-js <?php echo esc_attr( implode( ' ', $classes ) ); ?>">
	<?php
	wp_print_inline_script_tag( "document.body.className = document.body.className.replace('no-js','js');" );
	?>

	<?php
	/**
	 * Fires in the login page header after the body tag is opened.
	 *
	 * @since 4.6.0
	 */
	do_action( 'login_header' );
	?>
	<?php
	if ( 'confirm_admin_email' !== $action && ! empty( $title ) ) :
		?>
		<h1 class="screen-reader-text"><?php echo $title; ?></h1>
		<?php
	endif;
	?>
	<div id="login">
		<h1 role="presentation" class="wp-login-logo"><a href="<?php echo esc_url( $login_header_url ); ?>"><?php echo $login_header_text; ?></a></h1>
	<?php
	/**
	 * Filters the message to display above the login form.
	 *
	 * @since 2.1.0
	 *
	 * @param string $message Login message text.
	 */
	$message = apply_filters( 'login_message', $message );

	if ( ! empty( $message ) ) {
		echo $message . "\n";
	}

	// In case a plugin uses $error rather than the $wp_errors object.
	if ( ! empty( $error ) ) {
		$wp_error->add( 'error', $error );
		unset( $error );
	}

	if ( $wp_error->has_errors() ) {
		$error_list = array();
		$messages   = '';

		foreach ( $wp_error->get_error_codes() as $code ) {
			$severity = $wp_error->get_error_data( $code );
			foreach ( $wp_error->get_error_messages( $code ) as $error_message ) {
				if ( 'message' === $severity ) {
					$messages .= '<p>' . $error_message . '</p>';
				} else {
					$error_list[] = $error_message;
				}
			}
		}

		if ( ! empty( $error_list ) ) {
			$errors = '';

			if ( count( $error_list ) > 1 ) {
				$errors .= '<ul class="login-error-list">';

				foreach ( $error_list as $item ) {
					$errors .= '<li>' . $item . '</li>';
				}

				$errors .= '</ul>';
			} else {
				$errors .= '<p>' . $error_list[0] . '</p>';
			}

			/**
			 * Filters the error messages displayed above the login form.
			 *
			 * @since 2.1.0
			 *
			 * @param string $errors Login error messages.
			 */
			$errors = apply_filters( 'login_errors', $errors );

			wp_admin_notice(
				$errors,
				array(
					'type'           => 'error',
					'id'             => 'login_error',
					'paragraph_wrap' => false,
				)
			);
		}

		if ( ! empty( $messages ) ) {
			/**
			 * Filters instructional messages displayed above the login form.
			 *
			 * @since 2.5.0
			 *
			 * @param string $messages Login messages.
			 */
			$messages = apply_filters( 'login_messages', $messages );

			wp_admin_notice(
				$messages,
				array(
					'type'               => 'info',
					'id'                 => 'login-message',
					'additional_classes' => array( 'message' ),
					'paragraph_wrap'     => false,
				)
			);
		}
	}
} // End of login_header().

```

[View all references](https://developer.wordpress.org/reference/files/wp-login.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-login.php#L41) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-login.php#L41-L313)

## [Hooks](https://developer.wordpress.org/reference/functions/login_header/\#hooks)

[apply\_filters( ‘login\_body\_class’, string\[\]$classes, string$action )](https://developer.wordpress.org/reference/hooks/login_body_class/)

Filters the login page body classes.

[do\_action( ‘login\_enqueue\_scripts’ )](https://developer.wordpress.org/reference/hooks/login_enqueue_scripts/)

Enqueues scripts and styles for the login page.

[apply\_filters( ‘login\_errors’, string$errors )](https://developer.wordpress.org/reference/hooks/login_errors/)

Filters the error messages displayed above the login form.

[do\_action( ‘login\_head’ )](https://developer.wordpress.org/reference/hooks/login_head/)

Fires in the login page header after scripts are enqueued.

[do\_action( ‘login\_header’ )](https://developer.wordpress.org/reference/hooks/login_header/)

Fires in the login page header after the body tag is opened.

[apply\_filters( ‘login\_headertext’, string$login\_header\_text )](https://developer.wordpress.org/reference/hooks/login_headertext/)

Filters the link text of the header logo above the login form.

[apply\_filters\_deprecated( ‘login\_headertitle’, string$login\_header\_title )](https://developer.wordpress.org/reference/hooks/login_headertitle/)

Filters the title attribute of the header logo above login form.

[apply\_filters( ‘login\_headerurl’, string$login\_header\_url )](https://developer.wordpress.org/reference/hooks/login_headerurl/)

Filters link URL of the header logo above login form.

[apply\_filters( ‘login\_message’, string$message )](https://developer.wordpress.org/reference/hooks/login_message/)

Filters the message to display above the login form.

[apply\_filters( ‘login\_messages’, string$messages )](https://developer.wordpress.org/reference/hooks/login_messages/)

Filters instructional messages displayed above the login form.

[apply\_filters( ‘login\_title’, string$login\_title, string$title )](https://developer.wordpress.org/reference/hooks/login_title/)

Filters the title tag content for login page.

[apply\_filters( ‘shake\_error\_codes’, string\[\]$shake\_error\_codes )](https://developer.wordpress.org/reference/hooks/shake_error_codes/)

Filters the error codes array for shaking the login form.

## [Related](https://developer.wordpress.org/reference/functions/login_header/\#related)

| Uses | Description |
| --- | --- |
| [wp\_admin\_notice()](https://developer.wordpress.org/reference/functions/wp_admin_notice/) `wp-includes/functions.php` | Outputs an admin notice. |
| [wp\_remove\_surrounding\_empty\_script\_tags()](https://developer.wordpress.org/reference/functions/wp_remove_surrounding_empty_script_tags/) `wp-includes/script-loader.php` | Removes leading and trailing \_empty\_ script tags. |
| [wp\_print\_inline\_script\_tag()](https://developer.wordpress.org/reference/functions/wp_print_inline_script_tag/) `wp-includes/script-loader.php` | Prints an inline script tag. |
| [wp\_is\_recovery\_mode()](https://developer.wordpress.org/reference/functions/wp_is_recovery_mode/) `wp-includes/load.php` | Determines whether WordPress is in Recovery Mode. |
| [WP\_Error::has\_errors()](https://developer.wordpress.org/reference/classes/wp_error/has_errors/) `wp-includes/class-wp-error.php` | Verifies if the instance contains errors. |
| [apply\_filters\_deprecated()](https://developer.wordpress.org/reference/functions/apply_filters_deprecated/) `wp-includes/plugin.php` | Fires functions attached to a deprecated filter hook. |
| [sanitize\_html\_class()](https://developer.wordpress.org/reference/functions/sanitize_html_class/) `wp-includes/formatting.php` | Sanitizes an HTML classname to ensure it only contains valid characters. |
| [language\_attributes()](https://developer.wordpress.org/reference/functions/language_attributes/) `wp-includes/general-template.php` | Displays the language attributes for the ‘html’ tag. |
| [bloginfo()](https://developer.wordpress.org/reference/functions/bloginfo/) `wp-includes/general-template.php` | Displays information about the current site. |
| [wp\_enqueue\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_style/) `wp-includes/functions.wp-styles.php` | Enqueues a CSS stylesheet. |
| [WP\_Error::get\_error\_code()](https://developer.wordpress.org/reference/classes/wp_error/get_error_code/) `wp-includes/class-wp-error.php` | Retrieves the first error code available. |
| [WP\_Error::add()](https://developer.wordpress.org/reference/classes/wp_error/add/) `wp-includes/class-wp-error.php` | Adds an error or appends an additional message to an existing error. |
| [WP\_Error::get\_error\_data()](https://developer.wordpress.org/reference/classes/wp_error/get_error_data/) `wp-includes/class-wp-error.php` | Retrieves the most recently added error data for an error code. |
| [WP\_Error::get\_error\_messages()](https://developer.wordpress.org/reference/classes/wp_error/get_error_messages/) `wp-includes/class-wp-error.php` | Retrieves all error messages, or the error messages for the given error code. |
| [WP\_Error::get\_error\_codes()](https://developer.wordpress.org/reference/classes/wp_error/get_error_codes/) `wp-includes/class-wp-error.php` | Retrieves all error codes. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/) `wp-includes/general-template.php` | Retrieves information about the current site. |
| [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) `wp-includes/plugin.php` | Adds a callback function to a filter hook. |
| [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) `wp-includes/plugin.php` | Adds a callback function to an action hook. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 19 more](https://developer.wordpress.org/reference/functions/login_header/#) [Show less](https://developer.wordpress.org/reference/functions/login_header/#)

## [Changelog](https://developer.wordpress.org/reference/functions/login_header/\#changelog)

| Version | Description |
| --- | --- |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/login_header/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/login_header/#comment-content-1484)



**Example from \`wp-login.php\`**





`wp-login.php`
[Copy](https://developer.wordpress.org/reference/functions/login_header/#)




```php
$errors = new WP_Error();
// ...
login_header( __( 'Reset Password', 'textdomain' ), '<p class="message reset-pass">' . __( 'Enter your new password below.', 'textdomain' ) . '</p>', $errors );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flogin_header%2F%3Freplytocom%3D1484%23feedback-editor-1484)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flogin_header%2F) before being able to contribute a note or feedback.

Notifications