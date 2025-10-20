---
url: https://developer.wordpress.org/reference/hooks/lostpassword_redirect
scraped_at: 2025-10-20T03:12:35.383Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

lostpassword\_redirect


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)lostpassword\_redirect

Search

# apply\_filters( ‘lostpassword\_redirect’, string$lostpassword\_redirect )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#source)
- [Changelog](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#wp--skip-link--target)

Filters the URL redirected to after submitting the lostpassword/retrievepassword form.

## [Parameters](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/\#parameters)

`$lostpassword_redirect` string

The redirect destination URL.

## [More Information](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/\#more-information)

- The `lostpassword_redirect` filter is used to change the location redirected to after a user requests a password reset. This could be the location set by the “redirect\_to” parameter sent to the forgot password page.
- This filter is to redirect the user following reset of the password. To filter the location of the password reset itself, use [lostpassword\_url](https://developer.wordpress.org/reference/hooks/lostpassword_url/).

## [Source](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/\#source)

`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#)

```php
$redirect_to = apply_filters( 'lostpassword_redirect', $lostpassword_redirect );

```

[View all references](https://developer.wordpress.org/reference/files/wp-login.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-login.php#L864) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-login.php#L864-L864)

## [Changelog](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#comment-content-4595)



Example migrated from Codex:



This simple example will redirect a user to the [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) upon successful password reset.





`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/lostpassword_redirect/#)




```php
add_filter( 'lostpassword_redirect', 'my_redirect_home' );

function my_redirect_home( $lostpassword_redirect ) {
   	return home_url();
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flostpassword_redirect%2F%3Freplytocom%3D4595%23feedback-editor-4595)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flostpassword_redirect%2F) before being able to contribute a note or feedback.

Notifications