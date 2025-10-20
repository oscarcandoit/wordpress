---
url: https://developer.wordpress.org/reference/hooks/rest_post_dispatch
scraped_at: 2025-10-20T03:27:19.164Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

rest\_post\_dispatch


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_REST\_Server::serve\_request](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_request/)rest\_post\_dispatch

Search

# apply\_filters( ‘rest\_post\_dispatch’, WP\_HTTP\_Response$result, WP\_REST\_Server$server, WP\_REST\_Request$request )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#source)
- [Related](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#wp--skip-link--target)

Filters the REST API response.

## [Description](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/\#description)

Allows modification of the response before returning.

## [Parameters](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/\#parameters)

`$result` [WP\_HTTP\_Response](https://developer.wordpress.org/reference/classes/wp_http_response/)

Result to send to the client. Usually a `WP_REST_Response`.

`$server` [WP\_REST\_Server](https://developer.wordpress.org/reference/classes/wp_rest_server/)

Server instance.

`$request` [WP\_REST\_Request](https://developer.wordpress.org/reference/classes/wp_rest_request/)

Request used to generate the response.

## [Source](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/\#source)

`wp-includes/rest-api/class-wp-rest-server.php`
[Copy](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/#)

```php
$result = apply_filters( 'rest_post_dispatch', rest_ensure_response( $result ), $this, $request );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/rest-api/class-wp-rest-server.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/rest-api/class-wp-rest-server.php#L462) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/rest-api/class-wp-rest-server.php#L462-L462)

## [Related](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/\#related)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Server::serve\_batch\_request\_v1()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_batch_request_v1/) `wp-includes/rest-api/class-wp-rest-server.php` | Serves the batch/v1 request. |
| [rest\_preload\_api\_request()](https://developer.wordpress.org/reference/functions/rest_preload_api_request/) `wp-includes/rest-api.php` | Append result of internal request to REST API for purpose of preloading data to be attached to a page. |
| [WP\_REST\_Server::serve\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Handles serving a REST API request. |
| [WP\_REST\_Server::embed\_links()](https://developer.wordpress.org/reference/classes/wp_rest_server/embed_links/) `wp-includes/rest-api/class-wp-rest-server.php` | Embeds the links from the data into the request. |

## [Changelog](https://developer.wordpress.org/reference/hooks/rest_post_dispatch/\#changelog)

| Version | Description |
| --- | --- |
| [4.5.0](https://developer.wordpress.org/reference/since/4.5.0/) | Applied to embedded responses. |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frest_post_dispatch%2F) before being able to contribute a note or feedback.

Notifications