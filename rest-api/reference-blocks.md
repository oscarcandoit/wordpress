---
url: https://developer.wordpress.org/rest-api/reference/blocks
scraped_at: 2025-10-20T02:01:33.974Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/blocks/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Editor Blocks


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Editor Blocks

Search

# Editor Blocks

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/blocks/#schema)
- [List Editor Blocks](https://developer.wordpress.org/rest-api/reference/blocks/#list-editor-blocks)
  - [Definition](https://developer.wordpress.org/rest-api/reference/blocks/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/#arguments)
- [Create a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/#create-a-editor-block)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/blocks/#definition-2)
- [Retrieve a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/#retrieve-a-editor-block)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/blocks/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/#arguments-3)
- [Update a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/#update-a-editor-block)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/blocks/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/#example-request-2)
- [Delete a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/#delete-a-editor-block)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/blocks/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/blocks/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/blocks/\#schema)

The schema defines all the fields that exist within a Editor Block record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `date` | The date the post was published, in the site's timezone.<br>JSON data type: string or null,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the post was published, as GMT.<br>JSON data type: string or null,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `guid` | The globally unique identifier for the post.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit` |
| `id` | Unique identifier for the post.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit`, `embed` |
| `link` | URL to the post.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit`, `embed` |
| `modified` | The date the post was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `modified_gmt` | The date the post was last modified, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `slug` | An alphanumeric identifier for the post unique to its type.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `status` | A named status for the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `type` | Type of post.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `password` | A password to protect access to the content and excerpt.<br>JSON data type: string <br>Context: `edit` |
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |
| `template` | The theme file to use to display the post.<br>JSON data type: string <br>Context: `view`, `edit` |

## [List Editor Blocks](https://developer.wordpress.org/rest-api/reference/blocks/\#list-editor-blocks)

Query this endpoint to retrieve a collection of Editor Blocks. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/blocks/\#definition)

`GET /wp/v2/blocks`

### [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/blocks`

### [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to posts published after a given ISO8601 compliant date. |
| `modified_after` | Limit response to posts modified after a given ISO8601 compliant date. |
| `before` | Limit response to posts published before a given ISO8601 compliant date. |
| `modified_before` | Limit response to posts modified before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br>Default: `date`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title` |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `publish` |

## [Create a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/\#create-a-editor-block)

### [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/\#arguments-2)

|     |     |
| --- | --- |
| `[date](https://developer.wordpress.org/rest-api/reference/blocks/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/blocks/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/blocks/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/blocks/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/blocks/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/blocks/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/blocks/#schema-content)` | The content for the post. |
| `[meta](https://developer.wordpress.org/rest-api/reference/blocks/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/blocks/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/blocks/\#definition-2)

`POST /wp/v2/blocks`

## [Retrieve a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/\#retrieve-a-editor-block)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/blocks/\#definition-example-request)

`GET /wp/v2/blocks/<id>`

Query this endpoint to retrieve a specific Editor Block record.

`$ curl https://example.com/wp-json/wp/v2/blocks/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `password` | The password for the post if it is password protected. |

## [Update a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/\#update-a-editor-block)

### [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/blocks/#schema-id)` | Unique identifier for the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/blocks/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/blocks/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/blocks/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/blocks/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/blocks/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/blocks/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/blocks/#schema-content)` | The content for the post. |
| `[meta](https://developer.wordpress.org/rest-api/reference/blocks/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/blocks/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/blocks/\#definition-3)

`POST /wp/v2/blocks/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/\#example-request-2)

``

## [Delete a Editor Block](https://developer.wordpress.org/rest-api/reference/blocks/\#delete-a-editor-block)

### [Arguments](https://developer.wordpress.org/rest-api/reference/blocks/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/blocks/\#definition-4)

`DELETE /wp/v2/blocks/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/blocks/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/blocks/<id>`

First published

July 21, 2019

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Editor Blocks](https://github.com/WP-API/docs/edit/master/reference/blocks.md)

Changelog

[See list of changes: Editor Blocks](https://github.com/WP-API/docs/commits/master/reference/blocks.md)

[PreviousCommentsPrevious: Comments](https://developer.wordpress.org/rest-api/reference/comments/)

[NextGlobal\_StylesNext: Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/)

Notifications