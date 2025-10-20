---
url: https://www.advancedcustomfields.com/resources/adding-fields-menu-items
scraped_at: 2025-10-20T02:17:43.704Z
---

# Adding fields to Menu Items

Last updated Dec 22, 2020

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#overview)

## Overview

Link copied

This guide will demonstrate how to add custom fields to a WordPress Menu Item and how to then modify the Menu Item’s HTML.

Menus are used to organize a group of links (menu items) for your theme to display as navigation. If you are unfamiliar with registering or editing a Menu, please read the [WordPress Menu User Guide](https://codex.wordpress.org/WordPress_Menu_User_Guide) and [Navigation\_Menus](https://codex.wordpress.org/Navigation_Menus) documentation.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Menu Items are added to a Menu. Learn how to [add fields to Menus](https://www.advancedcustomfields.com/resources/adding-fields-menus/).

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#changelog)

## Changelog

Link copied

- Added support for Menu in version 5.6.0

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#adding-fields)

## Adding fields

Link copied

The Advanced Custom Fields plugin makes it very easy to add custom fields to a Menu Item, please follow the steps below.

1. From the **Custom Fields** admin screen, click the **Add New** button to create a new field group.
2. Add the fields you would like to see when editing a Menu Item
3. Under **Locations**, select the **Menu Item** rule and choose ‘All’ (to show this field group on all menu items) or a specific menu/location (to show this field group only for a specific menu’s items)

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Change the **Instruction placement** setting to ‘Below labels’ to best mimic the WP core UI.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-field-group.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-field-group.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#editing-fields)

## Editing fields

Link copied

Once you have created a field group and assigned it to appear for a Menu Item edit screen, editing the field values is done by navigating to the **Appearance > Menus** admin page.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

WP stores each Menu Item as a post object in the `wp_posts` table. ACF will store all custom field values in the `wp_postmeta` table.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-edit.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-edit.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#displaying-fields)

## Displaying fields

Link copied

Customizing the HTML for a WordPress Menu Item can be easily done via the [wp\_nav\_menu\_objects](https://developer.wordpress.org/reference/hooks/wp_nav_menu_objects/) filter. This filter is run each time a Menu is rendered (via the [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) function) and allows you to modify the Menu Item objects. Each object contains a `title` value which is output in each menu link `<a>` element.

This example shows how to modify all Menu Item objects and append an icon if a value exists for the new ‘icon’ field.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#functionsphp)

#### functions.php

Link copied

```php
add_filter('wp_nav_menu_objects', 'my_wp_nav_menu_objects', 10, 2);

function my_wp_nav_menu_objects( $items, $args ) {

    // loop
    foreach( $items as &$item ) {

        // vars
        $icon = get_field('icon', $item);


        // append icon
        if( $icon ) {

            $item->title .= ' <i class="fa fa-'.$icon.'"></i>';

        }

    }


    // return
    return $items;

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#conclusion)

## Conclusion

Link copied

Here is a look at how this may look in your browser. Notice the new icon `<i>` elements!

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-display.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2017/06/acf-adding-fields-to-menu-items-display.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#reserved-keywords)

### Reserved keywords

Link copied

Please be aware that some reserved keywords exist for Menu Items which may conflict with field names. To avoid any errors that may potentially break the Customizer screen, please avoid using “description” as a field name when attached to a Menu Item.

Save

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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#related)

## Related

Link copied

- Guides: [Adding fields to Menus](https://www.advancedcustomfields.com/resources/adding-fields-menus/)
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

[Got it](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/#)