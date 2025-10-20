---
url: https://developer.wordpress.org/apis/making-http-requests
scraped_at: 2025-10-20T04:09:13.123Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/making-http-requests/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Making HTTP requests


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Making HTTP requests

Search

# Making HTTP requests

[↑ Back to top](https://developer.wordpress.org/apis/making-http-requests/#wp--skip-link--target)

Very often we need to make HTTP requests from our theme or plugin, for example when we need to fetch data from an external API. Luckily WordPress has many helper functions to help you do that.

In this section, you will learn how to properly make HTTP requests and handle their responses.

Here’s an example of what you’re going to see

``
[Copy](https://developer.wordpress.org/apis/making-http-requests/#)

```php
$response = wp_remote_get( 'https://api.github.com/users/wordpress' );
$body     = wp_remote_retrieve_body( $response );
```

In the next articles you’ll see a detailed explanation on how to make the requests:

- [GETting data from an external service](https://developer.wordpress.org/apis/making-http-requests/getting-data-from-an-external-service/)
- [POSTing data to an external service](https://developer.wordpress.org/apis/making-http-requests/posting-data-to-an-external-service/)
- [Performance](https://developer.wordpress.org/apis/making-http-requests/performance/)
- [Advanced](https://developer.wordpress.org/apis/making-http-requests/advanced/)
- [Authentication](https://developer.wordpress.org/apis/making-http-requests/authentication/)

If you’re just looking for the available helper functions, here they are:

The functions below are the ones you will use to retrieve a URL.

- [`wp_remote_get()`](https://developer.wordpress.org/reference/functions/wp_remote_get/): Retrieves a URL using the GET HTTP method.
- [`wp_remote_post()`](https://developer.wordpress.org/reference/functions/wp_remote_post/): Retrieves a URL using the POST HTTP method.
- [`wp_remote_head()`](https://developer.wordpress.org/reference/functions/wp_remote_head/): Retrieves a URL using the HEAD HTTP method.
- [`wp_remote_request()`](https://developer.wordpress.org/reference/functions/wp_remote_request/): Retrieves a URL using either the default GET or a custom HTTP method that you specify.

The other helper functions deal with retrieving different parts of the response. These make usage of the API very simple and are the preferred method for processing response objects.

- `[wp\_remote\_retrieve\_body()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_body/)` – Retrieves just the body from the response.
- `[wp\_remote\_retrieve\_header()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_header/)` – Retrieve a single header by name from the raw response.
- `[wp\_remote\_retrieve\_headers()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_headers/)` – Retrieve only the headers from the raw response.
- `[wp\_remote\_retrieve\_response\_code()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/)` – Retrieve the response code for the HTTP response. This should be 200, but could be 4xx or even 3xx on failure.
- `[wp\_remote\_retrieve\_response\_message()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_message/)` – Retrieve only the response message from the raw response.

First published

July 13, 2020

Last updated

November 21, 2022

[PreviousPluginsPrevious: Plugins](https://developer.wordpress.org/apis/plugins/)

[NextGETting data from an external serviceNext: GETting data from an external service](https://developer.wordpress.org/apis/making-http-requests/getting-data-from-an-external-service/)

Notifications