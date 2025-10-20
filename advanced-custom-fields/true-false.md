---
url: https://www.advancedcustomfields.com/resources/true-false
scraped_at: 2025-10-20T02:18:59.806Z
---

# True / False

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#description)

## Description

Link copied

The True / False field allows you to select a value that is either 1 or 0.

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#screenshots)

## Screenshots

Link copied

[![True/false field that allows you to check a box or toggle a switch](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-true-false-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-true-false-field-interface.png) The True / False field interface[![List of settings shown when creating a True/false field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-true-false-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-true-false-field-settings-1.png) The True / False field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#changelog)

## Changelog

Link copied

- Added `UI` setting in version 5.5.0.
- Added `On Text` setting in version 5.5.0.
- Added `Off Text` setting in version 5.5.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#settings)

## Settings

Link copied

- **Message**


The text displayed alongside the toggle.

- **Default Value**


Specifies the default state selected when first editing the field’s value.

- **Stylized UI**


Changes the default checkbox input into a stylized toggle switch.

- **On Text**


The text displayed within the stylized toggle switch. Defaults to ‘Yes’. HTML may be entered for icons or custom markup.

- **Off Text**


The text displayed within the stylized toggle switch. Defaults to ‘No’. HTML may be entered for icons or custom markup.


[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#template-usage)

## Template usage

Link copied

The True / False field returns a Boolean value of either `true` or `false`.
Note that the actual value saved into the database is an integer of either 1 or 0.

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#conditional)

### Conditional

Link copied

This example demonstrates how to use the value of ‘enable\_sidebar’ to conditionally do a task.

```php
<?php
if( get_field('color') ) {
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#query-posts)

### Query Posts

Link copied

This example demonstrates how to query posts that have a `true` value for the field ‘show\_in\_sidebar’.

```php
<?php

$posts = get_posts( array(
    'meta_query' => array(
        array(
            'key'   => 'show_in_sidebar',
            'value' => '1',
        )
    )
) );

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/true-false/#related)

## Related

Link copied

- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Choice: [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)

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

[Got it](https://www.advancedcustomfields.com/resources/true-false/#)