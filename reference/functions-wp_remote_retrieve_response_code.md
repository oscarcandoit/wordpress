---
url: https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code
scraped_at: 2025-10-20T03:25:28.102Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_remote\_retrieve\_response\_code()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_remote\_retrieve\_response\_code()

Search

# wp\_remote\_retrieve\_response\_code( array\|WP\_Error$response ): int\|string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#wp--skip-link--target)

Retrieves only the response code from the raw response.

## [Description](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#description)

Will return an empty string if incorrect parameter value is given.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#parameters)

`$response` array\|[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)required

HTTP response.

## [Return](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#return)

int\|string The response code as an integer. Empty string if incorrect parameter given.

## [Source](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#source)

`wp-includes/http.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#)

```php
function wp_remote_retrieve_response_code( $response ) {
	if ( is_wp_error( $response ) || ! isset( $response['response'] ) || ! is_array( $response['response'] ) ) {
		return '';
	}

	return $response['response']['code'];
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/http.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/http.php#L270) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/http.php#L270-L276)

## [Related](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#related)

| Uses | Description |
| --- | --- |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

| Used by | Description |
| --- | --- |
| [WP\_Font\_Collection::load\_from\_url()](https://developer.wordpress.org/reference/classes/wp_font_collection/load_from_url/) `wp-includes/fonts/class-wp-font-collection.php` | Loads the font collection data from a JSON file URL. |
| [wp\_get\_https\_detection\_errors()](https://developer.wordpress.org/reference/functions/wp_get_https_detection_errors/) `wp-includes/https-detection.php` | Runs a remote HTTPS request to detect whether HTTPS supported, and stores potential errors. |
| [WP\_Site\_Health::check\_for\_page\_caching()](https://developer.wordpress.org/reference/classes/wp_site_health/check_for_page_caching/) `wp-admin/includes/class-wp-site-health.php` | Checks if site has page cache enabled or not. |
| [WP\_REST\_URL\_Details\_Controller::get\_remote\_url()](https://developer.wordpress.org/reference/classes/wp_rest_url_details_controller/get_remote_url/) `wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php` | Retrieves the document title from a remote URL. |
| [WP\_Site\_Health::wp\_cron\_scheduled\_check()](https://developer.wordpress.org/reference/classes/wp_site_health/wp_cron_scheduled_check/) `wp-admin/includes/class-wp-site-health.php` | Runs the scheduled event to check and update the latest site health status for the website. |
| [WP\_Site\_Health::get\_test\_rest\_availability()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_rest_availability/) `wp-admin/includes/class-wp-site-health.php` | Tests if the REST API is accessible. |
| [WP\_Site\_Health::can\_perform\_loopback()](https://developer.wordpress.org/reference/classes/wp_site_health/can_perform_loopback/) `wp-admin/includes/class-wp-site-health.php` | Runs a loopback test on the site. |
| [wp\_check\_php\_version()](https://developer.wordpress.org/reference/functions/wp_check_php_version/) `wp-admin/includes/misc.php` | Checks if the user needs to update PHP. |
| [WP\_Community\_Events::get\_events()](https://developer.wordpress.org/reference/classes/wp_community_events/get_events/) `wp-admin/includes/class-wp-community-events.php` | Gets data about events near a particular location. |
| [populate\_network()](https://developer.wordpress.org/reference/functions/populate_network/) `wp-admin/includes/schema.php` | Populate network settings. |
| [get\_core\_checksums()](https://developer.wordpress.org/reference/functions/get_core_checksums/) `wp-admin/includes/update.php` | Gets and caches the checksums for the given version of WordPress. |
| [wp\_check\_browser\_version()](https://developer.wordpress.org/reference/functions/wp_check_browser_version/) `wp-admin/includes/dashboard.php` | Checks if the user needs a browser update. |
| [download\_url()](https://developer.wordpress.org/reference/functions/download_url/) `wp-admin/includes/file.php` | Downloads a URL to a local temporary file using the WordPress HTTP API. |
| [wp\_credits()](https://developer.wordpress.org/reference/functions/wp_credits/) `wp-admin/includes/credits.php` | Retrieves the contributor credits. |
| [url\_is\_accessable\_via\_ssl()](https://developer.wordpress.org/reference/functions/url_is_accessable_via_ssl/) `wp-includes/deprecated.php` | Determines if the URL can be accessed over SSL. |
| [wp\_get\_http()](https://developer.wordpress.org/reference/functions/wp_get_http/) `wp-includes/deprecated.php` | Perform a HTTP HEAD or GET request. |
| [WP\_SimplePie\_File::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_simplepie_file/__construct/) `wp-includes/class-wp-simplepie-file.php` | Constructor. |
| [wp\_version\_check()](https://developer.wordpress.org/reference/functions/wp_version_check/) `wp-includes/update.php` | Checks WordPress version against the newest version. |
| [wp\_update\_plugins()](https://developer.wordpress.org/reference/functions/wp_update_plugins/) `wp-includes/update.php` | Checks for available updates to plugins based on the latest versions hosted on WordPress.org. |
| [wp\_update\_themes()](https://developer.wordpress.org/reference/functions/wp_update_themes/) `wp-includes/update.php` | Checks for available updates to themes based on the latest versions hosted on WordPress.org. |
| [WP\_oEmbed::\_fetch\_with\_format()](https://developer.wordpress.org/reference/classes/wp_oembed/_fetch_with_format/) `wp-includes/class-wp-oembed.php` | Fetches result from an oEmbed provider for a specific format and complete provider URL |
| [WP\_HTTP\_IXR\_Client::query()](https://developer.wordpress.org/reference/classes/wp_http_ixr_client/query/) `wp-includes/class-wp-http-ixr-client.php` |  |
| [\_fetch\_remote\_file()](https://developer.wordpress.org/reference/functions/_fetch_remote_file/) `wp-includes/rss.php` | Retrieve URL headers and content using WP HTTP Request API. |

[Show 18 more](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#) [Show less](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#changelog)

| Version | Description |
| --- | --- |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#comment-content-1445)



**Examples**





`wp-includes/http.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/#)




```php
$response = wp_remote_get( 'http://www.foo.com/file.txt' );
$response_code = wp_remote_retrieve_response_code( $response );
```





`$response_code` will contain a string representing the numeric response code sent from the server





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_remote_retrieve_response_code%2F%3Freplytocom%3D1445%23feedback-editor-1445)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_remote_retrieve_response_code%2F) before being able to contribute a note or feedback.

Notifications