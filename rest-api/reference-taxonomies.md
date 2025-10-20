---
url: https://developer.wordpress.org/rest-api/reference/taxonomies
scraped_at: 2025-10-20T03:54:53.305Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/taxonomies/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Taxonomies


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Taxonomies

Search

# Taxonomies

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/taxonomies/#schema)
- [Retrieve a Taxonomy](https://developer.wordpress.org/rest-api/reference/taxonomies/#retrieve-a-taxonomy)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/taxonomies/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/taxonomies/#arguments)
- [Retrieve a Taxonomy](https://developer.wordpress.org/rest-api/reference/taxonomies/#retrieve-a-taxonomy-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/taxonomies/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/taxonomies/#arguments-2)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/taxonomies/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/taxonomies/\#schema)

The schema defines all the fields that exist within a taxonomy record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `capabilities` | All capabilities used by the taxonomy.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `description` | A human-readable description of the taxonomy.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit` |
| `hierarchical` | Whether or not the taxonomy should have children.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit` |
| `labels` | Human-readable labels for the taxonomy for various contexts.<br>JSON data type: object <br>Read only<br>Context: `edit` |
| `name` | The title for the taxonomy.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the taxonomy.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `show_cloud` | Whether or not the term cloud should be displayed.<br>JSON data type: boolean <br>Read only<br>Context: `edit` |
| `types` | Types associated with the taxonomy.<br>JSON data type: array <br>Read only<br>Context: `view`, `edit` |
| `rest_base` | REST base route for the taxonomy.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `rest_namespace` | REST namespace route for the taxonomy.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `visibility` | The visibility settings for the taxonomy.<br>JSON data type: object <br>Read only<br>Context: `edit` |

## [Retrieve a Taxonomy](https://developer.wordpress.org/rest-api/reference/taxonomies/\#retrieve-a-taxonomy)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/taxonomies/\#definition-example-request)

`GET /wp/v2/taxonomies`

Query this endpoint to retrieve a specific taxonomy record.

`$ curl https://example.com/wp-json/wp/v2/taxonomies`

### [Arguments](https://developer.wordpress.org/rest-api/reference/taxonomies/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `type` | Limit results to taxonomies associated with a specific post type. |

## [Retrieve a Taxonomy](https://developer.wordpress.org/rest-api/reference/taxonomies/\#retrieve-a-taxonomy-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/taxonomies/\#definition-example-request-2)

`GET /wp/v2/taxonomies/<taxonomy>`

Query this endpoint to retrieve a specific taxonomy record.

`$ curl https://example.com/wp-json/wp/v2/taxonomies/<taxonomy>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/taxonomies/\#arguments-2)

|     |     |
| --- | --- |
| `taxonomy` | An alphanumeric identifier for the taxonomy. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Taxonomies](https://github.com/WP-API/docs/edit/master/reference/taxonomies.md)

Changelog

[See list of changes: Taxonomies](https://github.com/WP-API/docs/commits/master/reference/taxonomies.md)

[PreviousTagsPrevious: Tags](https://developer.wordpress.org/rest-api/reference/tags/)

[NextTemplate RevisionsNext: Template Revisions](https://developer.wordpress.org/rest-api/reference/wp_template-revisions/)

Notifications