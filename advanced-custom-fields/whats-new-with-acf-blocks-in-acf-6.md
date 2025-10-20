---
url: https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6
scraped_at: 2025-10-20T02:26:28.709Z
---

# What’s New With ACF Blocks in ACF 6

Last updated Aug 17, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#overview)

## Overview

Link copied

ACF 6.0 includes ACF Blocks Version 2. This next generation of ACF Blocks brings us much closer to the native block experience, while still giving you the PHP based templating language you know as a WordPress developer.

In the last few releases of WordPress, Gutenberg has made significant changes to all aspects of the block editor and block registration, and this has impacted ACF Blocks. We’ve not been able to move as fast as we would have liked on implementing changes to support these new features for back compatibility reasons. ACF 6.0 ships with a new block versioning system, allowing you to opt in to new versions which will change things like the markup and structure of ACF Blocks in both the backend and frontend, and may require updates to your theme to support.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#backwards-compatibility)

## Backwards Compatibility

Link copied

The changes to blocks in ACF 6.0 are designed to be backwards compatible with ACF 5.x, with one notable exception. Due to the changes in [block IDs](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-id), if you use `parse_blocks()` to read data from an ACF Block, it will no longer have a block ID present in that data. For workarounds to this, [see our examples](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-id) for adding a block ID back in.

Whilst we recommend users [upgrade to block.json blocks](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6) to take advantage of new and upcoming WordPress features if they can, blocks registered with `acf_register_block_type()` will continue to work with ACF 6.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#blockjson-support)

## Block.json Support

Link copied

Since WordPress 5.8, WordPress has supported – and recommended – that blocks are registered through a JSON configuration file. All of the [WordPress Block Documentation](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/) was migrated to only show `block.json` configuration objects, and it became confusing for users to know what WordPress configuration options were usable in ACF PRO. ACF 6.0 introduces support for `block.json` registration of blocks with ACF.

For blocks registered through a `block.json` file, you can mark them as ACF Blocks by adding a new ACF configuration key to the JSON file, which contains the ACF specific configuration, for example:

```json php
{
    "name": "all-fields-block",
    "title": "All Fields Test Block",
    "description": "All fields test block",
    "style": "file:./all-fields-block.css",
    "category": "theme",
    "icon": "admin-comments",
    "apiVersion": 2,
    "keywords": [\
        "test",\
        "quote"\
    ],
    "acf": {
        "mode": "preview",
        "renderTemplate": "all-fields-block.php",
        "postTypes": [ "post" ]
    },
    "styles": [\
        { "name": "default", "label": "Default", "isDefault": true },\
        { "name": "red", "label": "Red" },\
        { "name": "green", "label": "Green" },\
        { "name": "blue", "label": "Blue" }\
    ],
    "supports": {
        "align": true,
        "anchor": true,
        "alignContent": false,
        "color": {
            "text": true,
            "background": true,
            "link": true
        },
        "alignText": true,
        "spacing": {
            "margin": [\
                "top",\
                "bottom"\
            ],
            "padding": true
        },
        "typography": {
            "lineHeight": true,
            "fontSize": true
        },
        "fullHeight": true
    },
    "attributes": {
        "backgroundColor": {
            "type": "string",
            "default": "purple"
        }
    },
    "example": {
        "attributes": {
            "data": {
                "text": "This is an example text field",
                "text_area": "This is an example text area field"
            }
        }
    }
}
```

You then need to use the standard WordPress [block registration function](https://developer.wordpress.org/reference/functions/register_block_type/) `register_block_type`, rather than `acf_register_block_type`:

```php php
register_block_type( 'path/to/folder/containing/block.json' );
```

If you don’t specify a namespace for your block like in our example above: `"name": "all-fields-block",`, ACF will automatically add it if it is an ACF block to become the equivalent of `"name": "acf/all-fields-block"` although you are now free to use your own namespace for your blocks.

This new method of registering blocks is now the recommended way to register a block, replacing the `acf_register_block_type` function.

The `renderTemplate` property should either be a full path to the template file, or relative to the location of the JSON file.

You can also now specify default attributes for your block, as shown in our example above in the `attributes` key. You can use this to set defaults for the WordPress provided block attributes, such as `backgroundColor`.

WordPress uses a camelCase format inside JSON files, and ACF adopts that too. Configuration keys such as `render_template` when used in `acf_register_block_type` need to be `renderTemplate` when used in JSON, likewise `align_content` and `full_height` should be `alignContent` and `fullHeight` for example. All previous configuration objects are supported, except for `enqueue_style`, `enqueue_script` and `enqueue_assets` for reasons explained below:

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#asset-loading)

## Block Asset Loading

Link copied

When ACF Blocks was first introduced, it supported enqueueing block specific assets before WordPress had native support. Recent (and upcoming) updates to Gutenberg will require these assets to be loaded using specific [WordPress asset configuration keys](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/#editor-script) such as `editorScript`, `script`, `editorStyle` and `style`.

WordPress 5.9 users who use Block Styles may have noticed that the ACF registration of styles was not applied to those previews, which is why all ACF Block users should migrate their blocks to use those WordPress provided methods of asset loading.

The previous methods of asset loading in ACF Blocks will continue to work for the time being in `acf_register_block_type`, but as WordPress continues to make changes across releases we expect that to stop working – especially with the [upcoming plan](https://make.wordpress.org/core/2021/06/29/blocks-in-an-iframed-template-editor/#comments) to isolate each block in an iframe.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-id)

## Block ID Changes

Link copied

ACF 6.0 will no longer save block IDs to the block comment of ACF Blocks. This affects all versions of ACF Blocks and means you can easily copy and paste blocks, simplify your post type templates, use your blocks in block patterns, or duplicate blocks without having any issues where block IDs clash.

This change shouldn’t affect most users, since we still generate a `$block['id']` for your templates as we know some users use that for element IDs, but the format of those IDs will change. Just like in ACF 5.x, block IDs may be duplicated, but the number of situations where this can happen has been reduced significantly to one: if you have multiple blocks on the same page with the exact same data, attributes and context.

Due to the dynamic block ID generation, this change is backwards compatible for the majority of users, unless you use `parse_blocks()` to read ACF data, and rely on it returning a block ID.

Internally, ACF builds the new dynamic block ID from a md5 hash of the block’s attributes and context, but as WordPress block context may not be available in `parse_blocks()` so you will not reliably be able to match our dynamic block ID with the result of `parse_blocks()`.

There are a couple of options to get around this. You could generate your own hash through a checksum of the sorted data attributes, use user entered anchors, or you could automatically generate an ID that is saved server side whenever a block is saved using the `acf/pre_save_block` filter.

Here’s a couple of possible examples, the first will automatically generate an anchor attribute if the user doesn’t enter one:

```php php
add_filter(
    'acf/pre_save_block',
    function( $attributes ) {
        if ( empty( $attributes['anchor'] ) ) {
            $attributes['anchor'] = 'acf-block-' . uniqid();
        }
        return $attributes;
    }
);
```

Alternatively, you could generate a new custom ID attribute which would be used on the front-end too if set, but note that it will be regenerated each time the block is saved, and this id will not be used in the backend editor:

```php php
add_filter(
    'acf/pre_save_block',
    function( $attributes ) {
        if ( empty( $attributes['id'] ) ) {
            $attributes['id'] = 'acf-block-' . uniqid();
        }
        return $attributes;
    }
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-versioning)

## Block Versioning Details

Link copied

A new `blockVersion` (inside the ACF key in `block.json`) or `acf_block_version` (if using `acf_register_block_type`) key is now supported. For blocks registered via `block.json`, this defaults to `2`. For `acf_register_block_type`, this defaults to `1`.

For now, the main change between the two versions is the way `<InnerBlocks />` markup is rendered. If you use block version 2 (which requires WordPress 5.8+), the container markup when using InnerBlocks will match between backend and frontend rendering, with any inner blocks wrapped in a new (and single level) `<div class="acf-inner-blocks-container"></div>` element. This can help make your CSS layouts easier, as you can be sure both render views have the same markup.

Whilst this wrapper must appear in the backend block editor, if you wish to disable it for the frontend, you can do that with a new filter, and optionally enable or disable it based on the block name:

```php php
add_filter( 'acf/blocks/wrap_frontend_innerblocks', 'acf_should_wrap_innerblocks', 10, 2 );
function acf_should_wrap_innerblocks( $wrap, $name ) {
    if ( $name == 'acf/test-block' ) {
        return true;
    }
    return false;
}
```

If you just wish to modify the class being used for the wrapper, instead of the default `acf-inner-blocks-container` you can simply add a class to your `<InnerBlocks />` tag inside your block template, such as …

```html php
<InnerBlocks class="test-wrapper-class second-class" />
```

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-registry)

## Block Registry Standardization

Link copied

In previous versions of ACF PRO, a lightweight shim of the block configuration was registered in PHP, and then the full configuration registered in JS.

In this build of ACF, the full block configuration is now saved in the WordPress PHP Block Registry. This makes it easier for you to access details of the block configuration in your templates or render callbacks.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-context-changes)

## Block Context Changes

Link copied

During development, we saw a conversation on twitter discussing the viability of using data from an ACF Block inside blocks contained in its `<InnerBlocks>` children.

We suspected this would be possible using [block context](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-context/), the system core blocks like the Query Loop block use to know the current post type.

ACF 6.0 introduces support for block context. This means if you want to pass ACF field data from a parent block to an InnerBlock, the InnerBlock will automatically reload the template, showing changes live as you make changes to fields in the parent. This support should also improve the reliability of blocks used inside Query Loop blocks.

To enable this, you need to tell WordPress to share the ACF `data` attribute to its child blocks with a custom key ( `acf/fields` in our example) with `providesContext` in block.json:

```json php
"providesContext": {"acf/fields": "data"}
```

Then, to consume that context in an ACF block, you need to pass the context key in `usesContext`:

```json php
"usesContext": ["acf/fields"],
```

One thing to note: ACF Blocks use field keys in the block editor, and block data is only hydrated to field names upon save. Because of this, you should use `$context['acf/fields']['field_key']` to get access the data inside your template if it exists before defaulting back to `$context['acf/fields']['field_name']` if it doesn’t exist to support both backend and frontend output of context data.

You should also be aware that if you share ACF data through to your child blocks, the full ACF fields data will be sent back to the server in order to render previews. This may have performance implications for your blocks in the editor.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#blocks-without-fields)

## Blocks Without Fields

Link copied

With Full Site Editing and the Query Loop block, it’s now much more likely you might want to use ACF Blocks without any specific fields attached to the block, for example because it’s showing post templating elements like titles or post content, or because you want to display fields which are added on the post being displayed, rather than from the block.

ACF 6.0 adds support for this by providing advisory text when a block has no fields assigned, whereas previously the block’s edit mode would simply be blank and not selectable.

Developers who wish to modify the default advisory text can do so with the new `acf/blocks/no_fields_assigned_message` filter which offers 2 parameters: the message to be displayed and the name of the block it will be displayed on.

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#block-bugs)

## Block Bug Fixes

Link copied

We’ve also fixed a number of other bugs which apply to all versions of ACF Blocks.

- The `render_block_preview` JavaScript event is now always fired every time a block preview is displayed, rather than just the first time.
- Accordion fields inside an ACF block now are styled to match the native sidebar experience of the block editor.
- ACF Block preloading now works again for blocks saved in edit mode, and for blocks without any saved field data (due to changes in block preloading for the removal of Block IDs, you may need to edit each block once before it can be preloaded.)
- ACF Block edit forms will now behave correctly if they’re not visible when loaded.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- ACF Blocks: [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- ACF Blocks: [ACF Blocks Configuration via block.json](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/)

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

[Got it](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/#)