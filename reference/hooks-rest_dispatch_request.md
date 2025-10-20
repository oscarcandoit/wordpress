---
url: https://developer.wordpress.org/reference/hooks/rest_dispatch_request
scraped_at: 2025-10-20T03:21:53.980Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

rest\_dispatch\_request


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_REST\_Server::respond\_to\_request](https://developer.wordpress.org/reference/classes/wp_rest_server/respond_to_request/)rest\_dispatch\_request

Search

# apply\_filters( ‘rest\_dispatch\_request’, mixed$dispatch\_result, WP\_REST\_Request$request, string$route, array$handler )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#source)
- [Related](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#wp--skip-link--target)

Filters the REST API dispatch request result.

## [Description](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/\#description)

Allow plugins to override dispatching the request.

## [Parameters](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/\#parameters)

`$dispatch_result` mixed

Dispatch result, will be used if not empty.

`$request` [WP\_REST\_Request](https://developer.wordpress.org/reference/classes/wp_rest_request/)

Request used to generate the response.

`$route` string

Route matched for the request.

`$handler` array

Route handler used for the request.

## [Source](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/\#source)

`wp-includes/rest-api/class-wp-rest-server.php`
[Copy](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/#)

```php
$dispatch_result = apply_filters( 'rest_dispatch_request', null, $request, $route, $handler );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/rest-api/class-wp-rest-server.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/rest-api/class-wp-rest-server.php#L1286) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/rest-api/class-wp-rest-server.php#L1286-L1286)

## [Related](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/\#related)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Server::respond\_to\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/respond_to_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Dispatches the request to the callback handler. |

## [Changelog](https://developer.wordpress.org/reference/hooks/rest_dispatch_request/\#changelog)

| Version | Description |
| --- | --- |
| [4.5.0](https://developer.wordpress.org/reference/since/4.5.0/) | Added `$route` and `$handler` parameters. |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frest_dispatch_request%2F) before being able to contribute a note or feedback.

Notifications