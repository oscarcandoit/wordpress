---
url: https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions
scraped_at: 2025-10-20T02:02:20.222Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Nav\_Menu\_Item Revisions


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Nav\_Menu\_Item Revisions

Search

# Nav\_Menu\_Item Revisions

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema)
- [Retrieve a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#retrieve-a-nav_menu_item-revision)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#arguments)
- [Create a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#create-a-nav_menu_item-revision)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#definition)
- [Retrieve a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#retrieve-a-nav_menu_item-revision-2)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#definition-example-request-2)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#arguments-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#schema)

The schema defines all the fields that exist within a nav\_menu\_item revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `guid` | GUID for the revision, as it exists in the database.<br>JSON data type: string <br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br>JSON data type: string,<br>Format: datetime ( [details](https://core.trac.wordpress.org/ticket/41032))<br> <br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `title` | The title for the object.<br>JSON data type: string or object <br>Context: `view`, `edit`, `embed` |
| `preview_link` | Preview link for the post.<br>JSON data type: string,<br>Format: uri<br> <br>Read only<br>Context: `edit` |

## [Retrieve a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#retrieve-a-nav_menu_item-revision)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#definition-example-request)

`GET /wp/v2/menu-items/<id>/autosaves`

Query this endpoint to retrieve a specific nav\_menu\_item revision record.

`$ curl https://example.com/wp-json/wp/v2/menu-items/<id>/autosaves`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#arguments)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Create a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#create-a-nav_menu_item-revision)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#arguments-2)

|     |     |
| --- | --- |
| `[parent](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-parent)` | The ID for the parent of the object. |
| `[title](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-title)` | The title for the object. |
| `[type](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-type)` | The family of objects originally represented, such as "post\_type" or "taxonomy".<br> One of: `taxonomy`, `post_type`, `post_type_archive`, `custom` |
| `[status](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-status)` | A named status for the object.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[attr\_title](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-attr_title)` | Text for the title attribute of the link element for this menu item. |
| `[classes](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-classes)` | Class names for the link element of this menu item. |
| `[description](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-description)` | The description of this menu item. |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-menu_order)` | The DB ID of the nav\_menu\_item that is this item's menu parent, if any, otherwise 0. |
| `[object](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-object)` | The type of object originally represented, such as "category", "post", or "attachment". |
| `[object\_id](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-object_id)` | The database ID of the original object this menu item represents, for example the ID for posts or the term\_id for categories. |
| `[target](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-target)` | The target attribute of the link element for this menu item.<br> One of: `_blank`, `` |
| `[url](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-url)` | The URL to which this menu item points. |
| `[xfn](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-xfn)` | The XFN relationship expressed in the link of this menu item. |
| `[menus](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-menus)` | The terms assigned to the object in the nav\_menu taxonomy. |
| `[meta](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#definition)

`POST /wp/v2/menu-items/<id>/autosaves`

## [Retrieve a Nav\_Menu\_Item Revision](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#retrieve-a-nav_menu_item-revision-2)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#definition-example-request-2)

`GET /wp/v2/menu-items/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific nav\_menu\_item revision record.

`$ curl https://example.com/wp-json/wp/v2/menu-items/<parent>/autosaves/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/\#arguments-3)

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

[Improve it on GitHub: Nav\_Menu\_Item Revisions](https://github.com/WP-API/docs/edit/master/reference/nav_menu_item-revisions.md)

Changelog

[See list of changes: Nav\_Menu\_Item Revisions](https://github.com/WP-API/docs/commits/master/reference/nav_menu_item-revisions.md)

[PreviousNav\_MenusPrevious: Nav\_Menus](https://developer.wordpress.org/rest-api/reference/nav_menus/)

[NextNav\_Menu\_ItemsNext: Nav\_Menu\_Items](https://developer.wordpress.org/rest-api/reference/nav_menu_items/)

Notifications