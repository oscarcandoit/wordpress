---
url: https://developer.wordpress.org/block-editor/reference-guides/components/toolbar
scraped_at: 2025-10-20T03:19:38.348Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Toolbar


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Toolbar

Search

# Toolbar

## In this article

Table of Contents

- [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#design-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#usage)
  - [Best practices](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#best-practices)
  - [States](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#states)
- [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#development-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#usage-2)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#props)
- [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#related-components)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/#wp--skip-link--target)

Toolbar can be used to group related options. To emphasize groups of related icon buttons, a toolbar should share a common container.

![Toolbar component above an image block](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_96EC471FE9C9D91A996770229947AAB54A03351BDE98F444FD3C1BF0CED365EA_1541782974545_ButtonGroup.png?ssl=1)

## [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#design-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#usage)

### [Best practices](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#best-practices)

Toolbars should:

- **Clearly communicate that clicking or tapping will trigger an action.**
- **Use established colors appropriately.** For example, only use red for actions that are difficult or impossible to undo.
- When used with a block, have a consistent location above the block. **Otherwise, have a consistent location in the interface.**

![A toolbar attached to the top left side of a block. (1. Toolbar, 2. Block)](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_D8D19E5A314C2D056B8CCC92B2DB5E27164936A0C5ED98A4C2DFDA650BE2A771_1542388042335_toolbar-block.png?ssl=1)

### [States](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#states)

#### [Active and available toolbars](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#active-and-available-toolbars)

A toolbar’s state makes it clear which icon button is active. Hover and focus states express the available selection options for icon buttons in a toolbar.

![Toolbar component](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_96EC471FE9C9D91A996770229947AAB54A03351BDE98F444FD3C1BF0CED365EA_1541784539545_ButtonGroup.png?ssl=1)

#### [Disabled toolbars](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#disabled-toolbars)

Toolbars that cannot be selected can either be given a disabled state, or be hidden.

## [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#development-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#usage-2)

```jsx
import { Toolbar, ToolbarButton } from '@wordpress/components';
import { formatBold, formatItalic, link } from '@wordpress/icons';

function MyToolbar() {
    return (
        <Toolbar label="Options">
            <ToolbarButton icon={ formatBold } label="Bold" />
            <ToolbarButton icon={ formatItalic } label="Italic" />
            <ToolbarButton icon={ link } label="Link" />
        </Toolbar>
    );
}

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#props)

Toolbar will pass all HTML props to the underlying element. Additionally, you can pass the custom props specified below.

#### [className: string](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#classname-string)

Class to set on the container div.

- Required: No

#### [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#label-string)

An accessible label for the toolbar.

- Required: Yes

#### [variant: ‘unstyled’ \| undefined](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#variant-unstyled-undefined)

Specifies the toolbar’s style.

Leave undefined for the default style. Or `'unstyled'` which removes the border from the toolbar, but keeps the default popover style.

- Required: No
- Default: `undefined`

#### [orientation: ‘horizontal’ \| ‘vertical’](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#orientation-horizontal-vertical)

Specifies the toolbar’s orientation.

Leave undefined or ‘horizontal’ for horizontal orientation keyboard interactions, choose ‘vertical’ for the alternative.

- Required: No
- Default: `horizontal`

## [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar/\#related-components)

- Toolbar may contain [ToolbarGroup](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar-group/), [ToolbarButton](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar-button/) and [ToolbarItem](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar-Item/) as children.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Toolbar](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/toolbar/toolbar/README.md)

[PreviousToolbarItemPrevious: ToolbarItem](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-item/)

[NextToolsPanelHeaderNext: ToolsPanelHeader](https://developer.wordpress.org/block-editor/reference-guides/components/tools-panel-header/)

Notifications