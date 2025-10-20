---
url: https://developer.wordpress.org/reference/hooks/password_reset
scraped_at: 2025-10-20T03:22:11.594Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/password_reset/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

password\_reset


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)password\_reset

Search

# do\_action( ‘password\_reset’, WP\_User$user, string$new\_pass )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/password_reset/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/password_reset/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/password_reset/#source)
- [Related](https://developer.wordpress.org/reference/hooks/password_reset/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/password_reset/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/password_reset/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/password_reset/#wp--skip-link--target)

Fires before the user’s password is reset.

## [Parameters](https://developer.wordpress.org/reference/hooks/password_reset/\#parameters)

`$user` [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)

The user.

`$new_pass` string

New user password.

## [More Information](https://developer.wordpress.org/reference/hooks/password_reset/\#more-information)

Runs after the user submits a new password during password reset but before the new password is actually set.

## [Source](https://developer.wordpress.org/reference/hooks/password_reset/\#source)

`wp-includes/user.php`
[Copy](https://developer.wordpress.org/reference/hooks/password_reset/#)

```php
do_action( 'password_reset', $user, $new_pass );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/user.php#L3432) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/user.php#L3432-L3432)

## [Related](https://developer.wordpress.org/reference/hooks/password_reset/\#related)

| Used by | Description |
| --- | --- |
| [reset\_password()](https://developer.wordpress.org/reference/functions/reset_password/) `wp-includes/user.php` | Handles resetting the user’s password. |

## [Changelog](https://developer.wordpress.org/reference/hooks/password_reset/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/password_reset/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/password_reset/#comment-content-5888)





`wp-includes/user.php`
[Copy](https://developer.wordpress.org/reference/hooks/password_reset/#)




```php
add_action('password_reset', 'password_reset_action', 10, 2);
function password_reset_action($user, $new_pass) {
   	// user email. $user return full user info
   	$email = $user->data->user_email;
   	// new entered password (plain text)
   	$password = $new_pass;

   	// Do whatever you want...
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpassword_reset%2F%3Freplytocom%3D5888%23feedback-editor-5888)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpassword_reset%2F) before being able to contribute a note or feedback.

Notifications