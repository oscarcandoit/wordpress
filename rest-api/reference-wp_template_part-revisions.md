---
url: https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions
scraped_at: 2025-10-20T02:03:01.646Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Template\_Part Revisions


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Template\_Part Revisions

Search

# Template\_Part Revisions

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema)
- [List Template\_Part Revisions](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#list-template_part-revisions)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments)
- [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#retrieve-a-template_part-revision)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments-2)
- [Delete a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#delete-a-template_part-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments-3)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#example-request-2)
- [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#retrieve-a-template_part-revision-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments-4)
- [Create a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#create-a-template_part-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition-3)
- [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#retrieve-a-template_part-revision-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#definition-example-request-3)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#arguments-6)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#schema)

The schema defines all the fields that exist within a template\_part revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `guid` | GUID for the revision, as it exists in the database.<br>JSON data type: string <br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `title` | Title of template.<br>JSON data type: object or string <br>Context: `embed`, `view`, `edit` |
| `content` | Content of template.<br>JSON data type: object or string <br>Context: `embed`, `view`, `edit` |

## [List Template\_Part Revisions](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#list-template_part-revisions)

Query this endpoint to retrieve a collection of template\_part revisions. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition)

`GET /wp/v2/template-parts/<parent>/revisions`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set. |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by object attribute.<br>Default: `date`<br>One of: `date`, `id`, `include`, `relevance`, `slug`, `include_slugs`, `title` |

## [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#retrieve-a-template_part-revision)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition-example-request)

`GET /wp/v2/template-parts/<parent>/revisions/<id>`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments-2)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Delete a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#delete-a-template_part-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `force` | Required to be true, as revisions do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition-2)

`DELETE /wp/v2/template-parts/<parent>/revisions/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions/<id>`

## [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#retrieve-a-template_part-revision-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition-example-request-2)

`GET /wp/v2/template-parts/<id>/autosaves`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<id>/autosaves`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments-4)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Create a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#create-a-template_part-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments-5)

|     |     |
| --- | --- |
| `[parent](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-parent)` | The ID for the parent of the autosave. |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-slug)` | Unique slug identifying the template. |
| `[theme](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-theme)` | Theme identifier for the template. |
| `[type](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-type)` | Type of template. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-content)` | Content of template. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-title)` | Title of template. |
| `[description](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-description)` | Description of template. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-status)` | Status of template.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-author)` | The ID for the author of the template. |
| `[area](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/#schema-area)` | Where the template part is intended for use (header, footer, etc.) |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition-3)

`POST /wp/v2/template-parts/<id>/autosaves`

## [Retrieve a Template\_Part Revision](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#retrieve-a-template_part-revision-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#definition-example-request-3)

`GET /wp/v2/template-parts/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/autosaves/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/\#arguments-6)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Template\_Part Revisions](https://github.com/WP-API/docs/edit/master/reference/wp_template_part-revisions.md)

Changelog

[See list of changes: Template\_Part Revisions](https://github.com/WP-API/docs/commits/master/reference/wp_template_part-revisions.md)

[PreviousTemplatesPrevious: Templates](https://developer.wordpress.org/rest-api/reference/wp_templates/)

[NextTemplate\_PartsNext: Template\_Parts](https://developer.wordpress.org/rest-api/reference/wp_template_parts/)

Notifications