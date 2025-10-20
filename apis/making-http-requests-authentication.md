---
url: https://developer.wordpress.org/apis/making-http-requests/authentication
scraped_at: 2025-10-20T04:11:15.097Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/making-http-requests/authentication/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Authentication


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Making HTTP requests](https://developer.wordpress.org/apis/making-http-requests/)Authentication

Search

# Authentication

[↑ Back to top](https://developer.wordpress.org/apis/making-http-requests/authentication/#wp--skip-link--target)

Many APIs will require you to make authenticated requests to access some endpoints. A common authentication method is called HTTP Basic Authentication. It can be used in WordPress using the ‘Authorization’ header `[wp\_remote\_get()](https://developer.wordpress.org/reference/functions/wp_remote_get)`.

``
[Copy](https://developer.wordpress.org/apis/making-http-requests/authentication/#)

```php
$args = array(
    'headers' => array(
        'Authorization' => 'Basic ' . base64_encode( YOUR_USERNAME . ':' . YOUR_PASSWORD )
    )
);
wp_remote_get( $url, $args );
```

HTTP Basic Auth is very insecure because it exposes the username and password and is only used for testing and development. Check the documentation of the API you want to access for more information on how to authenticate.

If you want to make authenticated requests to the WordPress REST API, check [this article](https://developer.wordpress.org/rest-api/using-the-rest-api/authentication/).

First published

July 13, 2020

Last updated

November 17, 2022

[PreviousAdvancedPrevious: Advanced](https://developer.wordpress.org/apis/making-http-requests/advanced/)

[NextQuicktagsNext: Quicktags](https://developer.wordpress.org/apis/quicktags/)

Notifications