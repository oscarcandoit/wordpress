---
url: https://developer.wordpress.org/rest-api/reference/sidebars
scraped_at: 2025-10-20T02:04:12.743Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/sidebars/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Sidebars


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Sidebars

Search

# Sidebars

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/sidebars/#schema)
- [Retrieve a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/#retrieve-a-sidebar)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/#arguments)
- [Retrieve a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/#retrieve-a-sidebar-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/#arguments-2)
- [Update a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/#update-a-sidebar)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/#arguments-3)
  - [Definition](https://developer.wordpress.org/rest-api/reference/sidebars/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/#example-request)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/sidebars/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/sidebars/\#schema)

The schema defines all the fields that exist within a sidebar record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | ID of sidebar.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `name` | Unique name identifying the sidebar.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `description` | Description of sidebar.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `class` | Extra CSS class to assign to the sidebar in the Widgets interface.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `before_widget` | HTML content to prepend to each widget's HTML output when assigned to this sidebar. Default is an opening list item element.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `after_widget` | HTML content to append to each widget's HTML output when assigned to this sidebar. Default is a closing list item element.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `before_title` | HTML content to prepend to the sidebar title when displayed. Default is an opening h2 element.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `after_title` | HTML content to append to the sidebar title when displayed. Default is a closing h2 element.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `status` | Status of sidebar.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit`<br>One of: `active`, `inactive` |
| `widgets` | Nested widgets.<br>JSON data type: array <br>Context: `embed`, `view`, `edit` |

## [Retrieve a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/\#retrieve-a-sidebar)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/\#definition-example-request)

`GET /wp/v2/sidebars`

Query this endpoint to retrieve a specific sidebar record.

`$ curl https://example.com/wp-json/wp/v2/sidebars`

### [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Retrieve a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/\#retrieve-a-sidebar-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/\#definition-example-request-2)

`GET /wp/v2/sidebars/<id>`

Query this endpoint to retrieve a specific sidebar record.

`$ curl https://example.com/wp-json/wp/v2/sidebars/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/\#arguments-2)

|     |     |
| --- | --- |
| `id` | The id of a registered sidebar |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Sidebar](https://developer.wordpress.org/rest-api/reference/sidebars/\#update-a-sidebar)

### [Arguments](https://developer.wordpress.org/rest-api/reference/sidebars/\#arguments-3)

|     |     |
| --- | --- |
| `[widgets](https://developer.wordpress.org/rest-api/reference/sidebars/#schema-widgets)` | Nested widgets. |

### [Definition](https://developer.wordpress.org/rest-api/reference/sidebars/\#definition)

`POST /wp/v2/sidebars/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/sidebars/\#example-request)

``

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Sidebars](https://github.com/WP-API/docs/edit/master/reference/sidebars.md)

Changelog

[See list of changes: Sidebars](https://github.com/WP-API/docs/commits/master/reference/sidebars.md)

[PreviousSearch ResultsPrevious: Search Results](https://developer.wordpress.org/rest-api/reference/search-results/)

[NextSite SettingsNext: Site Settings](https://developer.wordpress.org/rest-api/reference/settings/)

Notifications