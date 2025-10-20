---
url: https://developer.wordpress.org/rest-api/reference/nav_menu_items
scraped_at: 2025-10-20T02:04:18.686Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Nav\_Menu\_Items


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Nav\_Menu\_Items

Search

# Nav\_Menu\_Items

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema)
- [List Nav\_Menu\_Items](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#list-nav_menu_items)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#arguments)
- [Create a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#create-a-nav_menu_item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#arguments-2)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#definition-2)
- [Retrieve a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#retrieve-a-nav_menu_item)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#definition-example-request)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#arguments-3)
- [Update a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#update-a-nav_menu_item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#arguments-4)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#definition-3)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#example-request-2)
- [Delete a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#delete-a-nav_menu_item)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#arguments-5)
  - [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#definition-4)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#example-request-3)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#schema)

The schema defines all the fields that exist within a nav\_menu\_item record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `title` | The title for the object.<br>JSON data type: string or object <br>Context: `view`, `edit`, `embed` |
| `id` | Unique identifier for the object.<br>JSON data type: integer <br>Read only<br>Context: `view`, `edit`, `embed` |
| `type_label` | The singular label used to describe this type of menu item.<br>JSON data type: string <br>Read only<br>Context: `view`, `edit`, `embed` |
| `type` | The family of objects originally represented, such as "post\_type" or "taxonomy".<br>JSON data type: string <br>Context: `view`, `edit`, `embed`<br>One of: `taxonomy`, `post_type`, `post_type_archive`, `custom` |
| `status` | A named status for the object.<br>JSON data type: string <br>Context: `view`, `edit`, `embed`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `parent` | The ID for the parent of the object.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `attr_title` | Text for the title attribute of the link element for this menu item.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `classes` | Class names for the link element of this menu item.<br>JSON data type: array <br>Context: `view`, `edit`, `embed` |
| `description` | The description of this menu item.<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `menu_order` | The DB ID of the nav\_menu\_item that is this item's menu parent, if any, otherwise 0.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `object` | The type of object originally represented, such as "category", "post", or "attachment".<br>JSON data type: string <br>Context: `view`, `edit`, `embed` |
| `object_id` | The database ID of the original object this menu item represents, for example the ID for posts or the term\_id for categories.<br>JSON data type: integer <br>Context: `view`, `edit`, `embed` |
| `target` | The target attribute of the link element for this menu item.<br>JSON data type: string <br>Context: `view`, `edit`, `embed`<br>One of: `_blank`, `` |
| `url` | The URL to which this menu item points.<br>JSON data type: string,<br>Format: uri<br> <br>Context: `view`, `edit`, `embed` |
| `xfn` | The XFN relationship expressed in the link of this menu item.<br>JSON data type: array <br>Context: `view`, `edit`, `embed` |
| `invalid` | Whether the menu item represents an object that no longer exists.<br>JSON data type: boolean <br>Read only<br>Context: `view`, `edit`, `embed` |
| `menus` | The terms assigned to the object in the nav\_menu taxonomy.<br>JSON data type: integer <br>Context: `view`, `edit` |
| `meta` | Meta fields.<br>JSON data type: object <br>Context: `view`, `edit` |

## [List Nav\_Menu\_Items](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#list-nav_menu_items)

Query this endpoint to retrieve a collection of nav\_menu\_items. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#definition)

`GET /wp/v2/menu-items`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#example-request)

`$ curl https://example.com/wp-json/wp/v2/menu-items`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br>Default: `100` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to posts published after a given ISO8601 compliant date. |
| `modified_after` | Limit response to posts modified after a given ISO8601 compliant date. |
| `before` | Limit response to posts published before a given ISO8601 compliant date. |
| `modified_before` | Limit response to posts modified before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br>Default: `asc`<br>One of: `asc`, `desc` |
| `orderby` | Sort collection by object attribute.<br>Default: `menu_order`<br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title`, `menu_order` |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br>Default: `publish` |
| `tax_relation` | Limit result set based on relationship between multiple taxonomies.<br> One of: `AND`, `OR` |
| `menus` | Limit result set to items with specific terms assigned in the menus taxonomy. |
| `menus_exclude` | Limit result set to items except those with specific terms assigned in the menus taxonomy. |
| `menu_order` | Limit result set to posts with a specific menu\_order value. |

## [Create a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#create-a-nav_menu_item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#arguments-2)

|     |     |
| --- | --- |
| `[title](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-title)` | The title for the object. |
| `[type](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-type)` | The family of objects originally represented, such as "post\_type" or "taxonomy".<br>Default: `custom`<br>One of: `taxonomy`, `post_type`, `post_type_archive`, `custom` |
| `[status](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-status)` | A named status for the object.<br>Default: `publish`<br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[parent](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-parent)` | The ID for the parent of the object. |
| `[attr\_title](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-attr_title)` | Text for the title attribute of the link element for this menu item. |
| `[classes](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-classes)` | Class names for the link element of this menu item. |
| `[description](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-description)` | The description of this menu item. |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-menu_order)` | The DB ID of the nav\_menu\_item that is this item's menu parent, if any, otherwise 0.<br>Default: `1` |
| `[object](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-object)` | The type of object originally represented, such as "category", "post", or "attachment". |
| `[object\_id](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-object_id)` | The database ID of the original object this menu item represents, for example the ID for posts or the term\_id for categories. |
| `[target](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-target)` | The target attribute of the link element for this menu item.<br> One of: `_blank`, `` |
| `[url](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-url)` | The URL to which this menu item points. |
| `[xfn](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-xfn)` | The XFN relationship expressed in the link of this menu item. |
| `[menus](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-menus)` | The terms assigned to the object in the nav\_menu taxonomy. |
| `[meta](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#definition-2)

`POST /wp/v2/menu-items`

## [Retrieve a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#retrieve-a-nav_menu_item)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#definition-example-request)

`GET /wp/v2/menu-items/<id>`

Query this endpoint to retrieve a specific nav\_menu\_item record.

`$ curl https://example.com/wp-json/wp/v2/menu-items/<id>`

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br>Default: `view`<br>One of: `view`, `embed`, `edit` |

## [Update a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#update-a-nav_menu_item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#arguments-4)

|     |     |
| --- | --- |
| `[id](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-id)` | Unique identifier for the post. |
| `[title](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-title)` | The title for the object. |
| `[type](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-type)` | The family of objects originally represented, such as "post\_type" or "taxonomy".<br> One of: `taxonomy`, `post_type`, `post_type_archive`, `custom` |
| `[status](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-status)` | A named status for the object.<br> One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[parent](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-parent)` | The ID for the parent of the object. |
| `[attr\_title](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-attr_title)` | Text for the title attribute of the link element for this menu item. |
| `[classes](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-classes)` | Class names for the link element of this menu item. |
| `[description](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-description)` | The description of this menu item. |
| `[menu\_order](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-menu_order)` | The DB ID of the nav\_menu\_item that is this item's menu parent, if any, otherwise 0. |
| `[object](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-object)` | The type of object originally represented, such as "category", "post", or "attachment". |
| `[object\_id](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-object_id)` | The database ID of the original object this menu item represents, for example the ID for posts or the term\_id for categories. |
| `[target](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-target)` | The target attribute of the link element for this menu item.<br> One of: `_blank`, `` |
| `[url](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-url)` | The URL to which this menu item points. |
| `[xfn](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-xfn)` | The XFN relationship expressed in the link of this menu item. |
| `[menus](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-menus)` | The terms assigned to the object in the nav\_menu taxonomy. |
| `[meta](https://developer.wordpress.org/rest-api/reference/nav_menu_items/#schema-meta)` | Meta fields. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#definition-3)

`POST /wp/v2/menu-items/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#example-request-2)

``

## [Delete a Nav\_Menu\_Item](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#delete-a-nav_menu_item)

### [Arguments](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#definition-4)

`DELETE /wp/v2/menu-items/<id>`

### [Example Request](https://developer.wordpress.org/rest-api/reference/nav_menu_items/\#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/menu-items/<id>`

First published

April 26, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Nav\_Menu\_Items](https://github.com/WP-API/docs/edit/master/reference/nav_menu_items.md)

Changelog

[See list of changes: Nav\_Menu\_Items](https://github.com/WP-API/docs/commits/master/reference/nav_menu_items.md)

[PreviousNav\_Menu\_Item RevisionsPrevious: Nav\_Menu\_Item Revisions](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/)

[NextPage RevisionsNext: Page Revisions](https://developer.wordpress.org/rest-api/reference/page-revisions/)

Notifications