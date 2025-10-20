---
url: https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts
scraped_at: 2025-10-20T03:22:30.599Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

KeyboardShortcuts


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)KeyboardShortcuts

Search

# KeyboardShortcuts

## In this article

Table of Contents

- [Example](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#example)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#props)
  - [children](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#children)
  - [shortcuts](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#shortcuts)
  - [bindGlobal](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#bindglobal)
  - [eventName](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#eventname)
- [References](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#references)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/#wp--skip-link--target)

`<KeyboardShortcuts />` is a component which handles keyboard sequences during the lifetime of the rendering element.

When passed children, it will capture key events which occur on or within the children. If no children are passed, events are captured on the document.

It uses the [Mousetrap](https://craig.is/killing/mice) library to implement keyboard sequence bindings.

## [Example](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#example)

Render `<KeyboardShortcuts />` with a `shortcuts` prop object:

```jsx
import { useState } from 'react';
import { KeyboardShortcuts } from '@wordpress/components';

const MyKeyboardShortcuts = () => {
    const [ isAllSelected, setIsAllSelected ] = useState( false );
    const selectAll = () => {
        setIsAllSelected( true );
    };

    return (
        <div>
            <KeyboardShortcuts
                shortcuts={ {
                    'mod+a': selectAll,
                } }
            />
            [cmd/ctrl + A] Combination pressed? { isAllSelected ? 'Yes' : 'No' }
        </div>
    );
};

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#props)

The component accepts the following props:

### [children](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#children)

Elements to render, upon whom key events are to be monitored.

- Type: `ReactNode`
- Required: No

### [shortcuts](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#shortcuts)

An object of shortcut bindings, where each key is a keyboard combination, the value of which is the callback to be invoked when the key combination is pressed.

- Type: `Object`
- Required: Yes

**Note:** The value of each shortcut should be a consistent function reference, not an anonymous function. Otherwise, the callback will not be correctly unbound when the component unmounts.

**Note:** The `KeyboardShortcuts` component will not update to reflect a changed `shortcuts` prop. If you need to change shortcuts, mount a separate `KeyboardShortcuts` element, which can be achieved by assigning a unique `key` prop.

### [bindGlobal](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#bindglobal)

By default, a callback will not be invoked if the key combination occurs in an editable field. Pass `bindGlobal` as `true` if the key events should be observed globally, including within editable fields.

- Type: `Boolean`
- Required: No

_Tip:_ If you need some but not all keyboard events to be observed globally, simply render two distinct `KeyboardShortcuts` elements, one with and one without the `bindGlobal` prop.

### [eventName](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#eventname)

By default, a callback is invoked in response to the `keydown` event. To override this, pass `eventName` with the name of a specific keyboard event.

- Type: `String`
- Required: No

## [References](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/\#references)

- [Mousetrap documentation](https://craig.is/killing/mice)

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: KeyboardShortcuts](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/keyboard-shortcuts/README.md)

[PreviousItemPrevious: Item](https://developer.wordpress.org/block-editor/reference-guides/components/item/)

[NextMenuGroupNext: MenuGroup](https://developer.wordpress.org/block-editor/reference-guides/components/menu-group/)

Notifications