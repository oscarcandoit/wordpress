---
url: https://www.advancedcustomfields.com/resources/acf_form
scraped_at: 2025-10-20T02:21:49.830Z
---

# acf\_form()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#description)

## Description

Link copied

Displays a form to add or edit a post. There are many settings available to customize the form and these are set by adding to the `$options` array as explained below.

You may also register a form using the [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/) function.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#parameters)

## Parameters

Link copied

```php
<?php acf_form( $settings ); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#settings)

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


[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#changelog)

## Changelog

Link copied

- `kses` added in version 5.6.5.
- `uploader` added in version 5.2.4.
- `honeypot` added in version 5.3.4
- `html_updated_message`, `html_submit_button`, and `html_submit_spinner` added in version 5.5.10

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#editing-current-post)

### Editing current post

Link copied

This example demonstrates how to display a basic form to edit the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#page-basic-formphp)

#### page-basic-form.php

Link copied

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

<div id="primary" class="content-area">
    <div id="content" class="site-content" role="main">
        <?php while ( have_posts() ) : the_post(); ?>
            <?php acf_form(); ?>
        <?php endwhile; ?>
    </div><!-- #content -->
</div><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#editing-a-specific-post)

### Editing a specific post

Link copied

This example demonstrates how to display a form which edits the meta fields of a specific post.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#page-specific-formphp)

#### page-specific-form.php

Link copied

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

<div id="primary" class="content-area">
    <div id="content" class="site-content" role="main">
    <?php while ( have_posts() ) : the_post(); ?>
    <?php acf_form(array(
        'post_id'       => 123,
        'post_title'    => false,
        'post_content'  => false,
        'submit_value'  => __('Update meta')
    )); ?>
    <?php endwhile; ?>
    </div><!-- #content -->
</div><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#create-a-specific-post)

### Create a specific post

Link copied

This example demonstrates how to create a new post when submitting the form.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#page-new-formphp)

#### page-new-form.php

Link copied

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

<div id="primary" class="content-area">
    <div id="content" class="site-content" role="main">
    <?php while ( have_posts() ) : the_post(); ?>
    <?php acf_form(array(
        'post_id'       => 'new_post',
        'new_post'      => array(
            'post_type'     => 'event',
            'post_status'   => 'publish'
        ),
        'submit_value'  => 'Create new event'
    )); ?>
    <?php endwhile; ?>
    </div><!-- #content -->
</div><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#displaying-within-an-ajax-modal)

### Displaying within an AJAX modal

Link copied

When displaying an ACF form within an AJAX modal (or any other dynamically appended method), please note that the page will require some extra PHP and JavaScript code.

- **PHP**


The following function must be run within the `<body>` tags and before the "wp\_footer" action. This will create a hidden WYSIWYG field and enqueue the required JS templates for the WP media popups.


```php
// Enqueue uploadedr scripts.
acf_enqueue_uploader();
```

- **JS**


The following JS must be run after the AJAX request has completed and new HTML (containing the ACF form) has been appended to the DOM. This will allow ACF to initialize the fields within the newly added HTML.


```php
// Trigger the append action and provide the newly appended jQuery element.
acf.do_action('append', $('#popup-id'));
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#acfformhead)

### acf\_form\_head()

Link copied

It is important to note that whilst the `acf_form()` function will display a form, it will not process the form when submit. This task is handled by another function called `acf_form_head()`. To allow the form to save data, you will need to place the `acf_form_head()` function at the top of your page template before any HTML is rendered.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#security)

### Security

Link copied

Since version 5.6.5, ACF uses the [wp\_kses\_post()](https://codex.wordpress.org/Function_Reference/wp_kses_post) function to sanitize content and strip out evil scripts. This sanitization can be disabled if needed by changing the form’s `kses` setting to false.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form/#related)

## Related

Link copied

- Functions: [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Using acf\_form to create a new post](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/)
- Guides: [Create a front end form](https://www.advancedcustomfields.com/resources/create-a-front-end-form/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_form/#)