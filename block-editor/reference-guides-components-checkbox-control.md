---
url: https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control
scraped_at: 2025-10-20T03:21:42.112Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

CheckboxControl


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)CheckboxControl

Search

# CheckboxControl

## In this article

Table of Contents

- [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#design-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#usage)
- [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#development-guidelines)
  - [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#usage-2)
  - [Props](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#props)
- [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#related-components)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/#wp--skip-link--target)

Checkboxes allow the user to select one or more items from a set.

![Selected and unselected checkboxes](https://i0.wp.com/make.wordpress.org/design/files/2019/02/CheckboxControl.png?ssl=1)

## [Design guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#design-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#usage)

#### [When to use checkboxes](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#when-to-use-checkboxes)

Use checkboxes when you want users to:

- Select one or multiple items from a list.
- Open a list containing sub-selections.

![](https://i0.wp.com/make.wordpress.org/design/files/2019/02/select-from-list.png?ssl=1)

**Do**

Use checkboxes when users can select multiple items from a list. They let users select more than one item.

![](https://i0.wp.com/make.wordpress.org/design/files/2019/02/many-form-toggles.png?ssl=1)

**Don’t**

Don’t use toggles when a list consists of multiple options. Use checkboxes — they take up less space.

![](https://i0.wp.com/make.wordpress.org/design/files/2019/02/checkbox-sublist.gif?ssl=1)

Checkboxes can be used to open a list containing sub-selections.

#### [Parent and child checkboxes](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#parent-and-child-checkboxes)

Checkboxes can have a parent-child relationship, with secondary options nested under primary options.

![](https://i0.wp.com/make.wordpress.org/design/files/2019/02/checkbox-parent.gif?ssl=1)

When the parent checkbox is _checked_, all the child checkboxes are checked. When a parent checkbox is _unchecked_, all the child checkboxes are unchecked.

![](https://i0.wp.com/make.wordpress.org/design/files/2019/02/mixed-checkbox.png?ssl=1)

If only a few child checkboxes are checked, the parent checkbox becomes a mixed checkbox.

## [Development guidelines](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#development-guidelines)

### [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#usage-2)

Render an is author checkbox:

```jsx
import { useState } from 'react';
import { CheckboxControl } from '@wordpress/components';

const MyCheckboxControl = () => {
    const [ isChecked, setChecked ] = useState( true );
    return (
        <CheckboxControl
            __nextHasNoMarginBottom
            label="Is author"
            help="Is the user a author or not?"
            checked={ isChecked }
            onChange={ setChecked }
        />
    );
};

```

### [Props](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#props)

The set of props accepted by the component will be specified below.

Props not included in this set will be applied to the input element.

#### [label: string](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#label-string)

A label for the input field, that appears at the side of the checkbox.

The prop will be rendered as content a label element.

If no prop is passed an empty label is rendered.

- Required: No

#### [help: string\|Element](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#help-stringelement)

If this property is added, a help text will be generated using help property as the content.

- Required: No

#### [checked: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#checked-boolean)

If checked is true the checkbox will be checked. If checked is false the checkbox will be unchecked.

If no value is passed the checkbox will be unchecked.

- Required: No

#### [onChange: function](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#onchange-function)

A function that receives the checked state (boolean) as input.

- Required: Yes

#### [indeterminate: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#indeterminate-boolean)

If indeterminate is true the state of the checkbox will be indeterminate.

- Required: No

#### [\_\_nextHasNoMarginBottom: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#__nexthasnomarginbottom-boolean)

Start opting into the new margin-free styles that will become the default in a future version.

- Required: No
- Default: `false`

## [Related components](https://developer.wordpress.org/block-editor/reference-guides/components/checkbox-control/\#related-components)

- To select one option from a set, and you want to show all the available options at once, use the `RadioControl` component.
- To toggle a single setting on or off, use the `FormToggle` component.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: CheckboxControl](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/checkbox-control/README.md)

[PreviousCardPrevious: Card](https://developer.wordpress.org/block-editor/reference-guides/components/card/)

[NextCircularOptionPickerNext: CircularOptionPicker](https://developer.wordpress.org/block-editor/reference-guides/components/circular-option-picker/)

Notifications