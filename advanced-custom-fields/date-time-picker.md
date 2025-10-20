---
url: https://www.advancedcustomfields.com/resources/date-time-picker
scraped_at: 2025-10-20T02:18:35.201Z
---

# Date Time Picker

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#description)

## Description

Link copied

The Date Time Picker field creates a jQuery date & time selection popup.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#screenshots)

## Screenshots

Link copied

[![A time date field that allows you to choose a specific date and time](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-date-time-picker-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-date-time-picker-interface.png) The Date Time Picker field interface[![List of field settings shown when setting up a date time picker field](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-date-time-picker-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-date-time-picker-settings-1.png) The Date Time Picker field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#changelog)

## Changelog

Link copied

- Added in version 5.3.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#settings)

## Settings

Link copied

- **Display Format**


The date format that is displayed when selecting a date.

- **Return Format**


The date format that is returned when loading the value. Please note that the value is always saved as `Y-m-d H:i:s` (YYYY-MM-DD HH:II:SS) in the database.

- **Week Starts On**


Specifies the day to start the week on.


[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#template-usage)

## Template usage

Link copied

The Date Time Picker field returns a date-time string using the _Return Format_ setting.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#display-value)

### Display value

Link copied

This example demonstrates how to display a date-time value.

```php
<p>Event starts: <?php the_field('start_date'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#query-posts-sorted-in-order)

### Query posts sorted in order

Link copied

This example demonstrates how you can query posts sorted in order of a custom field value.

```php
<?php

$posts = get_posts( array(
    'posts_per_page' => -1,
    'post_type'      => 'event',
    'order'          => 'ASC',
    'orderby'        => 'meta_value',
    'meta_key'       => 'start_date',
    'meta_type'      => 'DATETIME',
));

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#query-posts-within-date-range)

### Query posts within date range

Link copied

This example demonstrates how you can query posts to find events that are currently happening today.

```php
<?php

// Find todays date in Ymd format.
$date_now = date('Y-m-d H:i:s');

// Query posts using a meta_query to compare two custom fields; start_date and end_date.
$posts = get_posts( array(
    'post_type' => 'event',
    'meta_query' => array(
        array(
            'key'           => 'start_date',
            'compare'       => '<=',
            'value'         => $date_now,
            'type'          => 'DATETIME',
        ),
        array(
            'key'           => 'end_date',
            'compare'       => '>=',
            'value'         => $date_now,
            'type'          => 'DATETIME',
        )
    ),
));

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#query-upcoming-posts)

### Query upcoming posts

Link copied

This example demonstrates how to query and loop over upcoming events (in the next 7 days) ordered by a custom date time field value.

```php
<?php

// Find current date time.
$date_now = date('Y-m-d H:i:s');
$time_now = strtotime($date_now);

// Find date time in 7 days.
$time_next_week = strtotime('+7 day', $time_now);
$date_next_week = date('Y-m-d H:i:s', $time_next_week);

// Query events.
$posts = get_posts(array(
    'posts_per_page' => -1,
    'post_type'      => 'event',
    'meta_query'     => array(
        array(
            'key'         => 'start_date',
            'compare'     => 'BETWEEN',
            'value'       => array( $date_now, $date_next_week ),
            'type'        => 'DATETIME'
        )
    ),
    'order'          => 'ASC',
    'orderby'        => 'meta_value',
    'meta_key'       => 'start_date',
    'meta_type'      => 'DATETIME'
));

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#save-as-unix-timestamp)

### Save as unix timestamp

Link copied

This example demonstrates how to change the value saved from the standard ‘Y-m-d H:i:s’ string to a unix timestamp number. This may be necessary to maintain compatibility with third party date time picker fields.

```php
<?php

add_filter('acf/update_value/type=date_time_picker', 'my_update_value_date_time_picker', 10, 3);

function my_update_value_date_time_picker( $value, $post_id, $field ) {
    return strtotime( $value );
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#database-format)

### Database format

Link copied

The value selected can be returned and displayed in different formats but will be saved to the database as ‘Y-m-d H:i:s’. This format is used throughout the WordPress database tables and will allow for straight-foward database querying.

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#date-format-strings)

### Date format strings

Link copied

To customize the _Display Format_ and _Return Format_ settings further, refer to the full list of date format strings within the [DateTime::createFromFormat() documentation](https://www.php.net/manual/en/datetime.createfromformat.php).

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#date-formats-in-javascript)

### Date formats in JavaScript

Link copied

Some JavaScript libraries might format PHP date strings differently. For example, the following date function in PHP:

```php
echo date('F j, Y @ g:i a');
```

Will output something like:

```php
November 19, 2021 @ 1:49 pm
```

However, if you pass this value to the somethign like the [jQuery UI DatePicker Widget](https://api.jqueryui.com/datepicker/), it will see the `@` as a special character to be [formatted](https://api.jqueryui.com/datepicker/#utility-formatDate) return the Unix timestamp, which is not ideal.

In order to fix this, you can use the `acf/settings/php_to_js_date_formats` filter, which will convert any instance of the `@` symbol to `'@'`, and thereby treated as a string in JavaScript, instead of a character to be replaced.

```php
add_filter('acf/settings/php_to_js_date_formats', 'support_at_symbol_in_date_format', 10, 1);
function support_at_symbol_in_date_format($formats) {
    $formats['@'] = "'@'";
    return $formats;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#translations)

### Translations

Link copied

If you require the date to be displayed in a non English language, WordPress contains a function called [date\_i18n()](http://codex.wordpress.org/Function_Reference/date_i18n) which will perform the translation for you.

```php
<?php

// Load field value and convert to numeric timestamp.
$unixtimestamp = strtotime( get_field('date') );

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

[Link to heading#](https://www.advancedcustomfields.com/resources/date-time-picker/#related)

## Related

Link copied

- Field Types: [Date Picker](https://www.advancedcustomfields.com/resources/date-picker/)
- Field Types: [Time Picker](https://www.advancedcustomfields.com/resources/time-picker/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Field Types: [Page Link](https://www.advancedcustomfields.com/resources/page-link/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)

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

[Got it](https://www.advancedcustomfields.com/resources/date-time-picker/#)