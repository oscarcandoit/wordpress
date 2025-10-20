---
url: https://developer.wordpress.org/block-editor/reference-guides/components/flyout
scraped_at: 2025-10-20T03:20:33.706Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Flyout


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Flyout

Search

# Flyout

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#props)
  - [state: PopoverStateReturn](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#state-popoverstatereturn)
  - [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#label-string)
  - [animated: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#animated-boolean)
  - [animationDuration: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#animationduration-boolean)
  - [baseId: string](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#baseid-string)
  - [elevation: number](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#elevation-number)
  - [maxWidth: CSSProperties\[ ‘maxWidth’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#maxwidth-cssproperties-maxwidth)
  - [onVisibleChange: ( …args: any ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#onvisiblechange-args-any-void)
  - [trigger: FunctionComponentElement< any >](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#trigger-functioncomponentelement-any)
  - [visible: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#visible-boolean)
  - [placement: PopperPlacement](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#placement-popperplacement)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Flyout` is a component to render a floating content modal. It is similar in purpose to a tooltip, but renders content of any sort, not only simple text.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#usage)

``
[Copy](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#)

```php
import { Button, __experimentalFlyout as Flyout, __experimentalText as Text } from '@wordpress/components';

function Example() {
    return (
        <Flyout trigger={ <Button>Show/Hide content</Button> }>
            <Text>Code is Poetry</Text>
        </Flyout>
    );
}
```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#props)

### [state: PopoverStateReturn](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#state-popoverstatereturn)

- Required: No

### [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#label-string)

- Required: No

### [animated: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#animated-boolean)

Determines if `Flyout` has animations.

- Required: No
- Default: `true`

### [animationDuration: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#animationduration-boolean)

The duration of `Flyout` animations.

- Required: No
- Default: `160`

### [baseId: string](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#baseid-string)

ID that will serve as a base for all the items IDs. See https://reakit.io/docs/popover/#usepopoverstate

- Required: No
- Default: `160`

### [elevation: number](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#elevation-number)

Size of the elevation shadow. For more information, check out [`Card`](https://developer.wordpress.org/block-editor/reference-guide/components/card/card/#props).

- Required: No
- Default: `5`

### [maxWidth: CSSProperties\[ ‘maxWidth’ \]](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#maxwidth-cssproperties-maxwidth)

Max-width for the `Flyout` element.

- Required: No
- Default: `360`

### [onVisibleChange: ( …args: any ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#onvisiblechange-args-any-void)

Callback for when the `visible` state changes.

- Required: No

### [trigger: FunctionComponentElement< any >](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#trigger-functioncomponentelement-any)

Element that triggers the `visible` state of `Flyout` when clicked.

``
[Copy](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/#)

```php
<Flyout trigger={<Button>Greet</Button>}>
    <Text>Hi! I'm Olaf!</Text>
</Flyout>
```

- Required: Yes

### [visible: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#visible-boolean)

Whether `Flyout` is visible. See [the `Reakit` docs](https://reakit.io/docs/popover/#usepopoverstate) for more information.

- Required: No
- Default: `false`

### [placement: PopperPlacement](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/\#placement-popperplacement)

Position of the popover element. See [the `popper` docs](https://popper.js.org/docs/v1/#popperplacements--codeenumcode) for more information.

- Required: No
- Default: `auto`

First published

July 6, 2021

Last updated

May 18, 2022

Edit article

[Improve it on GitHub: Flyout](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/flyout/flyout/README.md)

[PreviousCompositePrevious: Composite](https://developer.wordpress.org/block-editor/reference-guides/components/composite/)

[NextConfirmDialogNext: ConfirmDialog](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/)

Notifications