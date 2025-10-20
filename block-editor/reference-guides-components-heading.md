---
url: https://developer.wordpress.org/block-editor/reference-guides/components/heading
scraped_at: 2025-10-20T03:19:14.083Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/heading/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Heading


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Heading

Search

# Heading

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/heading/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/heading/#props)
  - [level: 1 \| 2 \| 3 \| 4 \| 5 \| 6 \| ‘1’ \| ‘2’ \| ‘3’ \| ‘4’ \| ‘5’ \| ‘6’](https://developer.wordpress.org/block-editor/reference-guides/components/heading/#level-1-2-3-4-5-6-1-2-3-4-5-6)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/heading/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Heading` renders headings and titles using the library’s typography system.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/heading/\#usage)

```jsx
import { __experimentalHeading as Heading } from '@wordpress/components';

function Example() {
    return <Heading>Code is Poetry</Heading>;
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/heading/\#props)

`Heading` uses `Text` underneath, so we have access to all of `Text`‘s props except for:

- `size` which is replaced by `level`;
- `isBlock`‘s default value, which is `true` for the `Heading` component.

For a complete list of those props, check out [`Text`](https://developer.wordpress.org/block-editor/reference-guide/components/text/#props).

### [level: 1 \| 2 \| 3 \| 4 \| 5 \| 6 \| ‘1’ \| ‘2’ \| ‘3’ \| ‘4’ \| ‘5’ \| ‘6’](https://developer.wordpress.org/block-editor/reference-guides/components/heading/\#level-1-2-3-4-5-6-1-2-3-4-5-6)

Passing any of the heading levels to `level` will both render the correct typographic text size as well as the semantic element corresponding to the level ( `h1` for `1` for example).

- Required: No
- Default: `2`

First published

April 30, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Heading](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/heading/README.md)

[PreviousHStackPrevious: HStack](https://developer.wordpress.org/block-editor/reference-guides/components/h-stack/)

[NextNavigateRegionsNext: NavigateRegions](https://developer.wordpress.org/block-editor/reference-guides/components/navigate-regions/)

Notifications