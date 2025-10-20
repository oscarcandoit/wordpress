---
url: https://developer.wordpress.org/rest-api/reference/pattern-directory-items
scraped_at: 2025-10-20T02:03:12.837Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Pattern Directory Items


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Pattern Directory Items

Search

# Pattern Directory Items

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#schema)
- [List Pattern Directory Items](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#list-pattern-directory-items)
  - [Definition](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#arguments)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/\#schema)

The schema defines all the fields that exist within a pattern directory item record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | The pattern ID.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `title` | The pattern title, in human readable format.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `content` | The pattern content.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `categories` | The pattern's category slugs.<br>JSON data type: array <br>Context: `view`, `edit`, `embed` |
| `keywords` | The pattern's keywords.<br>JSON data type: array <br>Context: `view`, `edit`, `embed` |
| `description` | A description of the pattern.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `viewport_width` | The preferred width of the viewport when previewing a pattern, in pixels.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `block_types` | The block types which can use this pattern.<br>JSON data type: array <br>Context: `view`, `embed` |

## [List Pattern Directory Items](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/\#list-pattern-directory-items)

Query this endpoint to retrieve a collection of pattern directory items. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/\#definition)

`GET /wp/v2/pattern-directory/patterns`

### [Example Request](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/pattern-directory/patterns`

### [Arguments](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `100` |
| `search` | Limit results to those matching a string. |
| `category` | Limit results to those matching a category ID. |
| `keyword` | Limit results to those matching a keyword ID. |
| `slug` | Limit results to those matching a pattern (slug). |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br>Default: `date`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title`, `favorite_count` |

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Pattern Directory Items](https://github.com/WP-API/docs/edit/master/reference/pattern-directory-items.md)

Changelog

[See list of changes: Pattern Directory Items](https://github.com/WP-API/docs/commits/master/reference/pattern-directory-items.md)

[PreviousPagesPrevious: Pages](https://developer.wordpress.org/rest-api/reference/pages/)

[NextPluginsNext: Plugins](https://developer.wordpress.org/rest-api/reference/plugins/)

Notifications