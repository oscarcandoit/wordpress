---
url: https://www.advancedcustomfields.com/resources/group
scraped_at: 2025-10-20T02:16:05.231Z
---

# Group

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#description)

## Description

Link copied

The Group field provides a way to structure fields into groups. It assists in better organizing the edit screen UI as well as the data.

The Group field uses both the parent and child field names when saving and loading values. For example, a Group field named ‘hero’ with a sub field named ‘image’ will be saved to the database using the meta name ‘hero\_image’.

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#screenshots)

## Screenshots

Link copied

[![Group field that displays multiple fields (image, link, caption, etc.) within](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-field-group-interface-1.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-field-group-interface-1.jpg) The Group field interface[![List of settings shown when creating a Group field](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-field-group-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-field-group-settings-1.png) The Group field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#changelog)

## Changelog

Link copied

- Added in version 5.6.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#settings)

## Settings

Link copied

- **Sub Fields**


Defines the sub fields which will appear within this group.

- **Layout**


Defines the layout style used to render the field interface.

_Block_: Sub fields are displayed in blocks, one after the other.

_Table_: Sub fields are displayed in a single row table. Labels will appear in the table header.

_Row_: Sub fields are displayed in a two column table. Labels will appear in the first column.


[Link to heading#](https://www.advancedcustomfields.com/resources/group/#template-usage)

## Template Usage

Link copied

The Group field field returns an array containing each sub field’s value in a `name => value` format.

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#display-contents)

### Display contents

Link copied

This example demonstrates how to display the contents of a Group field.

```php
<?php
$hero = get_field('hero');
if( $hero ): ?>
    <div id="hero">
        <img src="<?php echo esc_url( $hero['image']['url'] ); ?>" alt="<?php echo esc_attr( $hero['image']['alt'] ); ?>" />
        <div class="content">
            <?php echo $hero['caption']; ?>
            <a href="<?php echo esc_url( $hero['link']['url'] ); ?>"><?php echo esc_html( $hero['link']['title'] ); ?></a>
        </div>
    </div>
    <style type="text/css">
        #hero {
            background-color: <?php echo esc_attr( $hero['color'] ); ?>;
        }
    </style>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#loop-example)

### Loop example

Link copied

This example demonstrates how to display the same group using the [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/) function. While similar to looping over a Repeater field value, there is only a single row in this value.

```php
<?php if( have_rows('hero') ): ?>
    <?php while( have_rows('hero') ): the_row();

        // Get sub field values.
        $image = get_sub_field('image');
        $link = get_sub_field('link');

        ?>
        <div id="hero">
            <img src="<?php echo esc_url( $image['url'] ); ?>" alt="<?php echo esc_attr( $image['alt'] ); ?>" />
            <div class="content">
                <?php the_sub_field('caption'); ?>
                <a href="<?php echo esc_url( $link['url'] ); ?>"><?php echo esc_attr( $link['title'] ); ?></a>
            </div>
        </div>
        <style type="text/css">
            #hero {
                background-color: <?php the_sub_field('color'); ?>;
            }
        </style>
    <?php endwhile; ?>
<?php endif; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/group/#related)

## Related

Link copied

- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)

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

[Got it](https://www.advancedcustomfields.com/resources/group/#)