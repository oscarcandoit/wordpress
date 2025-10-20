---
url: https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control
scraped_at: 2025-10-20T03:22:50.059Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

ComboboxControl


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)ComboboxControl

Search

# ComboboxControl

## In this article

Table of Contents

- [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#design-guidelines)
- [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#development-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#usage)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#props)
- [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#related-components)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/#wp--skip-link--target)

`ComboboxControl` is an enhanced version of a [`SelectControl`](https://developer.wordpress.org/block-editor/reference-guide/components/select-control/), with the addition of being able to search for options using a search input.

## [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#design-guidelines)

These are the same as [the ones for `SelectControl` s](https://developer.wordpress.org/block-editor/reference-guide/components/select-control/#design-guidelines), but this component is better suited for when there are too many items to scroll through or load at once so you need to filter them based on user input.

## [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#development-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#usage)

```jsx
import { useState } from 'react';
import { ComboboxControl } from '@wordpress/components';

const options = [\
    {\
        value: 'small',\
        label: 'Small',\
    },\
    {\
        value: 'normal',\
        label: 'Normal',\
    },\
    {\
        value: 'large',\
        label: 'Large',\
    },\
];

function MyComboboxControl() {
    const [ fontSize, setFontSize ] = useState();
    const [ filteredOptions, setFilteredOptions ] = useState( options );
    return (
        <ComboboxControl
            __next40pxDefaultSize
            __nextHasNoMarginBottom
            label="Font Size"
            value={ fontSize }
            onChange={ setFontSize }
            isLoading={ isLoading }
            options={ filteredOptions }
            onFilterValueChange={ ( inputValue ) =>
                setFilteredOptions(
                    options.filter( ( option ) =>
                        option.value === inputValue
                    )
                )
            }
        />
    );
}

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#props)

#### [label](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#label)

The label for the control.

- Type: `String`
- Required: Yes

#### [hideLabelFromVision](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#hidelabelfromvision)

If true, the label will only be visible to screen readers.

- Type: `Boolean`
- Required: No

#### [help](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#help)

If this property is added, a help text will be generated using help property as the content.

- Type: `String`
- Required: No

#### [options](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#options)

The options that can be chosen from.

- Type: `Array<{ value: string, label: string, disabled?: boolean }>`
- Required: Yes

#### [onFilterValueChange](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#onfiltervaluechange)

Function called when the control’s search input value changes. The argument contains the next input value.

- Type: `( value: string ) => void`
- Required: No

#### [onChange](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#onchange)

Function called with the selected value changes.

- Type: `( value: string | null | undefined ) => void`
- Required: No

#### [value](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#value)

The current value of the control.

- Type: `string | null`
- Required: No

#### [expandOnFocus](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#expandonfocus)

Automatically expand the dropdown when the control is focused.

If the control is clicked, the dropdown will expand regardless of this prop.

- Type: `Boolean`
- Required: No
- Default: `true`

#### [placeholder](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#placeholder)

If passed, the combobox input will show a placeholder string if no values are present.

- Type: `string`
- Required: No

#### [isLoading](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#isloading)

Show a spinner (and hide the suggestions dropdown) while data about the matching suggestions (ie the `options` prop) is loading

- Type: `Boolean`
- Required: No

#### [\_\_experimentalRenderItem](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#__experimentalrenderitem)

Custom renderer invoked for each option in the suggestion list. The render prop receives as its argument an object containing, under the `item` key, the single option’s data (directly from the array of data passed to the `options` prop).

- Type: `( args: { item: object } ) => ReactNode`
- Required: No

#### [\_\_next40pxDefaultSize](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#__next40pxdefaultsize)

Start opting into the larger default height that will become the default size in a future version.

- Type: `Boolean`
- Required: No
- Default: `false`

#### [\_\_nextHasNoMarginBottom](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#__nexthasnomarginbottom)

Start opting into the new margin-free styles that will become the default in a future version.

- Type: `Boolean`
- Required: No
- Default: `false`

## [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/combobox-control/\#related-components)

- Like this component, but without a search input, the [`CustomSelectControl`](https://developer.wordpress.org/block-editor/reference-guides/components/custom-select-control/) component.

- To select one option from a set, when you want to show all the available options at once, use the [`RadioControl`](https://developer.wordpress.org/block-editor/reference-guides/components/radio-control/) component.

- To select one or more items from a set, use the [`CheckboxControl`](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/) component.
- To toggle a single setting on or off, use the [`ToggleControl`](https://developer.wordpress.org/block-editor/reference-guides/components/toggle-control/) component.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: ComboboxControl](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/combobox-control/README.md)

[PreviousColorPickerPrevious: ColorPicker](https://developer.wordpress.org/block-editor/reference-guides/components/color-picker/)

[NextCompositeNext: Composite](https://developer.wordpress.org/block-editor/reference-guides/components/composite/)

Notifications