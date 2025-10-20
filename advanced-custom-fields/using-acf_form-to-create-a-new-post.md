---
url: https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post
scraped_at: 2025-10-20T02:16:44.509Z
---

# Using acf\_form to create a new post

Last updated Apr 7, 2015

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#overview)

## Overview

Link copied

This article will cover how to create a form on the front end of your website to add new content.

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#getting-started)

## Getting started

Link copied

If you have not already, please familiarize yourself with the acf form functions. Two functions are available to create a working form in a template file.

| Name | Description |
| --- | --- |
| `acf_form_head()` | This function is placed at the top of a template file and will register the necessary assets (CSS/JS), process the saved data, and redirect the url. This function does not accepts any parameters |
| [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/ "acf_form()") | This function is placed within a template file and will create the form’s HTML. This function accepts an array of settings to customize the form |

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#settings)

## Settings

Link copied

The acf\_form() parameter contains two settings called `post_id` and `new_post`. By using these settings correctly, a new post an be created using the form data.

The `post_id` setting  is used to edit an existing post, but when set to ‘new\_post’, a new post will be created.

The `new_post` setting is used to specify an array of elements that make up a post. These elements can be found in the [wp\_insert\_post()](https://codex.wordpress.org/Function_Reference/wp_insert_post)  documentation.

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#basic)

### Basic

Link copied

This form will create a new post.

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#page-new-postphp)

#### page-new-post.php

Link copied

```php
<?php

acf_form_head();

get_header();

?>
<div id="content">

    <?php

    acf_form(array(
        'post_id'       => 'new_post',
        'post_title'    => true,
        'post_content'  => true,
    ));

    ?>

</div>

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#post-type)

### Post Type

Link copied

This form will create a new published ‘event’ post.

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#page-new-postphp)

#### page-new-post.php

Link copied

```php
<?php

acf_form_head();

get_header();

?>
<div id="content">

    <?php

    acf_form(array(
        'post_id'       => 'new_post',
        'post_title'    => true,
        'post_content'  => true,
        'new_post'      => array(
            'post_type'     => 'event',
            'post_status'   => 'publish'
        )
    ));

    ?>

</div>

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#contact-form)

### Contact form

Link copied

This example will make a basic contact form, send an email, and redirect the user to a thank-you page.

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#page-contactphp)

#### page-contact.php

Link copied

```php
<?php

acf_form_head();

get_header();

?>
<div id="content">

    <?php

    acf_form(array(
        'post_id'       => 'new_post',
        'post_title'    => true,
        'post_content'  => true,
        'new_post'      => array(
            'post_type'     => 'contact_form',
            'post_status'   => 'publish'
        ),
        'return'        => home_url('contact-form-thank-you'),
        'submit_value'  => 'Send'
    ));

    ?>

</div>

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/save_post', 'my_save_post');

function my_save_post( $post_id ) {

    // bail early if not a contact_form post
    if( get_post_type($post_id) !== 'contact_form' ) {

        return;

    }


    // bail early if editing in admin
    if( is_admin() ) {

        return;

    }


    // vars
    $post = get_post( $post_id );


    // get custom fields (field group exists for content_form)
    $name = get_field('name', $post_id);
    $email = get_field('email', $post_id);


    // email data
    $to = 'contact@website.com';
    $headers = 'From: ' . $name . ' <' . $email . '>' . "\r\n";
    $subject = $post->post_title;
    $body = $post->post_content;


    // send email
    wp_mail($to, $subject, $body, $headers );

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

[Link to heading#](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#related)

## Related

Link copied

- Guides: [Create a front end form](https://www.advancedcustomfields.com/resources/create-a-front-end-form/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Functions: [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/)
- Functions: [acf\_form\_head()](https://www.advancedcustomfields.com/resources/acf_form_head/)
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

[Got it](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/#)