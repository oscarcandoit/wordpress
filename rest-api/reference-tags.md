---
url: https://developer.wordpress.org/rest-api/reference/tags
scraped_at: 2025-10-20T02:01:46.174Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/tags/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Tags


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Tags

Search

# Tags

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/tags/#schema)
- [List Tags](https://developer.wordpress.org/rest-api/reference/tags/#list-tags)
  - [Definition](https://developer.wordpress.org/rest-api/reference/tags/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/tags/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/tags/#arguments)
- [Create a Tag](https://developer.wordpress.org/rest-api/reference/tags/#create-a-tag)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/tags/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/tags/#definition-2)
- [Retrieve a Tag](https://developer.wordpress.org/rest-api/reference/tags/#retrieve-a-tag)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/tags/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/tags/#arguments-3)
- [Update a Tag](https://developer.wordpress.org/rest-api/reference/tags/#update-a-tag)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/tags/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/tags/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/tags/#example-request-2)
- [Delete a Tag](https://developer.wordpress.org/rest-api/reference/tags/#delete-a-tag)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/tags/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/tags/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/tags/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/tags/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/tags/\#schema)

The schema defines all the fields that exist within a tag record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the term.<br>JSON data type: integer <br>Read only<br>Context: `view`, `embed`, `edit` |
| `count` | Number of published posts for the term.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit` |
| `description` | HTML description of the term.<br>JSON data type: string <br>Context: `view`, `edit` |
| `link` | URL of the term.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `embed`, `edit` |
| `name` | HTML title for the term.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `slug` | An alphanumeric identifier for the term unique to its type.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `taxonomy` | Type attribution for the term.<br>JSON data type: string <br>Read only<br>Context: `view`, `embed`, `edit`<br>One of: `post_tag` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |

## [List Tags](https://developer.wordpress.org/rest-api/reference/tags/\#list-tags)

Query this endpoint to retrieve a collection of tags. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/tags/\#definition)

`GET /wp/v2/tags`

### [Example Request](https://developer.wordpress.org/rest-api/reference/tags/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/tags`

### [Arguments](https://developer.wordpress.org/rest-api/reference/tags/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `asc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by term attribute.<br>Default: `name`<br>One of: `id`, `include`, `name`, `slug`, `include_slugs`, `term_group`, `description`, `count` |
| `hide_empty` | Whether to hide terms not assigned to any posts. |
| `post` | Limit result set to terms assigned to a specific post. |
| `slug` | Limit result set to terms with one or more specific slugs. |

## [Create a Tag](https://developer.wordpress.org/rest-api/reference/tags/\#create-a-tag)

### [Arguments](https://developer.wordpress.org/rest-api/reference/tags/\#arguments-2)

|     |     |
| --- | --- |
| `[description](https://developer.wordpress.org/rest-api/reference/tags/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/tags/#schema-name)` | HTML title for the term.<br>Required: 1 |
| `[slug](https://developer.wordpress.org/rest-api/reference/tags/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](https://developer.wordpress.org/rest-api/reference/tags/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/tags/\#definition-2)

`POST /wp/v2/tags`

## [Retrieve a Tag](https://developer.wordpress.org/rest-api/reference/tags/\#retrieve-a-tag)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/tags/\#definition-example-request)

`GET /wp/v2/tags/<id>`

Query this endpoint to retrieve a specific tag record.

`$ curl https://example.com/wp-json/wp/v2/tags/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/tags/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Tag](https://developer.wordpress.org/rest-api/reference/tags/\#update-a-tag)

### [Arguments](https://developer.wordpress.org/rest-api/reference/tags/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/tags/#schema-id)` | Unique identifier for the term. |
| `[description](https://developer.wordpress.org/rest-api/reference/tags/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/tags/#schema-name)` | HTML title for the term. |
| `[slug](https://developer.wordpress.org/rest-api/reference/tags/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](https://developer.wordpress.org/rest-api/reference/tags/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/tags/\#definition-3)

`POST /wp/v2/tags/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/tags/\#example-request-2)

``

## [Delete a Tag](https://developer.wordpress.org/rest-api/reference/tags/\#delete-a-tag)

### [Arguments](https://developer.wordpress.org/rest-api/reference/tags/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `force` | Required to be true, as terms do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/tags/\#definition-4)

`DELETE /wp/v2/tags/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/tags/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/tags/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Tags](https://github.com/WP-API/docs/edit/master/reference/tags.md)

Changelog

[See list of changes: Tags](https://github.com/WP-API/docs/commits/master/reference/tags.md)

[PreviousStatusesPrevious: Statuses](https://developer.wordpress.org/rest-api/reference/post-statuses/)

[NextTaxonomiesNext: Taxonomies](https://developer.wordpress.org/rest-api/reference/taxonomies/)

Notifications