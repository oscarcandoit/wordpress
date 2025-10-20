---
url: https://developer.wordpress.org/reference/functions/register_block_template
scraped_at: 2025-10-20T03:20:49.208Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/register_block_template/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

register\_block\_template()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)register\_block\_template()

Search

# register\_block\_template( string$template\_name, array\|string$args = array() ): [WP\_Block\_Template](https://developer.wordpress.org/reference/classes/wp_block_template/) \| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/register_block_template/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/register_block_template/#return)
- [Source](https://developer.wordpress.org/reference/functions/register_block_template/#source)
- [Related](https://developer.wordpress.org/reference/functions/register_block_template/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/register_block_template/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/register_block_template/#wp--skip-link--target)

Register a block template.

## [Parameters](https://developer.wordpress.org/reference/functions/register_block_template/\#parameters)

`$template_name` stringrequired

Template name in the form of `plugin_uri//template_name`.

`$args` array\|stringoptional

- `title` string
Optional. Title of the template as it will be shown in the Site Editor and other UI elements.

- `description` string
Optional. Description of the template as it will be shown in the Site Editor.

- `content` string
Optional. Default content of the template that will be used when the template is rendered or edited in the editor.

- `post_types` string\[\]
Optional. Array of post types to which the template should be available.

- `plugin` string
Optional. Slug of the plugin that registers the template.


Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/register_block_template/\#return)

[WP\_Block\_Template](https://developer.wordpress.org/reference/classes/wp_block_template/) \| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) The registered template object on success, [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) object on failure.

## [Source](https://developer.wordpress.org/reference/functions/register_block_template/\#source)

`wp-includes/block-template.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_template/#)

```php
function register_block_template( $template_name, $args = array() ) {
	return WP_Block_Templates_Registry::get_instance()->register( $template_name, $args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/block-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/block-template.php#L411) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/block-template.php#L411-L413)

## [Related](https://developer.wordpress.org/reference/functions/register_block_template/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Block\_Templates\_Registry::get\_instance()](https://developer.wordpress.org/reference/classes/wp_block_templates_registry/get_instance/) `wp-includes/class-wp-block-templates-registry.php` | Utility method to retrieve the main instance of the class. |

## [Changelog](https://developer.wordpress.org/reference/functions/register_block_template/\#changelog)

| Version | Description |
| --- | --- |
| [6.7.0](https://developer.wordpress.org/reference/since/6.7.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_template%2F) before being able to contribute a note or feedback.

Notifications