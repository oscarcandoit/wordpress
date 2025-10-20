---
url: https://developer.wordpress.org/plugins/metadata/managing-post-metadata
scraped_at: 2025-10-20T03:17:05.205Z
---

[Skip to content](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Managing Post Metadata


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Metadata](https://developer.wordpress.org/plugins/metadata/)Managing Post Metadata

Search

# Managing Post Metadata

## In this article

Table of Contents

- [Adding Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#adding-metadata)
- [Updating Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#updating-metadata)
- [Deleting Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#deleting-metadata)
- [Character Escaping](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#character-escaping)
  - [Workaround](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#workaround)
- [Hidden Custom Fields](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#hidden-custom-fields)
  - [Hidden Arrays](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#hidden-arrays)

[↑ Back to top](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#wp--skip-link--target)

## [Adding Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#adding-metadata)

Adding metadata can be done quite easily with [add\_post\_meta()](https://developer.wordpress.org/reference/functions/add_post_meta/) . The function accepts a `post_id`, a `meta_key`, a `meta_value`, and a `unique` flag.

The `meta_key` is how your plugin will reference the meta value elsewhere in your code. Something like `mycrazymetakeyname` would work, however a prefix related to your plugin or theme followed by a description of the key would be more useful. `wporg_featured_menu` might be a good one. It should be noted that the same `meta_key` may be used multiple times to store variations of the metadata (see the unique flag below).

The `meta_value` can be a string, integer, or an array. If it’s an array, it will be automatically serialized before being stored in the database.

The `unique` flag allows you to declare whether this key should be unique. A **non** unique key is something a post can have multiple variations of, like price.

If you only ever want **one** price for a post, you should flag it `unique` and the `meta_key` will have one value only.

## [Updating Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#updating-metadata)

If a key already exists and you want to update it, use [update\_post\_meta()](https://developer.wordpress.org/reference/functions/update_post_meta/) . If you use this function and the key does **NOT** exist, then it will create it, as if you’d used [add\_post\_meta()](https://developer.wordpress.org/reference/functions/add_post_meta/) .

Similar to [add\_post\_meta()](https://developer.wordpress.org/reference/functions/add_post_meta/) , the function accepts a `post_id`, a `meta_key`, and `meta_value`. It also accepts an optional `prev_value` – which, if specified, will cause the function to only update existing metadata entries with this value. If it isn’t provided, the function defaults to updating all entries.

## [Deleting Metadata](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#deleting-metadata)

[delete\_post\_meta()](https://developer.wordpress.org/reference/functions/delete_post_meta/) takes a `post_id`, a `meta_key`, and optionally `meta_value`. It does exactly what the name suggests.

## [Character Escaping](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#character-escaping)

Post meta values are passed through the [stripslashes()](http://php.net/manual/en/function.stripslashes.php) function upon being stored, so you will need to be careful when passing in values (such as JSON) that might include escaped characters.

Consider the JSON value `{"key":"value with \"escaped quotes\""}`:

``
[Copy](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#)

```php
$escaped_json = '{"key":"value with \"escaped quotes\""}';
update_post_meta( $id, 'escaped_json', $escaped_json );
$broken = get_post_meta( $id, 'escaped_json', true );
/*
$broken, after stripslashes(), ends up unparsable:
{"key":"value with "escaped quotes""}
*/
```

### [Workaround](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#workaround)

By adding one more level of escaping using the function [wp\_slash()](https://developer.wordpress.org/reference/functions/wp_slash/) (introduced in WP 3.6), you can compensate for the call to [stripslashes()](http://php.net/manual/en/function.stripslashes.php):

``
[Copy](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#)

```php
$escaped_json = '{"key":"value with \"escaped quotes\""}';
update_post_meta( $id, 'double_escaped_json', wp_slash( $escaped_json ) );
$fixed = get_post_meta( $id, 'double_escaped_json', true );
/*
$fixed, after stripslashes(), ends up as desired:
{"key":"value with \"escaped quotes\""}
*/
```

## [Hidden Custom Fields](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#hidden-custom-fields)

If you are a plugin or theme developer and you are planning to use custom fields to store parameters, it is important to note that WordPress will not show custom fields which have `meta_key` starting with an “\_” (underscore) in the custom fields list on the post edit screen or when using the [the\_meta()](https://developer.wordpress.org/reference/functions/the_meta/) template function.

This can be useful in order to show these custom fields in an unusual way by using the [add\_meta\_box()](https://developer.wordpress.org/reference/functions/add_meta_box/) function.

The example below will add a unique custom field with the `meta_key` name ‘\_color’ and the `meta_value` of ‘red’ but this custom field will not display in the post edit screen:

``
[Copy](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/#)

```php
add_post_meta( 68, '_color', 'red', true );
```

### [Hidden Arrays](https://developer.wordpress.org/plugins/metadata/managing-post-metadata/\#hidden-arrays)

In addition, if the `meta_value` is an array, it will not be displayed on the page edit screen, even if you don’t prefix the `meta_key` name with an underscore.

First published

September 24, 2014

Last updated

November 17, 2022

[PreviousMetadataPrevious: Metadata](https://developer.wordpress.org/plugins/metadata/)

[NextCustom Meta BoxesNext: Custom Meta Boxes](https://developer.wordpress.org/plugins/metadata/custom-meta-boxes/)

Notifications