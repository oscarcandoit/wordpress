---
url: https://developer.wordpress.org/reference/functions/wp_register
scraped_at: 2025-10-20T03:12:44.266Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_register/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_register()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_register()

Search

# wp\_register( string$before = '<li>', string$after = '</li>', bool$display = true ): void\|string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_register/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_register/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_register/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_register/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_register/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_register/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_register/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_register/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_register/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_register/#wp--skip-link--target)

Displays the Registration or Admin link.

## [Description](https://developer.wordpress.org/reference/functions/wp_register/\#description)

Display a link which allows the user to navigate to the registration page if not logged in and registration is enabled or to the dashboard if logged in.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_register/\#parameters)

`$before` stringoptional

Text to output before the link. Default `<li>`.

Default: `'<li>'`

`$after` stringoptional

Text to output after the link. Default `</li>`.

Default: `'</li>'`

`$display` booloptional

Default to echo and not return the link.

Default: `true`

## [Return](https://developer.wordpress.org/reference/functions/wp_register/\#return)

void\|string Void if `$display` argument is true, registration or admin link if `$display` is false.

## [More Information](https://developer.wordpress.org/reference/functions/wp_register/\#more-information)

The “Register” link is not offered if the [Administration](https://wordpress.org/support/article/administration-screens/ "Administration Panels") \> [Settings](https://wordpress.org/support/article/administration-screens/ "Administration Panels") \> [General](https://wordpress.org/support/article/settings-general-screen/ "Settings General SubPanel") \> **Membership: Anyone can register** box is not checked.

## [Source](https://developer.wordpress.org/reference/functions/wp_register/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_register/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_register/#)

```php
function wp_register( $before = '<li>', $after = '</li>', $display = true ) {
	if ( ! is_user_logged_in() ) {
		if ( get_option( 'users_can_register' ) ) {
			$link = $before . '<a href="' . esc_url( wp_registration_url() ) . '">' . __( 'Register' ) . '</a>' . $after;
		} else {
			$link = '';
		}
	} elseif ( current_user_can( 'read' ) ) {
		$link = $before . '<a href="' . admin_url() . '">' . __( 'Site Admin' ) . '</a>' . $after;
	} else {
		$link = '';
	}

	/**
	 * Filters the HTML link to the Registration or Admin page.
	 *
	 * Users are sent to the admin page if logged-in, or the registration page
	 * if enabled and logged-out.
	 *
	 * @since 1.5.0
	 *
	 * @param string $link The HTML code for the link to the Registration or Admin page.
	 */
	$link = apply_filters( 'register', $link );

	if ( $display ) {
		echo $link;
	} else {
		return $link;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L701) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L701-L731)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_register/\#hooks)

[apply\_filters( ‘register’, string$link )](https://developer.wordpress.org/reference/hooks/register/)

Filters the HTML link to the Registration or Admin page.

## [Related](https://developer.wordpress.org/reference/functions/wp_register/\#related)

| Uses | Description |
| --- | --- |
| [is\_user\_logged\_in()](https://developer.wordpress.org/reference/functions/is_user_logged_in/) `wp-includes/pluggable.php` | Determines whether the current visitor is a logged in user. |
| [wp\_registration\_url()](https://developer.wordpress.org/reference/functions/wp_registration_url/) `wp-includes/general-template.php` | Returns the URL that allows the user to register on the site. |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current site. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

[Show 5 more](https://developer.wordpress.org/reference/functions/wp_register/#) [Show less](https://developer.wordpress.org/reference/functions/wp_register/#)

| Used by | Description |
| --- | --- |
| [WP\_Widget\_Meta::widget()](https://developer.wordpress.org/reference/classes/wp_widget_meta/widget/) `wp-includes/widgets/class-wp-widget-meta.php` | Outputs the content for the current Meta widget instance. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_register/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_register/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/wp_register/#comment-content-524)



**Default Usage**

`wp_register` displays the link in list format `<li>`.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_register/#)




```php
<?php wp_register(); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register%2F%3Freplytocom%3D524%23feedback-editor-524)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_register/#comment-content-525)



**Display Without Text Before or After**


The following code example displays the “Register” or “Site Admin” link with no text in before or after parameters.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_register/#)




```php
<?php wp_register('', ''); ?>
```





When not logged in the following HTML is produced:





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_register/#)




```php
<a href="http://www.example.com/wp-login.php?action=register">Register</a&gt;
```





When logged in the following HTML is produced:





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_register/#)




```php
<a href="http://www.example.com/wp-admin/">Site Admin</a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register%2F%3Freplytocom%3D525%23feedback-editor-525)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register%2F) before being able to contribute a note or feedback.

Notifications