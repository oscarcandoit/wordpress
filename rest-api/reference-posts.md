---
url: https://developer.wordpress.org/rest-api/reference/posts
scraped_at: 2025-10-20T02:03:24.353Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/posts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Posts


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Posts

Search

# Posts

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/posts/#schema)
- [List Posts](https://developer.wordpress.org/rest-api/reference/posts/#list-posts)
  - [Definition](https://developer.wordpress.org/rest-api/reference/posts/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/posts/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/posts/#arguments)
- [Create a Post](https://developer.wordpress.org/rest-api/reference/posts/#create-a-post)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/posts/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/posts/#definition-2)
- [Retrieve a Post](https://developer.wordpress.org/rest-api/reference/posts/#retrieve-a-post)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/posts/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/posts/#arguments-3)
- [Update a Post](https://developer.wordpress.org/rest-api/reference/posts/#update-a-post)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/posts/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/posts/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/posts/#example-request-2)
- [Delete a Post](https://developer.wordpress.org/rest-api/reference/posts/#delete-a-post)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/posts/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/posts/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/posts/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/posts/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/posts/\#schema)

The schema defines all the fields that exist within a post record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

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
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br>JSON data type: object <br>Context: `view`, `edit` |
| `author` | The ID for the author of the post.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `excerpt` | The excerpt for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `featured_media` | The ID of the featured media for the post.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `comment_status` | Whether or not comments are open on the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `ping_status` | Whether or not the post can be pinged.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `format` | The format for the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |
| `sticky` | Whether or not the post should be treated as sticky.<br>JSON data type: boolean <br>Context: `view`, `edit` |
| `template` | The theme file to use to display the post.<br>JSON data type: string <br>Context: `view`, `edit` |
| `categories` | The terms assigned to the post in the category taxonomy.<br>JSON data type: array <br>Context: `view`, `edit` |
| `tags` | The terms assigned to the post in the post\_tag taxonomy.<br>JSON data type: array <br>Context: `view`, `edit` |

## [List Posts](https://developer.wordpress.org/rest-api/reference/posts/\#list-posts)

Query this endpoint to retrieve a collection of posts. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/posts/\#definition)

`GET /wp/v2/posts`

### [Example Request](https://developer.wordpress.org/rest-api/reference/posts/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/posts`

### [Arguments](https://developer.wordpress.org/rest-api/reference/posts/\#arguments)

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
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `desc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br>Default: `date`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title` |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `publish` |
| `tax_relation` | Limit result set based on relationship between multiple taxonomies.<br> One of: `AND`, `OR` |
| `categories` | Limit result set to items with specific terms assigned in the categories taxonomy. |
| `categories_exclude` | Limit result set to items except those with specific terms assigned in the categories taxonomy. |
| `tags` | Limit result set to items with specific terms assigned in the tags taxonomy. |
| `tags_exclude` | Limit result set to items except those with specific terms assigned in the tags taxonomy. |
| `sticky` | Limit result set to items that are sticky. |

## [Create a Post](https://developer.wordpress.org/rest-api/reference/posts/\#create-a-post)

### [Arguments](https://developer.wordpress.org/rest-api/reference/posts/\#arguments-2)

|     |     |
| --- | --- |
| `[date](https://developer.wordpress.org/rest-api/reference/posts/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/posts/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/posts/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/posts/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/posts/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/posts/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/posts/#schema-content)` | The content for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/posts/#schema-author)` | The ID for the author of the post. |
| `[excerpt](https://developer.wordpress.org/rest-api/reference/posts/#schema-excerpt)` | The excerpt for the post. |
| `[featured\_media](https://developer.wordpress.org/rest-api/reference/posts/#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/posts/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/posts/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[format](https://developer.wordpress.org/rest-api/reference/posts/#schema-format)` | The format for the post.<br> One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `[meta](https://developer.wordpress.org/rest-api/reference/posts/#schema-meta)` | Meta fields. |
| `[sticky](https://developer.wordpress.org/rest-api/reference/posts/#schema-sticky)` | Whether or not the post should be treated as sticky. |
| `[template](https://developer.wordpress.org/rest-api/reference/posts/#schema-template)` | The theme file to use to display the post. |
| `[categories](https://developer.wordpress.org/rest-api/reference/posts/#schema-categories)` | The terms assigned to the post in the category taxonomy. |
| `[tags](https://developer.wordpress.org/rest-api/reference/posts/#schema-tags)` | The terms assigned to the post in the post\_tag taxonomy. |

### [Definition](https://developer.wordpress.org/rest-api/reference/posts/\#definition-2)

`POST /wp/v2/posts`

## [Retrieve a Post](https://developer.wordpress.org/rest-api/reference/posts/\#retrieve-a-post)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/posts/\#definition-example-request)

`GET /wp/v2/posts/<id>`

Query this endpoint to retrieve a specific post record.

`$ curl https://example.com/wp-json/wp/v2/posts/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/posts/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `password` | The password for the post if it is password protected. |

## [Update a Post](https://developer.wordpress.org/rest-api/reference/posts/\#update-a-post)

### [Arguments](https://developer.wordpress.org/rest-api/reference/posts/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/posts/#schema-id)` | Unique identifier for the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/posts/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/posts/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/posts/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/posts/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](https://developer.wordpress.org/rest-api/reference/posts/#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](https://developer.wordpress.org/rest-api/reference/posts/#schema-title)` | The title for the post. |
| `[content](https://developer.wordpress.org/rest-api/reference/posts/#schema-content)` | The content for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/posts/#schema-author)` | The ID for the author of the post. |
| `[excerpt](https://developer.wordpress.org/rest-api/reference/posts/#schema-excerpt)` | The excerpt for the post. |
| `[featured\_media](https://developer.wordpress.org/rest-api/reference/posts/#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/posts/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/posts/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[format](https://developer.wordpress.org/rest-api/reference/posts/#schema-format)` | The format for the post.<br> One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `[meta](https://developer.wordpress.org/rest-api/reference/posts/#schema-meta)` | Meta fields. |
| `[sticky](https://developer.wordpress.org/rest-api/reference/posts/#schema-sticky)` | Whether or not the post should be treated as sticky. |
| `[template](https://developer.wordpress.org/rest-api/reference/posts/#schema-template)` | The theme file to use to display the post. |
| `[categories](https://developer.wordpress.org/rest-api/reference/posts/#schema-categories)` | The terms assigned to the post in the category taxonomy. |
| `[tags](https://developer.wordpress.org/rest-api/reference/posts/#schema-tags)` | The terms assigned to the post in the post\_tag taxonomy. |

### [Definition](https://developer.wordpress.org/rest-api/reference/posts/\#definition-3)

`POST /wp/v2/posts/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/posts/\#example-request-2)

`$ curl -X POST https://example.com/wp-json/wp/v2/posts/<id> -d '{"title":"My New Title"}'
`

## [Delete a Post](https://developer.wordpress.org/rest-api/reference/posts/\#delete-a-post)

### [Arguments](https://developer.wordpress.org/rest-api/reference/posts/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/posts/\#definition-4)

`DELETE /wp/v2/posts/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/posts/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/posts/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Posts](https://github.com/WP-API/docs/edit/master/reference/posts.md)

Changelog

[See list of changes: Posts](https://github.com/WP-API/docs/commits/master/reference/posts.md)

[PreviousPost RevisionsPrevious: Post Revisions](https://developer.wordpress.org/rest-api/reference/post-revisions/)

[NextRendered BlocksNext: Rendered Blocks](https://developer.wordpress.org/rest-api/reference/rendered-blocks/)

Notifications