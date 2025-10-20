---
url: https://developer.wordpress.org/rest-api/reference/post-types
scraped_at: 2025-10-20T02:04:16.638Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/post-types/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Types


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Types

Search

# Types

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/post-types/#schema)
- [Retrieve a Type](https://developer.wordpress.org/rest-api/reference/post-types/#retrieve-a-type)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-types/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/post-types/#arguments)
- [Retrieve a Type](https://developer.wordpress.org/rest-api/reference/post-types/#retrieve-a-type-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-types/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/post-types/#arguments-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/post-types/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/post-types/\#schema)

The schema defines all the fields that exist within a type record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `capabilities` | All capabilities used by the post type.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `description` | A human-readable description of the post type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit` |
| `hierarchical` | Whether or not the post type should have children.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit` |
| `viewable` | Whether or not the post type can be viewed.<br>JSON data type: boolean <br>Read only<br>Context: `edit` |
| `labels` | Human-readable labels for the post type for various contexts.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `name` | The title for the post type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the post type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `supports` | All features, supported by the post type.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `has_archive` | If the value is a string, the value will be used as the archive slug. If the value is false the post type has no archive.<br>JSON data type: string or boolean <br>Read only<br>Context: `view`, `edit` |
| `taxonomies` | Taxonomies associated with post type.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit` |
| `rest_base` | REST base route for the post type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `rest_namespace` | REST route's namespace for the post type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `visibility` | The visibility settings for the post type.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `icon` | The icon for the post type.<br>JSON data type: string or null <br>Read only<br>Context: `view`, `edit`, `embed` |

## [Retrieve a Type](https://developer.wordpress.org/rest-api/reference/post-types/\#retrieve-a-type)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-types/\#definition-example-request)

`GET /wp/v2/types`

Query this endpoint to retrieve a specific type record.

`$ curl https://example.com/wp-json/wp/v2/types`

### [Arguments](https://developer.wordpress.org/rest-api/reference/post-types/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Retrieve a Type](https://developer.wordpress.org/rest-api/reference/post-types/\#retrieve-a-type-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/post-types/\#definition-example-request-2)

`GET /wp/v2/types/<type>`

Query this endpoint to retrieve a specific type record.

`$ curl https://example.com/wp-json/wp/v2/types/<type>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/post-types/\#arguments-2)

|     |     |
| --- | --- |
| `type` | An alphanumeric identifier for the post type. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Types](https://github.com/WP-API/docs/edit/master/reference/post-types.md)

Changelog

[See list of changes: Types](https://github.com/WP-API/docs/commits/master/reference/post-types.md)

[PreviousThemesPrevious: Themes](https://developer.wordpress.org/rest-api/reference/themes/)

[NextUsersNext: Users](https://developer.wordpress.org/rest-api/reference/users/)

Notifications