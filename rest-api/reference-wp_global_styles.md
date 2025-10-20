---
url: https://developer.wordpress.org/rest-api/reference/wp_global_styles
scraped_at: 2025-10-20T02:02:07.090Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Global\_Styles


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Global\_Styles

Search

# Global\_Styles

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#schema)
- [Retrieve a Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#retrieve-a-global_styles)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#arguments)
- [Update a Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#update-a-global_styles)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#example-request)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#schema)

The schema defines all the fields that exist within a global\_styles record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | ID of global styles config.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `styles` | Global styles.<br>JSON data type: object <br>Context: `view`, `edit` |
| `settings` | Global settings.<br>JSON data type: object <br>Context: `view`, `edit` |
| `title` | Title of the global styles variation.<br>JSON data type: object or string <br>Context: `embed`, `view`, `edit` |

## [Retrieve a Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#retrieve-a-global_styles)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#definition-example-request)

`GET /wp/v2/global-styles/<id>`

Query this endpoint to retrieve a specific global\_styles record.

`$ curl https://example.com/wp-json/wp/v2/global-styles/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#arguments)

|     |     |
| --- | --- |
| `id` | The id of a template |

## [Update a Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#update-a-global_styles)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#arguments-2)

|     |     |
| --- | --- |
| `[styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#schema-styles)` | Global styles. |
| `[settings](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#schema-settings)` | Global settings. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_global_styles/#schema-title)` | Title of the global styles variation. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#definition)

`POST /wp/v2/global-styles/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_global_styles/\#example-request)

``

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Global\_Styles](https://github.com/WP-API/docs/edit/master/reference/wp_global_styles.md)

Changelog

[See list of changes: Global\_Styles](https://github.com/WP-API/docs/commits/master/reference/wp_global_styles.md)

[PreviousEditor BlocksPrevious: Editor Blocks](https://developer.wordpress.org/rest-api/reference/blocks/)

[NextMediaNext: Media](https://developer.wordpress.org/rest-api/reference/media/)

Notifications