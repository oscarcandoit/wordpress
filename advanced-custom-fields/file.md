---
url: https://www.advancedcustomfields.com/resources/file
scraped_at: 2025-10-20T02:18:40.491Z
---

# File

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#description)

## Description

Link copied

The File field allows a file to be uploaded and selected by using the native WP media popup.

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#screenshots)

## Screenshots

Link copied

[![A file field that allows you to upload and select a file](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-file-field-interface.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-file-field-interface.jpg) The File field interface[![The list of File field settings shown when setting up a File field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-file-field-settings.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-file-field-settings.jpg) The File field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#changelog)

## Changelog

Link copied

- Added `minimum` setting in version 5.1.9.
- Added `maximum` setting in version 5.1.9.
- Added `allowed file types` setting in version 5.1.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#settings)

## Settings

Link copied

- **Return value**


Specifies the format of the returned data. Choose from File Array (array), File URL (string), or File ID (integer).

- **Library**


Limits file selection to only those that have been uploaded to this post, or the entire library.

- **Minimum**


Adds upload validation for minimum filesize in MB (integer). The filesize may also be entered as a string containing the unit. eg. ’400 KB’.

- **Maximum**


Adds upload validation for maximum filesize.

- **Allowed file types**


Adds upload validation for specific file types. Enter a comma separated list to specify which file types are allowed or leave blank for all types.


[Link to heading#](https://www.advancedcustomfields.com/resources/file/#template-usage)

## Template usage

Link copied

The File field will return either an array, a string or an integer value depending on the _Return Value_ set. Below are some examples of how you can use this data.

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#basic-display-array)

### Basic display (array)

Link copied

This example demonstrates how to display the selected file when using the `array` return type. This return type allows us to easily access data such as `url` and `filename`.

```php
<?php
$file = get_field('file');
if( $file ): ?>
    <a href="<?php echo $file['url']; ?>"><?php echo $file['filename']; ?></a>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#advanced-display-array)

### Advanced display (array)

Link copied

This example demonstrates how to display a custom link when using the `array` return type. This return type allows us to easily access data such as `url`, `title`, `type` and more.

```php
<?php
$file = get_field('file');
if( $file ):

    // Extract variables.
    $url = $file['url'];
    $title = $file['title'];
    $caption = $file['caption'];
    $icon = $file['icon'];

    // Display image thumbnail when possible.
    if( $file['type'] == 'image' ) {
        $icon =  $file['sizes']['thumbnail'];
    }

    // Begin caption wrap.
    if( $caption ): ?>
        <div class="wp-caption">
    <?php endif; ?>

    <a href="<?php echo esc_attr($url); ?>" title="<?php echo esc_attr($title); ?>">
        <img src="<?php echo esc_attr($icon); ?>" />
        <span><?php echo esc_html($title); ?></span>
    </a>

    <?php
    // End caption wrap.
    if( $caption ): ?>
        <p class="wp-caption-text"><?php echo esc_html($caption); ?></p>
        </div>
    <?php endif; ?>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#basic-display-id)

### Basic display (ID)

Link copied

This example demonstrates how to display the selected file when using the `ID` return type.

```php
<?php
$file = get_field('file');
if( $file ):
    $url = wp_get_attachment_url( $file ); ?>
    <a href="<?php echo esc_html($url); ?>" >Download File</a>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#basic-display-url)

### Basic display (URL)

Link copied

This example demonstrates how to display the selected file when using the `URL` return type.

```php
<?php if( get_field('file') ): ?>
    <a href="<?php the_field('file'); ?>" >Download File</a>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/file/#related)

## Related

Link copied

- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
- Content: [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Page Link](https://www.advancedcustomfields.com/resources/page-link/)

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

[Got it](https://www.advancedcustomfields.com/resources/file/#)