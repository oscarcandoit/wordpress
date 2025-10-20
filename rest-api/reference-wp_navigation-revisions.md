---
url: https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions
scraped_at: 2025-10-20T02:02:57.267Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Navigation Revisions


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Navigation Revisions

Search

# Navigation Revisions

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema)
- [List Navigation Revisions](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#list-navigation-revisions)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments)
- [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#retrieve-a-navigation-revision)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments-2)
- [Delete a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#delete-a-navigation-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments-3)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#example-request-2)
- [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#retrieve-a-navigation-revision-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments-4)
- [Create a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#create-a-navigation-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition-3)
- [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#retrieve-a-navigation-revision-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#definition-example-request-3)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#arguments-6)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#schema)

The schema defines all the fields that exist within a navigation revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `guid` | The globally unique identifier for the post.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |

## [List Navigation Revisions](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#list-navigation-revisions)

Query this endpoint to retrieve a collection of navigation revisions. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition)

`GET /wp/v2/navigation/<parent>/revisions`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/revisions`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set. |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by object attribute.<br>Default: `date`<br>One of: `date`, `id`, `include`, `relevance`, `slug`, `include_slugs`, `title` |

## [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#retrieve-a-navigation-revision)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition-example-request)

`GET /wp/v2/navigation/<parent>/revisions/<id>`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/revisions/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments-2)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Delete a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#delete-a-navigation-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `force` | Required to be true, as revisions do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition-2)

`DELETE /wp/v2/navigation/<parent>/revisions/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/navigation/<parent>/revisions/<id>`

## [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#retrieve-a-navigation-revision-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition-example-request-2)

`GET /wp/v2/navigation/<id>/autosaves`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<id>/autosaves`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments-4)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Create a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#create-a-navigation-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments-5)

|     |     |
| --- | --- |
| `[parent](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-parent)` | The ID for the parent of the autosave. |
| `[date](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-content)` | The content for the post. |
| `[template](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition-3)

`POST /wp/v2/navigation/<id>/autosaves`

## [Retrieve a Navigation Revision](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#retrieve-a-navigation-revision-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#definition-example-request-3)

`GET /wp/v2/navigation/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/autosaves/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/\#arguments-6)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Navigation Revisions](https://github.com/WP-API/docs/edit/master/reference/wp_navigation-revisions.md)

Changelog

[See list of changes: Navigation Revisions](https://github.com/WP-API/docs/commits/master/reference/wp_navigation-revisions.md)

[PreviousMenu LocationsPrevious: Menu Locations](https://developer.wordpress.org/rest-api/reference/menu-locations/)

[NextNavigationsNext: Navigations](https://developer.wordpress.org/rest-api/reference/wp_navigations/)

Notifications