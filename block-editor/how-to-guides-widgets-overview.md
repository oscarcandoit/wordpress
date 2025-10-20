---
url: https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview
scraped_at: 2025-10-20T03:16:46.362Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Widgets Block Editor overview


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)[Widgets](https://developer.wordpress.org/block-editor/how-to-guides/widgets/)Widgets Block Editor overview

Search

# Widgets Block Editor overview

## In this article

Table of Contents

- [Widgets Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/#widgets-block-editor)
  - [Customizer Widgets Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/#customizer-widgets-block-editor)
- [Compatibility](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/#compatibility)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/#wp--skip-link--target)

## [Widgets Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/\#widgets-block-editor)

The new Widgets Editor is a WordPress feature which upgrades widget areas to allow using blocks alongside widgets. It offers a new widget management experience built using the familiar WordPress block editor.

You can access the new Widgets Editor by navigating to Appearance → Widgets or Appearance → Customize → Widgets and choose a widget area.

The Widgets Block Editor allows you to insert blocks and widgets into any of the [Widget Areas or Sidebars](https://developer.wordpress.org/themes/functionality/sidebars/) defined by the site’s active theme, via a standalone editor or through the Customizer.

### [Customizer Widgets Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/\#customizer-widgets-block-editor)

The new Widgets Editor also replaces the Widgets section in the Customizer with the new block-based editor.

You can access the Customizer Widgets Block Editor by navigating to Appearance → Customize, selecting Widgets, and then selecting a Widget Area.

Using the new Widgets Editor through the Customizer goes beyond inserting blocks and widgets into a selected Widget Area, making use of the live preview of the changes, to the right of the editor, and of all the other Customizer specific features such as scheduling and sharing changes.

## [Compatibility](https://developer.wordpress.org/block-editor/how-to-guides/widgets/overview/\#compatibility)

Widgets that were added to a Widget Area before the new Widgets Editor will continue to work – via the Legacy Widget block.

The Legacy Widget block is the compatibility mechanism which allows us to edit and preview changes to a classic widget within the new block based Widgets Editor.

Any third party widgets registered by plugins can still be inserted in widget areas by adding and setting them up through a Legacy Widget block.

The Widgets Editor stores blocks using an underlying “Block” widget that is invisible to the user. This means that plugins and themes will continue to work normally, and that the Widgets Block Editor can be disabled without any data loss.

Themes may disable the Widgets Block Editor using `remove_theme_support( 'widgets-block-editor' )`.

Users may disable the Widgets Block Editor by installing the [Classic Widgets plugin](https://wordpress.org/plugins/classic-widgets/).

First published

May 8, 2021

Last updated

January 29, 2024

Edit article

[Improve it on GitHub: Widgets Block Editor overview](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/widgets/overview.md)

[PreviousWidgetsPrevious: Widgets](https://developer.wordpress.org/block-editor/how-to-guides/widgets/)

[NextRestoring the classic Widgets EditorNext: Restoring the classic Widgets Editor](https://developer.wordpress.org/block-editor/how-to-guides/widgets/opting-out/)

Notifications