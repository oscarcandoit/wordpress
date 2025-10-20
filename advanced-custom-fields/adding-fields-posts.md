---
url: https://www.advancedcustomfields.com/resources/adding-fields-posts
scraped_at: 2025-10-20T02:17:12.340Z
---

# Adding fields to Posts

Last updated Jul 7, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#overview)

## Overview

Link copied

This guide will demonstrate how to add custom fields to a WordPress Post and how to then modify the post’s template file HTML.

Posts are the most common way to create, edit and organize content. Posts, Pages and custom posts types are all considered as **Post** objects of different **post types**.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#adding-fields)

## Adding fields

Link copied

The Advanced Custom Fields plugin makes it very easy to add custom fields to a Post, please follow the steps below.

1. From the **Custom Fields** admin screen, click the **Add New** button to create a new field group
2. Add the fields you would like to see when editing a Post
3. Under **Locations**, select one of the **Post** related rule types (such as **Post Type**) and then select the corresponding value to show this field group

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Leave the **Style** setting as ‘Standard’ if you wish for the field group to appear within a **WP Postbox**.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-group.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-group.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#editing-fields)

## Editing fields

Link copied

Once you have created a field group and assigned it to appear for a Post edit screen, editing the field values is done by navigating to the **Posts > Add New** admin page.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

WP stores each Post as a post object in the `wp_posts` table. ACF will store all custom field values in the `wp_postmeta` table.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-edit.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-edit.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#displaying-fields)

## Displaying fields

Link copied

Customizing the HTML for a WordPress Post can be easily done by editing the `single.php` or `single-{$post_type}.php` file in your theme. Depending on your theme, you may also use template parts or filters to customize the HTML.

This example shows how to modify the `single-event.php` template from the twentyseventeen theme and display the content entered in the screenshot above.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#single-eventphp)

#### single-event.php

Link copied

```php
<?php

get_header();
the_post();

// vars
$location = get_field('location');
$thumbnail = get_field('thumbnail');

?>

<div class="wrap">

    <div id="event-hero">

        <?php if( $location ): ?>
        <div id="event-map" class="acf-map">
            <div class="marker" data-lat="<?php echo $location['lat']; ?>" data-lng="<?php echo $location['lng']; ?>"></div>
        </div>
        <?php endif; ?>


        <?php if( $thumbnail ): ?>
            <img class="thumbnail" src="<?php echo $thumbnail['url']; ?>" alt="<?php echo $thumbnail['alt']; ?>" />
        <?php endif; ?>

        <h2><?php the_title(); ?></h2>
        <h3><?php the_field('date'); ?> from <?php the_field('start_time'); ?> to <?php the_field('end_time'); ?></h3>
        <h4><?php echo $location['address']; ?></h4>

    </div>

    <div id="primary" class="content-area">
        <main id="main" class="site-main" role="main">
            <?php the_content(); ?>
        </main>
    </div>

</div>

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#conclusion)

## Conclusion

Link copied

Here is a look at how this may look in your browser with some extra CSS and JS!

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-group-display.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/04/acf-adding-fields-to-posts-field-group-display.jpg)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-posts/#related)

## Related

Link copied

- Guides: [Adding fields to Menus](https://www.advancedcustomfields.com/resources/adding-fields-menus/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Adding fields to Media Attachments](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/)
- Guides: [Adding fields to Menu Items](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)

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

[Got it](https://www.advancedcustomfields.com/resources/adding-fields-posts/#)