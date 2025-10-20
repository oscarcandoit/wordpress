---
url: https://developer.wordpress.org/block-editor/reference-guides/components/card
scraped_at: 2025-10-20T03:19:22.022Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/card/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Card


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Card

Search

# Card

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card/#props)
  - [elevation: number](https://developer.wordpress.org/block-editor/reference-guides/components/card/#elevation-number)
  - [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card/#isborderless-boolean)
  - [isRounded: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card/#isrounded-boolean)
  - [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card/#size-string)
  - [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/card/#inherited-props)
- [Sub-Components](https://developer.wordpress.org/block-editor/reference-guides/components/card/#sub-components)
  - [Sub-Components Example](https://developer.wordpress.org/block-editor/reference-guides/components/card/#sub-components-example)
  - [Context](https://developer.wordpress.org/block-editor/reference-guides/components/card/#context)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/card/#wp--skip-link--target)

`Card` provides a flexible and extensible content container.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#usage)

`Card` also provides a convenient set of [sub-components](https://developer.wordpress.org/block-editor/reference-guides/components/card/#sub-components) such as `CardBody`, `CardHeader`, `CardFooter`, and more (see below).

```jsx
import {
    Card,
    CardHeader,
    CardBody,
    CardFooter,
    __experimentalText as Text,
    __experimentalHeading as Heading,
} from '@wordpress/components';

function Example() {
    return (
        <Card>
            <CardHeader>
                <Heading level={ 4 }>Card Title</Heading>
            </CardHeader>
            <CardBody>
                <Text>Card Content</Text>
            </CardBody>
            <CardFooter>
                <Text>Card Footer</Text>
            </CardFooter>
        </Card>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#props)

### [elevation: number](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#elevation-number)

Size of the elevation shadow, based on the Style system’s elevation system. This may be helpful in highlighting certain content. For more information, check out [`Elevation`](https://developer.wordpress.org/block-editor/reference-guide/components/elevation/).

- Required: No
- Default: `0`

### [isBorderless: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#isborderless-boolean)

Renders without a border.

- Required: No
- Default: `false`

### [isRounded: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#isrounded-boolean)

Renders with rounded corners.

- Required: No
- Default: `true`

### [size: string](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#size-string)

Determines the amount of padding within the component.

- Required: No
- Default: `medium`
- Allowed values: `xSmall`, `small`, `medium`, `large`

### [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#inherited-props)

`Card` also inherits all of the [`Surface` props](https://developer.wordpress.org/block-editor/reference-guide/components/surface/#props).

## [Sub-Components](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#sub-components)

This component provides a collection of sub-component that can be used to compose various interfaces.

- [`<CardBody />`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card-body/)
- [`<CardDivider />`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card-divider/)
- [`<CardFooter />`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card-footer/))
- [`<CardHeader />`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card-header/))
- [`<CardMedia />`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card-media/))

### [Sub-Components Example](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#sub-components-example)

```jsx
import {
    Card,
    CardBody,
    CardDivider,
    CardFooter,
    CardHeader,
    CardMedia,
} from '@wordpress/components';

const Example = () => (
    <Card>
        <CardHeader>...</CardHeader>
        <CardBody>...</CardBody>
        <CardDivider />
        <CardBody>...</CardBody>
        <CardMedia>
            <img src="..." />
        </CardMedia>
        <CardFooter>...</CardFooter>
    </Card>
);

```

### [Context](https://developer.wordpress.org/block-editor/reference-guides/components/card/\#context)

`<Card />`‘s sub-components are connected to `<Card />` using [Context](https://react.dev/learn/passing-data-deeply-with-context). Certain props like `size` and `isBorderless` are passed through to some of the sub-components.

In the following example, the `<CardBody />` will render with a size of `small`:

```jsx
import { Card, CardBody } from '@wordpress/components';

const Example = () => (
    <Card size="small">
        <CardBody>...</CardBody>
    </Card>
);

```

These sub-components are designed to be flexible. The Context props can be overridden by the sub-component(s) as required. In the following example, the last `<CardBody />` will render it’s specified size:

```jsx
import { Card, CardBody } from '@wordpress/components';

const Example = () => (
    <Card size="small">
        <CardBody>...</CardBody>
        <CardBody>...</CardBody>
        <CardBody size="large">...</CardBody>
    </Card>
);

```

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Card](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/card/card/README.md)

[PreviousCardMediaPrevious: CardMedia](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/)

[NextCheckboxControlNext: CheckboxControl](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/)

Notifications