---
url: https://developer.wordpress.org/rest-api/reference/comments
scraped_at: 2025-10-20T02:02:47.857Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/comments/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Comments


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Comments

Search

# Comments

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/comments/#schema)
- [List Comments](https://developer.wordpress.org/rest-api/reference/comments/#list-comments)
  - [Definition](https://developer.wordpress.org/rest-api/reference/comments/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/comments/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/comments/#arguments)
- [Create a Comment](https://developer.wordpress.org/rest-api/reference/comments/#create-a-comment)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/comments/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/comments/#definition-2)
- [Retrieve a Comment](https://developer.wordpress.org/rest-api/reference/comments/#retrieve-a-comment)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/comments/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/comments/#arguments-3)
- [Update a Comment](https://developer.wordpress.org/rest-api/reference/comments/#update-a-comment)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/comments/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/comments/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/comments/#example-request-2)
- [Delete a Comment](https://developer.wordpress.org/rest-api/reference/comments/#delete-a-comment)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/comments/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/comments/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/comments/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/comments/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/comments/\#schema)

The schema defines all the fields that exist within a comment record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit`, `embed` |
| `author` | The ID of the user object, if author was a user.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `author_email` | Email address for the comment author.<br>JSON data type: string,<br>Format: email<br> <br>Context: `edit` |
| `author_ip` | IP address for the comment author.<br>JSON data type: string,<br>Format: ip<br> <br>Context: `edit` |
| `author_name` | Display name for the comment author.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `author_url` | URL for the comment author.<br>JSON data type: string,<br>Format: uri<br> <br>Context: `view`, `edit`, `embed` |
| `author_user_agent` | User agent for the comment author.<br>JSON data type: string <br>Context: `edit` |
| `content` | The content for the comment.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `date` | The date the comment was published, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the comment was published, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `link` | URL to the comment.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit`, `embed` |
| `parent` | The ID for the parent of the comment.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `post` | The ID of the associated post object.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `status` | State of the comment.<br>JSON data type: string <br>Context: `view`, `edit` |
| `type` | Type of the comment.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `author_avatar_urls` | Avatar URLs for the comment author.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit`, `embed` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |

## [List Comments](https://developer.wordpress.org/rest-api/reference/comments/\#list-comments)

Query this endpoint to retrieve a collection of comments. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/comments/\#definition)

`GET /wp/v2/comments`

### [Example Request](https://developer.wordpress.org/rest-api/reference/comments/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/comments`

### [Arguments](https://developer.wordpress.org/rest-api/reference/comments/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to comments published after a given ISO8601 compliant date. |
| `author` | Limit result set to comments assigned to specific user IDs. Requires authorization. |
| `author_exclude` | Ensure result set excludes comments assigned to specific user IDs. Requires authorization. |
| `author_email` | Limit result set to that from a specific author email. Requires authorization. |
| `before` | Limit response to comments published before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by comment attribute.<br>Default: `date_gmt`<br>One of: `date`, `date_gmt`, `id`, `include`, `post`, `parent`, `type` |
| `parent` | Limit result set to comments of specific parent IDs. |
| `parent_exclude` | Ensure result set excludes specific parent IDs. |
| `post` | Limit result set to comments assigned to specific post IDs. |
| `status` | Limit result set to comments assigned a specific status. Requires authorization.<br>Default: `approve` |
| `type` | Limit result set to comments assigned a specific type. Requires authorization.<br>Default: `comment` |
| `password` | The password for the post if it is password protected. |

## [Create a Comment](https://developer.wordpress.org/rest-api/reference/comments/\#create-a-comment)

### [Arguments](https://developer.wordpress.org/rest-api/reference/comments/\#arguments-2)

|     |     |
| --- | --- |
| `[author](https://developer.wordpress.org/rest-api/reference/comments/#schema-author)` | The ID of the user object, if author was a user. |
| `[author\_email](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_email)` | Email address for the comment author. |
| `[author\_ip](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_ip)` | IP address for the comment author. |
| `[author\_name](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_name)` | Display name for the comment author. |
| `[author\_url](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_url)` | URL for the comment author. |
| `[author\_user\_agent](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_user_agent)` | User agent for the comment author. |
| `[content](https://developer.wordpress.org/rest-api/reference/comments/#schema-content)` | The content for the comment. |
| `[date](https://developer.wordpress.org/rest-api/reference/comments/#schema-date)` | The date the comment was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/comments/#schema-date_gmt)` | The date the comment was published, as GMT. |
| `[parent](https://developer.wordpress.org/rest-api/reference/comments/#schema-parent)` | The ID for the parent of the comment. |
| `[post](https://developer.wordpress.org/rest-api/reference/comments/#schema-post)` | The ID of the associated post object. |
| `[status](https://developer.wordpress.org/rest-api/reference/comments/#schema-status)` | State of the comment. |
| `[meta](https://developer.wordpress.org/rest-api/reference/comments/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/comments/\#definition-2)

`POST /wp/v2/comments`

## [Retrieve a Comment](https://developer.wordpress.org/rest-api/reference/comments/\#retrieve-a-comment)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/comments/\#definition-example-request)

`GET /wp/v2/comments/<id>`

Query this endpoint to retrieve a specific comment record.

`$ curl https://example.com/wp-json/wp/v2/comments/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/comments/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `password` | The password for the parent post of the comment (if the post is password protected). |

## [Update a Comment](https://developer.wordpress.org/rest-api/reference/comments/\#update-a-comment)

### [Arguments](https://developer.wordpress.org/rest-api/reference/comments/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/comments/#schema-id)` | Unique identifier for the comment. |
| `[author](https://developer.wordpress.org/rest-api/reference/comments/#schema-author)` | The ID of the user object, if author was a user. |
| `[author\_email](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_email)` | Email address for the comment author. |
| `[author\_ip](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_ip)` | IP address for the comment author. |
| `[author\_name](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_name)` | Display name for the comment author. |
| `[author\_url](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_url)` | URL for the comment author. |
| `[author\_user\_agent](https://developer.wordpress.org/rest-api/reference/comments/#schema-author_user_agent)` | User agent for the comment author. |
| `[content](https://developer.wordpress.org/rest-api/reference/comments/#schema-content)` | The content for the comment. |
| `[date](https://developer.wordpress.org/rest-api/reference/comments/#schema-date)` | The date the comment was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/comments/#schema-date_gmt)` | The date the comment was published, as GMT. |
| `[parent](https://developer.wordpress.org/rest-api/reference/comments/#schema-parent)` | The ID for the parent of the comment. |
| `[post](https://developer.wordpress.org/rest-api/reference/comments/#schema-post)` | The ID of the associated post object. |
| `[status](https://developer.wordpress.org/rest-api/reference/comments/#schema-status)` | State of the comment. |
| `[meta](https://developer.wordpress.org/rest-api/reference/comments/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/comments/\#definition-3)

`POST /wp/v2/comments/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/comments/\#example-request-2)

``

## [Delete a Comment](https://developer.wordpress.org/rest-api/reference/comments/\#delete-a-comment)

### [Arguments](https://developer.wordpress.org/rest-api/reference/comments/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment. |
| `force` | Whether to bypass Trash and force deletion. |
| `password` | The password for the parent post of the comment (if the post is password protected). |

### [Definition](https://developer.wordpress.org/rest-api/reference/comments/\#definition-4)

`DELETE /wp/v2/comments/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/comments/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/comments/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Comments](https://github.com/WP-API/docs/edit/master/reference/comments.md)

Changelog

[See list of changes: Comments](https://github.com/WP-API/docs/commits/master/reference/comments.md)

[PreviousCategoriesPrevious: Categories](https://developer.wordpress.org/rest-api/reference/categories/)

[NextEditor BlocksNext: Editor Blocks](https://developer.wordpress.org/rest-api/reference/blocks/)

Notifications