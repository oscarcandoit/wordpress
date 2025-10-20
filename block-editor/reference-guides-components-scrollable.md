---
url: https://developer.wordpress.org/block-editor/reference-guides/components/scrollable
scraped_at: 2025-10-20T03:20:19.165Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Scrollable


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Scrollable

Search

# Scrollable

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#props)
  - [children: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#children-reactnode)
  - [scrollDirection: string](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#scrolldirection-string)
  - [smoothScroll: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#smoothscroll-boolean)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Scrollable` is a layout component that content in a scrollable container.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/\#usage)

```jsx
import { __experimentalScrollable as Scrollable } from '@wordpress/components';

function Example() {
    return (
        <Scrollable style={ { maxHeight: 200 } }>
            <div style={ { height: 500 } }>...</div>
        </Scrollable>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/\#props)

### [children: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/\#children-reactnode)

The children elements.

- Required: Yes

### [scrollDirection: string](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/\#scrolldirection-string)

Renders a scrollbar for a specific axis when content overflows.

- Required: No
- Default: `y`
- Allowed values: `x`, `y`, `auto`

### [smoothScroll: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/scrollable/\#smoothscroll-boolean)

Enables (CSS) smooth scrolling.

- Required: No
- Default: `false`

First published

June 7, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Scrollable](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/scrollable/README.md)

[PreviousScrollLockPrevious: ScrollLock](https://developer.wordpress.org/block-editor/reference-guides/components/scroll-lock/)

[NextSearchControlNext: SearchControl](https://developer.wordpress.org/block-editor/reference-guides/components/search-control/)

Notifications