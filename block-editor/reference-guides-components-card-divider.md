---
url: https://developer.wordpress.org/block-editor/reference-guides/components/card-divider
scraped_at: 2025-10-20T03:22:53.278Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

CardDivider


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)CardDivider

Search

# CardDivider

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/#props)
  - [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/#inherited-props)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/#wp--skip-link--target)

`CardDivider` renders an optional divider within a [`Card`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/). It is typically used to divide multiple `CardBody` components from each other.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/\#usage)

```jsx
import { Card, CardBody, CardDivider } from '@wordpress/components';

const Example = () => (
    <Card>
        <CardBody>...</CardBody>
        <CardDivider />
        <CardBody>...</CardBody>
    </Card>
);

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/\#props)

### [Inherited props](https://developer.wordpress.org/block-editor/reference-guides/components/card-divider/\#inherited-props)

`CardDivider` inherits all of the [`Divider` props](https://developer.wordpress.org/block-editor/reference-guide/components/divider/#props).

First published

June 10, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: CardDivider](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/card/card-divider/README.md)

[PreviousCardBodyPrevious: CardBody](https://developer.wordpress.org/block-editor/reference-guides/components/card-body/)

[NextCardFooterNext: CardFooter](https://developer.wordpress.org/block-editor/reference-guides/components/card-footer/)

Notifications