---
url: https://developer.wordpress.org/block-editor/reference-guides/components/elevation
scraped_at: 2025-10-20T03:21:24.342Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Elevation


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Elevation

Search

# Elevation

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#props)
  - [active: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#active-number)
  - [borderRadius: CSSProperties\[ ‘borderRadius’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#borderradius-cssproperties-borderradius)
  - [focus: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#focus-number)
  - [hover: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#hover-number)
  - [isInteractive: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#isinteractive-boolean)
  - [offset: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#offset-number)
  - [value: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#value-number)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Elevation` is a core component that renders shadow, using the component system’s shadow system.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#usage)

The shadow effect is generated using the `value` prop.

```jsx
import {
    __experimentalElevation as Elevation,
    __experimentalSurface as Surface,
    __experimentalText as Text,
} from '@wordpress/components';

function Example() {
    return (
        <Surface>
            <Text>Code is Poetry</Text>
            <Elevation value={ 5 } />
        </Surface>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#props)

### [active: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#active-number)

Size of the shadow value when active (see the `value` and `isInteractive` props).

- Required: No

### [borderRadius: CSSProperties\[ ‘borderRadius’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#borderradius-cssproperties-borderradius)

Renders the border-radius of the shadow.

- Required: No
- Default: `inherit`

### [focus: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#focus-number)

Size of the shadow value when focused (see the `value` and `isInteractive` props).

- Required: No

### [hover: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#hover-number)

Size of the shadow value when hovered (see the `value` and `isInteractive` props).

- Required: No

### [isInteractive: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#isinteractive-boolean)

Determines if `hover`, `active`, and `focus` shadow values should be automatically calculated and rendered.

- Required: No
- Default: `false`

### [offset: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#offset-number)

Dimensional offsets (margin) for the shadow.

- Required: No
- Default: `0`

### [value: number](https://developer.wordpress.org/block-editor/reference-guides/components/elevation/\#value-number)

Size of the shadow, based on the Style system’s elevation system. The `value` determines the strength of the shadow, which sense of depth.

In the example below, `isInteractive` is activated to give a better sense of depth.

```jsx
import { __experimentalElevation as Elevation } from '@wordpress/components';

function Example() {
    return (
        <div>
            <Elevation isInteractive value={ 200 } />
        </div>
    );
}

```

- Required: No
- Default: `0`

First published

May 21, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Elevation](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/elevation/README.md)

[PreviousDuotonePickerPrevious: DuotonePicker](https://developer.wordpress.org/block-editor/reference-guides/components/duotone-picker/)

[NextExternalLinkNext: ExternalLink](https://developer.wordpress.org/block-editor/reference-guides/components/external-link/)

Notifications