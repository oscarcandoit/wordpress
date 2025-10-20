---
url: https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel
scraped_at: 2025-10-20T03:21:55.923Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

TabPanel


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)TabPanel

Search

# TabPanel

## In this article

Table of Contents

- [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#design-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#usage)
  - [Anatomy](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#anatomy)
  - [Behavior](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#behavior)
  - [Placement](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#placement)
- [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#development-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#usage-2)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#props)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/#wp--skip-link--target)

TabPanel is a React component to render an ARIA-compliant TabPanel.

TabPanels organize content across different screens, data sets, and interactions. It has two sections: a list of tabs, and the view to show when tabs are chosen.

![The “Document” tab selected in the sidebar TabPanel.](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_E36D9C9B8FFA15A1A8CE224E422535A12B016F88884089575F9998E52016A49F_1541785098230_TabPanel.png?ssl=1)

## [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#design-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#usage)

TabPanels organize and allow navigation between groups of content that are related and at the same level of hierarchy.

#### [Tabs in a set](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#tabs-in-a-set)

As a set, all tabs are unified by a shared topic. For clarity, each tab should contain content that is distinct from all the other tabs in a set.

### [Anatomy](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#anatomy)

![](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_E36D9C9B8FFA15A1A8CE224E422535A12B016F88884089575F9998E52016A49F_1541787297310_TabPanelAnatomy.png?ssl=1)

1. Container
2. Active text label
3. Active tab indicator
4. Inactive text label
5. Tab item

#### [Labels](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#labels)

Tab labels appear in a single row, in the same typeface and size. Use text labels that clearly and succinctly describe the content of a tab, and make sure that a set of tabs contains a cohesive group of items that share a common characteristic.

Tab labels can wrap to a second line, but do not add a second row of tabs.

#### [Active tab indicators](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#active-tab-indicators)

To differentiate an active tab from an inactive tab, apply an underline and color change to the active tab’s text and icon.

![An underline and color change differentiate an active tab from the inactive ones.](https://i0.wp.com/wordpress.org/gutenberg/files/2019/01/s_E36D9C9B8FFA15A1A8CE224E422535A12B016F88884089575F9998E52016A49F_1541787691601_TabPanelActiveTab.png?ssl=1)

### [Behavior](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#behavior)

Users can navigate between tabs by tapping the tab key on the keyboard.

### [Placement](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#placement)

Place tabs above content. Tabs control the UI region displayed below them.

## [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#development-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#usage-2)

```jsx
import { TabPanel } from '@wordpress/components';

const onSelect = ( tabName ) => {
    console.log( 'Selecting tab', tabName );
};

const MyTabPanel = () => (
    <TabPanel
        className="my-tab-panel"
        activeClass="active-tab"
        onSelect={ onSelect }
        tabs={ [\
            {\
                name: 'tab1',\
                title: 'Tab 1',\
                className: 'tab-one',\
            },\
            {\
                name: 'tab2',\
                title: 'Tab 2',\
                className: 'tab-two',\
            },\
        ] }
    >
        { ( tab ) => <p>{ tab.title }</p> }
    </TabPanel>
);

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#props)

The component accepts the following props:

#### [className](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#classname)

The class to give to the outer container for the TabPanel

- Type: `String`
- Required: No
- Default: ''

#### [orientation](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#orientation)

The orientation of the tablist ( `vertical` or `horizontal`)

- Type: `String`
- Required: No
- Default: `horizontal`

#### [onSelect](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#onselect)

The function called when a tab has been selected. It is passed the `tabName` as an argument.

- Type: `Function`
- Required: No
- Default: `noop`

#### [tabs](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#tabs)

An array of objects containing the following properties:

- `name`: `(string)` Defines the key for the tab.
- `title`: `(string)` Defines the translated text for the tab.
- `className`: `(string)` Optional. Defines the class to put on the tab.
- `icon`: `(ReactNode)` Optional. When set, displays the icon in place of the tab title. The title is then rendered as an aria-label and tooltip.
- `disabled`: `(boolean)` Optional. Determines if the tab should be disabled or selectable.

> > **Note:** Other fields may be added to the object and accessed from the child function if desired.

- Type: `Array`
- Required: Yes

#### [activeClass](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#activeclass)

The class to add to the active tab

- Type: `String`
- Required: No
- Default: `is-active`

#### [initialTabName](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#initialtabname)

The name of the tab to be selected upon mounting of component. If this prop is not set, the first tab will be selected by default.

- Type: `String`
- Required: No
- Default: none

#### [selectOnMove](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#selectonmove)

When `true`, the tab will be selected when receiving focus (automatic tab activation). When `false`, the tab will be selected only when clicked (manual tab activation). See the [official W3C docs](https://www.w3.org/WAI/ARIA/apg/patterns/tabpanel/) for more info.

- Type: `boolean`
- Required: No
- Default: `true`

#### [children](https://developer.wordpress.org/block-editor/reference-guides/components/tab-panel/\#children)

A function which renders the tabviews given the selected tab. The function is passed the active tab object as an argument as defined the tabs prop.

- Type: ( `Object`) =\> `Element`
- Required: Yes

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: TabPanel](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/tab-panel/README.md)

[PreviousSurfacePrevious: Surface](https://developer.wordpress.org/block-editor/reference-guides/components/surface/)

[NextTextControlNext: TextControl](https://developer.wordpress.org/block-editor/reference-guides/components/text-control/)

Notifications