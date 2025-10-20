---
url: https://developer.wordpress.org/block-editor/reference-guides/components/card-media
scraped_at: 2025-10-20T03:24:15.247Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

CardMedia


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)CardMedia

Search

# CardMedia

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/#usage)
- [Placement](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/#placement)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/#wp--skip-link--target)

`CardMedia` provides a container for full-bleed content within a [`Card`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/), such as images, video, or even just a background color.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/\#usage)

```jsx
import { Card, CardBody, CardMedia } from '@wordpress/components';

const Example = () => (
    <Card>
        <CardMedia>
            <img src="..." />
        </CardMedia>
        <CardBody>...</CardBody>
    </Card>
);

```

## [Placement](https://developer.wordpress.org/block-editor/reference-guides/components/card-media/\#placement)

`CardMedia` can be placed in any order as a direct child of a `Card` (it can also exist as the only child component). The styles will automatically round the corners of the inner media element.

First published

June 10, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: CardMedia](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/card/card-media/README.md)

[PreviousCardHeaderPrevious: CardHeader](https://developer.wordpress.org/block-editor/reference-guides/components/card-header/)

[NextCardNext: Card](https://developer.wordpress.org/block-editor/reference-guides/components/card/)

Notifications