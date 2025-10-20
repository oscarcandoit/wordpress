---
url: https://developer.wordpress.org/rest-api/reference/block-patterns
scraped_at: 2025-10-20T02:03:26.254Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/block-patterns/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block Patterns


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Block Patterns

Search

# Block Patterns

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/block-patterns/#schema)
- [Retrieve a Block Pattern](https://developer.wordpress.org/rest-api/reference/block-patterns/#retrieve-a-block-pattern)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-patterns/#definition-example-request)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/block-patterns/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/block-patterns/\#schema)

The schema defines all the fields that exist within a block pattern record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The pattern name.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `title` | The pattern title, in human readable format.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `content` | The pattern content.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `description` | The pattern detailed description.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `viewport_width` | The pattern viewport width for inserter preview.<br>JSON data type: number <br>Read only<br>Context: `view`, `edit`, `embed` |
| `inserter` | Determines whether the pattern is visible in inserter.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit`, `embed` |
| `categories` | The pattern category slugs.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit`, `embed` |
| `keywords` | The pattern keywords.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit`, `embed` |
| `block_types` | Block types that the pattern is intended to be used with.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit`, `embed` |
| `post_types` | An array of post types that the pattern is restricted to be used with.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit`, `embed` |
| `template_types` | An array of template types where the pattern fits.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit`, `embed` |
| `source` | Where the pattern comes from e.g. core<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed`<br>One of: `core`, `plugin`, `theme`, `pattern-directory/core`, `pattern-directory/theme`, `pattern-directory/featured` |

## [Retrieve a Block Pattern](https://developer.wordpress.org/rest-api/reference/block-patterns/\#retrieve-a-block-pattern)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-patterns/\#definition-example-request)

`GET /wp/v2/block-patterns/patterns`

Query this endpoint to retrieve a specific block pattern record.

`$ curl https://example.com/wp-json/wp/v2/block-patterns/patterns`

There are no arguments for this endpoint.

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Block Patterns](https://github.com/WP-API/docs/edit/master/reference/block-patterns.md)

Changelog

[See list of changes: Block Patterns](https://github.com/WP-API/docs/commits/master/reference/block-patterns.md)

[PreviousBlock Pattern CategoriesPrevious: Block Pattern Categories](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/)

[NextBlock RevisionsNext: Block Revisions](https://developer.wordpress.org/rest-api/reference/block-revisions/)

Notifications