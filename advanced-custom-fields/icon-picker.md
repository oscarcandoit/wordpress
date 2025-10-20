---
url: https://www.advancedcustomfields.com/resources/icon-picker
scraped_at: 2025-10-20T02:33:32.335Z
---

# Icon Picker

Last updated May 8, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#description)

## Description

Link copied

The Icon Picker field allows you to easily select a [Dashicon](https://developer.wordpress.org/resource/dashicons/), a Media Library image, or a URL for an image or SVG.

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#screenshots)

## Screenshots

Link copied

[![An icon picker field that allows you to select an icon from various sources.](https://www.advancedcustomfields.com/wp-content/uploads/2024/05/acf-icon-picker-field-editor.png)](https://www.advancedcustomfields.com/wp-content/uploads/2024/05/acf-icon-picker-field-editor.png) The Icon Picker field interface.[![List of field settings shown when setting up an Icon Picker field.](https://www.advancedcustomfields.com/wp-content/uploads/2024/05/acf-icon-picker-admin.png)](https://www.advancedcustomfields.com/wp-content/uploads/2024/05/acf-icon-picker-admin.png) The Icon Picker field settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#changelog)

## Changelog

Link copied

- Added in version 6.3.0

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#settings)

## Settings

Link copied

- **Tabs**
Specifies which tabs should be shown for this instance of the Icon Picker. Choose from Dashicons, Media Library, and URL.

- **Return Format**


Specifies the format of the returned data. Choose from String or Array.
If String is chosen, for Dashicons this will be the string of the dashicon class, for Media Library it will be the URL to the attachment, and for URL it will be the URL value.


[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#template-usage)

## Template Usage

Link copied

The Icon Picker field returns an array or a string value, depending on the **Return Format** selected when creating the field.

If you chose **Array**, you will get an array with 2 keys. The first key is `type` and the second is `value`.

The `type` indicates the type of icon chosen and will be one of the following:

- `dashicons`
- `media_library`
- `url`

The `value` will correspond to the `type`, i.e., `dashicon` gives a dashicon class as the value, while `media_library` and `url` give a URL as the value.

If you chose **String**, you’ll get a string as the response, but the value of the string still depends on the type of icon selected in the picker:

- **Dashicon:** The value will be the dashicon class string.

- **Media Library:** The value will be the URL to the image.

- **URL**: The value will be the URL to the image.


_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Most often, you might choose **String** as a return type if you’ve also disabled all but one of the tabs when configuring the Icon Picker field for your field group. Otherwise, you’ll likely want to use **Array** so you can handle each icon type.

Your render template can be set up to handle any type of icon, as well as handling both array and string return formats:

```php
<?php
$icon = get_field('my_icon');

// Handle if the return type is a string.
if ( is_string( $icon ) ) {

   // If the type selected was a Dashicon, the value of $icon will be the dashicon class string.
   // If the type selected was a Media Library image, the value of $icon will be the URL to the image.
   // If the type selected was a URL, the value of $icon will be the URL to the image.
   echo esc_html( $icon );

} else {
   // Handle if the return type is an array.

   // If the type selected was a Dashicon, render a div with the dashicon class.
   if ( 'dashicons' === $icon['type'] ) {
       ?><div class="<?php echo esc_attr( $icon['value'] ); ?>”></div><?php
   }

   // If the type selected was a Media Library image, use the attachment ID to get and render the image.
   if ( 'media_library' === $icon['type'] ) {
       $attachment_id = $icon['value'];
       $size = 'full'; // (thumbnail, medium, large, full, or custom size)

       $image_html = wp_get_attachment_image( $attachment_id, $size );
       echo wp_kses_post( $image_html );
   }

   // If the type selected was a URL, render an image tag with the URL.
   if ( 'url' === $icon['type'] ) {
       $url = $icon['value'];
       ?><img src="<?php echo esc_url( $url ); ?>" alt=""><?php
   }
}
```

Note that for Dashicons, they are typically used as class names on an HTML element, and typically also rely on [this CSS stylesheet](https://github.com/WordPress/dashicons/blob/master/icon-font/css/dashicons.css). ACF does not enqueue this stylesheet, so if you rely on it, you will need to [enqueue it yourself](https://developer.wordpress.org/reference/functions/wp_enqueue_style/).

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#adding-custom-tabs)

## Adding Custom Tabs

Link copied

The Icon Picker field includes filters and action hooks that can be used to add custom tabs. The following is a basic example of how you can add a new “Cards” tab, complete with a custom icon set sourced from PNG files saved in your theme.

To add a new tab, first define the tab via the `acf/fields/icon_picker/tabs` filter:

```php
<?php
function add_cards_icon_picker_tab( array $tabs ): array {
    $tabs['cards'] = 'Cards';
    return $tabs;
}
add_filter( 'acf/fields/icon_picker/tabs', 'add_cards_icon_picker_tab' );
```

This will add a new empty tab to the Icon Picker field. This empty tab will then check for icons provided to the `acf/fields/icon_picker/{$tab_name}/icons` filter, where {$tab\_name} is the tab key provided to the above filter.

You can provide icons for the newly created tab like so:

```php
function add_cards_icons( array $icons ): array {
    // Replace with the base URL path of your custom icons.
    $base_url = get_template_directory_uri() . '/cards/';

    return array(
        array(
            'url'   => $base_url . 'ace-of-spades-playing-card.png', // URL of the icon.
            'key'   => 'ace-of-spades', // Saved as the value in the icon picker field.
            'label' => 'Ace of Spades', // Name of the card used in search.
        ),
        array(
            'url'   => $base_url . 'eight-of-clubs-playing-card.png',
            'key'   => 'eight-of-clubs',
            'label' => 'Eight of Clubs',
        ),
        array(
            'url'   => $base_url . 'jack-of-hearts-playing-card.png',
            'key'   => 'jack-of-hearts',
            'label' => 'Jack of Hearts',
        ),
    );
}
add_filter( 'acf/fields/icon_picker/cards/icons', 'add_cards_icons' );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/icon-picker/#related)

## Related

Link copied

- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)
- Content: [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)
- Field Types: [Date Time Picker](https://www.advancedcustomfields.com/resources/date-time-picker/)

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

[Got it](https://www.advancedcustomfields.com/resources/icon-picker/#)