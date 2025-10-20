---
url: https://developer.wordpress.org/rest-api/reference/users
scraped_at: 2025-10-20T02:02:45.122Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/users/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Users


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Users

Search

# Users

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/users/#schema)
- [List Users](https://developer.wordpress.org/rest-api/reference/users/#list-users)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/users/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments)
- [Create a User](https://developer.wordpress.org/rest-api/reference/users/#create-a-user)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition-2)
- [Retrieve a User](https://developer.wordpress.org/rest-api/reference/users/#retrieve-a-user)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/users/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-3)
- [Update a User](https://developer.wordpress.org/rest-api/reference/users/#update-a-user)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/users/#example-request-2)
- [Delete a User](https://developer.wordpress.org/rest-api/reference/users/#delete-a-user)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/users/#example-request-3)
- [Retrieve a User](https://developer.wordpress.org/rest-api/reference/users/#retrieve-a-user-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/users/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-6)
- [Update a User](https://developer.wordpress.org/rest-api/reference/users/#update-a-user-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-7)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition-5)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/users/#example-request-4)
- [Delete a User](https://developer.wordpress.org/rest-api/reference/users/#delete-a-user-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/users/#arguments-8)
  - [Definition](https://developer.wordpress.org/rest-api/reference/users/#definition-6)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/users/#example-request-5)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/users/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/users/\#schema)

The schema defines all the fields that exist within a user record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the user.<br>JSON data type: integer <br>Read only<br>Context: `embed`, `view`, `edit` |
| `username` | Login name for the user.<br>JSON data type: string <br>Context: `edit` |
| `name` | Display name for the user.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `first_name` | First name for the user.<br>JSON data type: string <br>Context: `edit` |
| `last_name` | Last name for the user.<br>JSON data type: string <br>Context: `edit` |
| `email` | The email address for the user.<br>JSON data type: string,<br>Format: email<br> <br>Context: `edit` |
| `url` | URL of the user.<br>JSON data type: string,<br>Format: uri<br> <br>Context: `embed`, `view`, `edit` |
| `description` | Description of the user.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `link` | Author URL of the user.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `embed`, `view`, `edit` |
| `locale` | Locale for the user.<br>JSON data type: string <br>Context: `edit`<br>One of: ``, `en_US` |
| `nickname` | The nickname for the user.<br>JSON data type: string <br>Context: `edit` |
| `slug` | An alphanumeric identifier for the user.<br>JSON data type: string <br>Context: `embed`, `view`, `edit` |
| `registered_date` | Registration date for the user.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `edit` |
| `roles` | Roles assigned to the user.<br>JSON data type: array <br>Context: `edit` |
| `password` | Password for the user (never included).<br>JSON data type: string <br>Context: `` |
| `capabilities` | All capabilities assigned to the user.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `extra_capabilities` | Any extra capabilities assigned to the user.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `avatar_urls` | Avatar URLs for the user.<br>JSON data type: object <br>Read only<br>Context: `embed`, `view`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |

## [List Users](https://developer.wordpress.org/rest-api/reference/users/\#list-users)

Query this endpoint to retrieve a collection of users. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition)

`GET /wp/v2/users`

### [Example Request](https://developer.wordpress.org/rest-api/reference/users/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/users`

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments)

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
| `orderby` | Sort collection by user attribute.<br>Default: `name`<br>One of: `id`, `include`, `name`, `registered_date`, `slug`, `include_slugs`, `email`, `url` |
| `slug` | Limit result set to users with one or more specific slugs. |
| `roles` | Limit result set to users matching at least one specific role provided. Accepts csv list or single role. |
| `capabilities` | Limit result set to users matching at least one specific capability provided. Accepts csv list or single capability. |
| `who` | Limit result set to users who are considered authors.<br> One of: `authors` |
| `has_published_posts` | Limit result set to users who have published posts. |

## [Create a User](https://developer.wordpress.org/rest-api/reference/users/\#create-a-user)

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-2)

|     |     |
| --- | --- |
| `[username](https://developer.wordpress.org/rest-api/reference/users/#schema-username)` | Login name for the user.<br>Required: 1 |
| `[name](https://developer.wordpress.org/rest-api/reference/users/#schema-name)` | Display name for the user. |
| `[first\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-first_name)` | First name for the user. |
| `[last\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-last_name)` | Last name for the user. |
| `[email](https://developer.wordpress.org/rest-api/reference/users/#schema-email)` | The email address for the user.<br>Required: 1 |
| `[url](https://developer.wordpress.org/rest-api/reference/users/#schema-url)` | URL of the user. |
| `[description](https://developer.wordpress.org/rest-api/reference/users/#schema-description)` | Description of the user. |
| `[locale](https://developer.wordpress.org/rest-api/reference/users/#schema-locale)` | Locale for the user.<br> One of: ``, `en_US` |
| `[nickname](https://developer.wordpress.org/rest-api/reference/users/#schema-nickname)` | The nickname for the user. |
| `[slug](https://developer.wordpress.org/rest-api/reference/users/#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](https://developer.wordpress.org/rest-api/reference/users/#schema-roles)` | Roles assigned to the user. |
| `[password](https://developer.wordpress.org/rest-api/reference/users/#schema-password)` | Password for the user (never included).<br>Required: 1 |
| `[meta](https://developer.wordpress.org/rest-api/reference/users/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition-2)

`POST /wp/v2/users`

## [Retrieve a User](https://developer.wordpress.org/rest-api/reference/users/\#retrieve-a-user)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/users/\#definition-example-request)

`GET /wp/v2/users/<id>`

Query this endpoint to retrieve a specific user record.

`$ curl https://example.com/wp-json/wp/v2/users/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the user. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a User](https://developer.wordpress.org/rest-api/reference/users/\#update-a-user)

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/users/#schema-id)` | Unique identifier for the user. |
| `[username](https://developer.wordpress.org/rest-api/reference/users/#schema-username)` | Login name for the user. |
| `[name](https://developer.wordpress.org/rest-api/reference/users/#schema-name)` | Display name for the user. |
| `[first\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-first_name)` | First name for the user. |
| `[last\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-last_name)` | Last name for the user. |
| `[email](https://developer.wordpress.org/rest-api/reference/users/#schema-email)` | The email address for the user. |
| `[url](https://developer.wordpress.org/rest-api/reference/users/#schema-url)` | URL of the user. |
| `[description](https://developer.wordpress.org/rest-api/reference/users/#schema-description)` | Description of the user. |
| `[locale](https://developer.wordpress.org/rest-api/reference/users/#schema-locale)` | Locale for the user.<br> One of: ``, `en_US` |
| `[nickname](https://developer.wordpress.org/rest-api/reference/users/#schema-nickname)` | The nickname for the user. |
| `[slug](https://developer.wordpress.org/rest-api/reference/users/#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](https://developer.wordpress.org/rest-api/reference/users/#schema-roles)` | Roles assigned to the user. |
| `[password](https://developer.wordpress.org/rest-api/reference/users/#schema-password)` | Password for the user (never included). |
| `[meta](https://developer.wordpress.org/rest-api/reference/users/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition-3)

`POST /wp/v2/users/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/users/\#example-request-2)

``

## [Delete a User](https://developer.wordpress.org/rest-api/reference/users/\#delete-a-user)

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the user. |
| `force` | Required to be true, as users do not support trashing. |
| `reassign` | Reassign the deleted user's posts and links to this user ID.<br>Required: 1 |

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition-4)

`DELETE /wp/v2/users/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/users/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<id>`

## [Retrieve a User](https://developer.wordpress.org/rest-api/reference/users/\#retrieve-a-user-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/users/\#definition-example-request-2)

`GET /wp/v2/users/me`

Query this endpoint to retrieve a specific user record.

`$ curl https://example.com/wp-json/wp/v2/users/me`

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-6)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a User](https://developer.wordpress.org/rest-api/reference/users/\#update-a-user-2)

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-7)

|     |     |
| --- | --- |
| `[username](https://developer.wordpress.org/rest-api/reference/users/#schema-username)` | Login name for the user. |
| `[name](https://developer.wordpress.org/rest-api/reference/users/#schema-name)` | Display name for the user. |
| `[first\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-first_name)` | First name for the user. |
| `[last\_name](https://developer.wordpress.org/rest-api/reference/users/#schema-last_name)` | Last name for the user. |
| `[email](https://developer.wordpress.org/rest-api/reference/users/#schema-email)` | The email address for the user. |
| `[url](https://developer.wordpress.org/rest-api/reference/users/#schema-url)` | URL of the user. |
| `[description](https://developer.wordpress.org/rest-api/reference/users/#schema-description)` | Description of the user. |
| `[locale](https://developer.wordpress.org/rest-api/reference/users/#schema-locale)` | Locale for the user.<br> One of: ``, `en_US` |
| `[nickname](https://developer.wordpress.org/rest-api/reference/users/#schema-nickname)` | The nickname for the user. |
| `[slug](https://developer.wordpress.org/rest-api/reference/users/#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](https://developer.wordpress.org/rest-api/reference/users/#schema-roles)` | Roles assigned to the user. |
| `[password](https://developer.wordpress.org/rest-api/reference/users/#schema-password)` | Password for the user (never included). |
| `[meta](https://developer.wordpress.org/rest-api/reference/users/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition-5)

`POST /wp/v2/users/me`

### [Example Request](https://developer.wordpress.org/rest-api/reference/users/\#example-request-4)

``

## [Delete a User](https://developer.wordpress.org/rest-api/reference/users/\#delete-a-user-2)

### [Arguments](https://developer.wordpress.org/rest-api/reference/users/\#arguments-8)

|     |     |
| --- | --- |
| `force` | Required to be true, as users do not support trashing. |
| `reassign` | Reassign the deleted user's posts and links to this user ID.<br>Required: 1 |

### [Definition](https://developer.wordpress.org/rest-api/reference/users/\#definition-6)

`DELETE /wp/v2/users/me`

### [Example Request](https://developer.wordpress.org/rest-api/reference/users/\#example-request-5)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/me`

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Users](https://github.com/WP-API/docs/edit/master/reference/users.md)

Changelog

[See list of changes: Users](https://github.com/WP-API/docs/commits/master/reference/users.md)

[PreviousTypesPrevious: Types](https://developer.wordpress.org/rest-api/reference/post-types/)

[NextWidget TypesNext: Widget Types](https://developer.wordpress.org/rest-api/reference/widget-types/)

Notifications