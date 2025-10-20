---
url: https://developer.wordpress.org/rest-api/reference/categories
scraped_at: 2025-10-20T02:06:11.223Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/categories/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Categories


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Categories

Search

# Categories

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/categories/#schema)
- [List Categories](https://developer.wordpress.org/rest-api/reference/categories/#list-categories)
  - [Definition](https://developer.wordpress.org/rest-api/reference/categories/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/categories/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/categories/#arguments)
- [Create a Category](https://developer.wordpress.org/rest-api/reference/categories/#create-a-category)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/categories/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/categories/#definition-2)
- [Retrieve a Category](https://developer.wordpress.org/rest-api/reference/categories/#retrieve-a-category)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/categories/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/categories/#arguments-3)
- [Update a Category](https://developer.wordpress.org/rest-api/reference/categories/#update-a-category)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/categories/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/categories/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/categories/#example-request-2)
- [Delete a Category](https://developer.wordpress.org/rest-api/reference/categories/#delete-a-category)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/categories/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/categories/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/categories/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/categories/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/categories/\#schema)

The schema defines all the fields that exist within a category record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the term.<br>JSON data type: integer <br>Read only<br>Context: `view`, `embed`, `edit` |
| `count` | Number of published posts for the term.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit` |
| `description` | HTML description of the term.<br>JSON data type: string <br>Context: `view`, `edit` |
| `link` | URL of the term.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `embed`, `edit` |
| `name` | HTML title for the term.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `slug` | An alphanumeric identifier for the term unique to its type.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `taxonomy` | Type attribution for the term.<br>JSON data type: string <br>Read only<br>Context: `view`, `embed`, `edit`<br>One of: `category` |
| `parent` | The parent term ID.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |

## [List Categories](https://developer.wordpress.org/rest-api/reference/categories/\#list-categories)

Query this endpoint to retrieve a collection of categories. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/categories/\#definition)

`GET /wp/v2/categories`

### [Example Request](https://developer.wordpress.org/rest-api/reference/categories/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/categories`

### [Arguments](https://developer.wordpress.org/rest-api/reference/categories/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `order` | Order sort attribute ascending or descending.<br>Default: `asc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by term attribute.<br>Default: `name`<br>One of: `id`, `include`, `name`, `slug`, `include_slugs`, `term_group`, `description`, `count` |
| `hide_empty` | Whether to hide terms not assigned to any posts. |
| `parent` | Limit result set to terms assigned to a specific parent. |
| `post` | Limit result set to terms assigned to a specific post. |
| `slug` | Limit result set to terms with one or more specific slugs. |

## [Create a Category](https://developer.wordpress.org/rest-api/reference/categories/\#create-a-category)

### [Arguments](https://developer.wordpress.org/rest-api/reference/categories/\#arguments-2)

|     |     |
| --- | --- |
| `[description](https://developer.wordpress.org/rest-api/reference/categories/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/categories/#schema-name)` | HTML title for the term.<br>Required: 1 |
| `[slug](https://developer.wordpress.org/rest-api/reference/categories/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[parent](https://developer.wordpress.org/rest-api/reference/categories/#schema-parent)` | The parent term ID. |
| `[meta](https://developer.wordpress.org/rest-api/reference/categories/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/categories/\#definition-2)

`POST /wp/v2/categories`

## [Retrieve a Category](https://developer.wordpress.org/rest-api/reference/categories/\#retrieve-a-category)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/categories/\#definition-example-request)

`GET /wp/v2/categories/<id>`

Query this endpoint to retrieve a specific category record.

`$ curl https://example.com/wp-json/wp/v2/categories/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/categories/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Category](https://developer.wordpress.org/rest-api/reference/categories/\#update-a-category)

### [Arguments](https://developer.wordpress.org/rest-api/reference/categories/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/categories/#schema-id)` | Unique identifier for the term. |
| `[description](https://developer.wordpress.org/rest-api/reference/categories/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/categories/#schema-name)` | HTML title for the term. |
| `[slug](https://developer.wordpress.org/rest-api/reference/categories/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[parent](https://developer.wordpress.org/rest-api/reference/categories/#schema-parent)` | The parent term ID. |
| `[meta](https://developer.wordpress.org/rest-api/reference/categories/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/categories/\#definition-3)

`POST /wp/v2/categories/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/categories/\#example-request-2)

``

## [Delete a Category](https://developer.wordpress.org/rest-api/reference/categories/\#delete-a-category)

### [Arguments](https://developer.wordpress.org/rest-api/reference/categories/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `force` | Required to be true, as terms do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/categories/\#definition-4)

`DELETE /wp/v2/categories/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/categories/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/categories/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Categories](https://github.com/WP-API/docs/edit/master/reference/categories.md)

Changelog

[See list of changes: Categories](https://github.com/WP-API/docs/commits/master/reference/categories.md)

[PreviousBlock TypesPrevious: Block Types](https://developer.wordpress.org/rest-api/reference/block-types/)

[NextCommentsNext: Comments](https://developer.wordpress.org/rest-api/reference/comments/)

Notifications