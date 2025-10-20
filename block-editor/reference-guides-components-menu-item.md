---
url: https://developer.wordpress.org/block-editor/reference-guides/components/menu-item
scraped_at: 2025-10-20T03:22:46.446Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

MenuItem


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)MenuItem

Search

# MenuItem

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#props)
  - [children](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#children)
  - [disabled](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#disabled)
  - [info](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#info)
  - [icon](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#icon)
  - [iconPosition](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#iconposition)
  - [isSelected](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#isselected)
  - [shortcut](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#shortcut)
  - [role](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#role)
  - [suffix](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#suffix)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#wp--skip-link--target)

MenuItem is a component which renders a button intended to be used in combination with the [DropdownMenu component](https://developer.wordpress.org/block-editor/reference-guide/components/dropdown-menu/).

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#usage)

```jsx
import { useState } from 'react';
import { MenuItem } from '@wordpress/components';

const MyMenuItem = () => {
    const [ isActive, setIsActive ] = useState( true );

    return (
        <MenuItem
            icon={ isActive ? 'yes' : 'no' }
            isSelected={ isActive }
            onClick={ () => setIsActive( ( state ) => ! state ) }
        >
            Toggle
        </MenuItem>
    );
};

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#props)

MenuItem supports the following props. Any additional props are passed through to the underlying [Button](https://developer.wordpress.org/block-editor/reference-guide/components/button/).

### [children](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#children)

- Type: `Element`
- Required: No

Element to render as child of button.

### [disabled](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#disabled)

- Type: `boolean`
- Required: No

Refer to documentation for [Button’s `disabled` prop](https://developer.wordpress.org/block-editor/reference-guide/components/button/#disabled-boolean).

### [info](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#info)

- Type: `string`
- Required: No

Text to use as description for button text.

Refer to documentation for [`label`](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/#label).

### [icon](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#icon)

- Type: `string`
- Required: No

Refer to documentation for [Button’s `icon` prop](https://developer.wordpress.org/block-editor/reference-guide/components/icon-button/#icon).

### [iconPosition](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#iconposition)

- Type: `string`
- Required: No
- Default: `'right'`

Determines where to display the provided `icon`.

### [isSelected](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#isselected)

- Type: `boolean`
- Required: No

Whether or not the menu item is currently selected. `isSelected` is only taken into account when the `role` prop is either `"menuitemcheckbox"` or `"menuitemradio"`.

### [shortcut](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#shortcut)

- Type: `string` or `object`
- Required: No

If shortcut is a string, it is expecting the display text. If shortcut is an object, it will accept the properties of `display` (string) and `ariaLabel` (string).

### [role](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#role)

- Type: `string`
- Require: No
- Default: `'menuitem'`

[Aria Spec](https://www.w3.org/TR/wai-aria-1.1/#aria-checked). If you need to have selectable menu items use menuitemradio for single select, and menuitemcheckbox for multiselect.

### [suffix](https://developer.wordpress.org/block-editor/reference-guides/components/menu-item/\#suffix)

- Type: `Element`
- Required: No

Allows for markup other than icons or shortcuts to be added to the menu item.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: MenuItem](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/menu-item/README.md)

[PreviousMenuGroupPrevious: MenuGroup](https://developer.wordpress.org/block-editor/reference-guides/components/menu-group/)

[NextMenuItemsChoiceNext: MenuItemsChoice](https://developer.wordpress.org/block-editor/reference-guides/components/menu-items-choice/)

Notifications