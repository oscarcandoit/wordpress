---
url: https://developer.wordpress.org/reference/hooks/login_site_html_link
scraped_at: 2025-10-20T03:16:57.618Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/login_site_html_link/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

login\_site\_html\_link


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)login\_site\_html\_link

Search

# apply\_filters( ‘login\_site\_html\_link’, string$link )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/login_site_html_link/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/login_site_html_link/#source)
- [Related](https://developer.wordpress.org/reference/hooks/login_site_html_link/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/login_site_html_link/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/login_site_html_link/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/login_site_html_link/#wp--skip-link--target)

Filters the “Go to site” link displayed in the login page footer.

## [Parameters](https://developer.wordpress.org/reference/hooks/login_site_html_link/\#parameters)

`$link` string

HTML link to the home URL of the current site.

## [Source](https://developer.wordpress.org/reference/hooks/login_site_html_link/\#source)

`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/login_site_html_link/#)

```php
echo apply_filters( 'login_site_html_link', $html_link );

```

[View all references](https://developer.wordpress.org/reference/files/wp-login.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-login.php#L349) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-login.php#L349-L349)

## [Related](https://developer.wordpress.org/reference/hooks/login_site_html_link/\#related)

| Used by | Description |
| --- | --- |
| [login\_footer()](https://developer.wordpress.org/reference/functions/login_footer/) `wp-login.php` | Outputs the footer for the login page. |

## [Changelog](https://developer.wordpress.org/reference/hooks/login_site_html_link/\#changelog)

| Version | Description |
| --- | --- |
| [5.7.0](https://developer.wordpress.org/reference/since/5.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/login_site_html_link/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/login_site_html_link/#comment-content-6939)



Modify the “Go to site” link displayed in the login page footer.


Copy and paste the following the child theme’s function.php file at the very end.





`wp-login.php`
[Expand code](https://developer.wordpress.org/reference/hooks/login_site_html_link/#)

[Copy](https://developer.wordpress.org/reference/hooks/login_site_html_link/#)




```php
add_filter( 'login_site_html_link', 'wpdocs_login_site_html_link_cb' );

/**
    * Filters the “Go to site” link displayed in the login page footer.
    *
    * @return string $html_link Modified "Go to Site" link.
    */
function wpdocs_login_site_html_link_cb() {
   	$html_link = sprintf(
   		'%s',
   		esc_url( home_url( '/' ) ),
   		sprintf(
   			/* translators: %s: Site title. */
   			_x( '← Go to %s', 'site' ),
   			get_bloginfo( 'title', 'display' )
   		)
   	);

   	return $html_link;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_site_html_link%2F%3Freplytocom%3D6939%23feedback-editor-6939)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_site_html_link%2F) before being able to contribute a note or feedback.

Notifications