---
url: https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices
scraped_at: 2025-10-20T02:30:15.707Z
---

# Dynamically Populate a Select Field’s Choices

Last updated Apr 8, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#overview)

## Overview

Link copied

Need to dynamically populate a field’s choices? This tutorial shows how to take a value saved to an options page and use it to override the `choices` array for a [Select](https://www.advancedcustomfields.com/resources/select/) field.

The ‘choices’ array attribute is also used with the [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/) and [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/) fields. Most of this tutorial applies to any of these fields, but the AJAX example can only be used with the Select field.

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#requirements)

## Requirements

Link copied

This tutorial requires the use of the [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/) filter, in conjunction with the `name` modifier to apply the filter to all fields of a specific `name`. The `name` attribute is how the field is stored and referred to in the WordPress database.

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#populating-choices-from-a-text-area-field)

## Populating Choices From a Text Area Field

Link copied

In this example, we will load a [Text Area](https://www.advancedcustomfields.com/resources/textarea/) field called `my_select_values` from an options page, and use the text on each line as an option for the Select field’s choices. The Select field’s `name` in this example is `color`.

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#functionsphp)

#### functions.php

Link copied

```php
function acf_load_color_field_choices( $field ) {

    // Reset choices
    $field['choices'] = array();


    // Get the Text Area values from the options page without any formatting
    $choices = get_field('my_select_values', 'option', false);


    // Explode the value so each line is a new element in the array
    $choices = explode("\n", $choices);


    // Remove unwanted white space
    $choices = array_map('trim', $choices);


    // Loop through the array and add to field 'choices'
    if( is_array($choices) ) {

        foreach( $choices as $choice ) {

            $field['choices'][ $choice ] = $choice;

        }

    }

    // Return the field
    return $field;

}

add_filter('acf/load_field/name=color', 'acf_load_color_field_choices');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#populating-choices-from-a-repeater-field)

## Populating Choices From a Repeater Field

Link copied

In this example, we will load a [Repeater](https://www.advancedcustomfields.com/resources/repeater/) field called `my_select_values` from the options page, and use the subfields `value` and `label` as the options for the Select field’s choices.

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#functionsphp)

#### functions.php

Link copied

```php
function acf_load_color_field_choices( $field ) {

    // Reset choices
    $field['choices'] = array();

    // Check to see if Repeater has rows of data to loop over
    if( have_rows('my_select_values', 'option') ) {

        // Execute repeatedly as long as the below statement is true
        while( have_rows('my_select_values', 'option') ) {

            // Return an array with all values after the loop is complete
            the_row();


            // Variables
            $value = get_sub_field('value');
            $label = get_sub_field('label');


            // Append to choices
            $field['choices'][ $value ] = $label;

        }

    }

    // Return the field
    return $field;

}

add_filter('acf/load_field/name=color', 'acf_load_color_field_choices');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#populating-a-select-field-with-ajax)

## Populating a Select Field With AJAX

Link copied

Unlike the Radio Button and Checkbox fields, the Select field can be populated via AJAX. This can help speed up page load times when using the `acf/load_field` filter to populate the Select field’s choices. The Select field must have “Stylized UI” and “Use AJAX to lazy load choices” turned on for this filter to work. The “Use AJAX to lazy load choices” option is hidden until “Stylized UI” is turned on in the Select field’s settings.

```php
function filter_field( array $field ) : array {

 if ( defined( 'DOING_AJAX' ) && DOING_AJAX ) {

   $field['choices'] = time_consuming_call_to_get_choices();

 }

 return $field;

}

add_filter( "acf/load_field/key=$key", 'filter_field', 10, 1 );
```

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

[Link to heading#](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#related)

## Related

Link copied

- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Choice: [Select](https://www.advancedcustomfields.com/resources/select/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Sort a Repeater Field](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/)

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

[Got it](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/#)