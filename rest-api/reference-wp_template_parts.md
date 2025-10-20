---
url: https://developer.wordpress.org/rest-api/reference/wp_template_parts
scraped_at: 2025-10-20T02:01:27.197Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Template\_Parts


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Template\_Parts

Search

# Template\_Parts

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema)
- [Retrieve a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#retrieve-a-template_part)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#arguments)
- [Create a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#create-a-template_part)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#definition)
- [Retrieve a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#retrieve-a-template_part-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#arguments-3)
- [Update a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#update-a-template_part)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#example-request)
- [Delete a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#delete-a-template_part)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#example-request-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#schema)

The schema defines all the fields that exist within a template\_part record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

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
| `area` | Where the template part is intended for use (header, footer, etc.)<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |

## [Retrieve a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#retrieve-a-template_part)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#definition-example-request)

`GET /wp/v2/template-parts`

Query this endpoint to retrieve a specific template\_part record.

`$ curl https://example.com/wp-json/wp/v2/template-parts`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `wp_id` | Limit to the specified post id. |
| `area` | Limit to the specified template part area. |
| `post_type` | Post type to get the templates for. |

## [Create a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#create-a-template_part)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#arguments-2)

|     |     |
| --- | --- |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-slug)` | Unique slug identifying the template.<br>Required: 1 |
| `[theme](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-theme)` | Theme identifier for the template. |
| `[type](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-type)` | Type of template. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-content)` | Content of template. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-title)` | Title of template. |
| `[description](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-description)` | Description of template. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-status)` | Status of template.<br>Default: `publish`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-author)` | The ID for the author of the template. |
| `[area](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-area)` | Where the template part is intended for use (header, footer, etc.) |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#definition)

`POST /wp/v2/template-parts`

## [Retrieve a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#retrieve-a-template_part-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#definition-example-request-2)

`GET /wp/v2/template-parts/<id>?)[\/\w%-]+)`

Query this endpoint to retrieve a specific template\_part record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<id>?)[\/\w%-]+)`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#arguments-3)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#update-a-template_part)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-id)` | The id of a template |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-slug)` | Unique slug identifying the template. |
| `[theme](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-theme)` | Theme identifier for the template. |
| `[type](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-type)` | Type of template. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-content)` | Content of template. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-title)` | Title of template. |
| `[description](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-description)` | Description of template. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-status)` | Status of template.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-author)` | The ID for the author of the template. |
| `[area](https://developer.wordpress.org/rest-api/reference/wp_template_parts/#schema-area)` | Where the template part is intended for use (header, footer, etc.) |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#definition-2)

`POST /wp/v2/template-parts/<id>?)[\/\w%-]+)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#example-request)

``

## [Delete a Template\_Part](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#delete-a-template_part)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#arguments-5)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#definition-3)

`DELETE /wp/v2/template-parts/<id>?)[\/\w%-]+)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_parts/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/template-parts/<id>?)[\/\w%-]+)`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Template\_Parts](https://github.com/WP-API/docs/edit/master/reference/wp_template_parts.md)

Changelog

[See list of changes: Template\_Parts](https://github.com/WP-API/docs/commits/master/reference/wp_template_parts.md)

[PreviousTemplate\_Part RevisionsPrevious: Template\_Part Revisions](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/)

[NextThemesNext: Themes](https://developer.wordpress.org/rest-api/reference/themes/)

Notifications