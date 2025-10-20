---
url: https://developer.wordpress.org/rest-api/reference/wp-site-health-tests
scraped_at: 2025-10-20T02:02:27.137Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Wp Site Health Tests


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Wp Site Health Tests

Search

# Wp Site Health Tests

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#schema)
- [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#retrieve-a-wp-site-health-test)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#definition-example-request)
- [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#retrieve-a-wp-site-health-test-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#definition-example-request-2)
- [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#retrieve-a-wp-site-health-test-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#definition-example-request-3)
- [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#retrieve-a-wp-site-health-test-4)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#definition-example-request-4)
- [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#retrieve-a-wp-site-health-test-5)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#definition-example-request-5)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#schema)

The schema defines all the fields that exist within a wp site health test record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `test` | The name of the test being run.<br>JSON data type: string <br>Read only<br>Context: `` |
| `label` | A label describing the test.<br>JSON data type: string <br>Read only<br>Context: `` |
| `status` | The status of the test.<br>JSON data type: string <br>Read only<br>Context: ``<br>One of: `good`, `recommended`, `critical` |
| `badge` | The category this test is grouped in.<br>JSON data type: object <br>Read only<br>Context: `` |
| `description` | A more descriptive explanation of what the test looks for, and why it is important for the user.<br>JSON data type: string <br>Read only<br>Context: `` |
| `actions` | HTML containing an action to direct the user to where they can resolve the issue.<br>JSON data type: string <br>Read only<br>Context: `` |

## [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#retrieve-a-wp-site-health-test)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#definition-example-request)

`GET /wp-site-health/v1/tests/background-updates`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/background-updates`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#retrieve-a-wp-site-health-test-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#definition-example-request-2)

`GET /wp-site-health/v1/tests/loopback-requests`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/loopback-requests`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#retrieve-a-wp-site-health-test-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#definition-example-request-3)

`GET /wp-site-health/v1/tests/https-status`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/https-status`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#retrieve-a-wp-site-health-test-4)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#definition-example-request-4)

`GET /wp-site-health/v1/tests/dotorg-communication`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/dotorg-communication`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#retrieve-a-wp-site-health-test-5)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/\#definition-example-request-5)

`GET /wp-site-health/v1/tests/authorization-header`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/authorization-header`

There are no arguments for this endpoint.

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Wp Site Health Tests](https://github.com/WP-API/docs/edit/master/reference/wp-site-health-tests.md)

Changelog

[See list of changes: Wp Site Health Tests](https://github.com/WP-API/docs/commits/master/reference/wp-site-health-tests.md)

[PreviousWidgetsPrevious: Widgets](https://developer.wordpress.org/rest-api/reference/widgets/)

[NextRequestsNext: Requests](https://developer.wordpress.org/rest-api/requests/)

Notifications