---
url: https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients
scraped_at: 2025-10-20T02:25:57.476Z
---

# Disable Custom Fields Editing on a Live Site

Last updated Jul 21, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#overview)

## Overview

Link copied

When delivering a website to a client, it may be beneficial to hide the “ACF” menu item. This prevents your client from changing or deleting fields and keeps the site running smoothly.

This doc details three methods for hiding the ACF menu:

- Hiding the menu for _all_ users on every site.
- Hiding the menu for _specific_ users on every site.
- Hiding the menu on a live site while retaining functionality on the staging site.

This last option is likely the most common use case, as it allows you to continue editing fields when needed while ensuring clients can’t make any unauthorized changes.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#hide-for-all-users)

### Hide for All Users

Link copied

The ACF menu item can be hidden for all users by adding the following code to the `functions.php` file of the active theme. However, we recommend putting the code in an [mu-plugin](https://wordpress.org/documentation/article/must-use-plugins/) instead, ensuring it isn’t lost when switching themes. Please note that `__return_false` is a WordPress function which simply returns false.

```php
add_filter('acf/settings/show_admin', '__return_false');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#hide-for-specific-users)

### Hide for Specific Users

Link copied

The code above can be enhanced to only return false for specific users. The following code uses the WordPress function `current_user_can()` to return true or false depending on the current user’s capability. Please note that `manage_options` is a capability that only admins (and super admins) have by default.

```php
add_filter('acf/settings/show_admin', 'my_acf_show_admin');

function my_acf_show_admin( $show ) {

    return current_user_can('manage_options');

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#hide-on-live-site-only)

### Hide on Live Site Only

Link copied

Adding the code below to your `functions.php` file hides the ACF menu on a live site, while retaining it on a staging or local development site.

```php
if ( wp_get_environment_type() === 'production' ) {

    // Only allow fields to be edited on development
    add_filter( 'acf/settings/show_admin', '__return_false' );

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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#related)

## Related

Link copied

- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Filters: [acf/settings](https://www.advancedcustomfields.com/resources/acf-settings/)
- Guides: [How to Create an Options Page](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-hide-acf-menu-from-clients/#)