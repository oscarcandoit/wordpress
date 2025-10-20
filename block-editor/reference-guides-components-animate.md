---
url: https://developer.wordpress.org/block-editor/reference-guides/components/animate
scraped_at: 2025-10-20T03:21:07.518Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Animate


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Animate

Search

# Animate

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#props)
- [Available Animation Types](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#available-animation-types)
  - [appear](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#appear)
  - [loading](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#loading)
  - [slide-in](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#slide-in)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/animate/#wp--skip-link--target)

Simple interface to introduce animations to components.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#usage)

```jsx
import { Animate, Notice } from '@wordpress/components';

const MyAnimatedNotice = () => (
    <Animate type="slide-in" options={ { origin: 'top' } }>
        { ( { className } ) => (
            <Notice className={ className } status="success">
                <p>Animation finished.</p>
            </Notice>
        ) }
    </Animate>
);

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#props)

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| `type` | `string` | `undefined` | Type of the animation to use. |
| `options` | `object` | `{}` | Options of the chosen animation. |
| `children` | `function` | `undefined` | A callback receiving a list of props ( `className` ) to apply to the DOM element to animate. |

## [Available Animation Types](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#available-animation-types)

### [appear](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#appear)

This animation is meant for popover/modal content, such as menus appearing. It shows the height and width of the animated element scaling from 0 to full size, from its point of origin.

#### [Options](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#options)

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| `origin` | `string` | `top center` | Point of origin ( `top`, `bottom`, `middle right`, `left`, `center`). |

### [loading](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#loading)

This animation is meant to be used to indicate that activity is happening in the background. It is an infinitely-looping fade from 50% to full opacity. This animation has no options, and should be removed as soon as its relevant operation is completed.

### [slide-in](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#slide-in)

This animation is meant for sidebars and sliding menus. It shows the height and width of the animated element moving from a hidden position to its normal one.

#### [Options](https://developer.wordpress.org/block-editor/reference-guides/components/animate/\#options-2)

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| `origin` | `string` | `left` | Point of origin ( `left`). |

First published

March 9, 2021

Last updated

October 30, 2024

Edit article

[Improve it on GitHub: Animate](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/animate/README.md)

[PreviousAnglePickerControlPrevious: AnglePickerControl](https://developer.wordpress.org/block-editor/reference-guides/components/angle-picker-control/)

[NextAutocompleteNext: Autocomplete](https://developer.wordpress.org/block-editor/reference-guides/components/autocomplete/)

Notifications