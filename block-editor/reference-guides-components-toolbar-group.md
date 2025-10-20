---
url: https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group
scraped_at: 2025-10-20T03:24:10.426Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ToolbarGroup


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)ToolbarGroup

Search

# ToolbarGroup

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/#usage)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/#props)
- [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/#related-components)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/#wp--skip-link--target)

A ToolbarGroup can be used to create subgroups of controls inside a [Toolbar](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar/toolbar/).

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/\#usage)

```jsx
import { Toolbar, ToolbarGroup, ToolbarButton } from '@wordpress/components';
import { paragraph, formatBold, formatItalic, link } from '@wordpress/icons';

function MyToolbar() {
    return (
        <Toolbar label="Options">
            <ToolbarGroup>
                <ToolbarButton icon={ paragraph } label="Paragraph" />
            </ToolbarGroup>
            <ToolbarGroup>
                <ToolbarButton icon={ formatBold } label="Bold" />
                <ToolbarButton icon={ formatItalic } label="Italic" />
                <ToolbarButton icon={ link } label="Link" />
            </ToolbarGroup>
        </Toolbar>
    );
}

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/\#props)

ToolbarGroup will pass all HTML props to the underlying element.

## [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-group/\#related-components)

- ToolbarGroup may contain [ToolbarButton](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar/toolbar-button/) and [ToolbarItem](https://developer.wordpress.org/block-editor/reference-guide/components/toolbar/toolbar-item/) as children.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: ToolbarGroup](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/toolbar/toolbar-group/README.md)

[PreviousToolbarDropdownMenuPrevious: ToolbarDropdownMenu](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-dropdown-menu/)

[NextToolbarItemNext: ToolbarItem](https://developer.wordpress.org/block-editor/reference-guides/components/toolbar-item/)

Notifications