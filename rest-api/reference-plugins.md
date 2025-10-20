---
url: https://developer.wordpress.org/rest-api/reference/plugins
scraped_at: 2025-10-20T02:02:33.731Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/plugins/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Plugins


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Plugins

Search

# Plugins

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/plugins/#schema)
- [Retrieve a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/#retrieve-a-plugin)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/plugins/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/#arguments)
- [Create a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/#create-a-plugin)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/plugins/#definition)
- [Retrieve a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/#retrieve-a-plugin-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/plugins/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/#arguments-3)
- [Update a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/#update-a-plugin)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/plugins/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/plugins/#example-request)
- [Delete a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/#delete-a-plugin)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/plugins/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/plugins/#example-request-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/plugins/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/plugins/\#schema)

The schema defines all the fields that exist within a plugin record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `plugin` | The plugin file.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `status` | The plugin activation status.<br>JSON data type: string <br>Context: `view`, `edit`, `embed`<br>One of: `inactive`, `active` |
| `name` | The plugin name.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `plugin_uri` | The plugin's website address.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit` |
| `author` | The plugin author.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit` |
| `author_uri` | Plugin author's website address.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit` |
| `description` | The plugin description.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit` |
| `version` | The plugin version number.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit` |
| `network_only` | Whether the plugin can only be activated network-wide.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit`, `embed` |
| `requires_wp` | Minimum required version of WordPress.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `requires_php` | Minimum required version of PHP.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `textdomain` | The plugin's text domain.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit` |

## [Retrieve a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/\#retrieve-a-plugin)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/plugins/\#definition-example-request)

`GET /wp/v2/plugins`

Query this endpoint to retrieve a specific plugin record.

`$ curl https://example.com/wp-json/wp/v2/plugins`

### [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `search` | Limit results to those matching a string. |
| `status` | Limits results to plugins with the given status. |

## [Create a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/\#create-a-plugin)

### [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/\#arguments-2)

|     |     |
| --- | --- |
| `[slug](https://developer.wordpress.org/rest-api/reference/plugins/#schema-slug)` | WordPress.org plugin directory slug.<br>Required: 1 |
| `[status](https://developer.wordpress.org/rest-api/reference/plugins/#schema-status)` | The plugin activation status.<br>Default: `inactive`<br>One of: `inactive`, `active` |

### [Definition](https://developer.wordpress.org/rest-api/reference/plugins/\#definition)

`POST /wp/v2/plugins`

## [Retrieve a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/\#retrieve-a-plugin-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/plugins/\#definition-example-request-2)

`GET /wp/v2/plugins/<plugin>?)`

Query this endpoint to retrieve a specific plugin record.

`$ curl https://example.com/wp-json/wp/v2/plugins/<plugin>?)`

### [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/\#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `plugin` |  |

## [Update a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/\#update-a-plugin)

### [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/\#arguments-4)

|     |     |
| --- | --- |
| `[context](https://developer.wordpress.org/rest-api/reference/plugins/#schema-context)` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `[plugin](https://developer.wordpress.org/rest-api/reference/plugins/#schema-plugin)` |  |
| `[status](https://developer.wordpress.org/rest-api/reference/plugins/#schema-status)` | The plugin activation status.<br> One of: `inactive`, `active` |

### [Definition](https://developer.wordpress.org/rest-api/reference/plugins/\#definition-2)

`POST /wp/v2/plugins/<plugin>?)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/plugins/\#example-request)

``

## [Delete a Plugin](https://developer.wordpress.org/rest-api/reference/plugins/\#delete-a-plugin)

### [Arguments](https://developer.wordpress.org/rest-api/reference/plugins/\#arguments-5)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `plugin` |  |

### [Definition](https://developer.wordpress.org/rest-api/reference/plugins/\#definition-3)

`DELETE /wp/v2/plugins/<plugin>?)`

### [Example Request](https://developer.wordpress.org/rest-api/reference/plugins/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/plugins/<plugin>?)`

First published

August 9, 2020

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Plugins](https://github.com/WP-API/docs/edit/master/reference/plugins.md)

Changelog

[See list of changes: Plugins](https://github.com/WP-API/docs/commits/master/reference/plugins.md)

[PreviousPattern Directory ItemsPrevious: Pattern Directory Items](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/)

[NextPost RevisionsNext: Post Revisions](https://developer.wordpress.org/rest-api/reference/post-revisions/)

Notifications