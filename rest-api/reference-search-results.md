---
url: https://developer.wordpress.org/rest-api/reference/search-results
scraped_at: 2025-10-20T02:02:36.286Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/search-results/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Search Results


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Search Results

Search

# Search Results

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/search-results/#schema)
- [List Search Results](https://developer.wordpress.org/rest-api/reference/search-results/#list-search-results)
  - [Definition](https://developer.wordpress.org/rest-api/reference/search-results/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/search-results/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/search-results/#arguments)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/search-results/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/search-results/\#schema)

The schema defines all the fields that exist within a search result record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the object.<br>JSON data type: integer or string <br>Read only<br>Context: `view`, `embed` |
| `title` | The title for the object.<br>JSON data type: string <br>Read only<br>Context: `view`, `embed` |
| `url` | URL to the object.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `embed` |
| `type` | Object type.<br>JSON data type: string <br>Read only<br>Context: `view`, `embed`<br>One of: `post`, `term`, `post-format` |
| `subtype` | Object subtype.<br>JSON data type: string <br>Read only<br>Context: `view`, `embed`<br>One of: `post`, `page`, `category`, `post_tag` |

## [List Search Results](https://developer.wordpress.org/rest-api/reference/search-results/\#list-search-results)

Query this endpoint to retrieve a collection of search results. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/search-results/\#definition)

`GET /wp/v2/search`

### [Example Request](https://developer.wordpress.org/rest-api/reference/search-results/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/search`

### [Arguments](https://developer.wordpress.org/rest-api/reference/search-results/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `type` | Limit results to items of an object type.<br>Default: `post`<br>One of: `post`, `term`, `post-format` |
| `subtype` | Limit results to items of one or more object subtypes.<br>Default: `any` |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |

First published

July 21, 2019

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Search Results](https://github.com/WP-API/docs/edit/master/reference/search-results.md)

Changelog

[See list of changes: Search Results](https://github.com/WP-API/docs/commits/master/reference/search-results.md)

[PreviousRendered BlocksPrevious: Rendered Blocks](https://developer.wordpress.org/rest-api/reference/rendered-blocks/)

[NextSidebarsNext: Sidebars](https://developer.wordpress.org/rest-api/reference/sidebars/)

Notifications