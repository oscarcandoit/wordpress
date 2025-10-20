---
url: https://developer.wordpress.org/block-editor/reference-guides/components/divider
scraped_at: 2025-10-20T03:24:01.686Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Divider


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Divider

Search

# Divider

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#props)
  - [margin: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#margin-number)
  - [marginEnd: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#marginend-number)
  - [marginStart: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#marginstart-number)
  - [orientation: horizontal \| vertical](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#orientation-horizontal-vertical)
  - [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#inherited-props)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/divider/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Divider` is a layout component that separates groups of related content.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#usage)

```jsx
import {
    __experimentalDivider as Divider,
    __experimentalText as Text,
    __experimentalVStack as VStack,
} from `@wordpress/components`;

function Example() {
    return (
        <VStack spacing={4}>
            <Text>Some text here</Text>
            <Divider />
            <Text>Some more text here</Text>
        </VStack>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#props)

### [margin: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#margin-number)

Adjusts all margins on the inline dimension.

- Required: No

### [marginEnd: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#marginend-number)

Adjusts the inline-end margin.

- Required: No

### [marginStart: number](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#marginstart-number)

Adjusts the inline-start margin.

- Required: No

### [orientation: horizontal \| vertical](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#orientation-horizontal-vertical)

Divider’s orientation. When using inside a flex container, you may need to make sure the divider is `stretch` aligned in order for it to be visible.

- Required: No
- Default: `horizontal`

### [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/divider/\#inherited-props)

`Divider` also inherits all of the [`Separator` props](https://ariakit.org/reference/separator#optional-props).

First published

May 7, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Divider](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/divider/README.md)

[PreviousDisabledPrevious: Disabled](https://developer.wordpress.org/block-editor/reference-guides/components/disabled/)

[NextDraggableNext: Draggable](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/)

Notifications