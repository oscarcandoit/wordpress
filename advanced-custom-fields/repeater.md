---
url: https://www.advancedcustomfields.com/resources/repeater
scraped_at: 2025-10-20T02:16:08.872Z
---

# Repeater

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#description)

## Description

Link copied

The Repeater field provides a neat solution for repeating content – think slides, team members, CTA tiles and alike.

This field type acts as a parent to a set of sub fields which can be repeated again and again. What makes this field type so special is its versatility. Any kind of field can be used within a Repeater, and there are no limits to the number of repeats either (👨‍💻 unless defined in the field settings).

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#screenshots)

## Screenshots

Link copied

[![A table-like layout displaying 3 rows of data each containing Image, Name, Specialities and Website fields.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/repater-in-editor.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/repater-in-editor.png) The Repeater field interface[![List of field settings shown when setting up a Repeater field.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/repeater-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/repeater-field-settings.png) The Repeater field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#settings)

## Settings

Link copied

- **Sub Fields**


Defines the set of repeatable sub fields.

- **Collapsed**


Enables each row to be collapsed by specifying a single sub field to display.

- **Minimum Rows**


Sets a limit on how many rows of data are required.

- **Maximum Rows**


Sets a limit on how many rows of data are allowed.

- **Layout**


Defines the layout style of the appearance of the sub fields.

_Table_: Sub fields are displayed in a table. Labels will appear in the table header.

_Block_: Sub fields are displayed in blocks, one after the other.

_Row_: Sub fields are displayed in a two column table. Labels will appear in the first column.

- **Button Label**


The text shown in the ‘Add Row’ button.

- **Pagination**


Added in ACF 6.0. Defines if the repeater should only load a set number of rows per page when editing the repeater in the admin. If disabled (which it is by default), all rows will be loaded at once. This setting does not affect template usage or results returned via the REST API. **Note**: This setting is not currently supported inside flexible content and other repeater fields. In these cases, this setting will not be shown.

- **Rows per page**


Added in ACF 6.0. Sets the number of rows that are displayed on a page if the “Pagination” setting is enabled.


[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#template-usage)

## Template usage

Link copied

The Repeater field will return an array of rows, where each row is an array containing sub field values.

For the best developer experience, we created some extra functions specifically for looping over rows and accessing sub field values. These are the [have\_rows](https://www.advancedcustomfields.com/resources/functions/have_rows/), [the\_row](https://www.advancedcustomfields.com/resources/functions/have_rows/), [get\_sub\_field](https://www.advancedcustomfields.com/resources/functions/get_sub_field/), and [the\_sub\_field](https://www.advancedcustomfields.com/resources/functions/the_sub_field/) functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#basic-loop)

### Basic loop

Link copied

This example demonstrates how to loop through a Repeater field and load a sub field value.

```php
<?php

// Check rows exists.
if( have_rows('repeater_field_name') ):

    // Loop through rows.
    while( have_rows('repeater_field_name') ) : the_row();

        // Load sub field value.
        $sub_value = get_sub_field('sub_field');
        // Do something, but make sure you escape the value if outputting directly...

    // End loop.
    endwhile;

// No value.
else :
    // Do something...
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#display-slider)

### Display a slider

Link copied

This example demonstrates how to loop through a Repeater field and generate the HTML for a basic image slider.

```php
<?php if( have_rows('slides') ): ?>
    <ul class="slides">
    <?php while( have_rows('slides') ): the_row();
        $image = get_sub_field('image');
        ?>
        <li>
            <?php echo wp_get_attachment_image( $image, 'full' ); ?>
            <p><?php echo acf_esc_html( get_sub_field('caption') ); ?></p>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#foreach-loop)

### Foreach Loop

Link copied

This example demonstrates how you can manually loop over a Repeater field value using a foreach loop.

```php
<?php
$rows = get_field('repeater_field_name');
if( $rows ) {
    echo '<ul class="slides">';
    foreach( $rows as $row ) {
        $image = $row['image'];
        echo '<li>';
            echo wp_get_attachment_image( $image, 'full' );
            echo wp_kses_post( wpautop( $row['caption'] ) );
        echo '</li>';
    }
    echo '</ul>';
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#nested-loops)

### Nested loops

Link copied

This example demonstrates how to loop through a nested Repeater field and load a sub-sub field value.

```php
<?php
/**
 * Field Structure:
 *
 * - parent_repeater (Repeater)
 *   - parent_title (Text)
 *   - child_repeater (Repeater)
 *     - child_title (Text)
 */
if( have_rows('parent_repeater') ):
    while( have_rows('parent_repeater') ) : the_row();

        // Get parent value.
        $parent_title = get_sub_field('parent_title');

        // Loop over sub repeater rows.
        if( have_rows('child_repeater') ):
            while( have_rows('child_repeater') ) : the_row();

                // Get sub value.
                $child_title = get_sub_field('child_title');

            endwhile;
        endif;
    endwhile;
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#accessing-first-row-values)

### Accessing first row values

Link copied

This example demonstrates how to load a sub field value from the first row of a Repeater field.

```php
<?php
$rows = get_field('repeater_field_name' );
if( $rows ) {
    $first_row = $rows[0];
    $first_row_title = $first_row['title'];
    // Do something...
}
```

You may also use the [break](https://www.php.net/manual/en/control-structures.break.php) statement within a `have_rows()` loop to step out at any time.

```php
<?php
if( have_rows('repeater_field_name') ) {
    while( have_rows('repeater_field_name') ) {
        the_row();
        $first_row_title = get_sub_field('title');
        // Do something...
        break;
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#accessing-random-row-values)

### Accessing random row values

Link copied

This example demonstrates how to load a sub field value from a random row of a Repeater field.

```php
<?php
$rows = get_field('repeater_field_name' );
if( $rows ) {
    $index = array_rand( $rows );
    $rand_row = $rows[ $index ];
    $rand_row_title = $rand_row['title'];
    // Do something...
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#editing-a-repeater)

## Editing a repeater

Link copied

Working with the repeater field is relatively straightforward – you just need to click the “Add Row” button to add a new row and edit the values of the subfields that are shown.

But there are a few tips and tricks that can make working with repeaters much easier.

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#pagination)

### Pagination

Link copied

The new “Pagination” setting introduced in ACF 6.0 helps with large repeaters by reducing the number of rows that are rendered at once, potentially avoiding browser crashes and PHP errors that might occur during repeater load or save.

However, there are a few scenarios where pagination isn’t supported. The pagination setting won’t be shown for repeater fields inside other repeaters or flexible content fields. This is something that we hope to address in a near-future release.

Pagination won’t work for [frontend forms](https://www.advancedcustomfields.com/blog/wordpress-frontend-form/) – if the pagination setting is enabled, the repeater will operate like a repeater with pagination disabled when viewed in a frontend form. However, pagination should still work for the same repeater when viewed through the WordPress admin.

Also, pagination does not currently work inside of ACF blocks. That may change in the future, but pagination won’t be able to provide much of a performance benefit in ACF blocks due to the way that blocks store all data in the post content and DOM.

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#adding-inserting-duplicating)

### Adding, inserting, and duplicating rows

Link copied

In addition to adding rows via the “Add Rows” button, you can also insert rows by hovering over a row and clicking the “+” / “Add Row” icon that appears in the far right of the row:

![Inserting a row in a repeater](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/insert-row.png)

If you hold the “Shift” key on your keyboard before clicking that icon, it will change to an icon that lets you duplicate the row:

![Duplicate row button in a repeater](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/duplicate-row.png)

If the row has been inserted, it will appear above the row that you were hovering over previously. If you instead duplicate the row, a new row will appear below the row you were hovering over, with the same values.

If pagination is enabled, rows that were inserted or duplicated won’t display a row number until the changes have been saved.

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#reordering-rows)

### Reordering rows

Link copied

Rows can be reordered in repeaters regardless of the “Pagination” setting. If pagination is disabled, you can hover over the row number on the left hand side and a drag and drop icon will appear.

![Reordering rows with pagination disabled](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/drag-to-to-reorder.png)

If pagination is enabled, you can instead click the row number to reveal a number input. Once you enter a row number and save the page, the row will be moved to the new position.

![Reordering a repeater with pagination enabled.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/reordering-paginated-repeater.png)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/repeater/#related)

## Related

Link copied

- Guides: [How to Use the Repeater Field](https://www.advancedcustomfields.com/resources/how-to-use-the-repeater-field/)
- Field Types: [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/)
- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)
- Functions: [update\_row()](https://www.advancedcustomfields.com/resources/update_row/)
- Functions: [get\_sub\_field()](https://www.advancedcustomfields.com/resources/get_sub_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/repeater/#)