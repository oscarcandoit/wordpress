---
url: https://developer.wordpress.org/rest-api/reference/media
scraped_at: 2025-10-20T02:02:13.860Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/media/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Media


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Media

Search

# Media

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/media/#schema)
- [List Media](https://developer.wordpress.org/rest-api/reference/media/#list-media)
  - [Definition](https://developer.wordpress.org/rest-api/reference/media/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/media/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/media/#arguments)
- [Create a Media Item](https://developer.wordpress.org/rest-api/reference/media/#create-a-media-item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/media/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/media/#definition-2)
- [Retrieve a Media Item](https://developer.wordpress.org/rest-api/reference/media/#retrieve-a-media-item)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/media/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/media/#arguments-3)
- [Update a Media Item](https://developer.wordpress.org/rest-api/reference/media/#update-a-media-item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/media/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/media/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/media/#example-request-2)
- [Delete a Media Item](https://developer.wordpress.org/rest-api/reference/media/#delete-a-media-item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/media/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/media/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/media/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/media/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/media/\#schema)

The schema defines all the fields that exist within a Media Item record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

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
| `permalink_template` | Permalink template for the post.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `generated_slug` | Slug automatically generated from the post title.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `title` | The title for the post.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `author` | The ID for the author of the post.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `comment_status` | Whether or not comments are open on the post.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `ping_status` | Whether or not the post can be pinged.<br>JSON data type: string <br>Context: `view`, `edit`<br>One of: `open`, `closed` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |
| `template` | The theme file to use to display the post.<br>JSON data type: string <br>Context: `view`, `edit` |
| `alt_text` | Alternative text to display when attachment is not displayed.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `caption` | The attachment caption.<br>JSON data type: object <br>Context: `view`, `edit`, `embed` |
| `description` | The attachment description.<br>JSON data type: object <br>Context: `view`, `edit` |
| `media_type` | Attachment type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed`<br>One of: `image`, `file` |
| `mime_type` | The attachment MIME type.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `media_details` | Details about the media file, specific to its type.<br>JSON data type: object <br>Read only<br>Context: `view`, `edit`, `embed` |
| `post` | The ID for the associated post of the attachment.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `source_url` | URL to the original attachment file.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `view`, `edit`, `embed` |
| `missing_image_sizes` | List of the missing image sizes of the attachment.<br>JSON data type: array <br>Read only<br>Context: `edit` |

## [List Media](https://developer.wordpress.org/rest-api/reference/media/\#list-media)

Query this endpoint to retrieve a collection of media. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/media/\#definition)

`GET /wp/v2/media`

### [Example Request](https://developer.wordpress.org/rest-api/reference/media/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/media`

### [Arguments](https://developer.wordpress.org/rest-api/reference/media/\#arguments)

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
| `parent` | Limit result set to items with particular parent IDs. |
| `parent_exclude` | Limit result set to all items except those of a particular parent ID. |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `inherit` |
| `media_type` | Limit result set to attachments of a particular media type.<br> One of: `image`, `video`, `text`, `application`, `audio` |
| `mime_type` | Limit result set to attachments of a particular MIME type. |

## [Create a Media Item](https://developer.wordpress.org/rest-api/reference/media/\#create-a-media-item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/media/\#arguments-2)

|     |     |
| --- | --- |
| `[date](https://developer.wordpress.org/rest-api/reference/media/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/media/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/media/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/media/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[title](https://developer.wordpress.org/rest-api/reference/media/#schema-title)` | The title for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/media/#schema-author)` | The ID for the author of the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/media/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/media/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[meta](https://developer.wordpress.org/rest-api/reference/media/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/media/#schema-template)` | The theme file to use to display the post. |
| `[alt\_text](https://developer.wordpress.org/rest-api/reference/media/#schema-alt_text)` | Alternative text to display when attachment is not displayed. |
| `[caption](https://developer.wordpress.org/rest-api/reference/media/#schema-caption)` | The attachment caption. |
| `[description](https://developer.wordpress.org/rest-api/reference/media/#schema-description)` | The attachment description. |
| `[post](https://developer.wordpress.org/rest-api/reference/media/#schema-post)` | The ID for the associated post of the attachment. |

### [Definition](https://developer.wordpress.org/rest-api/reference/media/\#definition-2)

`POST /wp/v2/media`

## [Retrieve a Media Item](https://developer.wordpress.org/rest-api/reference/media/\#retrieve-a-media-item)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/media/\#definition-example-request)

`GET /wp/v2/media/<id>`

Query this endpoint to retrieve a specific Media Item record.

`$ curl https://example.com/wp-json/wp/v2/media/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/media/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Media Item](https://developer.wordpress.org/rest-api/reference/media/\#update-a-media-item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/media/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/media/#schema-id)` | Unique identifier for the post. |
| `[date](https://developer.wordpress.org/rest-api/reference/media/#schema-date)` | The date the post was published, in the site's timezone. |
| `[date\_gmt](https://developer.wordpress.org/rest-api/reference/media/#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](https://developer.wordpress.org/rest-api/reference/media/#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](https://developer.wordpress.org/rest-api/reference/media/#schema-status)` | A named status for the post.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[title](https://developer.wordpress.org/rest-api/reference/media/#schema-title)` | The title for the post. |
| `[author](https://developer.wordpress.org/rest-api/reference/media/#schema-author)` | The ID for the author of the post. |
| `[comment\_status](https://developer.wordpress.org/rest-api/reference/media/#schema-comment_status)` | Whether or not comments are open on the post.<br> One of: `open`, `closed` |
| `[ping\_status](https://developer.wordpress.org/rest-api/reference/media/#schema-ping_status)` | Whether or not the post can be pinged.<br> One of: `open`, `closed` |
| `[meta](https://developer.wordpress.org/rest-api/reference/media/#schema-meta)` | Meta fields. |
| `[template](https://developer.wordpress.org/rest-api/reference/media/#schema-template)` | The theme file to use to display the post. |
| `[alt\_text](https://developer.wordpress.org/rest-api/reference/media/#schema-alt_text)` | Alternative text to display when attachment is not displayed. |
| `[caption](https://developer.wordpress.org/rest-api/reference/media/#schema-caption)` | The attachment caption. |
| `[description](https://developer.wordpress.org/rest-api/reference/media/#schema-description)` | The attachment description. |
| `[post](https://developer.wordpress.org/rest-api/reference/media/#schema-post)` | The ID for the associated post of the attachment. |

### [Definition](https://developer.wordpress.org/rest-api/reference/media/\#definition-3)

`POST /wp/v2/media/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/media/\#example-request-2)

``

## [Delete a Media Item](https://developer.wordpress.org/rest-api/reference/media/\#delete-a-media-item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/media/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/media/\#definition-4)

`DELETE /wp/v2/media/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/media/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/media/<id>`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Media](https://github.com/WP-API/docs/edit/master/reference/media.md)

Changelog

[See list of changes: Media](https://github.com/WP-API/docs/commits/master/reference/media.md)

[PreviousGlobal\_StylesPrevious: Global\_Styles](https://developer.wordpress.org/rest-api/reference/wp_global_styles/)

[NextMenu LocationsNext: Menu Locations](https://developer.wordpress.org/rest-api/reference/menu-locations/)

Notifications