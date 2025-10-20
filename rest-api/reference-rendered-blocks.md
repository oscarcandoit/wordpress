---
url: https://developer.wordpress.org/rest-api/reference/rendered-blocks
scraped_at: 2025-10-20T02:01:51.914Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Rendered Blocks


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Rendered Blocks

Search

# Rendered Blocks

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#schema)
- [Create a Rendered Block](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#create-a-rendered-block)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#arguments)
  - [Definition](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#definition)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/rendered-blocks/\#schema)

The schema defines all the fields that exist within a Rendered Block record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `rendered` | The rendered block.<br>JSON data type: string <br>Context: `edit` |

## [Create a Rendered Block](https://developer.wordpress.org/rest-api/reference/rendered-blocks/\#create-a-rendered-block)

### [Arguments](https://developer.wordpress.org/rest-api/reference/rendered-blocks/\#arguments)

|     |     |
| --- | --- |
| `[name](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#schema-name)` | Unique registered name for the block. |
| `[context](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#schema-context)` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `edit` |
| `[attributes](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#schema-attributes)` | Attributes for the block. |
| `[post\_id](https://developer.wordpress.org/rest-api/reference/rendered-blocks/#schema-post_id)` | ID of the post context. |

### [Definition](https://developer.wordpress.org/rest-api/reference/rendered-blocks/\#definition)

`POST /wp/v2/block-renderer/<name>`

First published

July 21, 2019

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Rendered Blocks](https://github.com/WP-API/docs/edit/master/reference/rendered-blocks.md)

Changelog

[See list of changes: Rendered Blocks](https://github.com/WP-API/docs/commits/master/reference/rendered-blocks.md)

[PreviousPostsPrevious: Posts](https://developer.wordpress.org/rest-api/reference/posts/)

[NextSearch ResultsNext: Search Results](https://developer.wordpress.org/rest-api/reference/search-results/)

Notifications