---
url: https://developer.wordpress.org/block-editor/reference-guides/components/z-stack
scraped_at: 2025-10-20T03:23:06.784Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ZStack


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)ZStack

Search

# ZStack

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#props)
  - [isLayered: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#islayered-boolean)
  - [isReversed: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#isreversed-boolean)
  - [offset: number](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#offset-number)
  - [children: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#children-reactnode)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#usage)

`ZStack` allows you to stack things along the Z-axis.

```jsx
import { __experimentalZStack as ZStack } from '@wordpress/components';

function Example() {
    return (
        <ZStack offset={ 20 } isLayered>
            <ExampleImage />
            <ExampleImage />
            <ExampleImage />
        </ZStack>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#props)

### [isLayered: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#islayered-boolean)

Layers children elements on top of each other (first: highest z-index, last: lowest z-index).

- Required: No
- Default: `true`

### [isReversed: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#isreversed-boolean)

Reverse the layer ordering (first: lowest z-index, last: highest z-index).

- Required: No
- Default: `false`

### [offset: number](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#offset-number)

The amount of space between each child element. Its value is automatically inverted (i.e. from positive to negative, and viceversa) when switching from LTR to RTL.

- Required: No
- Default: `0`

### [children: ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/\#children-reactnode)

The children to stack.

- Required: Yes

First published

May 21, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: ZStack](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/z-stack/README.md)

[PreviousVisuallyHiddenPrevious: VisuallyHidden](https://developer.wordpress.org/block-editor/reference-guides/components/visually-hidden/)

[NextPackage ReferenceNext: Package Reference](https://developer.wordpress.org/block-editor/reference-guides/packages/)

Notifications