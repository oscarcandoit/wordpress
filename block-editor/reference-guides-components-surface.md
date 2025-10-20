---
url: https://developer.wordpress.org/block-editor/reference-guides/components/surface
scraped_at: 2025-10-20T03:21:12.916Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Surface


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Surface

Search

# Surface

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#props)
  - [backgroundSize: number](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#backgroundsize-number)
  - [borderBottom: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#borderbottom-boolean)
  - [borderLeft: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#borderleft-boolean)
  - [borderRight: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#borderright-boolean)
  - [borderTop: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#bordertop-boolean)
  - [variant: string](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#variant-string)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/surface/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Surface` is a core component that renders a primary background color.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#usage)

In the example below, notice how the `Surface` renders in white (or dark gray if in dark mode).

```jsx
import {
    __experimentalSurface as Surface,
    __experimentalText as Text,
} from '@wordpress/components';

function Example() {
    return (
        <Surface>
            <Text>Code is Poetry</Text>
        </Surface>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#props)

### [backgroundSize: number](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#backgroundsize-number)

- Required: No
- Default: `12`

Determines the grid size for “dotted” and “grid” variants.

### [borderBottom: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#borderbottom-boolean)

- Required: No
- Default: `false`

Renders a bottom border.

### [borderLeft: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#borderleft-boolean)

- Required: No
- Default: `false`

Renders a left border.

### [borderRight: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#borderright-boolean)

- Required: No
- Default: `false`

Renders a right border.

### [borderTop: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#bordertop-boolean)

- Required: No
- Default: `false`

Renders a top border.

### [variant: string](https://developer.wordpress.org/block-editor/reference-guides/components/surface/\#variant-string)

- Required: No
- Default: `false`
- Allowed values: `primary`, `secondary`, `tertiary`, `dotted`, `grid`

Modifies the background color of `Surface`.

- `primary`: Used for almost all cases.
- `secondary`: Used as a secondary background for inner `Surface` components.
- `tertiary`: Used as the app/site wide background. Visible in **dark mode** only. Use case is rare.
- `grid`: Used to show a grid.
- `dotted`: Used to show a dots grid.

First published

June 8, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Surface](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/surface/README.md)

[PreviousSpinnerPrevious: Spinner](https://developer.wordpress.org/block-editor/reference-guides/components/spinner/)

[NextTabPanelNext: TabPanel](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/)

Notifications