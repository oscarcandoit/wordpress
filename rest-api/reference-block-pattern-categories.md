---
url: https://developer.wordpress.org/rest-api/reference/block-pattern-categories
scraped_at: 2025-10-20T02:03:03.808Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block Pattern Categories


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Block Pattern Categories

Search

# Block Pattern Categories

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/#schema)
- [Retrieve a Block Pattern Category](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/#retrieve-a-block-pattern-category)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/#definition-example-request)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/\#schema)

The schema defines all the fields that exist within a block pattern category record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The category name.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `label` | The category label, in human readable format.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `description` | The category description, in human readable format.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |

## [Retrieve a Block Pattern Category](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/\#retrieve-a-block-pattern-category)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/\#definition-example-request)

`GET /wp/v2/block-patterns/categories`

Query this endpoint to retrieve a specific block pattern category record.

`$ curl https://example.com/wp-json/wp/v2/block-patterns/categories`

There are no arguments for this endpoint.

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Block Pattern Categories](https://github.com/WP-API/docs/edit/master/reference/block-pattern-categories.md)

Changelog

[See list of changes: Block Pattern Categories](https://github.com/WP-API/docs/commits/master/reference/block-pattern-categories.md)

[PreviousBlock Directory ItemsPrevious: Block Directory Items](https://developer.wordpress.org/rest-api/reference/block-directory-items/)

[NextBlock PatternsNext: Block Patterns](https://developer.wordpress.org/rest-api/reference/block-patterns/)

Notifications