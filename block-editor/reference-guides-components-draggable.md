---
url: https://developer.wordpress.org/block-editor/reference-guides/components/draggable
scraped_at: 2025-10-20T03:19:25.600Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Draggable


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Draggable

Search

# Draggable

## In this article

Table of Contents

- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#props)
  - [appendToOwnerDocument: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#appendtoownerdocument-boolean)
  - [elementId: string](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#elementid-string)
  - [onDragEnd: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#ondragend-event-dragevent-void)
  - [onDragOver: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#ondragover-event-dragevent-void)
  - [onDragStart: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#ondragstart-event-dragevent-void)
  - [transferData: unknown](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#transferdata-unknown)
- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#usage)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/#wp--skip-link--target)

`Draggable` is a Component that provides a way to set up a cross-browser (including IE) customizable drag image and the transfer data for the drag event. It decouples the drag handle and the element to drag: use it by wrapping the component that will become the drag handle and providing the DOM ID of the element to drag.

Note that the drag handle needs to declare the `draggable="true"` property and bind the `Draggable` s `onDraggableStart` and `onDraggableEnd` event handlers to its own `onDragStart` and `onDragEnd` respectively. `Draggable` takes care of the logic to setup the drag image and the transfer data, but is not concerned with creating an actual DOM element that is draggable.

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#props)

The component accepts the following props:

### [appendToOwnerDocument: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#appendtoownerdocument-boolean)

Whether to append the cloned element to the `ownerDocument` body. By default, elements sourced by id are appended to the element’s wrapper.

- Required: No
- Default: `false`

### [elementId: string](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#elementid-string)

The HTML id of the element to clone on drag.

- Required: Yes

### [onDragEnd: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#ondragend-event-dragevent-void)

A function called when dragging ends. This callback receives the `event` object from the `dragend` event as its first parameter.

- Required: No
- Default: `noop`

### [onDragOver: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#ondragover-event-dragevent-void)

A function called when the element being dragged is dragged over a valid drop target. This callback receives the `event` object from the `dragover` event as its first parameter.

- Required: No
- Default: `noop`

### [onDragStart: ( event: DragEvent ) => void](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#ondragstart-event-dragevent-void)

A function called when dragging starts. This callback receives the `event` object from the `dragstart` event as its first parameter.

- Required: No
- Default: `noop`

### [transferData: unknown](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#transferdata-unknown)

Arbitrary data object attached to the drag and drop event.

- Required: Yes

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/draggable/\#usage)

```jsx
import { Draggable, Panel, PanelBody } from '@wordpress/components';
import { Icon, more } from '@wordpress/icons';

const MyDraggable = () => (
    <div id="draggable-panel">
        <Panel header="Draggable panel">
            <PanelBody>
                <Draggable elementId="draggable-panel" transferData={ {} }>
                    { ( { onDraggableStart, onDraggableEnd } ) => (
                        <div
                            className="example-drag-handle"
                            draggable
                            onDragStart={ onDraggableStart }
                            onDragEnd={ onDraggableEnd }
                        >
                            <Icon icon={ more } />
                        </div>
                    ) }
                </Draggable>
            </PanelBody>
        </Panel>
    </div>
);

```

In case you want to call your own `dragstart` / `dragend` event handlers as well, you can pass them to `Draggable` and it’ll take care of calling them after their own:

```jsx
import { Draggable, Panel, PanelBody } from '@wordpress/components';
import { Icon, more } from '@wordpress/icons';

const MyDraggable = ( { onDragStart, onDragEnd } ) => (
    <div id="draggable-panel">
        <Panel header="Draggable panel">
            <PanelBody>
                <Draggable
                    elementId="draggable-panel"
                    transferData={ {} }
                    onDragStart={ onDragStart }
                    onDragEnd={ onDragEnd }
                >
                    { ( { onDraggableStart, onDraggableEnd } ) => (
                        <div
                            className="example-drag-handle"
                            draggable
                            onDragStart={ onDraggableStart }
                            onDragEnd={ onDraggableEnd }
                        >
                            <Icon icon={ more } />
                        </div>
                    ) }
                </Draggable>
            </PanelBody>
        </Panel>
    </div>
);

```

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Draggable](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/draggable/README.md)

[PreviousDividerPrevious: Divider](https://developer.wordpress.org/block-editor/reference-guides/components/divider/)

[NextDropZoneNext: DropZone](https://developer.wordpress.org/block-editor/reference-guides/components/drop-zone/)

Notifications