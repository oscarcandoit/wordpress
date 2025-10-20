---
url: https://www.advancedcustomfields.com/resources/getting-started-with-acf
scraped_at: 2025-10-20T02:30:20.452Z
---

# Getting Started with ACF

Last updated Apr 22, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#overview)

## Overview

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#welcome)

## Welcome

Link copied

Advanced Custom Fields is a WordPress plugin which allows you to add **extra content fields** to your WordPress edit screens. These extra content fields are more commonly referred to as **Custom Fields** and can allow you to build websites faster and educate your clients quicker. In this guide, you’ll learn how to:

- Install the ACF plugin
- Create new fields
- Create field content
- Display fields in your theme
- Register custom post types and taxonomies

ACF Getting Started - YouTube

[Photo image of WP Engine Builders](https://www.youtube.com/channel/UCh1WuL54XFb9ZI6m6goFv1g?embeds_referring_euri=https%3A%2F%2Fwww.advancedcustomfields.com%2F)

WP Engine Builders

6.33K subscribers

[ACF Getting Started](https://www.youtube.com/watch?v=9C6_roqghZQ)

WP Engine Builders

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

0:00 / 4:24
•Live

•

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#the-basics)

## The Basics

Link copied

Custom fields are a native part of WordPress and appear on pages, posts and custom post types, however, the native custom field interface is not very user friendly. With ACF installed, you can tailor what fields to show and what they look like. For instance, you may require a ‘Hero Image’ to be selected for your home page. You can use ACF to easily create this Image field and show it when editing the home page! Here is the difference between native custom fields and Advanced Custom Fields.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2014/01/acf-overview-without.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2014/01/acf-overview-without.jpg)

Native Custom Fields


[![](https://www.advancedcustomfields.com/wp-content/uploads/2014/01/acf-overview-with.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2014/01/acf-overview-with.jpg)

Advanced Custom Fields


[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#installation)

## Installation

Link copied

The Advanced Custom Fields plugin does not come pre-installed with WordPress so you will need to install our plugin before using its awesome features! Luckily for you, WordPress makes this a very easy process! If you are familiar with WordPress, simply login to your site and search/install the **Advanced Custom Fields** plugin from the plugins page. For detailed instructions, please read our [step by step instruction guide](https://www.advancedcustomfields.com/resources/installation/).

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#creating-fields)

## Creating Fields

Link copied

Creating new custom fields is a very easy process and can be done with just a few clicks of our user friendly **field builder**! You can create as many fields as you like, each with their own name, type and settings. Each field is added to a group which allows you to both organize your fields and specify the edit screens where they appear.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

**Field groups** are used to organize fields and attach them to edit screens. Each field group contains a title, fields, location rules and visual settings. To get started with your first field group, please read our [Creating a Field Group guide](https://www.advancedcustomfields.com/resources/creating-a-field-group/).

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-field-groups-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-field-groups-1.png)

Field group list


[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-add-new-field-group-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-add-new-field-group-1.png)

Field group settings


[![Field group location rules](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-field-group-location-rules-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-field-group-location-rules-1.png)

Field group location rules


Each field contains settings to customize how the field looks (its type), where its value is saved (its name) and how it functions (its settings). These field settings can be customized when editing a field group. To learn more about field settings, please read our [Field Settings guide](https://www.advancedcustomfields.com/resources/field-settings/).

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#creating-content)

## Creating Content

Link copied

With your fields created, it’s time to start editing your content! All our fields are very intuitive to use and display seamlessly with the WordPress admin style. You don’t need to trigger any event to show or edit custom fields, they will appear and function just like the WP post\_title and post\_content fields! Simply enter your content and update the post!

[![](https://www.advancedcustomfields.com/wp-content/uploads/2017/04/acf-version-5-input.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/04/acf-version-5-input.png)

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

Fields are not just available for posts! You may also display fields your custom fields on the page, custom post type, user, taxonomy term, comment, media and [custom options pages](https://www.advancedcustomfields.com/pro/)!

To get an idea of the different content you can edit in ACF, please look over the available [field types](https://www.advancedcustomfields.com/resources/#field-types).

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#displaying-fields)

## Displaying Fields

Link copied

Displaying field values is ACF’s party piece! Any field value can be returned as a PHP variable or output as HTML via the magical functions `get_field()` and `the_field()`. These functions (alongside many others) provide a developer friendly way to customize your WordPress theme without spending hours reading our docs! Here is some example code to see how our intuitive API works!

```php
<h1><?php the_title(); ?></h1>

<?php if ( get_field('sub_heading' ) ): ?>
    <h2><?php echo esc_html( get_field('sub_heading') ); ?></h2>
<?php endif; ?>

<div class="hero">
    <?php $image = get_field('hero_image'); ?>
    <img src="<?php echo esc_url( $image['url'] ); ?>" alt="<?php echo esc_attr( $image['alt'] ); ?>" />
</div>

<?php if( have_rows('event') ): ?>
    <ul>
    <?php while( have_rows('event') ): the_row(); ?>
        <li>
            <a href="<?php echo esc_url( get_sub_field( 'url' ) ); ?>"><?php echo esc_html( get_sub_field( 'title' ) ); ?></a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>
```

To learn more about our API, please see our [Functions](https://www.advancedcustomfields.com/resources/#functions) and check out our [Code Examples guide](https://www.advancedcustomfields.com/resources/code-examples/).

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#section-education-and-support)

## Custom Post Types and Taxonomies

Link copied

Custom post types and taxonomies turn WordPress into a full content management system. Post types give you much greater control over how your content is created, customized, displayed, and managed. Taxonomies give you the same power over how your data and content is organized and categorized.

ACF allows you to register your custom post types and taxonomies directly in the plugin. This greatly simplifies workflows by avoiding the need to register them manually with code or use another plugin. Just create a post type in the UI, then follow it up by adding an existing field group, creating a new field group and defining fields, or by creating a taxonomy.

![Register a new custom post type with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/acf-register-post-type.png)

Please see [Post Types and Taxonomies](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/) for our in-depth guide.

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#education-and-support)

## Education and Support

Link copied

Good work! This guide covered all the basics for getting started creating with the Advanced Custom Fields plugin, but we’ve only scratched the surface of our available resources. As you work more about ACF, you’ll discover new features, functions, and even [a powerful suite of PRO features](https://www.advancedcustomfields.com/pro/) that can help you take your WordPress website to the next level. If you have any questions that weren’t addressed in this guide, visit our [Resource Center](https://www.advancedcustomfields.com/resources/) for more information or [contact our support team](https://support.advancedcustomfields.com/) directly.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#related)

## Related

Link copied

- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- : [Frequently Asked Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/getting-started-with-acf/#)