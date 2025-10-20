---
url: https://developer.wordpress.org/block-editor/reference-guides/components/flex
scraped_at: 2025-10-20T03:21:20.323Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Flex


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Flex

Search

# Flex

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#props)
  - [align: CSSProperties\[‘alignItems’\]](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#align-csspropertiesalignitems)
  - [direction: ResponsiveCSSValue<CSSProperties\[‘flexDirection’\]>](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#direction-responsivecssvaluecsspropertiesflexdirection)
  - [expanded: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#expanded-boolean)
  - [gap: number](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#gap-number)
  - [justify: CSSProperties\[‘justifyContent’\]](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#justify-csspropertiesjustifycontent)
  - [wrap: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#wrap-boolean)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/flex/#wp--skip-link--target)

`Flex` is a primitive layout component that adaptively aligns child content horizontally or vertically. `Flex` powers components like `HStack` and `VStack`.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#usage)

`Flex` is used with any of it’s two sub-components, `FlexItem` and `FlexBlock`.

```jsx
import { Flex, FlexBlock, FlexItem } from '@wordpress/components';

function Example() {
    return (
        <Flex>
            <FlexItem>
                <p>Code</p>
            </FlexItem>
            <FlexBlock>
                <p>Poetry</p>
            </FlexBlock>
        </Flex>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#props)

### [align: CSSProperties\[‘alignItems’\]](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#align-csspropertiesalignitems)

Aligns children using CSS Flexbox `align-items`. Vertically aligns content if the `direction` is `row`, or horizontally aligns content if the `direction` is `column`.

- Required: No
- Default: `center`

### [direction: ResponsiveCSSValue<CSSProperties\[‘flexDirection’\]>](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#direction-responsivecssvaluecsspropertiesflexdirection)

The direction flow of the children content can be adjusted with `direction`. `column` will align children vertically and `row` will align children horizontally.

- Required: No
- Default: `row`

### [expanded: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#expanded-boolean)

Expands to the maximum available width (if horizontal) or height (if vertical).

- Required: No
- Default: `true`

### [gap: number](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#gap-number)

Spacing in between each child can be adjusted by using `gap`. The value of `gap` works as a multiplier to the library’s grid system (base of `4px`).

- Required: No
- Default: `2`

### [justify: CSSProperties\[‘justifyContent’\]](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#justify-csspropertiesjustifycontent)

Horizontally aligns content if the `direction` is `row`, or vertically aligns content if the `direction` is `column`.

- Required: No
- Default: `space-between`

### [wrap: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flex/\#wrap-boolean)

Determines if children should wrap.

- Required: No
- Default: `false`

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Flex](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/flex/flex/README.md)

[PreviousFlexItemPrevious: FlexItem](https://developer.wordpress.org/block-editor/reference-guides/components/flex-item/)

[NextFocalPointPickerNext: FocalPointPicker](https://developer.wordpress.org/block-editor/reference-guides/components/focal-point-picker/)

Notifications