---
url: https://www.advancedcustomfields.com/resources/time-picker
scraped_at: 2025-10-20T02:23:24.219Z
---

# Time Picker

Last updated Mar 7, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#description)

## Description

Link copied

The Time Picker field creates a jQuery time selection popup.

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#screenshots)

## Screenshots

Link copied

[![A time picker field that allows you to choose a specific time](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-time-picker-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-time-picker-field-interface.png) The Time Picker field interface[![List of field settings shown when setting up a time picker field](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-time-picker-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/05/acf-time-picker-field-settings.png) The Time Picker field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#changelog)

## Changelog

Link copied

- Added in version 5.3.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#settings)

## Settings

Link copied

- **Display Format**


The time format that is displayed when selecting a date.

- **Return Format**


The time format that is returned when loading the value.


[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#template-usage)

## Template usage

Link copied

The Time Picker field returns a string value using the _Return Format_ setting.

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#display-value)

### Display value

Link copied

This example demonstrates how to display a time value.

```php
<p>Monday: <?php the_field('monday_open_time'); ?> - <?php the_field('monday_close_time'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#query-posts-within-time-range)

### Query posts within time range

Link copied

This example demonstrates how to query posts for all stores that are open.

It assumes a custom post type called ‘store’ exists with a custom field for each day’s open and close time in the following naming convention: ‘monday\_open\_time’, ‘monday\_close\_time’, ‘tuesday\_open\_time’, etc.

When working with the [meta\_query array](https://codex.wordpress.org/Class_Reference/WP_Query#Custom_Field_Parameters), remember that WordPress reads this as `$meta $compare $value` (eg. ‘monday\_open\_time’ < $time)

```php
<?php

// Find today's day of the week.
$today = date('l');
$today = strtolower( $today );

// Find current time.
$time = date('H:i:s');

// Query stores using custom fields in meta_query.
$posts = get_posts(array(
    'posts_per_page'    => -1,
    'post_type'         => 'store',
    'meta_query'        => array(
        'relation'          => 'AND',
        array(
            'key'           => $today.'_open_time',
            'compare'       => '<=',
            'value'         => $time,
            'type'          => 'TIME'
        ),
        array(
            'key'           => $today.'_close_time',
            'compare'       => '>=',
            'value'         => $time,
            'type'          => 'TIME'
        )
    )
));

if( $posts ): ?>

    <h2>Stores open now</h2>
    <ul id="events">
        <?php foreach( $posts as $p ): ?>
            <li>
                <strong><?php echo $p->post_title; ?></strong>:
                <?php echo $today; ?> <?php the_field( $today.'_open_time', $p->ID ); ?> -  <?php the_field( $today.'_close_time', $p->ID ); ?>
            </li>
        <?php endforeach; ?>
    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#database-format)

### Database format

Link copied

The value selected can be returned and displayed in different formats but will be saved to the database as ‘H:i:s’. This format is used throughout the WordPress database tables and will allow for straight-foward database querying.

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#time-format-strings)

### Time format strings

Link copied

To customize the _Display Format_ and _Return Format_ settings further, refer to the full list of time format strings within the [PHP date() documentation](http://php.net/manual/en/function.date.php).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/time-picker/#related)

## Related

Link copied

- Field Types: [Date Time Picker](https://www.advancedcustomfields.com/resources/date-time-picker/)
- Field Types: [Date Picker](https://www.advancedcustomfields.com/resources/date-picker/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)

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

[Got it](https://www.advancedcustomfields.com/resources/time-picker/#)