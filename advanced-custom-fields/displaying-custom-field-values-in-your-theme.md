---
url: https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme
scraped_at: 2025-10-20T02:25:07.470Z
---

# Displaying Values in Your Theme

Last updated Apr 26, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/#overview)

## Overview

Link copied

The Advanced Custom Field’s API makes it very easy to display field data in your theme. There are many functions available and all are well documented on the [resources page](https://www.advancedcustomfields.com/resources/#functions).

[Link to heading#](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/#the-basics)

## The Basics

Link copied

Once you have [created a field group](https://www.advancedcustomfields.com/resources/getting-started/creating-a-field-group/) and input some data, you can now load and display the data in your theme.

All values are saved as native post\_meta (when saved to a post) and although you can use the native WP function `get_post_meta()`, it is better practice to use the relevant ACF function such as `get_field()`. Why? Because ACF will format the value depending on the field type and make development quicker and easier!

To retrieve a field value as a variable, use the [get\_field()](https://www.advancedcustomfields.com/docs/functions/get_field/ "get_field()") function. This is the most versatile function which will always return a value for any type of field.

To display a field, use the [the\_field()](https://www.advancedcustomfields.com/docs/functions/the_field/ "the_field()") in a similar fashion.

Here’s a basic usage example, and please be sure to view the [code example](https://www.advancedcustomfields.com/docs/code-examples/ "Code Examples") page for more.

```php
<?php

/**
 * Template Name: Home Page
 */

get_header();

?>

<div id="primary">
    <div id="content" role="main">

        <?php while ( have_posts() ) : the_post(); ?>

            <h1><?php the_field('custom_title'); ?></h1>

            <img src="<?php the_field('hero_image'); ?>" />

            <p><?php the_content(); ?></p>

        <?php endwhile; // end of the loop. ?>

    </div><!-- #content -->
</div><!-- #primary -->

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/#does-acf-have-a-shortcode)

## Does ACF have a Shortcode?

Link copied

Yes, you can use it in the same way as the [the\_field()](https://www.advancedcustomfields.com/docs/functions/the_field/ "the_field()") function. It looks something like this:

```php
[acf field="{$field_name}"]
```

You can also specify the $post\_id to fetch the value from.

```php
[acf field="{$field_name}" post_id="{$post_id}"]
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

[Link to heading#](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/#related)

## Related

Link copied

- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Adding fields to Media Attachments](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)

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

[Got it](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/#)