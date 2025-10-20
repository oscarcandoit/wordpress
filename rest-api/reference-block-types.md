---
url: https://developer.wordpress.org/rest-api/reference/block-types
scraped_at: 2025-10-20T02:01:56.146Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/block-types/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block Types


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Block Types

Search

# Block Types

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/block-types/#schema)
- [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/#retrieve-a-block-type)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/#arguments)
- [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/#retrieve-a-block-type-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/#arguments-2)
- [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/#retrieve-a-block-type-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/#definition-example-request-3)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/#arguments-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/block-types/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/block-types/\#schema)

The schema defines all the fields that exist within a block type record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `api_version` | Version of block API.<br>JSON data type: integer <br>Read only<br>Context: `embed`, `view`, `edit` |
| `title` | Title of block type.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `name` | Unique name identifying the block type.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `description` | Description of block type.<br>JSON data type: string <br>Read only<br>Context: `embed`, `view`, `edit` |
| `icon` | Icon of block type.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `attributes` | Block attributes.<br>JSON data type: object or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `provides_context` | Context provided by blocks of this type.<br>JSON data type: object <br>Read only<br>Context: `embed`, `view`, `edit` |
| `uses_context` | Context values inherited by blocks of this type.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `selectors` | Custom CSS selectors.<br>JSON data type: object <br>Read only<br>Context: `embed`, `view`, `edit` |
| `supports` | Block supports.<br>JSON data type: object <br>Read only<br>Context: `embed`, `view`, `edit` |
| `category` | Block category.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `is_dynamic` | Is the block dynamically rendered.<br>JSON data type: boolean <br>Read only<br>Context: `embed`, `view`, `edit` |
| `editor_script_handles` | Editor script handles.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `script_handles` | Public facing and editor script handles.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `view_script_handles` | Public facing script handles.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `editor_style_handles` | Editor style handles.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `style_handles` | Public facing and editor style handles.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `styles` | Block style variations.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `variations` | Block variations.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `textdomain` | Public text domain.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `parent` | Parent blocks.<br>JSON data type: array or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `ancestor` | Ancestor blocks.<br>JSON data type: array or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `keywords` | Block keywords.<br>JSON data type: array <br>Read only<br>Context: `embed`, `view`, `edit` |
| `example` | Block example.<br>JSON data type: object or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `editor_script` | Editor script handle. DEPRECATED: Use \`editor\_script\_handles\` instead.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `script` | Public facing and editor script handle. DEPRECATED: Use \`script\_handles\` instead.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `view_script` | Public facing script handle. DEPRECATED: Use \`view\_script\_handles\` instead.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `editor_style` | Editor style handle. DEPRECATED: Use \`editor\_style\_handles\` instead.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |
| `style` | Public facing and editor style handle. DEPRECATED: Use \`style\_handles\` instead.<br>JSON data type: string or null <br>Read only<br>Context: `embed`, `view`, `edit` |

## [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/\#retrieve-a-block-type)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/\#definition-example-request)

`GET /wp/v2/block-types`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types`

### [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `namespace` | Block namespace. |

## [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/\#retrieve-a-block-type-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/\#definition-example-request-2)

`GET /wp/v2/block-types/<namespace>`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types/<namespace>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/\#arguments-2)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `namespace` | Block namespace. |

## [Retrieve a Block Type](https://developer.wordpress.org/rest-api/reference/block-types/\#retrieve-a-block-type-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/block-types/\#definition-example-request-3)

`GET /wp/v2/block-types/<namespace>/<name>`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types/<namespace>/<name>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/block-types/\#arguments-3)

|     |     |
| --- | --- |
| `name` | Block name. |
| `namespace` | Block namespace. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

August 9, 2020

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Block Types](https://github.com/WP-API/docs/edit/master/reference/block-types.md)

Changelog

[See list of changes: Block Types](https://github.com/WP-API/docs/commits/master/reference/block-types.md)

[PreviousBlock RevisionsPrevious: Block Revisions](https://developer.wordpress.org/rest-api/reference/block-revisions/)

[NextCategoriesNext: Categories](https://developer.wordpress.org/rest-api/reference/categories/)

Notifications