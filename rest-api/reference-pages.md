---
url: https://developer.wordpress.org/rest-api/reference/pages
scraped_at: 2025-10-20T02:02:09.577Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/pages/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Pages


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Pages

Search

# Pages

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/pages/#schema)
- [List Pages](https://developer.wordpress.org/rest-api/reference/pages/#list-pages)
  - [Definition](https://developer.wordpress.org/rest-api/reference/pages/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/pages/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pages/#arguments)
- [Create a Page](https://developer.wordpress.org/rest-api/reference/pages/#create-a-page)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pages/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/pages/#definition-2)
- [Retrieve a Page](https://developer.wordpress.org/rest-api/reference/pages/#retrieve-a-page)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/pages/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pages/#arguments-3)
- [Update a Page](https://developer.wordpress.org/rest-api/reference/pages/#update-a-page)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pages/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/pages/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/pages/#example-request-2)
- [Delete a Page](https://developer.wordpress.org/rest-api/reference/pages/#delete-a-page)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/pages/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/pages/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/pages/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/pages/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/pages/\#schema)

The schema defines all the fields that exist within a page record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

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
| `status` | A named status for the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `type` | Type of post.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `password` | A password to protect access to the content and excerpt.<br>JSON data type: string <br>Context: `edit` |
| `permalink_template` | Permalink template for the post.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `generated_slug` | Slug automatically generated from the post title.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `parent` | The ID for the parent of the post.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit` |
| `author` | The ID for the author of the post.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `excerpt` | The excerpt for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `featured_media` | The ID of the featured media for the post.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `comment_status` | Whether or not comments are open on the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `ping_status` | Whether or not the post can be pinged.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `menu_order` | The order of the post in relation to other posts.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |
| `template` | The theme file to use to display the post.<br>JSON data type: string <br>Context: `view`, `edit` |

## [List Pages](https://developer.wordpress.org/rest-api/reference/pages/\#list-pages)

Query this endpoint to retrieve a collection of pages. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/pages/\#definition)

`GET /wp/v2/pages`

### [Example Request](https://developer.wordpress.org/rest-api/reference/pages/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/pages`

### [Arguments](https://developer.wordpress.org/rest-api/reference/pages/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to posts published after a given ISO8601 compliant date. |
| `modified_after` | Limit response to posts modified after a given ISO8601 compliant date. |
| `author` | Limit result set to posts assigned to specific authors. |
| `author_exclude` | Ensure result set excludes posts assigned to specific authors. |
| `before` | Limit response to posts published before a given ISO8601 compliant date. |
| `modified_before` | Limit response to posts modified before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `menu_order` | Limit result set to posts with a specific menu\_order value. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br>Default: `date`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title`, `menu_order` |
| `parent` | Limit result set to items with particular parent IDs. |
| `parent_exclude` | Limit result set to all items except those of a particular parent ID. |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `publish` |

## [Create a Page](https://developer.wordpress.org/rest-api/reference/pages/\#create-a-page)

### [Arguments](https://developer.wordpress.org/rest-api/reference/pages/\#arguments-2)

|     |     |
| --- | --- |
| `[date](https://developer.wordpress.org/rest-api/reference/pages/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/pages/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/pages/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/pages/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/pages/#schema-password)` | A password to protect access to the content and excerpt. |
| `[parent](https://developer.wordpress.org/rest-api/reference/pages/#schema-parent)` | The ID for the parent of the post. |
| `[title](https://developer.wordpress.org/rest-api/reference/pages/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/pages/#schema-content)` | The content for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/pages/#schema-author)` | The ID for the author of the post. |
| `[excerpt](https://developer.wordpress.org/rest-api/reference/pages/#schema-excerpt)` | The excerpt for the post. |
| `[featured\_media](https://developer.wordpress.org/rest-api/reference/pages/#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/pages/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/pages/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/pages/#schema-menu_order)` | The order of the post in relation to other posts. |
| `[meta](https://developer.wordpress.org/rest-api/reference/pages/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/pages/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/pages/\#definition-2)

`POST /wp/v2/pages`

## [Retrieve a Page](https://developer.wordpress.org/rest-api/reference/pages/\#retrieve-a-page)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/pages/\#definition-example-request)

`GET /wp/v2/pages/<id>`

Query this endpoint to retrieve a specific page record.

`$ curl https://example.com/wp-json/wp/v2/pages/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/pages/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `password` | The password for the post if it is password protected. |

## [Update a Page](https://developer.wordpress.org/rest-api/reference/pages/\#update-a-page)

### [Arguments](https://developer.wordpress.org/rest-api/reference/pages/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/pages/#schema-id)` | Unique identifier for the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/pages/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/pages/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/pages/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/pages/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/pages/#schema-password)` | A password to protect access to the content and excerpt. |
| `[parent](https://developer.wordpress.org/rest-api/reference/pages/#schema-parent)` | The ID for the parent of the post. |
| `[title](https://developer.wordpress.org/rest-api/reference/pages/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/pages/#schema-content)` | The content for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/pages/#schema-author)` | The ID for the author of the post. |
| `[excerpt](https://developer.wordpress.org/rest-api/reference/pages/#schema-excerpt)` | The excerpt for the post. |
| `[featured\_media](https://developer.wordpress.org/rest-api/reference/pages/#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/pages/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/pages/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/pages/#schema-menu_order)` | The order of the post in relation to other posts. |
| `[meta](https://developer.wordpress.org/rest-api/reference/pages/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/pages/#schema-template)` | The theme file to use to display the post. |

### [Definition](https://developer.wordpress.org/rest-api/reference/pages/\#definition-3)

`POST /wp/v2/pages/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/pages/\#example-request-2)

``

## [Delete a Page](https://developer.wordpress.org/rest-api/reference/pages/\#delete-a-page)

### [Arguments](https://developer.wordpress.org/rest-api/reference/pages/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/pages/\#definition-4)

`DELETE /wp/v2/pages/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/pages/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/pages/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Pages](https://github.com/WP-API/docs/edit/master/reference/pages.md)

Changelog

[See list of changes: Pages](https://github.com/WP-API/docs/commits/master/reference/pages.md)

[PreviousPage RevisionsPrevious: Page Revisions](https://developer.wordpress.org/rest-api/reference/page-revisions/)

[NextPattern Directory ItemsNext: Pattern Directory Items](https://developer.wordpress.org/rest-api/reference/pattern-directory-items/)

Notifications