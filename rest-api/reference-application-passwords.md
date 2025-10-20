---
url: https://developer.wordpress.org/rest-api/reference/application-passwords
scraped_at: 2025-10-20T02:03:30.459Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/application-passwords/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Application Passwords


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Application Passwords

Search

# Application Passwords

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/application-passwords/#schema)
- [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#retrieve-a-application-password)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/#arguments)
- [Create a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#create-a-application-password)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition)
- [Delete a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#delete-a-application-password)
  - [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-2)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#example-request)
- [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#retrieve-a-application-password-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/#arguments-3)
- [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#retrieve-a-application-password-3)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-example-request-3)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/#arguments-4)
- [Update a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#update-a-application-password)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#example-request-2)
- [Delete a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/#delete-a-application-password-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/application-passwords/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/application-passwords/\#schema)

The schema defines all the fields that exist within a application password record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `uuid` | The unique identifier for the application password.<br>JSON data type: string,<br>Format: uuid<br> <br>Read only<br>Context: `view`, `edit`, `embed` |
| `app_id` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace.<br>JSON data type: string,<br>Format: uuid<br> <br>Context: `view`, `edit`, `embed` |
| `name` | The name of the application password.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `password` | The generated password. Only available after adding an application.<br>JSON data type: string <br>Read only<br>Context: `edit` |
| `created` | The GMT date the application password was created.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `last_used` | The GMT date the application password was last used.<br>JSON data type: string or null,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Read only<br>Context: `view`, `edit` |
| `last_ip` | The IP address the application password was last used by.<br>JSON data type: string or null,<br>Format: ip<br> <br>Read only<br>Context: `view`, `edit` |

## [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#retrieve-a-application-password)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-example-request)

`GET /wp/v2/users/<user_id>)/application-passwords`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords`

### [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Create a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#create-a-application-password)

### [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/\#arguments-2)

|     |     |
| --- | --- |
| `[app\_id](https://developer.wordpress.org/rest-api/reference/application-passwords/#schema-app_id)` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace. |
| `[name](https://developer.wordpress.org/rest-api/reference/application-passwords/#schema-name)` | The name of the application password.<br>Required: 1 |

### [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition)

`POST /wp/v2/users/<user_id>)/application-passwords`

## [Delete a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#delete-a-application-password)

There are no arguments for this endpoint.

### [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-2)

`DELETE /wp/v2/users/<user_id>)/application-passwords`

### [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#example-request)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords`

## [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#retrieve-a-application-password-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-example-request-2)

`GET /wp/v2/users/<user_id>)/application-passwords/introspect`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/introspect`

### [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/\#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Retrieve a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#retrieve-a-application-password-3)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-example-request-3)

`GET /wp/v2/users/<user_id>)/application-passwords/<uuid>`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/\#arguments-4)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#update-a-application-password)

### [Arguments](https://developer.wordpress.org/rest-api/reference/application-passwords/\#arguments-5)

|     |     |
| --- | --- |
| `[app\_id](https://developer.wordpress.org/rest-api/reference/application-passwords/#schema-app_id)` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace. |
| `[name](https://developer.wordpress.org/rest-api/reference/application-passwords/#schema-name)` | The name of the application password. |

### [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-3)

`POST /wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#example-request-2)

``

## [Delete a Application Password](https://developer.wordpress.org/rest-api/reference/application-passwords/\#delete-a-application-password-2)

There are no arguments for this endpoint.

### [Definition](https://developer.wordpress.org/rest-api/reference/application-passwords/\#definition-4)

`DELETE /wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/application-passwords/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/<uuid>`

First published

December 5, 2020

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Application Passwords](https://github.com/WP-API/docs/edit/master/reference/application-passwords.md)

Changelog

[See list of changes: Application Passwords](https://github.com/WP-API/docs/commits/master/reference/application-passwords.md)

[PreviousReferencePrevious: Reference](https://developer.wordpress.org/rest-api/reference/)

[NextBlock Directory ItemsNext: Block Directory Items](https://developer.wordpress.org/rest-api/reference/block-directory-items/)

Notifications