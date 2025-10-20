---
url: https://developer.wordpress.org/rest-api/reference/menu-locations
scraped_at: 2025-10-20T02:02:16.214Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/menu-locations/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Menu Locations


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Menu Locations

Search

# Menu Locations

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/menu-locations/#schema)
- [Retrieve a Menu Location](https://developer.wordpress.org/rest-api/reference/menu-locations/#retrieve-a-menu-location)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/menu-locations/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/menu-locations/#arguments)
- [Retrieve a Menu Location](https://developer.wordpress.org/rest-api/reference/menu-locations/#retrieve-a-menu-location-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/menu-locations/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/menu-locations/#arguments-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/menu-locations/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/menu-locations/\#schema)

The schema defines all the fields that exist within a menu location record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The name of the menu location.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `description` | The description of the menu location.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `menu` | The ID of the assigned menu.<br>JSON data type: integer <br>Read only<br>Context: `embed`, `view`, `edit` |

## [Retrieve a Menu Location](https://developer.wordpress.org/rest-api/reference/menu-locations/\#retrieve-a-menu-location)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/menu-locations/\#definition-example-request)

`GET /wp/v2/menu-locations`

Query this endpoint to retrieve a specific menu location record.

`$ curl https://example.com/wp-json/wp/v2/menu-locations`

### [Arguments](https://developer.wordpress.org/rest-api/reference/menu-locations/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Retrieve a Menu Location](https://developer.wordpress.org/rest-api/reference/menu-locations/\#retrieve-a-menu-location-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/menu-locations/\#definition-example-request-2)

`GET /wp/v2/menu-locations/<location>`

Query this endpoint to retrieve a specific menu location record.

`$ curl https://example.com/wp-json/wp/v2/menu-locations/<location>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/menu-locations/\#arguments-2)

|     |     |
| --- | --- |
| `location` | An alphanumeric identifier for the menu location. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Menu Locations](https://github.com/WP-API/docs/edit/master/reference/menu-locations.md)

Changelog

[See list of changes: Menu Locations](https://github.com/WP-API/docs/commits/master/reference/menu-locations.md)

[PreviousMediaPrevious: Media](https://developer.wordpress.org/rest-api/reference/media/)

[NextNavigation RevisionsNext: Navigation Revisions](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/)

Notifications