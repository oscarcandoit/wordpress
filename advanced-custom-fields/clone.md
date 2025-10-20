---
url: https://www.advancedcustomfields.com/resources/clone
scraped_at: 2025-10-20T02:15:05.555Z
---

# Clone

Last updated Jan 15, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#overview)

## Overview

Link copied

The Clone field allows you to select and display existing fields. It does not duplicate any fields in the database. Instead, it loads and displays the selected fields at run time.

You may also select one (or more) field groups, making it possible to load in “module” groups. A good example of this can be seen in the demo video below, where a single field group is created for “Button” information. This field group is then cloned when a button is needed.

The Clone field may be used in one of two ways. It can replace itself with the selected fields (seamless) or display the selected fields as a group of sub fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#demo)

## Demo

Link copied

Video Player

[https://www.advancedcustomfields.com/wp-content/uploads/2023/04/ACF-PRO-Clone-field-resized.mp4](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/ACF-PRO-Clone-field-resized.mp4)

Media error: Format(s) not supported or source(s) not found

[Download File: https://www.advancedcustomfields.com/wp-content/uploads/2023/04/ACF-PRO-Clone-field-resized.mp4?\_=1](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/ACF-PRO-Clone-field-resized.mp4?_=1)

00:00

00:00

00:00

Use Up/Down Arrow keys to increase or decrease volume.

For more, please see our tutorial on [how to use the Clone field](https://www.advancedcustomfields.com/resources/how-to-use-the-clone-field/).

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#changelog)

## Changelog

Link copied

- Added in version 5.4.0

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#settings)

## Settings

Link copied

| Name | Description |
| --- | --- |
| Fields | An array of fields/groups to clone. |
| Display | Specify how to display the cloned fields.<br>- Seamless – Completely replaces the Clone field with selected fields. Very useful to re-use fields within a Repeater or Flexible Content field.<br>- Group – Displays the selected fields within a group. Very useful to re-use an existing group or ‘modules’ such as a group containing “button” settings (used in following examples). |
| Layout | Change the layout style.<br>- Block – fields are displayed as normal (labels top aligned).<br>- Table – fields are displayed in a table (labels in table header) with each field in its own column.<br>- Row – fields are displayed in rows (labels left aligned). |
| Prefix Field Labels | This setting will modify all selected fields labels and prefix the current Clone field’s label. Very useful when using the “Seamless” display. You could name your Clone field “Hero” and have it prefixed to all selected fields like “Hero Button Text,” “Hero Button URL,” etc. |
| Prefix Field Names | Similar to the above, but will modify the field’s name. The name is used to save/load values. Very useful when using the “Group” display. You could clone a group multiple times on 1 edit screen, but have them save data with different names, e.g.,: “hero\_button\_text,” “welcome\_button\_text,” etc. |

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#template-usage)

## Template Usage

Link copied

Loading the value of a cloned field is the same as loading a normal field. If using the “Group” display setting, you may also load all cloned values as an array by loading the Clone field itself.

Some of the following examples use a Clone field called “main\_button,” which is cloning a field group called “Button.” The Button field group contains 2 fields called “text” and “url.”

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#basic)

### Basic

Link copied

This example shows how to load a Clone field value with the following default settings. Note that these settings will essentially replace the Clone field with the selected fields:

- Name: main\_button
- Display: seamless
- Prefix Names: no
- Fields: A field group called “Button”, as described above

```php
<?php

$text = get_field('text');
$url = get_field('url');

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#prefix-field-names)

### Prefix field names

Link copied

This example shows how to load a Clone field value with the following “Group” settings. Note that these settings will render the “button” fields within a group and prefix the field names. All values will be saved and loaded with the name prefix `main_button_`.

- Name: main\_button
- Display: group
- Prefix Names: yes
- Fields: A field group called “Button”, as described above

```php
<?php

$text = get_field('main_button_text');
$url = get_field('main_button_url');

?>
```

Using the “Group” display setting will allow ACF to load the cloned field values as an array, like so:

```php
<?php

$button = get_field('main_button');

$text = $button['text'];
$url = $button['url'];

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#sub-fields)

### Sub fields

Link copied

Clone fields may also be used within a [Repeater](https://www.advancedcustomfields.com/resources/repeater/) or [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/) field. This example shows the same “main\_button” Clone field from the previous example, but this time used within a Repeater field.

```php
<?php

if( have_rows('slides') ) {

    while( have_rows('slides') ) {

        // increment row
        the_row();


        // vars
        $button = get_sub_field('button');


        // ...

    }

}

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#limitations)

## Limitations

Link copied

The Clone field has a few limitations. These limitations are found in edge cases when using Clone fields within Repeater or Flexible Content fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#multiple-cloned-sub-fields)

### Multiple cloned sub fields

Link copied

A cloned sub field may not be able to save its value if it exists alongside another instance of itself. For example, imagine a Repeater field called “Row” containing 2 Clone fields, both cloning in the same field, called “Cell”. Even if both Clone fields use the “Prefix Name” setting to make each “Cell” have a unique name, they both use the same `field_key`, so they will override each other during save.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#using-the-haverows-function-with-a-nested-clone-field)

### Using the have\_rows() function with a nested Clone field

Link copied

The [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/) function will return false when loading a cloned sub field using the “Group” display setting and layout set to “Block”. Please note that using the “Seamless” display setting will allow sub `have_rows()` loops to work as expected.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#data-structure)

### Data structure

Link copied

The Clone field does not change the data structure when saving values to the database. The only change comes from the “Prefix Field Names” setting. Values are not saved as an array, but are saved as normal individual field values. This means that meta queries are possible as usual.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#data-conflicts)

### Data conflicts

Link copied

It is possible to create data conflicts by cloning a field with a name already used in the group. This is the same issue as creating 2 fields using the same name. Please use the “Prefix Field Names” setting when appropriate to avoid this.

A good rule of thumb is to use the “Prefix Field Names” setting when choosing the “Group” display setting, and the opposite when using the “Seamless” display setting.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#disabled-field-groups)

### Disabled field groups

Link copied

It is possible to clone a field group that is set to “Disabled”. Disabling a field group prevents it from being loaded on a post edit page, which is a good idea when making module groups.

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#cloning-a-clone)

### Cloning a clone

Link copied

It is possible to clone a Clone field. This may sound extreme, but it can be a useful feature in specific scenarios. For example, you may be creating a page builder with the Flexible Content field and find that each layout contains the same “settings” fields. Instead of duplicating these fields in each layout (and the headache of maintaining changes to these fields across multiple layouts), you could define all “settings” fields in the first layout only. The second layout could use a Clone field to clone these “settings” fields. The third layout could use a Clone field to clone the one defined in the second layout.

The benefit of this is that if you add a new “setting” to the first layout, you only need to update the Clone field in your second layout. All other Clone fields (in layout 3, 4, etc.) will mimic this and show the new “settings” field!

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/clone/#related)

## Related

Link copied

- Guides: [How to Use the Clone Field](https://www.advancedcustomfields.com/resources/how-to-use-the-clone-field/)
- Guides: [Creating a new field type](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/)
- Field Types: [Group](https://www.advancedcustomfields.com/resources/group/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/clone/#)