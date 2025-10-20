---
url: https://www.advancedcustomfields.com/resources/acf_register_form
scraped_at: 2025-10-20T02:21:57.934Z
---

# acf\_register\_form()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#description)

## Description

Link copied

Registers a form for use with the [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/) function. There are many settings available to customize a form which are set by adding to the `$settings` array (see below).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#parameters)

## Parameters

Link copied

```php
<?php acf_register_form( $settings ); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#settings)

### $settings

Link copied

_(String \| Array)_ Array of settings or ‘id’ of a registered form.

- **id**


(String) A unique identifier for the form. Defaults to ‘acf-form’.


```php
'id' => 'acf-form',
```

- **post\_id**


(Integer \| String) The post ID used to determine which fields to show, where data is loaded, and where data is saved. Defaults to current post ID. Can also be sent to ‘new\_post’ to create a new post on submit.


```php
'post_id' => false,
```

- **new\_post**


(Array) When the above attribute is set to "new\_post", this setting is used to create the post. See [wp\_insert\_post](https://developer.wordpress.org/reference/functions/wp_insert_post/) for available parameters.


```php
'new_post' => false,
```

- **field\_groups**


(Array) An array of field group IDs/keys to override the fields displayed in this form.


```php
'field_groups' => false,
```

- **fields**


(Array) An array of field IDs/keys to override the fields displayed in this form.


```php
'fields' => false,
```

- **post\_title**


(Boolean) Whether or not to show the post title text field. Defaults to false.


```php
'post_title' => false,
```

- **post\_content**


(Boolean) Whether or not to show the post content editor field. Defaults to false.


```php
'post_content' => false,
```

- **form**


(Boolean) Whether or not to create a `form` element. Useful when adding to an existing form. Defaults to true.


```php
'form' => true,
```

- **form\_attributes**


(Array) An array or HTML attributes for the form element.


```php
'form_attributes' => array(),
```

- **return**


(String) The URL to be redirected to after the form is submitted. Defaults to the current URL with a GET parameter ‘?updated=true’.


A special placeholder ‘%post\_url%’ will be converted to post’s permalink.


A special placeholder ‘%post\_id%’ will be converted to post’s ID.


```php
'return' => '',
```

- **html\_before\_fields**


(String) Extra HTML to add before the fields.


```php
'html_before_fields' => '',
```

- **html\_after\_fields**


(String) Extra HTML to add after the fields.


```php
'html_after_fields' => '',
```

- **submit\_value**


(String) The text displayed on the submit button.


```php
'submit_value' => __("Update", 'acf'),
```

- **updated\_message**


(String) The message displayed above the form after being redirected. Can also be set to false for no message.


```php
'updated_message' => __("Post updated", 'acf'),
```

- **label\_placement**


(String) Determines where field labels are places in relation to fields. Defaults to ‘top’.
Choices of ‘top’ (above fields) or ‘left’ (beside fields).


```php
'label_placement' => 'top',
```

- **instruction\_placement**


(String) Determines where field instructions are placed in relation to fields. Defaults to ‘label’.
Choice of ‘label’ (below labels) or ‘field’ (below fields).


```php
'instruction_placement' => 'label',
```

- **field\_el**


(String) Determines element used to wrap a field. Defaults to ‘div’.
Choices of ‘div’, ‘tr’, ‘td’, ‘ul’, ‘ol’, ‘dl’.


```php
'field_el' => 'div',
```

- **uploader**


(String) Whether to use the WP uploader or a basic input for image and file fields. Defaults to ‘wp’ .
Choices of ‘wp’ or ‘basic’.


```php
'uploader' => 'wp',
```

- **honeypot**


(Boolean) Whether to include a hidden input field to capture non-human form submission. Defaults to true.


```php
'honeypot' => true,
```

- **html\_updated\_message**


(String) The HTML used to render the updated message.


```php
'html_updated_message'  => '<div id="message" class="updated"><p>%s</p></div>',
```

- **html\_submit\_button**


(String) The HTML used to render the submit button.


```php
'html_submit_button'  => '<input type="submit" class="acf-button button button-primary button-large" value="%s" />',
```

- **html\_submit\_spinner**


(String) The HTML used to render the submit button loading spinner.


```php
'html_submit_spinner' => '<span class="acf-spinner"></span>',
```

- **kses**


(Boolean) Whether or not to sanitize all `$_POST` data with the `wp_kses_post()` function. Defaults to true.


```php
'kses' => true
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#changelog)

## Changelog

Link copied

- `kses` added in version 5.6.5.
- `uploader` added in version 5.2.4.
- `honeypot` added in version 5.3.4
- `html_updated_message`, `html_submit_button`, and `html_submit_spinner` added in version 5.5.10

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#basic-usage)

### Basic usage

Link copied

This example demonstrates how to register a form in the `functions.php` file and later display that form within a page template.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_form_init');
function my_acf_form_init() {

    // Check function exists.
    if( function_exists('acf_register_form') ) {

        // Register form.
        acf_register_form(array(
            'id'       => 'new-event',
            'post_id'  => 'new_post',
            'new_post' => array(
                'post_type'   => 'event',
                'post_status' => 'publish'
            ),
            'post_title'  => true,
            'post_content'=> true,
        ));
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#page-new-eventphp)

#### page-new-event.php

Link copied

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

<div id="primary" class="content-area">
    <div id="content">
        <?php acf_form('new-event'); ?>
    </div><!-- #content -->
</div><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_register_form/#related)

## Related

Link copied

- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Guides: [Using acf\_form to create a new post](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Create a front end form](https://www.advancedcustomfields.com/resources/create-a-front-end-form/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_register_form/#)