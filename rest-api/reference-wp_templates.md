---
url: https://developer.wordpress.org/rest-api/reference/wp_templates
scraped_at: 2025-10-20T02:06:06.919Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_templates/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Templates


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Templates

Search

# Templates

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema)
- [Retrieve a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/#retrieve-a-template)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/#arguments)
- [Create a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/#create-a-template)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/#definition)
- [Retrieve a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/#retrieve-a-template-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/#arguments-3)
- [Update a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/#update-a-template)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/#example-request)
- [Delete a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/#delete-a-template)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/#example-request-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_templates/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_templates/\#schema)

The schema defines all the fields that exist within a template record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | ID of template.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `slug` | Unique slug identifying the template.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `theme` | Theme identifier for the template.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `type` | Type of template.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `source` | Source of template<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `origin` | Source of a customized template<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `content` | Content of template.<br>JSON data type: object or string <br>Context: `embed`, `view`, `edit` |
| `title` | Title of template.<br>JSON data type: object or string <br>Context: `embed`, `view`, `edit` |
| `description` | Description of template.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `status` | Status of template.<br>JSON data type: string <br>Context: `embed`, `view`, `edit`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `wp_id` | Post ID.<br>JSON data type: integer <br>Read only<br>Context: `embed`, `view`, `edit` |
| `has_theme_file` | Theme file exists.<br>JSON data type: bool <br>Read only<br>Context: `embed`, `view`, `edit` |
| `author` | The ID for the author of the template.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `modified` | The date the template was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `is_custom` | Whether a template is a custom template.<br>JSON data type: bool <br>Read only<br>Context: `embed`, `view`, `edit` |

## [Retrieve a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/\#retrieve-a-template)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/\#definition-example-request)

`GET /wp/v2/templates`

Query this endpoint to retrieve a specific template record.

`$ curl https://example.com/wp-json/wp/v2/templates`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `wp_id` | Limit to the specified post id. |
| `area` | Limit to the specified template part area. |
| `post_type` | Post type to get the templates for. |

## [Create a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/\#create-a-template)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/\#arguments-2)

|     |     |
| --- | --- |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-slug)` | Unique slug identifying the template.<br>Required: 1 |
| `[theme](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-theme)` | Theme identifier for the template. |
| `[type](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-type)` | Type of template. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-content)` | Content of template. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-title)` | Title of template. |
| `[description](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-description)` | Description of template. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-status)` | Status of template.<br>Default: `publish`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-author)` | The ID for the author of the template. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/\#definition)

`POST /wp/v2/templates`

## [Retrieve a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/\#retrieve-a-template-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/\#definition-example-request-2)

`GET /wp/v2/templates/<id>?)[\/\w%-]+)`

Query this endpoint to retrieve a specific template record.

`$ curl https://example.com/wp-json/wp/v2/templates/<id>?)[\/\w%-]+)`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/\#arguments-3)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/\#update-a-template)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-id)` | The id of a template |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-slug)` | Unique slug identifying the template. |
| `[theme](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-theme)` | Theme identifier for the template. |
| `[type](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-type)` | Type of template. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-content)` | Content of template. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-title)` | Title of template. |
| `[description](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-description)` | Description of template. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-status)` | Status of template.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](https://developer.wordpress.org/rest-api/reference/wp_templates/#schema-author)` | The ID for the author of the template. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/\#definition-2)

`POST /wp/v2/templates/<id>?)[\/\w%-]+)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/\#example-request)

``

## [Delete a Template](https://developer.wordpress.org/rest-api/reference/wp_templates/\#delete-a-template)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_templates/\#arguments-5)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_templates/\#definition-3)

`DELETE /wp/v2/templates/<id>?)[\/\w%-]+)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_templates/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/templates/<id>?)[\/\w%-]+)`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Templates](https://github.com/WP-API/docs/edit/master/reference/wp_templates.md)

Changelog

[See list of changes: Templates](https://github.com/WP-API/docs/commits/master/reference/wp_templates.md)

[PreviousTemplate RevisionsPrevious: Template Revisions](https://developer.wordpress.org/rest-api/reference/wp_template-revisions/)

[NextTemplate\_Part RevisionsNext: Template\_Part Revisions](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/)

Notifications