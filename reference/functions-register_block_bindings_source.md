---
url: https://developer.wordpress.org/reference/functions/register_block_bindings_source
scraped_at: 2025-10-20T03:25:58.569Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

register\_block\_bindings\_source()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)register\_block\_bindings\_source()

Search

# register\_block\_bindings\_source( string$source\_name, array$source\_properties ): [WP\_Block\_Bindings\_Source](https://developer.wordpress.org/reference/classes/wp_block_bindings_source/) \|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#description)
- [Example](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#example)
  - [Registering a source](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#registering-a-source)
  - [Usage in a block](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#usage-in-a-block)
- [Parameters](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#return)
- [Source](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#source)
- [Related](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#wp--skip-link--target)

Registers a new block bindings source.

## [Description](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#description)

Registering a source consists of defining a **name** for that source and a callback function specifying how to get a value from that source and pass it to a block attribute.

Once a source is registered, any block that supports the Block Bindings API can use a value from that source by setting its `metadata.bindings` attribute to a value that refers to the source.

Note that `register_block_bindings_source()` should be called from a handler attached to the `init` hook.

## [Example](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#example)

### [Registering a source](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#registering-a-source)

First, you need to define a function that will be used to get the value from the source.

`wp-includes/block-bindings.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#)

```php
function my_plugin_get_custom_source_value( array $source_args, $block_instance, string $attribute_name ) {
  // Your custom logic to get the value from the source.
  // For example, you can use the `$source_args` to look up a value in a custom table or get it from an external API.
  $value = $source_args['key'];

  return "The value passed to the block is: $value"
}
```

The `$source_args` will contain the arguments passed to the source in the block’s `metadata.bindings` attribute. See the example in the "Usage in a block" section below.

`wp-includes/block-bindings.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#)

```php
function my_plugin_register_block_bindings_sources() {
  register_block_bindings_source( 'my-plugin/my-custom-source', array(
    'label'              => __( 'My Custom Source', 'my-plugin' ),
    'get_value_callback' => 'my_plugin_get_custom_source_value',
  ) );
}
add_action( 'init', 'my_plugin_register_block_bindings_sources' );
```

### [Usage in a block](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#usage-in-a-block)

In a block’s `metadata.bindings` attribute, you can specify the source and its arguments. Such a block will use the source to override the block attribute’s value. For example:

`wp-includes/block-bindings.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#)

[Copy](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#)

```php
<!-- wp:paragraph {
  "metadata": {
    "bindings": {
      "content": {
        "source": "my-plugin/my-custom-source",
        "args": {
          "key": "you can pass any custom arguments here"
        }
      }
    }
  }
} -->
<p>Fallback text that gets replaced.</p>
<!-- /wp:paragraph -->
```

## [Parameters](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#parameters)

`$source_name` stringrequired

The name of the source. It must be a string containing a namespace prefix, i.e.

`my-plugin/my-custom-source`. It must only contain lowercase alphanumeric characters, the forward slash `/` and dashes.

`$source_properties` arrayrequired

The array of arguments that are used to register a source.

- `label` string
The label of the source.

- `get_value_callback` callable
A callback executed when the source is processed during block rendering.


The callback should have the following signature: `function( $source_args, $block_instance, $attribute_name ): mixed`



- @param array $source\_args Array containing source arguments used to look up the override value, i.e. {"key": "foo"}.
- @param [WP\_Block](https://developer.wordpress.org/reference/classes/wp_block/) $block\_instance The block instance.
- @param string $attribute\_name The name of an attribute.

The callback has a mixed return type; it may return a string to override the block’s original value, null, false to remove an attribute, etc.

- `uses_context` string\[\]
Optional. Array of values to add to block `uses_context` needed by the source.


## [Return](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#return)

[WP\_Block\_Bindings\_Source](https://developer.wordpress.org/reference/classes/wp_block_bindings_source/) \|false Source when the registration was successful, or `false` on failure.

## [Source](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#source)

`wp-includes/block-bindings.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_bindings_source/#)

```php
function register_block_bindings_source( string $source_name, array $source_properties ) {
	return WP_Block_Bindings_Registry::get_instance()->register( $source_name, $source_properties );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/block-bindings.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/block-bindings.php#L94) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/block-bindings.php#L94-L96)

## [Related](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Block\_Bindings\_Registry::get\_instance()](https://developer.wordpress.org/reference/classes/wp_block_bindings_registry/get_instance/) `wp-includes/class-wp-block-bindings-registry.php` | Utility method to retrieve the main instance of the class. |

| Used by | Description |
| --- | --- |
| [\_register\_block\_bindings\_post\_meta\_source()](https://developer.wordpress.org/reference/functions/_register_block_bindings_post_meta_source/) `wp-includes/block-bindings/post-meta.php` | Registers Post Meta source in the block bindings registry. |
| [\_register\_block\_bindings\_pattern\_overrides\_source()](https://developer.wordpress.org/reference/functions/_register_block_bindings_pattern_overrides_source/) `wp-includes/block-bindings/pattern-overrides.php` | Registers Pattern Overrides source in the Block Bindings registry. |

## [Changelog](https://developer.wordpress.org/reference/functions/register_block_bindings_source/\#changelog)

| Version | Description |
| --- | --- |
| [6.5.0](https://developer.wordpress.org/reference/since/6.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_bindings_source%2F) before being able to contribute a note or feedback.

Notifications