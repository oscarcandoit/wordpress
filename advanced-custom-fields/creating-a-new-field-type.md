---
url: https://www.advancedcustomfields.com/resources/creating-a-new-field-type
scraped_at: 2025-10-20T02:28:08.316Z
---

# Creating a new field type

Last updated Jan 16, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#overview)

## Overview

Link copied

The Advanced Custom Fields plugin is packed with loads of useful field types such as text, image and WYSIWYG. However, when working on a project, it may be necessary to create a new type of field to save & load unique data.

This guide will demonstrate how to create a new field type for the ACF plugin.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#download)

## Download

Link copied

To make life easier, we put together a comprehensive template for creating an ACF field type, complete with an NPM script that get you up and running even faster.

[![A screenshot of the ACF Example Field Type repository](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/github-1.png)](https://github.com/AdvancedCustomFields/acf-example-field-type)

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#acf-example-field-type-template-on-github)

### ACF Example Field Type template on Github

Link copied

Please download or clone the ACF Example Field Type repository. Alternatively, you can click the green “Use this template” button to create a new repository based on this template.

https://github.com/AdvancedCustomFields/acf-example-field-type

Once you’ve downloaded the template, follow the steps in the README to get started on your custom field type.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#customization)

## Customization

Link copied

All logic for your field’s appearance and functionality is defined in the `acf-FIELD-NAME/class-PREFIX-acf-field-FIELD-NAME.php` file. This class extends the `acf_field` class, which is packed full of powerful functions which allow you to customize how data is saved and displayed! Each function is documented with internal comments, so it is best to open up the file and read it over top to bottom.

Here is a quick overview of the functions:

| Name | Description |
| --- | --- |
| `__construct` | Initialize function which sets the field’s data such as name, label, category and defaults |
| `render_field_settings` | Create extra settings for your field. These are visible when editing a field |
| `render_field` | Create the HTML interface for your field |
| `input_admin_enqueue_scripts` | Enqueue CSS + JavaScript to assist your render\_field() function |
| `input_admin_head` | Add inline CSS and JavaScript to assist your render\_field() function |
| `input_form_data` | Add hidden inline HTML |
| `input_admin_footer` | Add inline CSS and JavaScript to assist your render\_field() function |
| `load_value` | This filter is applied to the $value after it is loaded from the db |
| `update_value` | This filter is applied to the $value before it is saved in the db |
| `format_value` | This filter is applied to the $value before being returned to template API |
| `validate_value` | This filter is used to perform validation on the value prior to saving |
| `delete_value` | This action is fired after a value has been deleted from the db |

The above are only some of the functions available in the acf\_field class. Please read over the extended comments found above each function to learn more.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#html-escaping)

## HTML Escaping

Link copied

Some field types may output potentially unsafe HTML directly, such as iframes or script tags.

Starting from ACF 6.2.5, where these would automatically be removed when using the ACF shortcode or `the_field()`, ACF supports field types escaping their own HTML when requested. This is done by a second parameter being passed into the `format_value` method, if this value is true, we require a HTML safe version of the output.

In this instance, your field type should ensure there is no way for malicious HTML to be rendered on the front-end by a malicious user modifying the raw value in the database. For example, the core WYSIWYG field handles this by running `acf_esc_html` on the value before running `the_content` filter to handle any embeds in the field.

Once your field type is ready to handle its own HTML, you can mark the field as compatible by adding `’escaping_html’ => true` to the new `supports` class property:

```php
$this->supports = array(
    'escaping_html' => true,
);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#related)

## Related

Link copied

- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Adding Custom Settings to Fields](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/#)