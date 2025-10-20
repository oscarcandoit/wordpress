---
url: https://www.advancedcustomfields.com/resources/acf_form_head
scraped_at: 2025-10-20T02:21:41.559Z
---

# acf\_form\_head()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#description)

## Description

Link copied

Used to process, validate and save the submitted form data created by the [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/) function. It will also enqueue all ACF related scripts and styles for the form to display correctly.

This function must be placed before any HTML has been output, preferably above the `get_header()` function of your theme file.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#parameters)

## Parameters

Link copied

```php
acf_form_head();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#example)

## Example

Link copied

This example demonstrates a basic `acf_form()` to edit the current post being viewed.

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

    <div id="primary" class="content-area">
        <div id="content" class="site-content" role="main">
            <?php acf_form(); ?>
        </div>
    </div>

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#actions--filters)

## Actions & Filters

Link copied

The following actions and filters are provided to customize the submission process.

- **acf/pre\_submit\_form**


This filter is run after a form has been submit, and before any data has been saved.
Use this filter to modify the `$form` array before `$_POST` data is saved.


```php
add_filter('acf/pre_submit_form', 'my_acf_pre_submit_form', 10, 1);
function my_acf_pre_submit_form( $form ) {
      // Create post using $form['new_post'].
      // Modify $form['redirect'].
      return $form;
}
```

- **acf/pre\_save\_post**


This filter is run after the _acf/pre\_submit\_form_ filter, and before any data has been saved.
Use this filter to modify the `$post_id` value used to save the `$_POST` data.


```php
add_filter('acf/pre_save_post', 'my_acf_pre_save_post', 10, 2);
function my_acf_pre_save_post( $post_id, $form ) {
      // Create post using $form and update $post_id.
      return $post_id;
}
```

- **acf/save\_post**


This action runs when ACF saves the `$_POST` data.
For more information, please refer to the [acf/save\_post](https://www.advancedcustomfields.com/resources/acf-save_post) guide.


```php
add_action('acf/save_post', 'my_acf_save_post', 20);
function my_acf_save_post( $post_id ) {

      // Get new value.
      $value = get_field('my_field', $post_id);

      // Do something.
}
```

- **acf/submit\_form**


This action runs after the `$_POST` data has been saved.
Use this action to perform custom logic before the _return_ setting is used to redirect the browser.


```php
add_action('acf/submit_form', 'my_acf_submit_form', 10, 2);
function my_acf_submit_form( $form, $post_id ) {

      // Get new value.
      $value = get_field('my_field', $post_id);

      // Redirect.
      wp_redirect( 'http://www.website.com/' . $value );
      exit;
}
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#changelog)

## Changelog

Link copied

- `acf/pre_submit_form` added in version 5.5.10
- `acf/submit_form` added in version 5.5.10
- `acf/pre_save_post` added in version 4.1.6

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_form_head/#related)

## Related

Link copied

- Guides: [Create a front end form](https://www.advancedcustomfields.com/resources/create-a-front-end-form/)
- Filters: [acf/pre\_save\_post](https://www.advancedcustomfields.com/resources/acf-pre_save_post/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Functions: [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/)
- Guides: [Using acf\_form to create a new post](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_form_head/#)