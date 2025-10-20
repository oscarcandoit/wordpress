---
url: https://developer.wordpress.org/rest-api/reference/widgets
scraped_at: 2025-10-20T02:01:49.960Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/widgets/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Widgets


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Widgets

Search

# Widgets

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/widgets/#schema)
- [Retrieve a Widget](https://developer.wordpress.org/rest-api/reference/widgets/#retrieve-a-widget)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/widgets/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/#arguments)
- [Create a Widget](https://developer.wordpress.org/rest-api/reference/widgets/#create-a-widget)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/widgets/#definition)
- [Retrieve a Widget](https://developer.wordpress.org/rest-api/reference/widgets/#retrieve-a-widget-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/widgets/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/#arguments-3)
- [Update a Widget](https://developer.wordpress.org/rest-api/reference/widgets/#update-a-widget)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/widgets/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/widgets/#example-request)
- [Delete a Widget](https://developer.wordpress.org/rest-api/reference/widgets/#delete-a-widget)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/widgets/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/widgets/#example-request-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/widgets/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/widgets/\#schema)

The schema defines all the fields that exist within a widget record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the widget.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `id_base` | The type of the widget. Corresponds to ID in widget-types endpoint.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `sidebar` | The sidebar the widget belongs to.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `rendered` | HTML representation of the widget.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `rendered_form` | HTML representation of the widget admin form.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `instance` | Instance settings of the widget, if supported.<br>JSON data type: object <br>Context: `edit` |
| `form_data` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only.<br>JSON data type: string <br>Context: `` |

## [Retrieve a Widget](https://developer.wordpress.org/rest-api/reference/widgets/\#retrieve-a-widget)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/widgets/\#definition-example-request)

`GET /wp/v2/widgets`

Query this endpoint to retrieve a specific widget record.

`$ curl https://example.com/wp-json/wp/v2/widgets`

### [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `sidebar` | The sidebar to return widgets for. |

## [Create a Widget](https://developer.wordpress.org/rest-api/reference/widgets/\#create-a-widget)

### [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/\#arguments-2)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/widgets/#schema-id)` | Unique identifier for the widget. |
| `[id\_base](https://developer.wordpress.org/rest-api/reference/widgets/#schema-id_base)` | The type of the widget. Corresponds to ID in widget-types endpoint. |
| `[sidebar](https://developer.wordpress.org/rest-api/reference/widgets/#schema-sidebar)` | The sidebar the widget belongs to.<br>Required: 1<br> <br>Default: `wp_inactive_widgets` |
| `[instance](https://developer.wordpress.org/rest-api/reference/widgets/#schema-instance)` | Instance settings of the widget, if supported. |
| `[form\_data](https://developer.wordpress.org/rest-api/reference/widgets/#schema-form_data)` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only. |

### [Definition](https://developer.wordpress.org/rest-api/reference/widgets/\#definition)

`POST /wp/v2/widgets`

## [Retrieve a Widget](https://developer.wordpress.org/rest-api/reference/widgets/\#retrieve-a-widget-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/widgets/\#definition-example-request-2)

`GET /wp/v2/widgets/<id>`

Query this endpoint to retrieve a specific widget record.

`$ curl https://example.com/wp-json/wp/v2/widgets/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/\#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Widget](https://developer.wordpress.org/rest-api/reference/widgets/\#update-a-widget)

### [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/widgets/#schema-id)` | Unique identifier for the widget. |
| `[id\_base](https://developer.wordpress.org/rest-api/reference/widgets/#schema-id_base)` | The type of the widget. Corresponds to ID in widget-types endpoint. |
| `[sidebar](https://developer.wordpress.org/rest-api/reference/widgets/#schema-sidebar)` | The sidebar the widget belongs to. |
| `[instance](https://developer.wordpress.org/rest-api/reference/widgets/#schema-instance)` | Instance settings of the widget, if supported. |
| `[form\_data](https://developer.wordpress.org/rest-api/reference/widgets/#schema-form_data)` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only. |

### [Definition](https://developer.wordpress.org/rest-api/reference/widgets/\#definition-2)

`POST /wp/v2/widgets/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/widgets/\#example-request)

``

## [Delete a Widget](https://developer.wordpress.org/rest-api/reference/widgets/\#delete-a-widget)

### [Arguments](https://developer.wordpress.org/rest-api/reference/widgets/\#arguments-5)

|     |     |
| --- | --- |
| `force` | Whether to force removal of the widget, or move it to the inactive sidebar. |

### [Definition](https://developer.wordpress.org/rest-api/reference/widgets/\#definition-3)

`DELETE /wp/v2/widgets/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/widgets/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/widgets/<id>`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Widgets](https://github.com/WP-API/docs/edit/master/reference/widgets.md)

Changelog

[See list of changes: Widgets](https://github.com/WP-API/docs/commits/master/reference/widgets.md)

[PreviousWidget TypesPrevious: Widget Types](https://developer.wordpress.org/rest-api/reference/widget-types/)

[NextWp Site Health TestsNext: Wp Site Health Tests](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/)

Notifications