---
url: https://developer.wordpress.org/rest-api/reference/nav_menus
scraped_at: 2025-10-20T02:02:22.871Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/nav_menus/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Nav\_Menus


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Nav\_Menus

Search

# Nav\_Menus

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema)
- [List Nav\_Menus](https://developer.wordpress.org/rest-api/reference/nav_menus/#list-nav_menus)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/#arguments)
- [Create a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/#create-a-nav_menu)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/#definition-2)
- [Retrieve a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/#retrieve-a-nav_menu)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/#arguments-3)
- [Update a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/#update-a-nav_menu)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/#example-request-2)
- [Delete a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/#delete-a-nav_menu)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/nav_menus/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/nav_menus/\#schema)

The schema defines all the fields that exist within a nav\_menu record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the term.<br>JSON data type: integer <br>Read only<br>Context: `view`, `embed`, `edit` |
| `description` | HTML description of the term.<br>JSON data type: string <br>Context: `view`, `edit` |
| `name` | HTML title for the term.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `slug` | An alphanumeric identifier for the term unique to its type.<br>JSON data type: string <br>Context: `view`, `embed`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |
| `locations` | The locations assigned to the menu.<br>JSON data type: array <br>Context: `view`, `edit` |
| `auto_add` | Whether to automatically add top level pages to this menu.<br>JSON data type: boolean <br>Context: `view`, `edit` |

## [List Nav\_Menus](https://developer.wordpress.org/rest-api/reference/nav_menus/\#list-nav_menus)

Query this endpoint to retrieve a collection of nav\_menus. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/\#definition)

`GET /wp/v2/menus`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/menus`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `asc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by term attribute.<br>Default: `name`<br>One of: `id`, `include`, `name`, `slug`, `include_slugs`, `term_group`, `description`, `count` |
| `hide_empty` | Whether to hide terms not assigned to any posts. |
| `post` | Limit result set to terms assigned to a specific post. |
| `slug` | Limit result set to terms with one or more specific slugs. |

## [Create a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/\#create-a-nav_menu)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/\#arguments-2)

|     |     |
| --- | --- |
| `[description](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-name)` | HTML title for the term.<br>Required: 1 |
| `[slug](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-meta)` | Meta fields. |
| `[locations](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-locations)` | The locations assigned to the menu. |
| `[auto\_add](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-auto_add)` | Whether to automatically add top level pages to this menu. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/\#definition-2)

`POST /wp/v2/menus`

## [Retrieve a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/\#retrieve-a-nav_menu)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/\#definition-example-request)

`GET /wp/v2/menus/<id>`

Query this endpoint to retrieve a specific nav\_menu record.

`$ curl https://example.com/wp-json/wp/v2/menus/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/\#update-a-nav_menu)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-id)` | Unique identifier for the term. |
| `[description](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-description)` | HTML description of the term. |
| `[name](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-name)` | HTML title for the term. |
| `[slug](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-meta)` | Meta fields. |
| `[locations](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-locations)` | The locations assigned to the menu. |
| `[auto\_add](https://developer.wordpress.org/rest-api/reference/nav_menus/#schema-auto_add)` | Whether to automatically add top level pages to this menu. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/\#definition-3)

`POST /wp/v2/menus/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/\#example-request-2)

``

## [Delete a Nav\_Menu](https://developer.wordpress.org/rest-api/reference/nav_menus/\#delete-a-nav_menu)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menus/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `force` | Required to be true, as terms do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menus/\#definition-4)

`DELETE /wp/v2/menus/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menus/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/menus/<id>`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Nav\_Menus](https://github.com/WP-API/docs/edit/master/reference/nav_menus.md)

Changelog

[See list of changes: Nav\_Menus](https://github.com/WP-API/docs/commits/master/reference/nav_menus.md)

[PreviousNavigationsPrevious: Navigations](https://developer.wordpress.org/rest-api/reference/wp_navigations/)

[NextNav\_Menu\_Item RevisionsNext: Nav\_Menu\_Item Revisions](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/)

Notifications