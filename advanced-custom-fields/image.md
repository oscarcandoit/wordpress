---
url: https://www.advancedcustomfields.com/resources/image
scraped_at: 2025-10-20T02:31:46.306Z
---

# Image

Last updated Oct 23, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#description)

## Description

Link copied

The Image field allows an image to be uploaded and selected by using the native WordPress media modal.

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#screenshots)

## Screenshots

Link copied

[![An image field that allows you to select an image to upload to your media](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-image-field-interface-1.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-image-field-interface-1.jpg) The Image field interface[![List of field settings shown when setting up an Image field.](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-image-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-image-field-settings.png) The Image field settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#changelog)

## Changelog

Link copied

- Added `Minimum` setting in version 5.1.9.
- Added `Maximum` setting in version 5.1.9.
- Added `Allowed File Types` setting in version 5.1.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#settings)

## Settings

Link copied

- **Return Format**


Specifies the format of the returned data. Choose from Image Array (array), Image URL (string), or Image ID (integer).

- **Preview Size**


The WordPress image size displayed when editing values.

- **Library**


Limits file selection to only those that have been uploaded to this post, or the entire library.

- **Minimum**


Adds upload validation for minimum width in pixels (integer), height in pixels (integer) and filesize in MB (integer). The filesize may also be entered as a string containing the unit, e.g., `'400KB'`.

- **Maximum**


Adds upload validation for maximum width, height and file size.

- **Allowed File Types**


Adds upload validation for specific file types. Enter a comma separated list to specify which file types are allowed or leave blank to accept all types.


[Link to heading#](https://www.advancedcustomfields.com/resources/image/#template-usage)

## Template usage

Link copied

The Image field will return either an array, a string or an integer value depending on the _Return Value_ set.

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#display-image-id)

### Display image (ID)

Link copied

This example demonstrates how to display the selected image when using the `Image ID` return type. This example uses the [wp\_get\_attachment\_image()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image/) function to generate the image HTML.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function also generates the srcset attribute allowing for [responsive images](https://make.wordpress.org/core/2015/11/10/responsive-images-in-wordpress-4-4/)!

```php
<?php
$image = get_field('image');
$size = 'full'; // (thumbnail, medium, large, full or custom size)
if( $image ) {
    echo wp_get_attachment_image( $image, $size );
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#display-image-array)

### Display image (array)

Link copied

This example demonstrates how to display the selected image when using the `Image Array` return type. This return type provides extra image data such as alt text, caption, and sizes.

```php
<?php
$image = get_field('image');
if( !empty( $image ) ): ?>
    <img src="<?php echo esc_url($image['url']); ?>" alt="<?php echo esc_attr($image['alt']); ?>" />
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#customized-display-array)

### Customized display (array)

Link copied

This example demonstrates how to display a custom size of the selected image when using the `Image Array` return type. This return type allows us to access extra image data such as sizes, width, height, and more.

```php
<?php
$image = get_field('image');
if( $image ):

    // Image variables.
    $url = $image['url'];
    $title = $image['title'];
    $alt = $image['alt'];
    $caption = $image['caption'];

    // Thumbnail size attributes.
    $size = 'thumbnail';
    $thumb = $image['sizes'][ $size ];
    $width = $image['sizes'][ $size . '-width' ];
    $height = $image['sizes'][ $size . '-height' ];

    // Begin caption wrap.
    if( $caption ): ?>
        <div class="wp-caption">
    <?php endif; ?>

    <a href="<?php echo esc_url($url); ?>" title="<?php echo esc_attr($title); ?>">
        <img src="<?php echo esc_url($thumb); ?>" alt="<?php echo esc_attr($alt); ?>" />
    </a>

    <?php
    // End caption wrap.
    if( $caption ): ?>
        <p class="wp-caption-text"><?php echo esc_html($caption); ?></p>
        </div>
    <?php endif; ?>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#display-image-url)

### Display image (URL)

Link copied

This example demonstrates how to display the selected image when using the `Image URL` return type. This return type allows us to efficiently display a basic image but prevents us from loading any extra data about the image.

```php
<?php if( get_field('image') ): ?>
    <img src="<?php the_field('image'); ?>" />
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

[Link to heading#](https://www.advancedcustomfields.com/resources/image/#related)

## Related

Link copied

- Content: [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)
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

[Got it](https://www.advancedcustomfields.com/resources/image/#)