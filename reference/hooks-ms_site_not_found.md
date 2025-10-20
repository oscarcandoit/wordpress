---
url: https://developer.wordpress.org/reference/hooks/ms_site_not_found
scraped_at: 2025-10-20T03:17:55.879Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ms\_site\_not\_found


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)ms\_site\_not\_found

Search

# do\_action( ‘ms\_site\_not\_found’, WP\_Network$current\_site, string$domain, string$path )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#source)
- [Related](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#wp--skip-link--target)

Fires when a network can be determined but a site cannot.

## [Description](https://developer.wordpress.org/reference/hooks/ms_site_not_found/\#description)

At the time of this action, the only recourse is to redirect somewhere and exit. If you want to declare a particular site, do so earlier.

## [Parameters](https://developer.wordpress.org/reference/hooks/ms_site_not_found/\#parameters)

`$current_site` [WP\_Network](https://developer.wordpress.org/reference/classes/wp_network/)

The network that had been determined.

`$domain` string

The domain used to search for a site.

`$path` string

The path used to search for a site.

## [Source](https://developer.wordpress.org/reference/hooks/ms_site_not_found/\#source)

`wp-includes/ms-load.php`
[Copy](https://developer.wordpress.org/reference/hooks/ms_site_not_found/#)

```php
do_action( 'ms_site_not_found', $current_site, $domain, $path );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/ms-load.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/ms-load.php#L418) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/ms-load.php#L418-L418)

## [Related](https://developer.wordpress.org/reference/hooks/ms_site_not_found/\#related)

| Used by | Description |
| --- | --- |
| [ms\_load\_current\_site\_and\_network()](https://developer.wordpress.org/reference/functions/ms_load_current_site_and_network/) `wp-includes/ms-load.php` | Identifies the network and site of a requested domain and path and populates the corresponding network and site global objects as part of the multisite bootstrap process. |

## [Changelog](https://developer.wordpress.org/reference/hooks/ms_site_not_found/\#changelog)

| Version | Description |
| --- | --- |
| [3.9.0](https://developer.wordpress.org/reference/since/3.9.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fms_site_not_found%2F) before being able to contribute a note or feedback.

Notifications