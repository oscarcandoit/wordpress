---
url: https://www.advancedcustomfields.com/resources/link
scraped_at: 2025-10-20T02:33:40.531Z
---

# Link

Last updated May 30, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#description)

## Description

Link copied

The Link field allows a link to be selected or defined (url, title, target) by using the native WordPress link popup.

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#screenshots)

## Screenshots

Link copied

[![A Link field that allows you to enter a new URL or choose an existing link from a list](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-link-field-interface-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-link-field-interface-1.png) The Link field interface[![List of field settings shown when setting up a Link field](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-link-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-link-field-settings-1.png) The Link field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#changelog)

## Changelog

Link copied

- Added in version 5.6.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#settings)

## Settings

Link copied

- **Return value**


Specifies the format of the returned data. Choose from Link Array (array of data) or Link URL (string).

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#template-usage)

## Template usage

Link copied

The Link field will return either an array or string depending on the _return value_ setting. Below are some examples of how you can use this data.

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#basic-display-array)

### Basic display (array)

Link copied

This example demonstrates how to display the selected link when using the `Link Array` return type.

```php
<?php
$link = get_field('link');
if( $link ):
    $link_url = $link['url'];
    $link_title = $link['title'];
    $link_target = $link['target'] ? $link['target'] : '_self';
    ?>
    <a class="button" href="<?php echo esc_url( $link_url ); ?>" target="<?php echo esc_attr( $link_target ); ?>"><?php echo esc_html( $link_title ); ?></a>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#basic-display-string)

### Basic display (string)

Link copied

This example demonstrates how to display the selected link when using the `Link URL` return type.

```php
<?php
$link = get_field('link');
if( $link ): ?>
    <a class="button" href="<?php echo esc_url( $link ); ?>">Continue Reading</a>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#require-input-in-link-field)

### Require input in link field

Link copied

Depending on how you are using the link field’s data, you may want to require the link text field be filled out, especially if using it for accessibility purposes.

You can add a custom validation function to require the link text field be completed using the `acf/validate_value` filter like this:

```php
function my_custom_validation_callback_function( $valid, $value, $field, $input_name ) {
    // If the field type being validated is a link field, the return format is "array", and the title is blank.
    if ( 'link' === $field['type'] && 'array' === $field['return_format'] && empty( $value['title'] ) ) {
        // Show an error message.
         return __( 'Please ensure you have entered a value for the link text.' );
    }
    // Otherwise, don't change anything.
    return $valid;
}
add_filter( 'acf/validate_value', 'my_custom_validation_callback_function', 10, 4 );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/link/#related)

## Related

Link copied

- Content: [File](https://www.advancedcustomfields.com/resources/file/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
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

[Got it](https://www.advancedcustomfields.com/resources/link/#)