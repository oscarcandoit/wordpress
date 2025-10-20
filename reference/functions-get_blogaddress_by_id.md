---
url: https://developer.wordpress.org/reference/functions/get_blogaddress_by_id
scraped_at: 2025-10-20T03:27:04.760Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_blogaddress\_by\_id()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_blogaddress\_by\_id()

Search

# get\_blogaddress\_by\_id( int$blog\_id ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#wp--skip-link--target)

Gets a full site URL, given a site ID.

## [Parameters](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/\#parameters)

`$blog_id` intrequired

Site ID.

## [Return](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/\#return)

string Full site URL if found. Empty string if not.

## [Source](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/\#source)

`wp-includes/ms-blogs.php`
[Copy](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/#)

```php
function get_blogaddress_by_id( $blog_id ) {
	$bloginfo = get_site( (int) $blog_id );

	if ( empty( $bloginfo ) ) {
		return '';
	}

	$scheme = parse_url( $bloginfo->home, PHP_URL_SCHEME );
	$scheme = empty( $scheme ) ? 'http' : $scheme;

	return esc_url( $scheme . '://' . $bloginfo->domain . $bloginfo->path );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/ms-blogs.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/ms-blogs.php#L46) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/ms-blogs.php#L46-L57)

## [Related](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/\#related)

| Uses | Description |
| --- | --- |
| [get\_site()](https://developer.wordpress.org/reference/functions/get_site/) `wp-includes/ms-site.php` | Retrieves site data given a site ID or site object. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |

| Used by | Description |
| --- | --- |
| [wpmu\_welcome\_notification()](https://developer.wordpress.org/reference/functions/wpmu_welcome_notification/) `wp-includes/ms-functions.php` | Notifies the site administrator that their site activation was successful. |
| [install\_blog()](https://developer.wordpress.org/reference/functions/install_blog/) `wp-includes/ms-deprecated.php` | Install an empty blog. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_blogaddress_by_id/\#changelog)

| Version | Description |
| --- | --- |
| [MU (3.0.0)](https://developer.wordpress.org/reference/since/mu.3.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_blogaddress_by_id%2F) before being able to contribute a note or feedback.

Notifications