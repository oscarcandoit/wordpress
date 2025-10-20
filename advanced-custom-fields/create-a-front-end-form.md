---
url: https://www.advancedcustomfields.com/resources/create-a-front-end-form
scraped_at: 2025-10-20T02:32:55.469Z
---

# Create a front end form

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#overview)

## Overview

Link copied

This article will cover how to create a [form on the front end](https://www.advancedcustomfields.com/blog/wordpress-frontend-form/) of your website to add or edit content. Two functions are available to create a working form in a template file.

| Name | Description |
| --- | --- |
| `acf_form_head()` | This function is placed at the top of a template file and will register the necessary assets (CSS/JS), process the saved data, and redirect the url. This function does not accept any parameters |
| [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/ "acf_form()") | This function is placed within a template file and will create the form’s HTML. This function accepts an array or settings to customize the form in many ways |

[Link to heading#](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#example)

## Example

Link copied

This example shows how to add a front end form to a single post page. This would allow a user to edit the current post’s content

[Link to heading#](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#singlephp)

#### single.php

Link copied

```php
<?php acf_form_head(); ?>
<?php get_header(); ?>

    <div id="primary">
        <div id="content" role="main">

            <?php /* The loop */ ?>
            <?php while ( have_posts() ) : the_post(); ?>

                <h1><?php the_title(); ?></h1>

                <?php the_content(); ?>

                <p>My custom field: <?php the_field('my_custom_field'); ?></p>

                <?php acf_form(); ?>

            <?php endwhile; ?>

        </div><!-- #content -->
    </div><!-- #primary -->

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#settings)

## Settings

Link copied

The [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/ "acf_form()") function accepts an array of settings to customize the form element. Such settings include the ability to create a new post, edit a specific post, select which field groups to show, and customize HTML elements. Please read the complete [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/ "acf_form()") documentation to learn more about available settings.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#related)

## Related

Link copied

- Guides: [Using acf\_form to create a new post](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Functions: [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Functions: [acf\_form\_head()](https://www.advancedcustomfields.com/resources/acf_form_head/)

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

[Got it](https://www.advancedcustomfields.com/resources/create-a-front-end-form/#)