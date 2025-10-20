---
url: https://developer.wordpress.org/block-editor/reference-guides/components/card-header
scraped_at: 2025-10-20T03:21:48.139Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

CardHeader


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)CardHeader

Search

# CardHeader

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#props)
  - [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#isborderless-boolean)
  - [isShady: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#isshady-boolean)
  - [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#size-string)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/#wp--skip-link--target)

`CardHeader` renders an optional header within a [`Card`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/).

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/\#usage)

```jsx
import { Card, CardHeader } from '@wordpress/components';

const Example = () => (
    <Card>
        <CardHeader>...</CardHeader>
        <CardBody>...</CardBody>
    </Card>
);

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/\#props)

Note: This component is connected to [`Card`‘s Context](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/#context). The value of the `size` and `isBorderless` props is derived from the `Card` parent component (if there is one). Setting these props directly on this component will override any derived values.

### [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/\#isborderless-boolean)

Renders without a border.

- Required: No
- Default: `false`

### [isShady: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/\#isshady-boolean)

Renders with a light gray background color.

- Required: No
- Default: `false`

### [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/\#size-string)

Determines the amount of padding within the component.

- Required: No
- Default: `medium`
- Allowed values: `xSmall`, `small`, `medium`, `large`

First published

June 10, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: CardHeader](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/card/card-header/README.md)

[PreviousCardFooterPrevious: CardFooter](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/)

[NextCardMediaNext: CardMedia](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/)

Notifications