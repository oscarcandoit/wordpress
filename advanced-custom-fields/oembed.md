---
url: https://www.advancedcustomfields.com/resources/oembed
scraped_at: 2025-10-20T02:18:46.027Z
---

# oEmbed

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#description)

## Description

Link copied

The oEmbed field provides an interactive component for embedding videos, images, tweets, audio, and other content. This field makes use of the native [WordPress oEmbed functionality](https://codex.wordpress.org/Embeds).

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#screenshots)

## Screenshots

Link copied

[![An oEmbed field with an example video from Vimeo in use](https://www.advancedcustomfields.com/wp-content/uploads/2014/04/acf-oembed-field-interface-1.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2014/04/acf-oembed-field-interface-1.jpg) The oEmbed field interface[![List of field settings shown when setting up a oEmbed field](https://www.advancedcustomfields.com/wp-content/uploads/2014/04/acf-oembed-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2014/04/acf-oembed-field-settings.png) The oEmbed field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#changelog)

## Changelog

Link copied

- Added in version 5.0.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#settings)

## Settings

Link copied

- **Embed Size**


Defines the width and height settings for the embed element.

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#template-usage)

## Template usage

Link copied

The oEmbed field will return a string containing the embed HTML obtained by the [wp\_oembed\_get()](https://codex.wordpress.org/Function_Reference/wp_oembed_get) function.

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#display-value)

### Display value.

Link copied

This example demonstrates how to display an oEmbed.

```php
<div class="embed-container">
    <?php the_field('oembed'); ?>
</div>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#display-value-with-additional-attributes)

### Display value with additional attributes.

Link copied

This example demonstrates how to add extra attributes to both the iframe src and HTML.

```php
<?php

// Load value.
$iframe = get_field('oembed');

// Use preg_match to find iframe src.
preg_match('/src="(.+?)"/', $iframe, $matches);
$src = $matches[1];

// Add extra parameters to src and replace HTML.
$params = array(
    'controls'  => 0,
    'hd'        => 1,
    'autohide'  => 1
);
$new_src = add_query_arg($params, $src);
$iframe = str_replace($src, $new_src, $iframe);

// Add extra attributes to iframe HTML.
$attributes = 'frameborder="0"';
$iframe = str_replace('></iframe>', ' ' . $attributes . '></iframe>', $iframe);

// Display customized HTML.
echo $iframe;
?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#responsive-embeds)

### Responsive embeds

Link copied

Thanks to the work done by [embedresponsively.com](http://embedresponsively.com/), it is possible to make embeds responsive. Please view the website to learn more as each provider may need different CSS settings.

```php
<div class="embed-container">
    <?php the_field('oembed'); ?>
</div>
<style>
    .embed-container {
        position: relative;
        padding-bottom: 56.25%;
        overflow: hidden;
        max-width: 100%;
        height: auto;
    }

    .embed-container iframe,
    .embed-container object,
    .embed-container embed {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
</style>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#customizing-other-embed-features)

### Customizing other embed features

Link copied

Due to the large number of embed providers, no settings are available to customize embed features such as overlays and buttons. To customize these settings, you will need to perform a search / replace on the string to add additional arguments to the iframe src.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/oembed/#related)

## Related

Link copied

- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
- Content: [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)

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

[Got it](https://www.advancedcustomfields.com/resources/oembed/#)