---
url: https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container
scraped_at: 2025-10-20T03:22:22.038Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

NavigableContainer


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)NavigableContainer

Search

# NavigableContainer

## In this article

Table of Contents

- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#props)
  - [cycle: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#cycle-boolean)
  - [eventToOffset: ( event: KeyboardEvent ) => -1 \| 0 \| 1 \| undefined](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#eventtooffset-event-keyboardevent-1-0-1-undefined)
  - [onKeyDown: ( event: KeyboardEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#onkeydown-event-keyboardevent-void)
  - [onNavigate: ( index: number, focusable: HTMLElement ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#onnavigate-index-number-focusable-htmlelement-void)
  - [orientation: ‘vertical’ \| ‘horizontal’ \| ‘both’](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#orientation-vertical-horizontal-both)
- [Components](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#components)
  - [NavigableMenu](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#navigablemenu)
  - [TabbableContainer](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#tabbablecontainer)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#usage)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/#wp--skip-link--target)

`NavigableContainer` is a React component to render a container navigable using the keyboard. Only things that are focusable can be navigated to. It will currently always be a `div`.

`NavigableContainer` is exported as two components: `NavigableMenu` and `TabbableContainer`. `NavigableContainer` itself is **not** exported. `NavigableMenu` and `TabbableContainer` have the props listed below. Any other props will be passed through to the `div`.

* * *

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#props)

These are the props that `NavigableMenu` and `TabbableContainer`. Any props which are specific to one component are labelled appropriately.

### [cycle: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#cycle-boolean)

A boolean which tells the component whether or not to cycle from the end back to the beginning and vice versa.

- Required: No
- default: `true`

### [eventToOffset: ( event: KeyboardEvent ) => -1 \| 0 \| 1 \| undefined](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#eventtooffset-event-keyboardevent-1-0-1-undefined)

(TabbableContainer only)

Gets an offset, given an event.

- Required: No

### [onKeyDown: ( event: KeyboardEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#onkeydown-event-keyboardevent-void)

A callback invoked on the keydown event.

- Required: No

### [onNavigate: ( index: number, focusable: HTMLElement ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#onnavigate-index-number-focusable-htmlelement-void)

A callback invoked when the menu navigates to one of its children passing the index and child as an argument

- Required: No

### [orientation: ‘vertical’ \| ‘horizontal’ \| ‘both’](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#orientation-vertical-horizontal-both)

(NavigableMenu only)

The orientation of the menu. It could be “vertical”, “horizontal”, or “both”.

- Required: No
- Default: `"vertical"`

## [Components](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#components)

### [NavigableMenu](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#navigablemenu)

A NavigableMenu allows movement up and down (or left and right) the component via the arrow keys. The `tab` key is not handled. The `orientation` prop is used to determine whether the arrow keys used are vertical, horizontal or both.

The `NavigableMenu` by default has a `menu` role and therefore, in order to function as expected, the component expects its children elements to have one of the following roles: `'menuitem' | 'menuitemradio' | 'menuitemcheckbox'`.

### [TabbableContainer](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#tabbablecontainer)

A `TabbableContainer` will only be navigated using the `tab` key. Every intended tabstop must have a tabIndex `0`.

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/navigable-container/\#usage)

```jsx
import {
    NavigableMenu,
    TabbableContainer,
    Button,
} from '@wordpress/components';

function onNavigate( index, target ) {
    console.log( `Navigates to ${ index }`, target );
}

const MyNavigableContainer = () => (
    <div>
        <span>Navigable Menu:</span>
        <NavigableMenu onNavigate={ onNavigate } orientation="horizontal">
            <Button variant="secondary">Item 1</Button>
            <Button variant="secondary">Item 2</Button>
            <Button variant="secondary">Item 3</Button>
        </NavigableMenu>

        <span>Tabbable Container:</span>
        <TabbableContainer onNavigate={ onNavigate }>
            <Button variant="secondary" tabIndex="0">
                Section 1
            </Button>
            <Button variant="secondary" tabIndex="0">
                Section 2
            </Button>
            <Button variant="secondary" tabIndex="0">
                Section 3
            </Button>
            <Button variant="secondary" tabIndex="0">
                Section 4
            </Button>
        </TabbableContainer>
    </div>
);

```

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: NavigableContainer](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/navigable-container/README.md)

[PreviousModalPrevious: Modal](https://developer.wordpress.org/block-editor/reference-guides/components/modal/)

[NextNavigationNext: Navigation](https://developer.wordpress.org/block-editor/reference-guides/components/navigation/)

Notifications