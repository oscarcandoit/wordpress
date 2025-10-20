---
url: https://developer.wordpress.org/apis/metadata
scraped_at: 2025-10-20T04:07:02.960Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Metadata


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Metadata

Search

# Metadata

## In this article

Table of Contents

- [Overview](https://developer.wordpress.org/apis/metadata/#overview)
- [Function Reference](https://developer.wordpress.org/apis/metadata/#function-reference)
- [Database Requirements](https://developer.wordpress.org/apis/metadata/#database-requirements)
  - [Default Meta Tables](https://developer.wordpress.org/apis/metadata/#default-meta-tables)
  - [Meta Table Structure](https://developer.wordpress.org/apis/metadata/#meta-table-structure)
- [Source File](https://developer.wordpress.org/apis/metadata/#source-file)
- [Related](https://developer.wordpress.org/apis/metadata/#related)

[↑ Back to top](https://developer.wordpress.org/apis/metadata/#wp--skip-link--target)

## [Overview](https://developer.wordpress.org/apis/metadata/\#overview)

The **Metadata API** is a simple and standarized way for retrieving and manipulating metadata of various WordPress object types.

Metadata for an object is a represented by a simple key-value pair.

Objects may contain multiple metadata entries that share the same key and differ only in their value.

## [Function Reference](https://developer.wordpress.org/apis/metadata/\#function-reference)

Add/Delete Metadata:

- [add\_metadata()](https://developer.wordpress.org/reference/functions/add_metadata/)
- [delete\_metadata()](https://developer.wordpress.org/reference/functions/delete_metadata/)

Get/Update Metadata:

- [get\_metadata()](https://developer.wordpress.org/reference/functions/get_metadata/)
- [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/)

## [Database Requirements](https://developer.wordpress.org/apis/metadata/\#database-requirements)

This function assumes that a dedicated MySQL table exists for the `$meta_type` you specify. Some desired `$meta_types` do not come with pre-installed WordPress tables, and so they must be created manually.

### [Default Meta Tables](https://developer.wordpress.org/apis/metadata/\#default-meta-tables)

Assuming a prefix of `wp_`, WordPress’s included meta tables are:

- `wp_commentmeta`: Metadata for specific comments.
- `wp_postmeta`: Metadata for pages, posts, and all other post types.
- `wp_usermeta`: Metadata for users.

### [Meta Table Structure](https://developer.wordpress.org/apis/metadata/\#meta-table-structure)

To store data for meta types not included in the above table list, a new table needs to be created. All meta tables require four columns.

- `meta_id` – BIGINT(20): unsigned, auto\_increment, not null, primary key.
- `object_id` – BIGINT(20): unsigned, not null.

Replace _object_ with the singular name of the content type being used.

For instance, this column might be named post\_id or term\_id.

Although this column is used like a foreign key, it should not be defined as one.
- `meta_key` – VARCHAR(255): The key of your custom meta data.
- `meta_value` – LONGTEXT: The value of your custom meta data.

## [Source File](https://developer.wordpress.org/apis/metadata/\#source-file)

Metadata API is located in `[wp-includes/meta.php](https://core.trac.wordpress.org/browser/tags/5.2.1/src/wp-includes/meta.php#L0)`.

## [Related](https://developer.wordpress.org/apis/metadata/\#related)

**Metadata API**: [add\_metadata()](https://developer.wordpress.org/reference/functions/add_metadata/), [get\_metadata()](https://developer.wordpress.org/reference/functions/get_metadata/), [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/), [delete\_metadata()](https://developer.wordpress.org/reference/functions/delete_metadata/).

First published

August 12, 2019

Last updated

November 21, 2022

[PreviousGlobal VariablesPrevious: Global Variables](https://developer.wordpress.org/apis/global-variables/)

[NextOptionsNext: Options](https://developer.wordpress.org/apis/options/)

Notifications