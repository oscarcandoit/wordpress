---
url: https://developer.wordpress.org/block-editor/reference-guides/components/item
scraped_at: 2025-10-20T03:20:12.498Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/item/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Item


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Item

Search

# Item

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/item/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/item/#props)
  - [onClick: React.MouseEventHandler<HTMLDivElement>](https://developer.wordpress.org/block-editor/reference-guides/components/item/#onclick-react-mouseeventhandlerhtmldivelement)
  - [size: ‘small’ \| ‘medium’ \| ‘large’](https://developer.wordpress.org/block-editor/reference-guides/components/item/#size-small-medium-large)
  - [Context](https://developer.wordpress.org/block-editor/reference-guides/components/item/#context)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/item/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Item` is used in combination with `ItemGroup` to display a list of items grouped and styled together.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/item/\#usage)

`Item` should be used in combination with the [`ItemGroup` component](https://developer.wordpress.org/block-editor/reference-guide/components/item-group/item-group/).

```jsx
import {
    __experimentalItemGroup as ItemGroup,
    __experimentalItem as Item,
} from '@wordpress/components';

function Example() {
    return (
        <ItemGroup>
            <Item>Code</Item>
            <Item>is</Item>
            <Item>Poetry</Item>
        </ItemGroup>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/item/\#props)

### [onClick: React.MouseEventHandler<HTMLDivElement>](https://developer.wordpress.org/block-editor/reference-guides/components/item/\#onclick-react-mouseeventhandlerhtmldivelement)

Even handler for processing `click` events. When defined, the `Item` component will render as a `button` (unless differently specified via the `as` prop).

- Required: No

### [size: ‘small’ \| ‘medium’ \| ‘large’](https://developer.wordpress.org/block-editor/reference-guides/components/item/\#size-small-medium-large)

Determines the amount of padding within the component.

- Required: No
- Default: `medium`

### [Context](https://developer.wordpress.org/block-editor/reference-guides/components/item/\#context)

`Item` is connected to [the `<ItemGroup />` parent component](https://developer.wordpress.org/block-editor/reference-guide/components/item-group/item-group/) using [Context](https://reactjs.org/docs/context.html). Therefore, `Item` receives the `size` prop from the `ItemGroup` parent component.

In the following example, the `<Item />` will render with a size of `small`:

```jsx
import {
    __experimentalItemGroup as ItemGroup,
    __experimentalItem as Item,
} from '@wordpress/components';

const Example = () => (
    <ItemGroup size="small">
        <Item>...</Item>
    </ItemGroup>
);

```

First published

July 29, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Item](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/item-group/item/README.md)

[PreviousItemGroupPrevious: ItemGroup](https://developer.wordpress.org/block-editor/reference-guides/components/item-group/)

[NextKeyboardShortcutsNext: KeyboardShortcuts](https://developer.wordpress.org/block-editor/reference-guides/components/keyboard-shortcuts/)

Notifications