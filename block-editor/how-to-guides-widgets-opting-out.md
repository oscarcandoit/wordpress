---
url: https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out
scraped_at: 2025-10-20T03:15:38.064Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Restoring the classic Widgets Editor


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)[Widgets](https://developer.wordpress.org/block-editor/how-to-guides/widgets/)Restoring the classic Widgets Editor

Search

# Restoring the classic Widgets Editor

## In this article

Table of Contents

- [Using remove\_theme\_support](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/#using-remove_theme_support)
- [Using the Classic Widgets plugin](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/#using-the-classic-widgets-plugin)
- [Using a filter](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/#using-a-filter)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/#wp--skip-link--target)

There are several ways to disable the new Widgets Block Editor.

## [Using remove\_theme\_support](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/\#using-remove_theme_support)

Themes may disable the Widgets Block Editor by calling `remove_theme_support( 'widgets-block-editor' )`.

For example, a theme may have the following PHP code in `functions.php`.

```php
function example_theme_support() {
    remove_theme_support( 'widgets-block-editor' );
}
add_action( 'after_setup_theme', 'example_theme_support' );

```

## [Using the Classic Widgets plugin](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/\#using-the-classic-widgets-plugin)

End users may disable the Widgets Block Editor by installing and activating the [Classic Widgets plugin](https://wordpress.org/plugins/classic-widgets/).

With this plugin installed, the Widgets Block Editor can be toggled on and off by deactivating and activating the plugin.

## [Using a filter](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/\#using-a-filter)

the `use_widgets_block_editor` filter controls whether or not the Widgets Block Editor is enabled.

For example, a site administrator may include the following PHP code in a mu-plugin to disable the Widgets Block Editor.

```php
add_filter( 'use_widgets_block_editor', '__return_false' );

```

For more advanced uses, you may supply your own function. In this example, the Widgets Block Editor is disabled for a specific user.

```php
function example_use_widgets_block_editor( $use_widgets_block_editor ) {
    if ( 123 === get_current_user_id() ) {
        return false;
    }
    return $use_widgets_block_editor;
}
add_filter( 'use_widgets_block_editor', 'example_use_widgets_block_editor' );

```

First published

May 8, 2021

Last updated

January 29, 2024

Edit article

[Improve it on GitHub: Restoring the classic Widgets Editor](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/widgets/opting-out.md)

[PreviousWidgets Block Editor overviewPrevious: Widgets Block Editor overview](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/)

[NextAbout the Legacy Widget blockNext: About the Legacy Widget block](https://developer.wordpress.org/block-editor/how-to-guides/widgets/legacy-widget-block/)

Notifications