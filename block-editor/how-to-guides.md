---
url: https://developer.wordpress.org/block-editor/how-to-guides
scraped_at: 2025-10-20T03:17:17.062Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

How-to Guides


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)How-to Guides

Search

# How-to Guides

## In this article

Table of Contents

- [Creating blocks](https://developer.wordpress.org/block-editor/how-to-guides/#creating-blocks)
- [Extending blocks](https://developer.wordpress.org/block-editor/how-to-guides/#extending-blocks)
- [Extending the Editor UI](https://developer.wordpress.org/block-editor/how-to-guides/#extending-the-editor-ui)
- [Meta boxes](https://developer.wordpress.org/block-editor/how-to-guides/#meta-boxes)
- [Theme support](https://developer.wordpress.org/block-editor/how-to-guides/#theme-support)
- [Autocomplete](https://developer.wordpress.org/block-editor/how-to-guides/#autocomplete)
- [Block parsing and serialization](https://developer.wordpress.org/block-editor/how-to-guides/#block-parsing-and-serialization)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/#wp--skip-link--target)

The new editor is highly flexible, like most of WordPress. You can build custom blocks, modify the editor’s appearance, add special plugins, and much more.

## [Creating blocks](https://developer.wordpress.org/block-editor/how-to-guides/\#creating-blocks)

The editor is about blocks, and the main extensibility API is the Block API. It allows you to create your own static blocks, [Dynamic Blocks](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/creating-dynamic-blocks/) ( rendered on the server ) and also blocks capable of saving data to Post Meta for more structured content.

If you want to learn more about block creation, see the [Create a Block tutorial](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/) for the best place to start.

## [Extending blocks](https://developer.wordpress.org/block-editor/how-to-guides/\#extending-blocks)

It is also possible to modify the behavior of existing blocks or even remove them completely using filters.

Learn more in the [Block Filters](https://developer.wordpress.org/block-editor/reference-guides/filters/block-filters/) section.

Specifically for `Query Loop` block, besides the available filters, there are more ways to extend it and create bespoke versions of it. Learn more in the [Extending the Query Loop block](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/extending-the-query-loop-block/) section.

## [Extending the Editor UI](https://developer.wordpress.org/block-editor/how-to-guides/\#extending-the-editor-ui)

Extending the editor UI can be accomplished with the `registerPlugin` API, allowing you to define all your plugin’s UI elements in one place.

Refer to the [Plugins](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-plugins/) and [Edit Post](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-edit-post/) section for more information.

You can also filter certain aspects of the editor; this is documented on the [Editor Filters](https://developer.wordpress.org/block-editor/reference-guides/filters/editor-filters/) page.

## [Meta boxes](https://developer.wordpress.org/block-editor/how-to-guides/\#meta-boxes)

Porting PHP meta boxes to blocks or sidebar plugins is highly encouraged, learn how in the [meta box](https://developer.wordpress.org/block-editor/how-to-guides/metabox/) and [sidebar plugin](https://developer.wordpress.org/block-editor/how-to-guides/plugin-sidebar-0/) guides.

## [Theme support](https://developer.wordpress.org/block-editor/how-to-guides/\#theme-support)

By default, blocks provide their styles to enable basic support for blocks in themes without any change. Themes can add/override these styles, or rely on defaults.

There are some advanced block features which require opt-in support in the theme. See [theme support](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-support/) and [how to filter global styles](https://developer.wordpress.org/block-editor/reference-guides/filters/global-styles-filters/).

## [Autocomplete](https://developer.wordpress.org/block-editor/how-to-guides/\#autocomplete)

Autocompleters within blocks may be extended and overridden. Learn more about the [autocomplete](https://developer.wordpress.org/block-editor/reference-guides/filters/autocomplete-filters/) filters.

## [Block parsing and serialization](https://developer.wordpress.org/block-editor/how-to-guides/\#block-parsing-and-serialization)

Posts in the editor move through a couple of different stages between being stored in `post_content` and appearing in the editor. Since the blocks themselves are data structures that live in memory it takes a parsing and serialization step to transform out from and into the stored format in the database.

Customizing the parser is an advanced topic that you can learn more about in the [Extending the Parser](https://developer.wordpress.org/block-editor/reference-guides/filters/parser-filters/) section.

First published

March 9, 2021

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: How-to Guides](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/README.md)

[PreviousFrequently Asked QuestionsPrevious: Frequently Asked Questions](https://developer.wordpress.org/block-editor/getting-started/faq/)

[NextAccessibilityNext: Accessibility](https://developer.wordpress.org/block-editor/how-to-guides/accessibility/)

Notifications