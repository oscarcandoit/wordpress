---
url: https://www.advancedcustomfields.com/resources/adding-fields-menus
scraped_at: 2025-10-20T02:17:20.561Z
---

# Adding fields to Menus

Last updated Sep 6, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#overview)

## Overview

Link copied

This guide will demonstrate how to add custom fields to a WordPress Menu and how to then modify the Menu’s HTML.

Menus are used to organize a group of links (menu items) for your theme to display as navigation. If you are unfamiliar with registering or editing a Menu, please read the [WordPress Menu User Guide](https://codex.wordpress.org/WordPress_Menu_User_Guide) and [Navigation\_Menus](https://codex.wordpress.org/Navigation_Menus) documentation.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Menus are used to group menu items. Learn how to [add fields to Menu Items](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/).

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#changelog)

## Changelog

Link copied

- Added support for Menu in version 5.6.0

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#adding-fields)

## Adding fields

Link copied

The Advanced Custom Fields plugin makes it very easy to add custom fields to a Menu, please follow the steps below.

1. From the **Custom Fields** admin screen, click the **Add New** button to create a new field group.
2. Add the fields you would like to see when editing a Menu
3. Under **Locations**, select the **Menu** rule and choose either ‘All’ (to show this field group on all menus) or a specific menu/location (to show this field group only for a specific menu)

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Change the **Style** setting to ‘Seamless’ if you wish for the field group to appear joined to the core settings (No heading or border) as shown in this guide’s screenshots.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-field-group.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-field-group.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#editing-fields)

## Editing fields

Link copied

Once you have created a field group and assigned it to appear for a Menu edit screen, editing the field values is done by navigating to the **Appearance > Menus** admin page.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

WP stores each Menu as a term object in the `wp_terms` table. ACF will store all custom field values in the `wp_termmeta` table.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-edit.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-edit.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#displaying-fields)

## Displaying fields

Link copied

Customizing the HTML for a WordPress Menu can be easily done via the [wp\_nav\_menu\_items](https://developer.wordpress.org/reference/hooks/wp_nav_menu_items/) filter. This filter is run each time a Menu is rendered (via the [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) function) and allows you to modify the `<li>` elements HTML for the Menu.

This example shows how to modify the main navigation menu from the twentyseventeen theme (Menu location is called ‘top’ in this theme). Please note that a second argument is required by the ACF functions to specify where to load the value from. Because each Menu is a term object, we can simply pass this object as the second parameter. The Menu term object is found by using the `$args->menu` data.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#functionsphp)

#### functions.php

Link copied

```php
add_filter('wp_nav_menu_items', 'my_wp_nav_menu_items', 10, 2);

function my_wp_nav_menu_items( $items, $args ) {

    // get menu
    $menu = wp_get_nav_menu_object($args->menu);


    // modify primary only
    if( $args->theme_location == 'top' ) {

        // vars
        $logo = get_field('logo', $menu);
        $color = get_field('color', $menu);


        // prepend logo
        $html_logo = '<li class="menu-item-logo"><a href="'.home_url().'"><img src="'.$logo['url'].'" alt="'.$logo['alt'].'" /></a></li>';


        // append style
        $html_color = '<style type="text/css">.navigation-top{ background: '.$color.';}</style>';


        // append html
        $items = $html_logo . $items . $html_color;

    }


    // return
    return $items;

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#conclusion)

## Conclusion

Link copied

Here is a look at how this may look in your browser. Notice the new logo `<img>` and color `<style>` elements!

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-display.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menus-display.jpg)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menus/#related)

## Related

Link copied

- Guides: [Adding fields to Menu Items](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Guides: [Adding fields to Media Attachments](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)

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

[Got it](https://www.advancedcustomfields.com/resources/adding-fields-menus/#)