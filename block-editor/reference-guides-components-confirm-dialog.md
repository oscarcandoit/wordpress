---
url: https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog
scraped_at: 2025-10-20T03:23:34.696Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ConfirmDialog


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)ConfirmDialog

Search

# ConfirmDialog

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#usage)
  - [Uncontrolled mode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#uncontrolled-mode)
  - [Controlled mode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#controlled-mode)
  - [Unsupported: Multiple instances](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#unsupported-multiple-instances)
- [Custom Types](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#custom-types)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#props)
  - [title: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#title-string)
  - [children: React.ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#children-react-reactnode)
  - [isOpen: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#isopen-boolean)
  - [onConfirm: ( event: DialogInputEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#onconfirm-event-dialoginputevent-void)
  - [onCancel: ( event: DialogInputEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#oncancel-event-dialoginputevent-void)
  - [confirmButtonText: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#confirmbuttontext-string)
  - [cancelButtonText: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#cancelbuttontext-string)
- [Best practices](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#best-practices)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`ConfirmDialog` is built of top of [`Modal`](https://developer.wordpress.org/block-editor/reference-guide/components/modal/) and displays a confirmation dialog, with _confirm_ and _cancel_ buttons.

The dialog is confirmed by clicking the _confirm_ button or by pressing the `Enter` key. It is cancelled (closed) by clicking the _cancel_ button, by pressing the `ESC` key, or by clicking outside the dialog focus (i.e, the overlay).

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#usage)

`ConfirmDialog` has two main implicit modes: controlled and uncontrolled.

### [Uncontrolled mode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#uncontrolled-mode)

Allows the component to be used standalone, just by declaring it as part of another React’s component render method:

- It will be automatically open (displayed) upon mounting;
- It will be automatically closed when clicking the _cancel_ button, by pressing the `ESC` key, or by clicking outside the dialog focus (i.e, the overlay);
- `onCancel` is not mandatory but can be passed. Even if passed, the dialog will still be able to close itself.

Activating this mode is as simple as omitting the `isOpen` prop. The only mandatory prop, in this case, is the `onConfirm` callback. The message is passed as the `children`. You can pass any JSX you’d like, which allows to further format the message or include sub-component if you’d like:

```jsx
import { __experimentalConfirmDialog as ConfirmDialog } from '@wordpress/components';

function Example() {
    return (
        <ConfirmDialog onConfirm={ () => console.debug( ' Confirmed! ' ) }>
            Are you sure? <strong>This action cannot be undone!</strong>
        </ConfirmDialog>
    );
}

```

### [Controlled mode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#controlled-mode)

Let the parent component control when the dialog is open/closed. It’s activated when a boolean value is passed to `isOpen`:

- It will not be automatically closed. You need to let it know when to open/close by updating the value of the `isOpen` prop;
- Both `onConfirm` and the `onCancel` callbacks are mandatory props in this mode;
- You’ll want to update the state that controls `isOpen` by updating it from the `onCancel` and `onConfirm` callbacks.

```jsx
import { useState } from 'react';
import { __experimentalConfirmDialog as ConfirmDialog } from '@wordpress/components';

function Example() {
    const [ isOpen, setIsOpen ] = useState( true );

    const handleConfirm = () => {
        console.debug( 'Confirmed!' );
        setIsOpen( false );
    };

    const handleCancel = () => {
        console.debug( 'Cancelled!' );
        setIsOpen( false );
    };

    return (
        <ConfirmDialog
            isOpen={ isOpen }
            onConfirm={ handleConfirm }
            onCancel={ handleCancel }
        >
            Are you sure? <strong>This action cannot be undone!</strong>
        </ConfirmDialog>
    );
}

```

### [Unsupported: Multiple instances](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#unsupported-multiple-instances)

Multiple `ConfirmDialog` s is an edge case that’s currently not officially supported by this component. At the moment, new instances will end up closing the last instance due to the way the `Modal` is implemented.

## [Custom Types](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#custom-types)

```ts
type DialogInputEvent =
    | KeyboardEvent< HTMLDivElement >
    | MouseEvent< HTMLButtonElement >;

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#props)

### [title: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#title-string)

- Required: No

An optional `title` for the dialog. Setting a title will render it in a title bar at the top of the dialog, making it a bit taller. The bar will also include an `x` close button at the top-right corner.

### [children: React.ReactNode](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#children-react-reactnode)

- Required: Yes

The actual message for the dialog. It’s passed as children and any valid `ReactNode` is accepted:

```jsx
<ConfirmDialog>
    Are you sure? <strong>This action cannot be undone!</strong>
</ConfirmDialog>

```

### [isOpen: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#isopen-boolean)

- Required: No

Defines if the dialog is open (displayed) or closed (not rendered/displayed). It also implicitly toggles the controlled mode if set or the uncontrolled mode if it’s not set.

### [onConfirm: ( event: DialogInputEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#onconfirm-event-dialoginputevent-void)

- Required: Yes

The callback that’s called when the user confirms. A confirmation can happen when the `OK` button is clicked or when `Enter` is pressed.

### [onCancel: ( event: DialogInputEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#oncancel-event-dialoginputevent-void)

- Required: Only if `isOpen` is not set

The callback that’s called when the user cancels. A cancellation can happen when the `Cancel` button is clicked, when the `ESC` key is pressed, or when a click outside of the dialog focus is detected (i.e. in the overlay).

It’s not required if `isOpen` is not set (uncontrolled mode), as the component will take care of closing itself, but you can still pass a callback if something must be done upon cancelling (the component will still close itself in this case).

If `isOpen` is set (controlled mode), then it’s required, and you need to set the state that defines `isOpen` to `false` as part of this callback if you want the dialog to close when the user cancels.

### [confirmButtonText: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#confirmbuttontext-string)

- Required: No
- Default: “OK”

The optional custom text to display as the confirmation button’s label

### [cancelButtonText: string](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#cancelbuttontext-string)

- Required: No
- Default: “Cancel”

The optional custom text to display as the cancellation button’s label

## [Best practices](https://developer.wordpress.org/block-editor/reference-guides/components/confirm-dialog/\#best-practices)

The ConfirmDialog component should:

- Be used only for short confirmation messages where a cancel and confirm actions are provided.
- Use a descriptive text for the _confirm_ button. Default is “OK”.

First published

November 25, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: ConfirmDialog](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/confirm-dialog/README.md)

[PreviousFlyoutPrevious: Flyout](https://developer.wordpress.org/block-editor/reference-guides/components/flyout/)

[NextCustomSelectControlNext: CustomSelectControl](https://developer.wordpress.org/block-editor/reference-guides/components/custom-select-control/)

Notifications