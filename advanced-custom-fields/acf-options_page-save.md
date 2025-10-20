---
url: https://www.advancedcustomfields.com/resources/acf-options_page-save
scraped_at: 2025-10-20T02:29:20.994Z
---

# acf/options\_page/save

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-save/#description)

## Description

Link copied

Fires after publishing a save on an options page.

This action allows you to hook in after an options page has been saved in the admin.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-save/#parameters)

## Parameters

Link copied

```php
do_action( 'acf/options_page/save', $post_id, $menu_slug );
```

- `$post_id` _(int\|string)_ The ID of the page being edited.
- `$menu_slug` _(string)_ The current options page menu slug.

The `$post_id` defaults to ‘options’, but can be set as a post or a user ID when [registering the options page](https://www.advancedcustomfields.com/resources/acf_add_options_page/#settings).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-save/#changelog)

## Changelog

Link copied

- Added in version 6.1.7

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-save/#example)

## Example

Link copied

```php
add_action('acf/options_page/save', 'my_acf_save_options_page', 10, 2);
function my_acf_save_options_page( $post_id, $menu_slug ) {

    if ( 'theme-settings' !== $menu_slug ) {
        return;
    }
    // Get newly saved values for the theme settings page.
    $values = get_fields( $post_id );

    // Check the new value of a specific field.
    $analytics_code = get_field('analytics_code', $post_id);
    if( $analytics_code ) {
        // Do something...
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-save/#related)

## Related

Link copied

- Actions: [acf/save\_post](https://www.advancedcustomfields.com/resources/acf-save_post/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Deprecated: [acf\_set\_options\_page\_title()](https://www.advancedcustomfields.com/resources/acf_set_options_page_title/)
- Actions: [acf/validate\_save\_post](https://www.advancedcustomfields.com/resources/acf-validate_save_post/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-options_page-save/#)