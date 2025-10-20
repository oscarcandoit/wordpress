---
url: https://developer.wordpress.org/rest-api/reference/block-directory-items
scraped_at: 2025-10-20T02:01:47.998Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/block-directory-items/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block Directory Items


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Block Directory Items

Search

# Block Directory Items

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/block-directory-items/#schema)
- [List Block Directory Items](https://developer.wordpress.org/rest-api/reference/block-directory-items/#list-block-directory-items)
  - [Definition](https://developer.wordpress.org/rest-api/reference/block-directory-items/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/block-directory-items/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/block-directory-items/#arguments)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/block-directory-items/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/block-directory-items/\#schema)

The schema defines all the fields that exist within a block directory item record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The block name, in namespace/block-name format.<br>JSON data type: string <br>Context: `view` |
| `title` | The block title, in human readable format.<br>JSON data type: string <br>Context: `view` |
| `description` | A short description of the block, in human readable format.<br>JSON data type: string <br>Context: `view` |
| `id` | The block slug.<br>JSON data type: string <br>Context: `view` |
| `rating` | The star rating of the block.<br>JSON data type: number <br>Context: `view` |
| `rating_count` | The number of ratings.<br>JSON data type: integer <br>Context: `view` |
| `active_installs` | The number sites that have activated this block.<br>JSON data type: integer <br>Context: `view` |
| `author_block_rating` | The average rating of blocks published by the same author.<br>JSON data type: number <br>Context: `view` |
| `author_block_count` | The number of blocks published by the same author.<br>JSON data type: integer <br>Context: `view` |
| `author` | The WordPress.org username of the block author.<br>JSON data type: string <br>Context: `view` |
| `icon` | The block icon.<br>JSON data type: string,<br>Format: uri<br> <br>Context: `view` |
| `last_updated` | The date when the block was last updated.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view` |
| `humanized_updated` | The date when the block was last updated, in fuzzy human readable format.<br>JSON data type: string <br>Context: `view` |

## [List Block Directory Items](https://developer.wordpress.org/rest-api/reference/block-directory-items/\#list-block-directory-items)

Query this endpoint to retrieve a collection of block directory items. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/block-directory-items/\#definition)

`GET /wp/v2/block-directory/search`

### [Example Request](https://developer.wordpress.org/rest-api/reference/block-directory-items/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/block-directory/search`

### [Arguments](https://developer.wordpress.org/rest-api/reference/block-directory-items/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `term` | Limit result set to blocks matching the search term.<br>Required: 1 |

First published

August 9, 2020

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Block Directory Items](https://github.com/WP-API/docs/edit/master/reference/block-directory-items.md)

Changelog

[See list of changes: Block Directory Items](https://github.com/WP-API/docs/commits/master/reference/block-directory-items.md)

[PreviousApplication PasswordsPrevious: Application Passwords](https://developer.wordpress.org/rest-api/reference/application-passwords/)

[NextBlock Pattern CategoriesNext: Block Pattern Categories](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/)

Notifications