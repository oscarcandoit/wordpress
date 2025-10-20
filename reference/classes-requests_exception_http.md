---
url: https://developer.wordpress.org/reference/classes/requests_exception_http
scraped_at: 2025-10-20T03:27:27.092Z
---

[Skip to content](https://developer.wordpress.org/reference/classes/requests_exception_http/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Requests\_Exception\_HTTP


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Classes](https://developer.wordpress.org/reference/classes/)Requests\_Exception\_HTTP

Search

# class Requests\_Exception\_HTTP {}

## In this article

Table of Contents

- [Methods](https://developer.wordpress.org/reference/classes/requests_exception_http/#methods)
- [Source](https://developer.wordpress.org/reference/classes/requests_exception_http/#source)
- [Related](https://developer.wordpress.org/reference/classes/requests_exception_http/#related)

[↑ Back to top](https://developer.wordpress.org/reference/classes/requests_exception_http/#wp--skip-link--target)

Exception based on HTTP response

## [Methods](https://developer.wordpress.org/reference/classes/requests_exception_http/\#methods)

| Name | Description |
| --- | --- |
| [Requests\_Exception\_HTTP::\_\_construct](https://developer.wordpress.org/reference/classes/requests_exception_http/__construct/) | Create a new exception |
| [Requests\_Exception\_HTTP::get\_class](https://developer.wordpress.org/reference/classes/requests_exception_http/get_class/) | Get the correct exception class for a given error code |
| [Requests\_Exception\_HTTP::getReason](https://developer.wordpress.org/reference/classes/requests_exception_http/getreason/) | Get the status message |

## [Source](https://developer.wordpress.org/reference/classes/requests_exception_http/\#source)

[View all references](https://developer.wordpress.org/reference/files/wp-includes/requests/exception/http.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/Requests/Exception/HTTP.php#L13)

## [Related](https://developer.wordpress.org/reference/classes/requests_exception_http/\#related)

| Uses | Description |
| --- | --- |
| [Requests\_Exception](https://developer.wordpress.org/reference/classes/requests_exception/) `wp-includes/Requests/Exception.php` | Exception for HTTP requests |

| Used by | Description |
| --- | --- |
| [Requests\_Exception\_HTTP\_403](https://developer.wordpress.org/reference/classes/requests_exception_http_403/) `wp-includes/Requests/Exception/HTTP/403.php` | Exception for 403 Forbidden responses |
| [Requests\_Exception\_HTTP\_511](https://developer.wordpress.org/reference/classes/requests_exception_http_511/) `wp-includes/Requests/Exception/HTTP/511.php` | Exception for 511 Network Authentication Required responses |
| [Requests\_Exception\_HTTP\_404](https://developer.wordpress.org/reference/classes/requests_exception_http_404/) `wp-includes/Requests/Exception/HTTP/404.php` | Exception for 404 Not Found responses |
| [Requests\_Exception\_HTTP\_415](https://developer.wordpress.org/reference/classes/requests_exception_http_415/) `wp-includes/Requests/Exception/HTTP/415.php` | Exception for 415 Unsupported Media Type responses |
| [Requests\_Exception\_HTTP\_505](https://developer.wordpress.org/reference/classes/requests_exception_http_505/) `wp-includes/Requests/Exception/HTTP/505.php` | Exception for 505 HTTP Version Not Supported responses |
| [Requests\_Exception\_HTTP\_409](https://developer.wordpress.org/reference/classes/requests_exception_http_409/) `wp-includes/Requests/Exception/HTTP/409.php` | Exception for 409 Conflict responses |
| [Requests\_Exception\_HTTP\_412](https://developer.wordpress.org/reference/classes/requests_exception_http_412/) `wp-includes/Requests/Exception/HTTP/412.php` | Exception for 412 Precondition Failed responses |
| [Requests\_Exception\_HTTP\_431](https://developer.wordpress.org/reference/classes/requests_exception_http_431/) `wp-includes/Requests/Exception/HTTP/431.php` | Exception for 431 Request Header Fields Too Large responses |
| [Requests\_Exception\_HTTP\_402](https://developer.wordpress.org/reference/classes/requests_exception_http_402/) `wp-includes/Requests/Exception/HTTP/402.php` | Exception for 402 Payment Required responses |
| [Requests\_Exception\_HTTP\_401](https://developer.wordpress.org/reference/classes/requests_exception_http_401/) `wp-includes/Requests/Exception/HTTP/401.php` | Exception for 401 Unauthorized responses |
| [Requests\_Exception\_HTTP\_504](https://developer.wordpress.org/reference/classes/requests_exception_http_504/) `wp-includes/Requests/Exception/HTTP/504.php` | Exception for 504 Gateway Timeout responses |
| [Requests\_Exception\_HTTP\_414](https://developer.wordpress.org/reference/classes/requests_exception_http_414/) `wp-includes/Requests/Exception/HTTP/414.php` | Exception for 414 Request-URI Too Large responses |
| [Requests\_Exception\_HTTP\_406](https://developer.wordpress.org/reference/classes/requests_exception_http_406/) `wp-includes/Requests/Exception/HTTP/406.php` | Exception for 406 Not Acceptable responses |
| [Requests\_Exception\_HTTP\_413](https://developer.wordpress.org/reference/classes/requests_exception_http_413/) `wp-includes/Requests/Exception/HTTP/413.php` | Exception for 413 Request Entity Too Large responses |
| [Requests\_Exception\_HTTP\_429](https://developer.wordpress.org/reference/classes/requests_exception_http_429/) `wp-includes/Requests/Exception/HTTP/429.php` | Exception for 429 Too Many Requests responses |
| [Requests\_Exception\_HTTP\_417](https://developer.wordpress.org/reference/classes/requests_exception_http_417/) `wp-includes/Requests/Exception/HTTP/417.php` | Exception for 417 Expectation Failed responses |
| [Requests\_Exception\_HTTP\_Unknown](https://developer.wordpress.org/reference/classes/requests_exception_http_unknown/) `wp-includes/Requests/Exception/HTTP/Unknown.php` | Exception for unknown status responses |
| [Requests\_Exception\_HTTP\_304](https://developer.wordpress.org/reference/classes/requests_exception_http_304/) `wp-includes/Requests/Exception/HTTP/304.php` | Exception for 304 Not Modified responses |
| [Requests\_Exception\_HTTP\_503](https://developer.wordpress.org/reference/classes/requests_exception_http_503/) `wp-includes/Requests/Exception/HTTP/503.php` | Exception for 503 Service Unavailable responses |
| [Requests\_Exception\_HTTP\_428](https://developer.wordpress.org/reference/classes/requests_exception_http_428/) `wp-includes/Requests/Exception/HTTP/428.php` | Exception for 428 Precondition Required responses |
| [Requests\_Exception\_HTTP\_416](https://developer.wordpress.org/reference/classes/requests_exception_http_416/) `wp-includes/Requests/Exception/HTTP/416.php` | Exception for 416 Requested Range Not Satisfiable responses |
| [Requests\_Exception\_HTTP\_418](https://developer.wordpress.org/reference/classes/requests_exception_http_418/) `wp-includes/Requests/Exception/HTTP/418.php` | Exception for 418 I’m A Teapot responses |
| [Requests\_Exception\_HTTP\_500](https://developer.wordpress.org/reference/classes/requests_exception_http_500/) `wp-includes/Requests/Exception/HTTP/500.php` | Exception for 500 Internal Server Error responses |
| [Requests\_Exception\_HTTP\_400](https://developer.wordpress.org/reference/classes/requests_exception_http_400/) `wp-includes/Requests/Exception/HTTP/400.php` | Exception for 400 Bad Request responses |
| [Requests\_Exception\_HTTP\_502](https://developer.wordpress.org/reference/classes/requests_exception_http_502/) `wp-includes/Requests/Exception/HTTP/502.php` | Exception for 502 Bad Gateway responses |
| [Requests\_Exception\_HTTP\_408](https://developer.wordpress.org/reference/classes/requests_exception_http_408/) `wp-includes/Requests/Exception/HTTP/408.php` | Exception for 408 Request Timeout responses |
| [Requests\_Exception\_HTTP\_410](https://developer.wordpress.org/reference/classes/requests_exception_http_410/) `wp-includes/Requests/Exception/HTTP/410.php` | Exception for 410 Gone responses |
| [Requests\_Exception\_HTTP\_501](https://developer.wordpress.org/reference/classes/requests_exception_http_501/) `wp-includes/Requests/Exception/HTTP/501.php` | Exception for 501 Not Implemented responses |
| [Requests\_Exception\_HTTP\_405](https://developer.wordpress.org/reference/classes/requests_exception_http_405/) `wp-includes/Requests/Exception/HTTP/405.php` | Exception for 405 Method Not Allowed responses |
| [Requests\_Exception\_HTTP\_305](https://developer.wordpress.org/reference/classes/requests_exception_http_305/) `wp-includes/Requests/Exception/HTTP/305.php` | Exception for 305 Use Proxy responses |

[Show 25 more](https://developer.wordpress.org/reference/classes/requests_exception_http/#) [Show less](https://developer.wordpress.org/reference/classes/requests_exception_http/#)

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Frequests_exception_http%2F) before being able to contribute a note or feedback.

Notifications