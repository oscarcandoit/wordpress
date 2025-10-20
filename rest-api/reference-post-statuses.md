---
url: https://developer.wordpress.org/rest-api/reference/post-statuses
scraped_at: 2025-10-20T02:03:10.603Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/post-statuses/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Statuses


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Statuses

Search

# Statuses

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/post-statuses/#schema)
- [Retrieve a Status](https://developer.wordpress.org/rest-api/reference/post-statuses/#retrieve-a-status)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-statuses/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/post-statuses/#arguments)
- [Retrieve a Status](https://developer.wordpress.org/rest-api/reference/post-statuses/#retrieve-a-status-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-statuses/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/post-statuses/#arguments-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/post-statuses/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/post-statuses/\#schema)

The schema defines all the fields that exist within a status record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The title for the status.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `private` | Whether posts with this status should be private.<br>JSON data type: boolean <br>Read only<br>Context: `edit` |
| `protected` | Whether posts with this status should be protected.<br>JSON data type: boolean <br>Read only<br>Context: `edit` |
| `public` | Whether posts of this status should be shown in the front end of the site.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit` |
| `queryable` | Whether posts with this status should be publicly-queryable.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit` |
| `show_in_list` | Whether to include posts in the edit listing for their post type.<br>JSON data type: boolean <br>Read only<br>Context: `edit` |
| `slug` | An alphanumeric identifier for the status.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `date_floating` | Whether posts of this status may have floating published dates.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit` |

## [Retrieve a Status](https://developer.wordpress.org/rest-api/reference/post-statuses/\#retrieve-a-status)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-statuses/\#definition-example-request)

`GET /wp/v2/statuses`

Query this endpoint to retrieve a specific status record.

`$ curl https://example.com/wp-json/wp/v2/statuses`

### [Arguments](https://developer.wordpress.org/rest-api/reference/post-statuses/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Retrieve a Status](https://developer.wordpress.org/rest-api/reference/post-statuses/\#retrieve-a-status-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-statuses/\#definition-example-request-2)

`GET /wp/v2/statuses/<status>`

Query this endpoint to retrieve a specific status record.

`$ curl https://example.com/wp-json/wp/v2/statuses/<status>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/post-statuses/\#arguments-2)

|     |     |
| --- | --- |
| `status` | An alphanumeric identifier for the status. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Statuses](https://github.com/WP-API/docs/edit/master/reference/post-statuses.md)

Changelog

[See list of changes: Statuses](https://github.com/WP-API/docs/commits/master/reference/post-statuses.md)

[PreviousSite SettingsPrevious: Site Settings](https://developer.wordpress.org/rest-api/reference/settings/)

[NextTagsNext: Tags](https://developer.wordpress.org/rest-api/reference/tags/)

Notifications