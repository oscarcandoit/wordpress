---
url: https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field
scraped_at: 2025-10-20T02:25:22.738Z
---

# Sort a Repeater Field

Last updated May 17, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#overview)

## Overview

Link copied

This article will cover how to sort a repeater field based on it’s sub field values using a function called [array\_multisort()](http://php.net/manual/en/function.array-multisort.php).

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#getting-started)

## Getting started

Link copied

The following examples assume a repeater field exists containing 2 sub field; ID (number field) and Name (text field). This repeater field is illustrated below. For the purpose of these examples, we will sort the repeater rows based on the ID, however, the same code could be used in a more ‘real’ situation such as order by name, age, etc.

In both examples, the before and after $value will look the same.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/sort-repeater-input.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/sort-repeater-input.png)

Field


[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/sort-repeater-values.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/sort-repeater-values.png)

Value


[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#basic)

### Basic

Link copied

This example uses the get\_field function to simply load an array of repeater field data, which is then sorted and looped through. Please note that the [get\_sub\_field](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()") and [the\_sub\_field](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()") functions will not work in this loop.

```php
<?php

// get repeater field data
$repeater = get_field('repeater');

// vars
$order = array();

// populate order
foreach( $repeater as $i => $row ) {

    $order[ $i ] = $row['id'];

}

/*

$order should look like this:

Array (
    [0] => 3
    [1] => 2
    [2] => 4
    [3] => 1
)

*/

// multisort
array_multisort( $order, SORT_DESC, $repeater );

// loop through repeater
if( $repeater ): ?>

    <ul>

    <?php foreach( $repeater as $i => $row ): ?>

        <li><?php echo $row['id']; ?>. <?php echo $row['name']; ?></li>

    <?php endforeach; ?>

    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#advanced)

### Advanced

Link copied

This example uses the [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/ "acf/load_value") filter to reorder the repeater field when it is loaded from the database. This allows the value to be modified for both the front and backend and also allows the [get\_sub\_field](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()") and [the\_sub\_field](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()") functions to work.

Please note that during this filter, the repeater field $value does not contain nice field names but instead uses the sub field’s key. This is visible when populating the $row variable.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#functionsphp)

#### functions.php

Link copied

```php
function my_acf_load_value( $value, $post_id, $field ) {

    // vars
    $order = array();


    // bail early if no value
    if( empty($value) ) {

        return $value;

    }


    // populate order
    foreach( $value as $i => $row ) {

        $order[ $i ] = $row['field_55121d86dd2f6'];

    }


    // multisort
    array_multisort( $order, SORT_DESC, $value );


    // return
    return $value;

}

add_filter('acf/load_value/name=scores', 'my_acf_load_value', 10, 3);
```

```php
<?php if( have_rows('repeater') ): ?>

    <ul>

    <?php while( have_rows('repeater') ): the_row(); ?>

        <li><?php the_sub_field('id'); ?>. <?php the_sub_field('name'); ?></li>

    <?php endwhile; ?>

    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#how-it-works)

## How it works

Link copied

The array\_multisort function uses a “snapshot” array ( `$row` in above examples) to compare and reorder the `$value` array. This function is not limited to 1 “snapshot” array. In fact, you can use multiple $column variables to sort the data.

Therefore, it is possible to order by one sub field and then by another (ID and Name).

There are a few options for the sorting direction, these are: **`SORT_ASC`**, **`SORT_DESC`**, **`SORT_REGULAR`**, **`SORT_NUMERIC`**, **`SORT_STRING`**.

Please read more about this function here: [http://php.net/manual/en/function.array-multisort.php](http://php.net/manual/en/function.array-multisort.php)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#related)

## Related

Link copied

- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from an options page](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/)
- Deprecated: [the\_repeater\_field()](https://www.advancedcustomfields.com/resources/the_repeater_field/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)
- Guides: [Dynamically Populate a Select Field’s Choices](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/#)