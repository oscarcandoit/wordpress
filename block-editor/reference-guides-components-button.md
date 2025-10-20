---
url: https://developer.wordpress.org/block-editor/reference-guides/components/button
scraped_at: 2025-10-20T03:20:42.386Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/button/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Button


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Button

Search

# Button

## In this article

Table of Contents

- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/button/#props)
  - [\_\_next40pxDefaultSize](https://developer.wordpress.org/block-editor/reference-guides/components/button/#__next40pxdefaultsize)
  - [accessibleWhenDisabled](https://developer.wordpress.org/block-editor/reference-guides/components/button/#accessiblewhendisabled)
  - [children](https://developer.wordpress.org/block-editor/reference-guides/components/button/#children)
  - [description](https://developer.wordpress.org/block-editor/reference-guides/components/button/#description)
  - [disabled](https://developer.wordpress.org/block-editor/reference-guides/components/button/#disabled)
  - [href](https://developer.wordpress.org/block-editor/reference-guides/components/button/#href)
  - [icon](https://developer.wordpress.org/block-editor/reference-guides/components/button/#icon)
  - [iconPosition](https://developer.wordpress.org/block-editor/reference-guides/components/button/#iconposition)
  - [iconSize](https://developer.wordpress.org/block-editor/reference-guides/components/button/#iconsize)
  - [isBusy](https://developer.wordpress.org/block-editor/reference-guides/components/button/#isbusy)
  - [isDestructive](https://developer.wordpress.org/block-editor/reference-guides/components/button/#isdestructive)
  - [isPressed](https://developer.wordpress.org/block-editor/reference-guides/components/button/#ispressed)
  - [label](https://developer.wordpress.org/block-editor/reference-guides/components/button/#label)
  - [shortcut](https://developer.wordpress.org/block-editor/reference-guides/components/button/#shortcut)
  - [showTooltip](https://developer.wordpress.org/block-editor/reference-guides/components/button/#showtooltip)
  - [size](https://developer.wordpress.org/block-editor/reference-guides/components/button/#size)
  - [text](https://developer.wordpress.org/block-editor/reference-guides/components/button/#text)
  - [tooltipPosition](https://developer.wordpress.org/block-editor/reference-guides/components/button/#tooltipposition)
  - [target](https://developer.wordpress.org/block-editor/reference-guides/components/button/#target)
  - [variant](https://developer.wordpress.org/block-editor/reference-guides/components/button/#variant)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/button/#wp--skip-link--target)

See the [WordPress Storybook](https://wordpress.github.io/gutenberg/?path=/docs/components-button--docs) for more detailed, interactive documentation.

Lets users take actions and make choices with a single click or tap.

```jsx
import { Button } from '@wordpress/components';
const Mybutton = () => (
  <Button
    variant="primary"
    onClick={ handleClick }
  >
    Click here
  </Button>
);

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#props)

### [\_\_next40pxDefaultSize](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#__next40pxdefaultsize)

- Type: `boolean`
- Required: No
- Default: `false`

Start opting into the larger default height that will become the

default size in a future version.

### [accessibleWhenDisabled](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#accessiblewhendisabled)

- Type: `boolean`
- Required: No
- Default: `false`

Whether to keep the button focusable when disabled.

In most cases, it is recommended to set this to `true`. Disabling a control without maintaining focusability

can cause accessibility issues, by hiding their presence from screen reader users,

or by preventing focus from returning to a trigger element.

Learn more about the [focusability of disabled controls](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/#focusabilityofdisabledcontrols)

in the WAI-ARIA Authoring Practices Guide.

### [children](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#children)

- Type: `ReactNode`
- Required: No

The button’s children.

### [description](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#description)

- Type: `string`
- Required: No

A visually hidden accessible description for the button.

### [disabled](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#disabled)

- Type: `boolean`
- Required: No

Whether the button is disabled. If `true`, this will force a `button` element

to be rendered, even when an `href` is given.

In most cases, it is recommended to also set the `accessibleWhenDisabled` prop to `true`.

### [href](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#href)

- Type: `string`
- Required: Yes

If provided, renders `a` instead of `button`.

### [icon](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#icon)

- Type: `IconType`
- Required: No

If provided, renders an Icon component inside the button.

### [iconPosition](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#iconposition)

- Type: `"left" | "right"`
- Required: No
- Default: `'left'`

If provided with `icon`, sets the position of icon relative to the `text`.

### [iconSize](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#iconsize)

- Type: `number`
- Required: No

If provided with `icon`, sets the icon size.

Please refer to the Icon component for more details regarding

the default value of its `size` prop.

### [isBusy](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#isbusy)

- Type: `boolean`
- Required: No

Indicates activity while a action is being performed.

### [isDestructive](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#isdestructive)

- Type: `boolean`
- Required: No

Renders a red text-based button style to indicate destructive behavior.

### [isPressed](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#ispressed)

- Type: `boolean`
- Required: No

Renders a pressed button style.

### [label](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#label)

- Type: `string`
- Required: No

Sets the `aria-label` of the component, if none is provided.

Sets the Tooltip content if `showTooltip` is provided.

### [shortcut](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#shortcut)

- Type: `string | { display: string; ariaLabel: string; }`
- Required: No

If provided with `showTooltip`, appends the Shortcut label to the tooltip content.

If an object is provided, it should contain `display` and `ariaLabel` keys.

### [showTooltip](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#showtooltip)

- Type: `boolean`
- Required: No

If provided, renders a Tooltip component for the button.

### [size](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#size)

- Type: `"small" | "default" | "compact"`
- Required: No
- Default: `'default'`

The size of the button.

- `'default'`: For normal text-label buttons, unless it is a toggle button.
- `'compact'`: For toggle buttons, icon buttons, and buttons when used in context of either.
- `'small'`: For icon buttons associated with more advanced or auxiliary features.

If the deprecated `isSmall` prop is also defined, this prop will take precedence.

### [text](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#text)

- Type: `string`
- Required: No

If provided, displays the given text inside the button. If the button contains children elements, the text is displayed before them.

### [tooltipPosition](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#tooltipposition)

- Type: `"top" | "middle" | "bottom" | "top center" | "top left" | "top right" | "middle center" | "middle left" | "middle right" | "bottom center" | ...`
- Required: No

If provided with `showTooltip`, sets the position of the tooltip.

Please refer to the Tooltip component for more details regarding the defaults.

### [target](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#target)

- Type: `string`
- Required: No

If provided with `href`, sets the `target` attribute to the `a`.

### [variant](https://developer.wordpress.org/block-editor/reference-guides/components/button/\#variant)

- Type: `"link" | "primary" | "secondary" | "tertiary"`
- Required: No

Specifies the button’s style.

The accepted values are:

1. `'primary'` (the primary button styles)
2. `'secondary'` (the default button styles)
3. `'tertiary'` (the text-based button styles)
4. `'link'` (the link button styles)

First published

March 9, 2021

Last updated

December 26, 2024

Edit article

[Improve it on GitHub: Button](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/button/README.md)

[PreviousButtonGroupPrevious: ButtonGroup](https://developer.wordpress.org/block-editor/reference-guides/components/button-group/)

[NextDateCalendarNext: DateCalendar](https://developer.wordpress.org/block-editor/reference-guides/components/date-calendar/)

Notifications