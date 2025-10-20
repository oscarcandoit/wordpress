---
url: https://developer.wordpress.org/plugins/post-types/registering-custom-post-types
scraped_at: 2025-10-20T03:36:08.504Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Registering Custom Post Types


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Custom Post Types](https://developer.wordpress.org/plugins/post-types/)Registering Custom Post Types

Search

# Registering Custom Post Types

## In this article

Table of Contents

- [Naming Best Practices](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#naming-best-practices)
- [URLs](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#urls)
  - [A Custom Slug for a Custom Post Type](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#a-custom-slug-for-a-custom-post-type)

[↑ Back to top](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#wp--skip-link--target)

WordPress comes with five default post types: `post`, `page`, `attachment`, `revision`, and `menu`.

While developing your plugin, you may need to create your own specific content type: for example, products for an e-commerce website, assignments for an e-learning website, or movies for a review website.

Using Custom Post Types, you can register your own post type. Once a custom post type is registered, it gets a new top-level administrative screen that can be used to manage and create posts of that type.

To register a new post type, you use the [register\_post\_type()](https://developer.wordpress.org/reference/functions/register_post_type/) function.

We recommend that you put custom post types in a plugin rather than a theme. This ensures that user content remains portable even if the theme is changed.

The following minimal example registers a new post type, Products, which is identified in the database as `wporg_product`.

``
[Expand code](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#)

[Copy](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#)

```php
function wporg_custom_post_type() {
	register_post_type('wporg_product',
		array(
			'labels'      => array(
				'name'          => __('Products', 'textdomain'),
				'singular_name' => __('Product', 'textdomain'),
			),
				'public'      => true,
				'has_archive' => true,
		)
	);
}
add_action('init', 'wporg_custom_post_type');

```

Please visit the reference page for [register\_post\_type()](https://developer.wordpress.org/reference/functions/register_post_type/) for the description of arguments.

You must call `register_post_type()` before the `[admin\_init](https://developer.wordpress.org/reference/hooks/admin_init/)` hook and after the `[after\_setup\_theme](https://developer.wordpress.org/reference/hooks/after_setup_theme/)` hook. A good hook to use is the `[init](https://developer.wordpress.org/reference/hooks/init/)` action hook.

## [Naming Best Practices](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/\#naming-best-practices)

It is important that you prefix your post type functions and identifiers with a short prefix that corresponds to your plugin, theme, or website.

**Make sure your custom post type identifier does not exceed 20 characters** as the `post_type` column in the database is currently a VARCHAR field of that length.

**To ensure forward compatibility**, do not use **wp\_** as your identifier — it is being used by WordPress core.

If your identifier is too generic (for example: “ `product`“), it may conflict with other plugins or themes that have chosen to use that same identifier.

**Solving duplicate post type identifiers is not possible without disabling one of the conflicting post types.**

## [URLs](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/\#urls)

A custom post type gets its own slug within the site URL structure.

A post of type `wporg_product` will use the following URL structure by default: `http://example.com/wporg_product/%product_name%`.

`wporg_product` is the slug of your custom post type and `%product_name%` is the slug of your particular product.

The final permalink would be: `http://example.com/wporg_product/wporg-is-awesome`.

You can see the permalink on the edit screen for your custom post type, just like with default post types.

### [A Custom Slug for a Custom Post Type](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/\#a-custom-slug-for-a-custom-post-type)

To set a custom slug for the slug of your custom post type all you need to do is add a key => value pair to the `rewrite` key in the `register_post_type()` arguments array.

Example:

``
[Expand code](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#)

[Copy](https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/#)

```php
function wporg_custom_post_type() {
	register_post_type('wporg_product',
		array(
			'labels'      => array(
				'name'          => __( 'Products', 'textdomain' ),
				'singular_name' => __( 'Product', 'textdomain' ),
			),
			'public'      => true,
			'has_archive' => true,
			'rewrite'     => array( 'slug' => 'products' ), // my custom slug
		)
	);
}
add_action('init', 'wporg_custom_post_type');

```

The above will result in the following URL structure: `http://example.com/products/%product_name%`

Using a generic slug like `products` can potentially conflict with other plugins or themes, so try to use one that is more specific to your content.

Unlike the custom post type identifiers, the duplicate slug problem can be solved easily by changing the slug for one of the conflicting post types.

If the plugin author included an `apply_filters()` call on the arguments, this can be done programmatically by overriding the arguments submitted via the `register_post_type()` function.

First published

September 24, 2014

Last updated

November 17, 2022

[PreviousCustom Post TypesPrevious: Custom Post Types](https://developer.wordpress.org/plugins/post-types/)

[NextWorking with Custom Post TypesNext: Working with Custom Post Types](https://developer.wordpress.org/plugins/post-types/working-with-custom-post-types/)

Notifications