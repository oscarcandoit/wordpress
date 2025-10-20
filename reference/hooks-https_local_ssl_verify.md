---
url: https://developer.wordpress.org/reference/hooks/https_local_ssl_verify
scraped_at: 2025-10-20T03:21:57.451Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

https\_local\_ssl\_verify


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Http\_Streams::request](https://developer.wordpress.org/reference/classes/wp_http_streams/request/)https\_local\_ssl\_verify

Search

# apply\_filters( ‘https\_local\_ssl\_verify’, bool\|string$ssl\_verify, string$url )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#source)
- [Related](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#wp--skip-link--target)

Filters whether SSL should be verified for local HTTP API requests.

## [Parameters](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/\#parameters)

`$ssl_verify` bool\|string

Boolean to control whether to verify the SSL connection or path to an SSL certificate.

`$url` string

The request URL.

## [Source](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/\#source)

`wp-includes/class-wp-http-streams.php`
[Copy](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#)

```php
$ssl_verify = apply_filters( 'https_local_ssl_verify', $ssl_verify, $url );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-http-streams.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-http-streams.php#L113) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-http-streams.php#L113-L113)

## [Related](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Automatic\_Updater::has\_fatal\_error()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/has_fatal_error/) `wp-admin/includes/class-wp-automatic-updater.php` | Performs a loopback request to check for potential fatal errors. |
| [WP\_Site\_Health::check\_for\_page\_caching()](https://developer.wordpress.org/reference/classes/wp_site_health/check_for_page_caching/) `wp-admin/includes/class-wp-site-health.php` | Checks if site has page cache enabled or not. |
| [WP\_Site\_Health::get\_test\_rest\_availability()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_rest_availability/) `wp-admin/includes/class-wp-site-health.php` | Tests if the REST API is accessible. |
| [WP\_Site\_Health::can\_perform\_loopback()](https://developer.wordpress.org/reference/classes/wp_site_health/can_perform_loopback/) `wp-admin/includes/class-wp-site-health.php` | Runs a loopback test on the site. |
| [wp\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_edit_theme_plugin_file/) `wp-admin/includes/file.php` | Attempts to edit a file for a theme or plugin. |
| [spawn\_cron()](https://developer.wordpress.org/reference/functions/spawn_cron/) `wp-includes/cron.php` | Sends a request to run cron through HTTP request that doesn’t halt page loading. |
| [WP\_Http\_Curl::request()](https://developer.wordpress.org/reference/classes/wp_http_curl/request/) `wp-includes/class-wp-http-curl.php` | Send a HTTP request to a URI using cURL extension. |
| [WP\_Http\_Streams::request()](https://developer.wordpress.org/reference/classes/wp_http_streams/request/) `wp-includes/class-wp-http-streams.php` | Send a HTTP request to a URI using PHP Streams. |

[Show 3 more](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#) [Show less](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/#)

## [Changelog](https://developer.wordpress.org/reference/hooks/https_local_ssl_verify/\#changelog)

| Version | Description |
| --- | --- |
| [5.1.0](https://developer.wordpress.org/reference/since/5.1.0/) | The `$url` parameter was added. |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fhttps_local_ssl_verify%2F) before being able to contribute a note or feedback.

Notifications