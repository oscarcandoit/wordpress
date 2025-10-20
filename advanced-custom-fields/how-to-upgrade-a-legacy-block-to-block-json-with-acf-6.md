---
url: https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6
scraped_at: 2025-10-20T02:26:45.116Z
---

# How To Upgrade a Legacy Block to block.json With ACF 6

Last updated Aug 25, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#overview)

## Overview

Link copied

ACF 6.0 introduces support for WordPress’s `block.json` method of block registration, the recommended way of registering blocks since WordPress 5.8 and newer. You don’t have to upgrade your blocks, but you’ll need to do so if you want to take advantage of new WordPress functionality like attribute defaults (for things like background colors) or block assets loading for compatibility with block patterns.

It’s a relatively quick and painless process to upgrade your blocks from the `acf_register_block_type` method in ACF 5 to the new `block.json` format, and in this guide we’ll demonstrate how to upgrade our `testimonial` block from the ACF 5 documentation to a `block.json` block.

Let’s start with the old block example:

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#functionsphp)

#### functions.php

Link copied

```php php
add_action('acf/init', 'my_acf_blocks_init');
function my_acf_blocks_init() {

    // Check function exists.
    if( function_exists('acf_register_block_type') ) {

        // Register a testimonial block.
        acf_register_block_type(array(
            'name'              => 'testimonial',
            'title'             => __('Testimonial'),
            'description'       => __('A custom testimonial block.'),
            'render_template'   => 'template-parts/blocks/testimonial/testimonial.php',
            'mode'              => 'preview',
            'category'          => 'formatting',
        ));
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#template-partsblockstestimonialtestimonialphp)

#### template-parts/blocks/testimonial/testimonial.php

Link copied

```php php
<?php

/**
 * Testimonial Block Template.
 *
 * @param   array $block The block settings and attributes.
 * @param   string $content The block inner HTML (empty).
 * @param   bool $is_preview True during AJAX preview.
 * @param   (int|string) $post_id The post ID this block is saved to.
 */

// Create id attribute allowing for custom "anchor" value.
$id = 'testimonial-' . $block['id'];
if( !empty($block['anchor']) ) {
    $id = $block['anchor'];
}

// Create class attribute allowing for custom "className" and "align" values.
$className = 'testimonial';
if( !empty($block['className']) ) {
    $className .= ' ' . $block['className'];
}
if( !empty($block['align']) ) {
    $className .= ' align' . $block['align'];
}

// Load values and handle defaults.
$text = get_field('testimonial') ?: 'Your testimonial here...';
$author = get_field('author') ?: 'Author name';
$role = get_field('role') ?: 'Author role';
$image = get_field('image') ?: 295;
$background_color = get_field('background_color');
$text_color = get_field('text_color');

?>
<div id="<?php echo esc_attr( $id ); ?>" class="<?php echo esc_attr( $className ); ?>">
    <blockquote class="testimonial-blockquote">
        <span class="testimonial-text"><?php echo esc_html( $text ); ?></span>
        <span class="testimonial-author"><?php echo esc_html( $author ); ?></span>
        <span class="testimonial-role"><?php echo esc_html( $author_role ); ?></span>
    </blockquote>
    <div class="testimonial-image">
        <?php echo wp_get_attachment_image( $image, 'full' ); ?>
    </div>
    <style type="text/css">
        #<?php echo esc_attr( $id ); ?> {
            background: <?php echo esc_attr( $background_color ); ?>;
            color: <?php echo esc_attr( $text_color); ?>;
        }
    </style>
</div>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#upgrading-your-block)

## Upgrading Your Block

Link copied

To upgrade this block, we need to turn the code into a new `block.json` file, which contains a JSON object of all the settings for the block.

If you want to store blocks in your theme, you need to make sure you’re using WordPress 6.0 which introduced support for that. If you’re storing them in a plugin, you need at least WordPress 5.8.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#blockstestimonialblockjson)

#### blocks/testimonial/block.json

Link copied

```json php
{
    "name": "acf/testimonial",
    "title": "Testimonial",
    "description": "A custom testimonial block.",
    "style": [ "file:./testimonial.css" ],
    "category": "formatting",
    "icon": "admin-comments",
    "keywords": ["testimonial", "quote"],
    "acf": {
        "mode": "preview",
        "renderTemplate": "testimonial.php"
    },
    "align": "full"
}
```

The key changes in the transition from the old method is that all ACF specific configuration now lives inside an `acf` key. You can view the full options for that array in our [ACF `block.json`](https://www.advancedcustomfields.com/resources/acf-blocks-with-block-json/) documentation.

You’ll also notice that the WordPress convention for `block.json` files is that all property keys are camelCase. We’ve respected this in ACF’s configuration, and anything that used to contain underscores is now camelCased, for example `render_template` is now `renderTemplate`.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#asset-loading)

## Asset Loading

Link copied

Another major change regards asset loading. Instead of using the `enqueue_script`, `enqueue_style` functions, or an `enqueue_assets` callback, you should use the new WordPress provided [block asset functions](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/#editor-script). You’re mostly to use `script` or `style` which will load your assets in both the backend editor, and the frontend view too. Although there are options which will load separate assets in each view if you prefer.

For all the asset properties of your `block.json` file, you can either pass an asset handle which has already been registered before you register your block as a string – or you can use the `file:./filename.css` method above.

This is a custom format called a [WPDefinedAsset](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/#wpdefinedasset). You can also add a `filename.asset.php` which provides some metadata for your asset, such as dependencies and versions. This is useful to ensure your block also has things like jQuery available. See the [WPDefinedAsset](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/#wpdefinedasset) documentation for full details of this.

Most of these options also support arrays of multiple files, but be aware of the version of WordPress that introduced support for multiple assets for the type of asset loading you’re using.

If you opt to use `wp_register_style()` or `wp_register_script()` style handles, we recommend you register them on the line before you load the block to ensure it’s available.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#loading-the-new-blockjson-block)

## Loading the New block.json Block

Link copied

Registering the block is as simple as using the WordPress native function [`register_block_type`](https://developer.wordpress.org/reference/functions/register_block_type/), for which you pass a path to the folder containing the `block.json` file. If you prefer, you can instead pass the full path to the `block.json`, but it is important to note your block must be called `block.json` to load. No other file names are allowed as of WordPress 6.0.

We also recommend registering the block earlier than `acf/init`, so we use the WordPress default of `init`. You may also find if you want to use script or style handles you should pass a priority earlier than the default of 10. In our example below we use 5.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#functionsphp)

#### functions.php

Link copied

```php php
add_action( 'init', 'register_acf_blocks', 5 );
function register_acf_blocks() {
    register_block_type( __DIR__ . '/blocks/testimonial' );
}
```

This should be all you need to do to upgrade your ACF 5 block to an ACF 6 block! Your existing templating will still work and shouldn’t need any changes, although we’ve got a few notes on that below.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#templating)

## Templating

Link copied

Our previous ACF 5 documentation for blocks showed the following method of applying styles specific to a block, using the `$block['id']`:

```php php
<style type="text/css">
#<?php echo esc_attr( $id ); ?> {
    background: <?php echo esc_attr( $background_color ); ?>;
    color: <?php echo esc_attr( $text_color ); ?>;
}
</style>
```

Various new WordPress features since 5.8, such as the Query Loop block and Block Patterns, mean using either of those features would result in `$id` duplication.

In ACF 6.0, we’ve [changed block IDs](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-id) to overcome this, and while we still generate one for your template, if you have two copies of the exact same block on a page, their IDs will still be the same. For this reason, you should not rely on the `$block['id']` being unique, and not use it to target CSS classes.

Instead, we’ve updated our testimonial template file to build a `style` property which is added to the DOM element instead:

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#blocktestimonialtestimonialphp)

#### block/testimonial/testimonial.php

Link copied

```php php
<?php
/**
 * Testimonial Block Template.
 *
 * @param   array $block The block settings and attributes.
 * @param   string $content The block inner HTML (empty).
 * @param   bool $is_preview True during backend preview render.
 * @param   int $post_id The post ID the block is rendering content against.
 *          This is either the post ID currently being displayed inside a query loop,
 *          or the post ID of the post hosting this block.
 * @param   array $context The context provided to the block by the post or its parent block.
 */

// Support custom "anchor" values.
$anchor = '';
if ( ! empty( $block['anchor'] ) ) {
    $anchor = 'id="' . esc_attr( $block['anchor'] ) . '" ';
}

// Create class attribute allowing for custom "className" and "align" values.
$class_name = 'testimonial-block';
if ( ! empty( $block['className'] ) ) {
    $class_name .= ' ' . $block['className'];
}
if ( ! empty( $block['align'] ) ) {
    $class_name .= ' align' . $block['align'];
}

// Load values and assign defaults.
$text             = get_field( 'testimonial' ) ?: 'Your testimonial here...';
$author           = get_field( 'author' ) ?: 'Author name';
$author_role      = get_field( 'role' ) ?: 'Author role';
$image            = get_field( 'image' ) ?: 295;
$background_color = get_field( 'background_color' );
$text_color       = get_field( 'text_color' );

// Build a valid style attribute for background and text colors.
$styles = array( 'background-color: ' . $background_color, 'color: ' . $text_color );
$style  = implode( '; ', $styles );

?>
<div <?php echo $anchor; ?>class="<?php echo esc_attr( $class_name ); ?>" style="<?php echo esc_attr( $style ); ?>">
    <blockquote class="testimonial-blockquote">
        <span class="testimonial-text"><?php echo esc_html( $text ); ?></span>
        <span class="testimonial-author"><?php echo esc_html( $author ); ?></span>
        <span class="testimonial-role"><?php echo esc_html( $author_role ); ?></span>
    </blockquote>
    <div class="testimonial-image">
        <?php echo wp_get_attachment_image( $image, 'full' ); ?>
    </div>
</div>
```

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- ACF Blocks: [ACF Blocks Configuration via block.json](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/)
- ACF Blocks: [Save ACF Block Field Values to Post Meta](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/)
- ACF Blocks: [What’s New With ACF Blocks in ACF 6](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/#)