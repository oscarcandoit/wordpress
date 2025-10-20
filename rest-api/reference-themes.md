---
url: https://developer.wordpress.org/rest-api/reference/themes
scraped_at: 2025-10-20T02:01:31.882Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/themes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Themes


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Themes

Search

# Themes

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/themes/#schema)
- [Retrieve a Theme](https://developer.wordpress.org/rest-api/reference/themes/#retrieve-a-theme)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/themes/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/themes/#arguments)
- [Retrieve a Theme](https://developer.wordpress.org/rest-api/reference/themes/#retrieve-a-theme-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/themes/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/themes/#arguments-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/themes/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/themes/\#schema)

The schema defines all the fields that exist within a theme record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `stylesheet` | The theme's stylesheet. This uniquely identifies the theme.<br>JSON data type: string <br>Read only<br>Context: `` |
| `template` | The theme's template. If this is a child theme, this refers to the parent theme, otherwise this is the same as the theme's stylesheet.<br>JSON data type: string <br>Read only<br>Context: `` |
| `author` | The theme author.<br>JSON data type: object <br>Read only<br>Context: `` |
| `author_uri` | The website of the theme author.<br>JSON data type: object <br>Read only<br>Context: `` |
| `description` | A description of the theme.<br>JSON data type: object <br>Read only<br>Context: `` |
| `is_block_theme` | Whether the theme is a block-based theme.<br>JSON data type: boolean <br>Read only<br>Context: `` |
| `name` | The name of the theme.<br>JSON data type: object <br>Read only<br>Context: `` |
| `requires_php` | The minimum PHP version required for the theme to work.<br>JSON data type: string <br>Read only<br>Context: `` |
| `requires_wp` | The minimum WordPress version required for the theme to work.<br>JSON data type: string <br>Read only<br>Context: `` |
| `screenshot` | The theme's screenshot URL.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `` |
| `tags` | Tags indicating styles and features of the theme.<br>JSON data type: object <br>Read only<br>Context: `` |
| `textdomain` | The theme's text domain.<br>JSON data type: string <br>Read only<br>Context: `` |
| `theme_supports` | Features supported by this theme.<br>JSON data type: object <br>Read only<br>Context: `` |
| `theme_uri` | The URI of the theme's webpage.<br>JSON data type: object <br>Read only<br>Context: `` |
| `version` | The theme's current version.<br>JSON data type: string <br>Read only<br>Context: `` |
| `status` | A named status for the theme.<br>JSON data type: string <br>Context: ``<br>One of: `inactive`, `active` |

## [Retrieve a Theme](https://developer.wordpress.org/rest-api/reference/themes/\#retrieve-a-theme)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/themes/\#definition-example-request)

`GET /wp/v2/themes`

Query this endpoint to retrieve a specific theme record.

`$ curl https://example.com/wp-json/wp/v2/themes`

### [Arguments](https://developer.wordpress.org/rest-api/reference/themes/\#arguments)

|     |     |
| --- | --- |
| `status` | Limit result set to themes assigned one or more statuses. |

## [Retrieve a Theme](https://developer.wordpress.org/rest-api/reference/themes/\#retrieve-a-theme-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/themes/\#definition-example-request-2)

`GET /wp/v2/themes/<stylesheet>?)`

Query this endpoint to retrieve a specific theme record.

`$ curl https://example.com/wp-json/wp/v2/themes/<stylesheet>?)`

### [Arguments](https://developer.wordpress.org/rest-api/reference/themes/\#arguments-2)

|     |     |
| --- | --- |
| `stylesheet` | The theme's stylesheet. This uniquely identifies the theme. |

First published

July 21, 2019

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Themes](https://github.com/WP-API/docs/edit/master/reference/themes.md)

Changelog

[See list of changes: Themes](https://github.com/WP-API/docs/commits/master/reference/themes.md)

[PreviousTemplate\_PartsPrevious: Template\_Parts](https://developer.wordpress.org/rest-api/reference/wp_template_parts/)

[NextTypesNext: Types](https://developer.wordpress.org/rest-api/reference/post-types/)

Notifications