---
url: https://developer.wordpress.org/rest-api/reference/wp_navigations
scraped_at: 2025-10-20T02:01:44.119Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_navigations/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Navigations


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Navigations

Search

# Navigations

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema)
- [List Navigations](https://developer.wordpress.org/rest-api/reference/wp_navigations/#list-navigations)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/#arguments)
- [Create a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/#create-a-navigation)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/#definition-2)
- [Retrieve a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/#retrieve-a-navigation)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/#arguments-3)
- [Update a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/#update-a-navigation)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/#example-request-2)
- [Delete a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/#delete-a-navigation)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_navigations/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#schema)

The schema defines all the fields that exist within a navigation record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `date` | The date the post was published, in the site's timezone.<br>JSON data type: string or null,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the post was published, as GMT.<br>JSON data type: string or null,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `guid` | The globally unique identifier for the post.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit` |
| `id` | Unique identifier for the post.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit`, `embed` |
| `link` | URL to the post.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit`, `embed` |
| `modified` | The date the post was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `modified_gmt` | The date the post was last modified, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `slug` | An alphanumeric identifier for the post unique to its type.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `status` | A named status for the post.<br>JSON data type: string <br>Context: `view`, `edit`, `embed`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `type` | Type of post.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `password` | A password to protect access to the content and excerpt.<br>JSON data type: string <br>Context: `edit` |
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `template` | The theme file to use to display the post.<br>JSON data type: string <br>Context: `view`, `edit` |

## [List Navigations](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#list-navigations)

Query this endpoint to retrieve a collection of navigations. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#definition)

`GET /wp/v2/navigation`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/navigation`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to posts published after a given ISO8601 compliant date. |
| `modified_after` | Limit response to posts modified after a given ISO8601 compliant date. |
| `before` | Limit response to posts published before a given ISO8601 compliant date. |
| `modified_before` | Limit response to posts modified before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br>Default: `date`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title` |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `publish` |

## [Create a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#create-a-navigation)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#arguments-2)

|     |     |
| --- | --- |
| `[date](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-content)` | The content for the post. |
| `[template](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#definition-2)

`POST /wp/v2/navigation`

## [Retrieve a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#retrieve-a-navigation)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#definition-example-request)

`GET /wp/v2/navigation/<id>`

Query this endpoint to retrieve a specific navigation record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `password` | The password for the post if it is password protected. |

## [Update a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#update-a-navigation)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-id)` | Unique identifier for the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-content)` | The content for the post. |
| `[template](https://developer.wordpress.org/rest-api/reference/wp_navigations/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#definition-3)

`POST /wp/v2/navigation/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#example-request-2)

``

## [Delete a Navigation](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#delete-a-navigation)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#definition-4)

`DELETE /wp/v2/navigation/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigations/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/navigation/<id>`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Navigations](https://github.com/WP-API/docs/edit/master/reference/wp_navigations.md)

Changelog

[See list of changes: Navigations](https://github.com/WP-API/docs/commits/master/reference/wp_navigations.md)

[PreviousNavigation RevisionsPrevious: Navigation Revisions](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/)

[NextNav\_MenusNext: Nav\_Menus](https://developer.wordpress.org/rest-api/reference/nav_menus/)

Notifications