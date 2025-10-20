---
url: https://www.advancedcustomfields.com/resources/date-picker
scraped_at: 2025-10-20T02:29:12.374Z
---

# Date Picker

Last updated Mar 22, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#description)

## Description

Link copied

The Date Picker field provides a jQuery date selection popup.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#screenshots)

## Screenshots

Link copied

​​

![Creating a Date Picker Field in an ACF field group. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/ACF-Date-Picker-Settings.png)

Creating a Date Picker Field in an ACF field group.

![The Date Picker field from the point of view of a content editor. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/ACF-Date-Picker-Content-Editor-View.png)

The Date Picker field from the point of view of a content editor.

![Clicking on the field opens a calendar, allowing the content editor to easily choose the correct date. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/ACF-Date-Picker-Content-Editor-View-Calendar-1.png)

Clicking on the field opens a calendar, allowing the content editor to easily choose the correct date.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#settings)

## Settings

Link copied

- **Display Format**


The date format that is displayed when selecting a date.

- **Return Format**


The date format that is returned when loading the value. Please note that the value is always saved as `Ymd` (YYYYMMDD) in the database.

- **Week Starts On**


Specifies the day to start the week on. Defaults to Monday.

- **Required**


Found on the Validation tab, this prevents the field from accepting empty values. Defaults to off.

- **Instructions**


Shows instructions when submitting data.


[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#template-usage)

## Template usage

Link copied

The Date Picker field returns a date string using the _Return Format_ setting.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#display-value)

### Display value

Link copied

This example demonstrates how to display a date value.

```php
<p>Event Date: <?php echo esc_html ( get_field( 'date' ) ); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#modify-value)

### Modify value

Link copied

This example demonstrates how to convert a string date value into a DateTime object.

```php
<?php

// Load field value.
$date_string = get_field( 'date' );

// Create DateTime object from value (formats must match).
$date = DateTime::createFromFormat( 'Ymd', $date_string );

// Output current date in custom format.
?>
<p>Event start date: <?php echo $date->format( 'j M Y' ); ?></p>
<?php

// Increase by 1 day and output again.
$date->modify( '+1 day' );
?>
<p>Event end date: <?php echo $date->format( 'j M Y' ); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#query-posts-sorted-in-order)

### Query posts sorted in order

Link copied

This example demonstrates how you can query posts sorted in order of a custom field value.

```php
<?php

$posts = get_posts( array(
    'post_type' => 'event',
    'meta_key'  => 'date',
    'orderby'   => 'meta_value_num',
    'order'     => 'ASC',
));

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#query-posts-within-date-range)

### Query posts within date range

Link copied

This example demonstrates how you can query posts to find events happening today.

```php
<?php

// Find today’s date in Ymd format.
$today = date( 'Ymd' );

// Query posts using a meta_query to compare two custom fields: start_date and end_date.
$posts = get_posts( array(
    'post_type' => 'event',
    'meta_query' => array(
        array(
            'key'     => 'start_date',
            'compare' => '>=',
            'value'   => $today,
        ),
         array(
            'key'     => 'end_date',
            'compare' => '<=',
            'value'   => $today,
        )
    ),
));

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#database-format)

### Database format

Link copied

The value selected can be returned and displayed in different formats but will be saved to the database as ‘Ymd’. If you are updating this value manually, you _must_ use the `Ymd` format. This format is used throughout the WordPress database tables and will allow for straight-foward database querying.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#date-format-strings)

### Date format strings

Link copied

To customize the _Display Format_ and _Return Format_ settings further, refer to the full list of date format strings within the [DateTime::createFromFormat() documentation](https://www.php.net/manual/en/datetime.createfromformat.php).

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#date-formats-in-javascript)

### Date formats in JavaScript

Link copied

Some JavaScript libraries might format PHP date strings differently. For example, the following date function in PHP:

```php
echo date( 'F j, Y @ g:i a' );
```

Will output something like:

```php
November 19, 2021 @ 1:49 pm
```

However, if you pass this value to something like the [jQuery UI DatePicker Widget](https://api.jqueryui.com/datepicker/), it will see the `@` as a special character to be [formatted](https://api.jqueryui.com/datepicker/#utility-formatDate) with the Unix timestamp, which is not ideal.

Use the `acf/settings/php_to_js_date_formats` filter to fix this, as it will convert any instance of the `@` symbol to `'@'`. This will ensure it’s treated as a string in JavaScript instead of a character to be replaced.

```php php
add_filter( 'acf/settings/php_to_js_date_formats', 'support_at_symbol_in_date_format', 10, 1 );
function support_at_symbol_in_date_format( $formats ) {
    $formats['@'] = "'@'";
    return $formats;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#translations)

### Translations

Link copied

If you require the date to be displayed in a non-English language, WordPress contains a function called [date\_i18n()](http://codex.wordpress.org/Function_Reference/date_i18n) which will perform the translation for you.

```php
<?php

// Load field value and convert to numeric timestamp.
$unixtimestamp = strtotime( get_field( 'date' ) );

// Display date in the format "l d F, Y".
echo date_i18n( "l d F, Y", $unixtimestamp );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/date-picker/#related)

## Related

Link copied

- Field Types: [Date Time Picker](https://www.advancedcustomfields.com/resources/date-time-picker/)
- Field Types: [Time Picker](https://www.advancedcustomfields.com/resources/time-picker/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)

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

[Got it](https://www.advancedcustomfields.com/resources/date-picker/#)