---
url: https://developer.wordpress.org/rest-api/reference/page-revisions
scraped_at: 2025-10-20T02:01:24.903Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/page-revisions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Page Revisions


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Page Revisions

Search

# Page Revisions

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema)
- [List Page Revisions](https://developer.wordpress.org/rest-api/reference/page-revisions/#list-page-revisions)
  - [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments)
- [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/#retrieve-a-page-revision)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments-2)
- [Delete a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/#delete-a-page-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments-3)
  - [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/#example-request-2)
- [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/#retrieve-a-page-revision-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments-4)
- [Create a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/#create-a-page-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition-3)
- [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/#retrieve-a-page-revision-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/#definition-example-request-3)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/#arguments-6)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/page-revisions/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/page-revisions/\#schema)

The schema defines all the fields that exist within a page revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

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
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit` |
| `excerpt` | The excerpt for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |

## [List Page Revisions](https://developer.wordpress.org/rest-api/reference/page-revisions/\#list-page-revisions)

Query this endpoint to retrieve a collection of page revisions. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition)

`GET /wp/v2/pages/<parent>/revisions`

### [Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/pages/<parent>/revisions`

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments)

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

## [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/\#retrieve-a-page-revision)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition-example-request)

`GET /wp/v2/pages/<parent>/revisions/<id>`

Query this endpoint to retrieve a specific page revision record.

`$ curl https://example.com/wp-json/wp/v2/pages/<parent>/revisions/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments-2)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Delete a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/\#delete-a-page-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `force` | Required to be true, as revisions do not support trashing. |

### [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition-2)

`DELETE /wp/v2/pages/<parent>/revisions/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/\#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/pages/<parent>/revisions/<id>`

## [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/\#retrieve-a-page-revision-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition-example-request-2)

`GET /wp/v2/pages/<id>/autosaves`

Query this endpoint to retrieve a specific page revision record.

`$ curl https://example.com/wp-json/wp/v2/pages/<id>/autosaves`

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments-4)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Create a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/\#create-a-page-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments-5)

|     |     |
| --- | --- |
| `[parent](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-parent)` | The ID for the parent of the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-content)` | The content for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-author)` | The ID for the author of the post. |
| `[excerpt](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-excerpt)` | The excerpt for the post. |
| `[featured\_media](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-menu_order)` | The order of the post in relation to other posts. |
| `[meta](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/page-revisions/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition-3)

`POST /wp/v2/pages/<id>/autosaves`

## [Retrieve a Page Revision](https://developer.wordpress.org/rest-api/reference/page-revisions/\#retrieve-a-page-revision-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/page-revisions/\#definition-example-request-3)

`GET /wp/v2/pages/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific page revision record.

`$ curl https://example.com/wp-json/wp/v2/pages/<parent>/autosaves/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/page-revisions/\#arguments-6)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

November 4, 2017

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Page Revisions](https://github.com/WP-API/docs/edit/master/reference/page-revisions.md)

Changelog

[See list of changes: Page Revisions](https://github.com/WP-API/docs/commits/master/reference/page-revisions.md)

[PreviousNav\_Menu\_ItemsPrevious: Nav\_Menu\_Items](https://developer.wordpress.org/rest-api/reference/nav_menu_items/)

[NextPagesNext: Pages](https://developer.wordpress.org/rest-api/reference/pages/)

Notifications