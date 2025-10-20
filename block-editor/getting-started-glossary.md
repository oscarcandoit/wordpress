---
url: https://developer.wordpress.org/block-editor/getting-started/glossary
scraped_at: 2025-10-20T03:16:57.618Z
---

[Skip to content](https://developer.wordpress.org/block-editor/getting-started/glossary/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Glossary


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Getting Started](https://developer.wordpress.org/block-editor/getting-started/)Glossary

Search

# Glossary

## In this article

Table of Contents

- [Attribute sources](https://developer.wordpress.org/block-editor/getting-started/glossary/#attribute-sources)
- [Attributes](https://developer.wordpress.org/block-editor/getting-started/glossary/#attributes)
- [Block](https://developer.wordpress.org/block-editor/getting-started/glossary/#block)
- [Block Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-styles)
- [Block Supports](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-supports)
- [Block Theme](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-theme)
- [Block categories](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-categories)
- [Block ~Inserter~ Library](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-inserter-library)
- [Block name](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-name)
- [Block Templates](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-templates)
- [Block Template Parts](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-template-parts)
- [Block type](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-type)
- [Classic block](https://developer.wordpress.org/block-editor/getting-started/glossary/#classic-block)
- [Dynamic block](https://developer.wordpress.org/block-editor/getting-started/glossary/#dynamic-block)
- [Full Site Editing](https://developer.wordpress.org/block-editor/getting-started/glossary/#full-site-editing)
- [Global Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#global-styles)
- [Inspector](https://developer.wordpress.org/block-editor/getting-started/glossary/#inspector)
- [Local Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#local-styles)
- [Navigation Block](https://developer.wordpress.org/block-editor/getting-started/glossary/#navigation-block)
- [Patterns](https://developer.wordpress.org/block-editor/getting-started/glossary/#patterns)
- [Post settings](https://developer.wordpress.org/block-editor/getting-started/glossary/#post-settings)
- [Query Block](https://developer.wordpress.org/block-editor/getting-started/glossary/#query-block)
- [Reusable block](https://developer.wordpress.org/block-editor/getting-started/glossary/#reusable-block)
- [RichText](https://developer.wordpress.org/block-editor/getting-started/glossary/#richtext)
- [Serialization](https://developer.wordpress.org/block-editor/getting-started/glossary/#serialization)
- [Settings Sidebar](https://developer.wordpress.org/block-editor/getting-started/glossary/#settings-sidebar)
- [Site Editor](https://developer.wordpress.org/block-editor/getting-started/glossary/#site-editor)
- [Static block](https://developer.wordpress.org/block-editor/getting-started/glossary/#static-block)
- [Template Editing Mode](https://developer.wordpress.org/block-editor/getting-started/glossary/#template-editing-mode)
- [Theme Blocks](https://developer.wordpress.org/block-editor/getting-started/glossary/#theme-blocks)
- [TinyMCE](https://developer.wordpress.org/block-editor/getting-started/glossary/#tinymce)
- [Toolbar](https://developer.wordpress.org/block-editor/getting-started/glossary/#toolbar)

[↑ Back to top](https://developer.wordpress.org/block-editor/getting-started/glossary/#wp--skip-link--target)

## [Attribute sources](https://developer.wordpress.org/block-editor/getting-started/glossary/\#attribute-sources)

An object describing the attributes shape of a block. The keys can be named as most appropriate to describe the state of a block type. The value for each key is a function which describes the strategy by which the attribute value should be extracted from the content of a saved post’s content. When processed, a new object is created, taking the form of the keys defined in the attribute sources, where each value is the result of the attribute source function.

## [Attributes](https://developer.wordpress.org/block-editor/getting-started/glossary/\#attributes)

The object representation of the current state of a block in post content. When loading a saved post, this is determined by the attribute sources for the block type. These values can change over time during an editing session when the user modifies a block, and are used when determining how to serialize the block.

## [Block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block)

The abstract term used to describe units of markup that, composed together, form the content or layout of a webpage. The idea combines concepts of what in WordPress today we achieve with shortcodes, custom HTML, and embed discovery into a single consistent API and user experience.

## [Block Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-styles)

The CSS styles that are part of the block, either via its stylesheet or via the block markup itself. For example, a class attached to the block markup is considered block styles.

Compare to [Global Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#global-styles). In contraposition to Global Styles, block styles are sometimes referred to as [Local Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#local-styles).

Learn more about [Block Styles](https://developer.wordpress.org/block-editor/explanations/architecture/styles/#block-styles).

## [Block Supports](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-supports)

An API for blocks to declare what features they support. By declaring support for a feature, the API would add additional [attributes](https://developer.wordpress.org/block-editor/getting-started/glossary/#attributes) to the block and matching UI controls for most of the existing block supports.

See [Block Supports reference documentation](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-supports/) for a deep dive into the API.

## [Block Theme](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-theme)

A theme built in block forward way that allows Full Site Editing to work. The core of a block theme are its block templates and block template parts. To date, block theme templates have been HTML files of block markup that map to templates from the standard WordPress template hierarchy.

## [Block categories](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-categories)

These are not a WordPress taxonomy, but instead used internally to sort blocks in the Block Library.

## [Block ~Inserter~ Library](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-inserter-library)

Primary interface for selecting from the available blocks, triggered by plus icon buttons on Blocks or in the top-left of the editor interface.

## [Block name](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-name)

A unique identifier for a block type, consisting of a plugin-specific namespace and a short label describing the block’s intent. e.g. `core/image`

## [Block Templates](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-templates)

A template is a pre-defined arrangement of blocks, possibly with predefined attributes or placeholder content. You can provide a template for a post type, to give users a starting point when creating a new piece of content, or inside a custom block with the `InnerBlocks` component. At their core, templates are simply HTML files of block markup that map to templates from the standard WordPress template hierarchy, for example index, single or archive. This helps control the front-end defaults of a site that are not edited via the Page Editor or the Post Editor. See the [templates documentation](https://developer.wordpress.org/block-editor/developers/block-api/block-templates/) for more information.

## [Block Template Parts](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-template-parts)

Building on Block Templates, these parts help set structure for reusable items like a Footer or Header that one typically sees in a WordPress site. They are primarily site structure and are never to be mixed with the post content editor. With Full Site Editing and block based themes, users can create their own arbitrary Template Parts, save those in the database for their site, and re-use them throughout their site. Template parts are equivalent – in blocks – of theme template parts. They are generally defined by a theme first, carry some semantic meaning (could be swapped between themes such as a header), and can only be inserted in the site editor context (within “templates”).

## [Block type](https://developer.wordpress.org/block-editor/getting-started/glossary/\#block-type)

In contrast with the blocks composing a particular post, a block type describes the blueprint by which any block of that type should behave. So while there may be many images within a post, each behaves consistent with a unified image block type definition.

## [Classic block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#classic-block)

A block which embeds the TinyMCE editor as a block, TinyMCE was the base of the previous core editor. Older content created prior to the block editor will be loaded in to a single Classic block.

## [Dynamic block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#dynamic-block)

A type of block in which the content may change and cannot be determined at the time of saving a post, instead calculated any time the post is shown on the front of a site. These blocks may save fallback content or no content at all in their JavaScript implementation, instead deferring to a PHP block implementation for runtime rendering.

## [Full Site Editing](https://developer.wordpress.org/block-editor/getting-started/glossary/\#full-site-editing)

This refers to a collection of features that ultimately allows users to edit their entire website using blocks as the starting point. This feature set includes everything from block patterns to global styles to templates to design tools for blocks (and more). First released in WordPress 5.9.

## [Global Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/\#global-styles)

The CSS styles generated by WordPress and enqueued as an embedded stylesheet in the front end of the site. The stylesheet ID is `global-styles-inline-css`. The contents of this stylesheet come from the default `theme.json` of WordPress, the theme’s `theme.json`, and the styles provided by the user via the global styles sidebar in the site editor.

See [theme.json reference docs](https://developer.wordpress.org/block-editor/reference-guides/theme-json-reference/), the [how to guide](https://developer.wordpress.org/block-editor/how-to-guides/themes/global-settings-and-styles/), and an introduction to [styles in the block editor](https://developer.wordpress.org/block-editor/explanations/architecture/styles/).

Compare to [block styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-styles).

## [Inspector](https://developer.wordpress.org/block-editor/getting-started/glossary/\#inspector)

Deprecated term. See [Settings Sidebar.](https://developer.wordpress.org/block-editor/getting-started/glossary/#settings-sidebar)

## [Local Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/\#local-styles)

See [Block Styles](https://developer.wordpress.org/block-editor/getting-started/glossary/#block-styles).

## [Navigation Block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#navigation-block)

A block that allows you to edit a site’s navigation menu, both in terms of structure and design.

## [Patterns](https://developer.wordpress.org/block-editor/getting-started/glossary/\#patterns)

Patterns are predefined layouts of blocks that can be inserted as starter content that are meant to be changed by the user every time. Once inserted, they exist as a local save and are not global.

## [Post settings](https://developer.wordpress.org/block-editor/getting-started/glossary/\#post-settings)

A sidebar region containing metadata fields for the post, including scheduling, visibility, terms, and featured image.

## [Query Block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#query-block)

A block that replicates the classic [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) and allows for further customization with additional functionality.

## [Reusable block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#reusable-block)

A block that is saved and then can be shared as a reusable, repeatable piece of content.

## [RichText](https://developer.wordpress.org/block-editor/getting-started/glossary/\#richtext)

A common component enabling rich content editing including bold, italics, hyperlinks, etc.

## [Serialization](https://developer.wordpress.org/block-editor/getting-started/glossary/\#serialization)

The process of converting a block’s attributes object into HTML markup, which occurs each time a block is edited.

## [Settings Sidebar](https://developer.wordpress.org/block-editor/getting-started/glossary/\#settings-sidebar)

The panel on the right that contains the document and block settings. The sidebar is toggled using the Settings gear icon. Block settings are shown when a block is selected, otherwise document settings are shown.

## [Site Editor](https://developer.wordpress.org/block-editor/getting-started/glossary/\#site-editor)

The cohesive experience that allows you to directly edit and navigate between various templates, template parts, styling options, and more.

## [Static block](https://developer.wordpress.org/block-editor/getting-started/glossary/\#static-block)

A type of block where the content of which is known at the time of saving a post. A static block will be saved with HTML markup directly in post content.

## [Template Editing Mode](https://developer.wordpress.org/block-editor/getting-started/glossary/\#template-editing-mode)

A scaled down direct editing experience allowing you to edit/change/create the template a post/page uses.

## [Theme Blocks](https://developer.wordpress.org/block-editor/getting-started/glossary/\#theme-blocks)

Blocks that accomplish everything possible in traditional templates using template tags (ex: Post Author Block). A full list can be found [here](https://github.com/WordPress/gutenberg/issues/22724).

## [TinyMCE](https://developer.wordpress.org/block-editor/getting-started/glossary/\#tinymce)

[TinyMCE](https://www.tinymce.com/) is a web-based JavaScript WYSIWYG (What You See Is What You Get) editor.

## [Toolbar](https://developer.wordpress.org/block-editor/getting-started/glossary/\#toolbar)

A set of button controls. In the context of a block, usually referring to the toolbar of block controls shown above the selected block.

First published

March 10, 2021

Last updated

June 3, 2025

Edit article

[Improve it on GitHub: Glossary](https://github.com/WordPress/gutenberg/edit/trunk/docs/getting-started/glossary.md)

[PreviousWorking with JavaScript for the Block EditorPrevious: Working with JavaScript for the Block Editor](https://developer.wordpress.org/block-editor/getting-started/fundamentals/javascript-in-the-block-editor/)

[NextFrequently Asked QuestionsNext: Frequently Asked Questions](https://developer.wordpress.org/block-editor/getting-started/faq/)

Notifications