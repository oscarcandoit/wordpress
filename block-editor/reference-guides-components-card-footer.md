---
url: https://developer.wordpress.org/block-editor/reference-guides/components/card-footer
scraped_at: 2025-10-20T03:22:58.296Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

CardFooter


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)CardFooter

Search

# CardFooter

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#usage)
  - [Flex](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#flex)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#props)
  - [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#isborderless-boolean)
  - [isShady: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#isshady-boolean)
  - [justify: CSSProperties\[ ‘justifyContent’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#justify-cssproperties-justifycontent)
  - [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#size-string)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/#wp--skip-link--target)

`CardFooter` renders an optional footer within a [`Card`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/).

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#usage)

```jsx
import { Card, CardFooter } from '@wordpress/components';

const Example = () => (
    <Card>
        <CardBody>...</CardBody>
        <CardFooter>...</CardFooter>
    </Card>
);

```

### [Flex](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#flex)

Underneath, `CardFooter` uses the [`Flex` layout component](https://developer.wordpress.org/block-editor/reference-guide/components/flex/flex/). This improves the alignment of child items within the component.

```jsx
import {
    Button,
    Card,
    CardFooter,
    FlexItem,
    FlexBlock,
} from '@wordpress/components';

const Example = () => (
    <Card>
        <CardBody>...</CardBody>
        <CardFooter>
            <FlexBlock>Content</FlexBlock>
            <FlexItem>
                <Button>Action</Button>
            </FlexItem>
        </CardFooter>
    </Card>
);

```

Check out [the documentation](https://developer.wordpress.org/block-editor/reference-guide/components/flex/flex/) on `Flex` for more details on layout composition.

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#props)

Note: This component is connected to [`Card`‘s Context](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/#context). The value of the `size` and `isBorderless` props is derived from the `Card` parent component (if there is one). Setting these props directly on this component will override any derived values.

### [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#isborderless-boolean)

Renders without a border.

- Required: No
- Default: `false`

### [isShady: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#isshady-boolean)

Renders with a light gray background color.

- Required: No
- Default: `false`

### [justify: CSSProperties\[ ‘justifyContent’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#justify-cssproperties-justifycontent)

See the documentation for the `justify` prop for the [`Flex` component](https://developer.wordpress.org/block-editor/reference-guide/components/flex/flex/#justify)

### [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/\#size-string)

Determines the amount of padding within the component.

- Required: No
- Default: `medium`
- Allowed values: `xSmall`, `small`, `medium`, `large`

First published

June 10, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: CardFooter](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/card/card-footer/README.md)

[PreviousCardDividerPrevious: CardDivider](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/)

[NextCardHeaderNext: CardHeader](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/)

Notifications