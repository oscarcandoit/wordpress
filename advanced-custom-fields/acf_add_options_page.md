---
url: https://www.advancedcustomfields.com/resources/acf_add_options_page
scraped_at: 2025-10-20T02:33:23.325Z
---

# acf\_add\_options\_page()

Last updated Apr 17, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#description)

## Description

Link copied

Adds an options page to the admin menu.

Options pages are used to store global settings. These settings are not tied to a specific post, but are instead stored in the `wp_options` table.

Once registered, your page will appear in the admin menu. You can then assign fields to your page via the “Options Page” location rule when editing a field group.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#parameters)

## Parameters

Link copied

```php
acf_add_options_page( [$settings] );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#settings)

### $settings

Link copied

_(array)_ _(Optional)_ Array of arguments for registering an options page.
– **page\_title**

(string) The title displayed on the options page. Defaults to ‘Options’.
~~~
‘page\_title’ => \_\_(‘My Options’),
~~~

- **menu\_title**


(string) The title displayed in the admin menu. Defaults to ‘page\_title’ value.


```php
'menu_title' => __('My Options'),
```

- **menu\_slug**


(string) The URL slug used to uniquely identify this options page. Defaults to a url friendly version of menu\_title.


```php
'menu_slug' => 'my-options',
```

- **capability**


(string) The capability required for this menu to be displayed to the user. Defaults to ‘edit\_posts’. Read more about [Roles and Capabilities](http://codex.wordpress.org/Roles_and_Capabilities).


```php
'capability' => 'edit_posts',
```

- **position**


(int\|string) The position in the menu order where this menu should appear.
WARNING: if two menu items use the same position, one of the items may be overwritten. Risk of conflict can be reduced by using decimal instead of integer values, e.g. ‘63.3’ instead of 63 (must use quotes). Defaults to bottom of utility menu items.


```php
'position' => '',
```

- **parent\_slug**


(string) The slug of another WP admin page. If set, this will become a child page of that parent.


```php
'parent_slug' => 'my-parent-page',
```

- **icon\_url**


(string) The icon class for this menu. Defaults to default WordPress gear. Read more about [Dashicons](https://developer.wordpress.org/resource/dashicons/).


```php
'icon_url' => '',
```

- **redirect**


(bool) If set to true, this options page will redirect to the first child page (if a child page exists).
If set to false, this parent page will appear alongside any child pages as its own page. Defaults to true.


```php
'redirect' => true,
```

- **post\_id**


(int\|string) The `$post_id` to save and load values from. Can be set to a numeric post ID (123), or a string (‘user\_2’). Read more about the [available post\_id values](https://www.advancedcustomfields.com/resources/get_field/). Defaults to ‘options’. Added in v5.2.7.


```php
'post_id' => 'options',
```

- **autoload**


(bool) Data saved in the wp\_options table is given an “autoload” identifier.
When set to true, WP will automatically load these values within a single SQL query which can improve page load performance. Defaults to false. Added in v5.2.8.


```php
'autoload' => false,
```

- **update\_button**


(string) The text displayed on the options page submit button. Added in v5.3.7.


```php
'update_button' => __('Update', 'acf'),
```

- **updated\_message**


(string) The message shown above the form after updating the options page. Added in v5.6.0.


```php
'updated_message' => __("Options Updated", 'acf'),
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#return)

## Return

Link copied

_(array)_ The validated and final page settings. This is useful to find the page’s menu\_slug and use it later when adding child options pages.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#default-options-page)

### Default options page

Link copied

This example shows how to create the default options page.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', function() {
  if( function_exists('acf_add_options_page') ) {
    acf_add_options_page();
  }
} );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#customized-options-page)

### Customized options page

Link copied

This example shows how to create a customized options page and store the data in a variable for later use.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_op_init');
function my_acf_op_init() {

    // Check function exists.
    if( function_exists('acf_add_options_page') ) {

        // Register options page.
        $option_page = acf_add_options_page(array(
            'page_title'    => __('Theme General Settings'),
            'menu_title'    => __('Theme Settings'),
            'menu_slug'     => 'theme-general-settings',
            'capability'    => 'edit_posts',
            'redirect'      => false
        ));
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#creating-sub-pages)

### Creating sub pages

Link copied

This example shows how to create an options sub page using the _parent\_slug_ attribute.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_op_init');
function my_acf_op_init() {

    // Check function exists.
    if( function_exists('acf_add_options_page') ) {

        // Add parent.
        $parent = acf_add_options_page(array(
            'page_title'  => __('Theme General Settings'),
            'menu_title'  => __('Theme Settings'),
            'redirect'    => false,
        ));

        // Add sub page.
        $child = acf_add_options_page(array(
            'page_title'  => __('Social Settings'),
            'menu_title'  => __('Social'),
            'parent_slug' => $parent['menu_slug'],
        ));
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#priority)

### Priority

Link copied

This function must be used before the action `admin_menu` (priority 99) as this is when admin pages are registered in WordPress core. We advise using the “acf/init” action.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#wordpress-68)

### WordPress 6.8

Link copied

Since WordPress 6.8, any function that causes ACF to initialise early such as this one will trigger an PHP notice, if you call it before the `acf/init` action:

```php
Notice: Function _load_textdomain_just_in_time was called incorrectly. Translation loading for the acf domain was triggered too early. This is usually an indicator for some code in the plugin or theme running too early. Translations should be loaded at the init action or later.
```

To avoid this, you must make sure you don’t call any ACF functions before the `acf/init` action. Our code samples above show how to wrap these calls appropriately.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_page/#related)

## Related

Link copied

- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Guides: [How to Create an Options Page](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Guides: [Register multiple options pages](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/)
- Features: [Options Page](https://www.advancedcustomfields.com/resources/options-page/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_add_options_page/#)