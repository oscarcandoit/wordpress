---
url: https://www.advancedcustomfields.com/resources/gallery
scraped_at: 2025-10-20T02:15:07.718Z
---

# Gallery

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#description)

## Description

Link copied

The Gallery field provides an interactive interface for managing a collection of attachments.

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#screenshots)

## Screenshots

Link copied

[![A gallery field that allows you to select multiple images](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-gallery-field-interface.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-gallery-field-interface.jpg) The Gallery field interface[![List of field settings shown when setting up a Gallery field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-gallery-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-gallery-field-settings.png) The Gallery field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#changelog)

## Changelog

Link copied

- Added `Minimum` setting in version 5.1.9.
- Added `Maximum` setting in version 5.1.9.
- Added `Allowed File Types` setting in version 5.1.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#settings)

## Settings

Link copied

- **Return Format**


Specifies the format of the returned data. Choose from Array (array), URL (string), or ID (integer).

- **Preview Size**


The WordPress image size displayed when editing.

- **Insert**


Specifies where new attachments are added. Chose from either Beginning or End.

- **Library**


Limits file selection to only those that have been uploaded to this post, or the entire library.

- **Minimum Selection**


The minimum number of attachments required for field validation.

- **Maximum Selection**


The maximum number of attachments allowed for field validation.

- **Minimum**


Adds upload validation for minimum width in pixels (integer), height in pixels (integer) and filesize in MB (integer). The filesize may also be entered as a string containing the unit. eg. `’400 KB’`.

- **Maxiumum**


Adds upload validation for maximum width, height and filesize.

- **Allowed File Types**


Adds upload validation for specific file types. Enter a comma separated list to specify which file types are allowed or leave blank to accept all types.


[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#template-usage)

## Template usage

Link copied

The Gallery field will return an array of attachments where each attachment is either an array, a string or an integer value depending on the _Return Format_ set.

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#display-list-of-images)

### Display list of images

Link copied

This example demonstrates how to loop over a Gallery field value and display a list of images. It uses the [wp\_get\_attachment\_image()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image/) function to generate the image HTML. The field in this example uses `ID` as the _Return Format_.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function also generates the srcset attribute allowing for [responsive images](https://make.wordpress.org/core/2015/11/10/responsive-images-in-wordpress-4-4/)!

```php
<?php
$images = get_field('gallery');
$size = 'full'; // (thumbnail, medium, large, full or custom size)
if( $images ): ?>
    <ul>
        <?php foreach( $images as $image_id ): ?>
            <li>
                <?php echo wp_get_attachment_image( $image_id, $size ); ?>
            </li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#display-list-of-images-with-custom-html)

### Display list of images with custom HTML

Link copied

This example also demonstrates how to loop over a Gallery field value and display a list of images. The field in this example uses `Array` as the _Return Format_.

```php
<?php
$images = get_field('gallery');
if( $images ): ?>
    <ul>
        <?php foreach( $images as $image ): ?>
            <li>
                <a href="<?php echo esc_url($image['url']); ?>">
                     <img src="<?php echo esc_url($image['sizes']['thumbnail']); ?>" alt="<?php echo esc_attr($image['alt']); ?>" />
                </a>
                <p><?php echo esc_html($image['caption']); ?></p>
            </li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#display-images-in-a-slider)

### Display images in a slider

Link copied

This example demonstrates how to display the images from a Gallery field in the correct markup required for a WooThemes [Flexslider](http://www.woothemes.com/flexslider/) to work. The field in this example uses `Array` as the _Return Format_.

```php
<?php
$images = get_field('gallery');
if( $images ): ?>
    <div id="slider" class="flexslider">
        <ul class="slides">
            <?php foreach( $images as $image ): ?>
                <li>
                    <img src="<?php echo esc_url($image['url']); ?>" alt="<?php echo esc_attr($image['alt']); ?>" />
                    <p><?php echo esc_html($image['caption']); ?></p>
                </li>
            <?php endforeach; ?>
        </ul>
    </div>
    <div id="carousel" class="flexslider">
        <ul class="slides">
            <?php foreach( $images as $image ): ?>
                <li>
                    <img src="<?php echo esc_url($image['sizes']['thumbnail']); ?>" alt="Thumbnail of <?php echo esc_url($image['alt']); ?>" />
                </li>
            <?php endforeach; ?>
        </ul>
    </div>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#create-a-wordpress-gallery)

### Create a WordPress Gallery

Link copied

This example demonstrates how to display the images from a Gallery field in a WordPress gallery by generating and rendering a gallery shortcode. The field in this example uses `ID` as the _Return Format_.

```php
<?php

// Load value (array of ids).
$image_ids = get_field('gallery');
if( $image_ids ) {

    // Generate string of ids ("123,456,789").
    $images_string = implode( ',', $image_ids );

    // Generate and do shortcode.
    // Note: The following string is split to simply prevent our own website from rendering the gallery shortcode.
    $shortcode = sprintf( '[' . 'gallery ids="%s"]', esc_attr($images_string) );
    echo do_shortcode( $shortcode );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/gallery/#related)

## Related

Link copied

- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Page Link](https://www.advancedcustomfields.com/resources/page-link/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)

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

[Got it](https://www.advancedcustomfields.com/resources/gallery/#)