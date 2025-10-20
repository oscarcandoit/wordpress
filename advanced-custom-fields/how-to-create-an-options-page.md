---
url: https://www.advancedcustomfields.com/resources/how-to-create-an-options-page
scraped_at: 2025-10-20T02:27:14.001Z
---

# How to Create an Options Page

Last updated Oct 3, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#overview)

## Overview

Link copied

Options pages are setting pages in the WordPress admin area containing fields with the ability to control global options. This allows builders or clients to make one change and update content that appears in many places throughout the site: contact information, calls-to-action, or notifications about sales and special events.

A more advanced options page could even allow clients to switch between entirely different site designs with just a few clicks. The biggest challenge with options pages is coding them, as it’s often time consuming and tedious.

The [Options Page feature](https://www.advancedcustomfields.com/resources/options-page/) released in [ACF PRO 6.2](https://www.advancedcustomfields.com/blog/acf-6-2-0-released/) gives you a way to register new options pages in the WordPress admin without breaking your workflow or writing a single line of code. This is an extremely powerful tool with almost limitless applications, but it’s important to understand the basics first. In this tutorial, we’ll show you how to use ACF PRO to create an options page that functions as a sitewide notification bar.

The notification bar will be displayed across the top of the entire site, so it’s an ideal example of something you’d want controlled from a custom “Site Settings” page. We’ll include features to allow our editors to toggle the bar on or off, as well as add a custom message.

Here is a breakdown of the steps to set up our sitewide notification bar:

1. Create a new options page
2. Create a new field group
3. Verify the field group is assigned to the options page
4. Add code to handle display logic (shown if active and hidden if inactive)

The video below will give you a look at the steps we’ll take and the final outcome.

Video Player

[https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Options-Pages-tutorial-optimized.mp4](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Options-Pages-tutorial-optimized.mp4)

Media error: Format(s) not supported or source(s) not found

[Download File: https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Options-Pages-tutorial-optimized.mp4?\_=1](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/ACF-Options-Pages-tutorial-optimized.mp4?_=1)

00:00

00:00

00:00

Use Up/Down Arrow keys to increase or decrease volume.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#create-a-new-options-page)

## Create a New Options Page

Link copied

First, we need to create a new options page called “Site Settings”. Under ACF’s menu, choose **Options Pages**, and then click **Add New** to create a new options page. Click under **Page Title** and use the default “Site Settings”. Next, click under **Menu Slug**, and again use the default “site-settings”.

Leave “Parent Page” set to “No Parent” for now. We’ll look at how to create a child options page in a later section. Be sure to save your changes.

**Stay in the flow!** Saving a new Options Page for the first time prompts you with a notification along the top to either “Add fields” or “Link existing field groups”. This allows you to stay in the flow when you’re creating new options pages, field groups, post types, and taxonomies.

![After saving a new options page for the first time, a notification will prompt you to continue by creating a new field group or assigning an existing one.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/workflow-notification-screenshot-new.png)

[![The step-by-step process of creating an options page within ACF's UI. After creating a new options page through ACF PRO’s menu, the first step is to give it a Page Title. Next, save your changes, and then visit your new page.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Create-Options-Page-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Create-Options-Page-optimized.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#create-a-new-field-group)

## Create a New Field Group

Link copied

Now that we have our Site Settings options page, we need to assign some fields. We’ll start with a [Group](https://www.advancedcustomfields.com/resources/group/) field, and then add a [True/False](https://www.advancedcustomfields.com/resources/true-false/) field and a [Text Area](https://www.advancedcustomfields.com/resources/textarea/) field under the Group field’s “Sub Fields” setting. Here is what our field group setup will look like for our notification bar:

- **Group** field to organize our other fields.


  - Field Label: Notification Bar
  - Field Name: `notification_bar`
  - The “Layout” setting (along the bottom) controls how the Group field displays the fields within it. In this case, we’ll choose **Row**.
- **True/False** field for toggling the notification bar on and off.


  - Field Label: Notification On/Off
  - Field Name: `notification_onoff`
  - Under the “Presentation” tab, enable **Stylized UI**, and then set the text to “On” and “Off”.
- **Text Area** field to allow editors to add a custom message when the notification bar is displayed.

  - Field Label: Notification Message
  - Field Name: `notification_message`
  - Click the **Conditional Logic** tab and toggle it on. Set the values for ”Show this field if” to **Notification On/Off**, **Value is equal to**, and **Checked**. This will make the Text Area visible to editors only when the notification bar is toggled on.

Save your changes and proceed to the next step.

[![An overview of field groups for the notification bar. The Group field includes the True/False and Text Area fields as sub fields.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/notification-bar-field-group-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/notification-bar-field-group-optimized.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#set-the-location-rules-for-an-options-page)

## Set the Location Rules for an Options Page

Link copied

You can associate any field group with an options page on the “Location Rules” tab, located under “Settings” at the bottom of the field group editor. Under “Show this field group if”, select **Options Page**, **is equal to**, and then the page you would like your field group to be associated with.

Lucky for us, we used ACF’s seamless fields flow to automatically associate our field group on creation, directly after initializing our new Site Settings options page. This automatically creates a rule to only show the field group on our Site Settings page. You can create additional rules using the “and” and “or” buttons to finetune the conditions under which your field group will display.

[![The notification bar field group with the Location Rules highlighted to assign to Site Settings. The rules read “Show this field group if Options Page is equal to Site Settings.” ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Field-Group-Location-Rules-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Field-Group-Location-Rules-optimized.png)

Be sure to save your changes. Now, when you click on your new **Site Settings** page in the WordPress admin, you should see your notification bar field group.

[![How the Site Settings page for our notification bar might appear to content editors. The True/False field shows as Notification On/Off and has been toggled on. The Text Area field shows as Notification Message, and allows content editors to enter an input. Here, text has been entered that reads Free shipping with $69 purchase, and then an HTML link on the text Show Now. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/notification-bar-overview-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/notification-bar-overview-optimized.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#add-display-logic-code)

## Add Display Logic Code

Link copied

We’ll utilize WordPress’s handy [wp\_body\_open](https://developer.wordpress.org/reference/functions/wp_body_open/) action to hook up and display our notification bar at the top of our page. Here are the few lines of code we need:

```php php
<?php
/**
 * Get the site notice message, and display it.
 *
 * @return void
 */
function demo_acf_output_notification() {
    $has_notice = get_field( 'notification_bar', 'options' );

    if ( ! $has_notice || ! $has_notice['notification_onoff'] ) {
        return;
    }
    ?>

    <div class="notification-bar">
        <div class="notification-bar__wrapper">
            <p class="notification-bar__text"><?php echo wp_kses_post( $has_notice['notification_message'] ); ?></p>
        </div>
    </div>
    <?php
}
// Notification to be placed after opening body tag.
add_action( 'wp_body_open', 'demo_acf_output_notification' );
```

Once you place your display logic code, you should see your notification bar on the frontend of your site (if it is enabled). Of course, you can apply your own CSS to get the appearance to your liking.

[![A view of the notification bar site settings page, with an arrow pointing to the final notification bar in the header of the site’s front end. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/toggling-notification-bar-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/toggling-notification-bar-optimized.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#create-a-child-options-pagecreate-child-options-page)

## Create a Child Options Page{\#create-child-options-page}

Link copied

You don’t have to stop there. You can create additional options pages and even nest child pages within parents. Options pages can be designated as children during creation or at any later time by clicking the area under “Parent Page” on the “Add New Options Page” or “Edit Options Page” screens. This allows you to designate the options page as a child of any part of the WordPress admin. This includes any options pages you have already created with the “Parent Page” set to **No Parent.**

[![The step-by-step process of creating a child options page within ACF's UI. The process shown has four steps: 1. Give it a “Page Title”. 2. Choose a “Parent Page”. 3. Save your changes. 4. Visit your new page. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Create-Child-Options-Page-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Create-Child-Options-Page-optimized.png)

So far, we’ve covered everything you need to create new options pages in the ACF PRO UI, but this is by no means the end of the available options. Toggling on **Advanced Configuration** gives you access to powerful customizations affecting the options page’s [visibility](https://www.advancedcustomfields.com/resources/options-page/#visibility), [labels](https://www.advancedcustomfields.com/resources/options-page/#labels), and [permissions](https://www.advancedcustomfields.com/resources/options-page/#permissions).

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#change-an-option-pages-menu-position)

## Change an Option Page’s Menu Position

Link copied

For example, you can take things even further by prioritizing your option page’s menu position within the WordPress admin area, and even assign a custom icon using [Dashicons](https://developer.wordpress.org/resource/dashicons/). Both of these settings are found under the “Visibility” tab.

To change the menu’s position, enter a numerical input that matches the [Menu Structure](https://developer.wordpress.org/reference/functions/add_menu_page/#menu-structure) used by WordPress.

[![Step-by-step of updating an options page's menu position in WP Admin. Two images of the ACF Edit Options Page screen are shown. In the first, we can see that both “Menu Icon” and “Menu Position” have been left at their defaults. In the second image, a value of “dashicons-privacy” has been entered under “Menu Icon”, and “15” has been entered under “Menu Position”. This is reflected in an altered icon and a menu position much closer to the top of the page.  ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Options-Page-Menu-Position-optimized.png)](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Options-Page-Menu-Position-optimized.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#conclusion)

## Conclusion

Link copied

The Options Pages feature in ACF PRO allows you to give editors a centralized area to control sitewide features. It’s a simple concept with wide-ranging applications. Make sure to message us on [Twitter](https://twitter.com/wp_acf) and let us know how you’ve used ACF PRO’s Options Page feature. We’re certain you’ll surprise us.

Get the best results from [ACF PRO](https://www.advancedcustomfields.com/pro/) fields and features with our tutorials on [how to create your first ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/), [how to use the Repeater field](https://www.advancedcustomfields.com/resources/repeater/how-to-use-the-repeater-field/), [how to build layouts with the Flexible Content field](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/), and [how to use the Gallery field](https://www.advancedcustomfields.com/resources/how-to-use-the-gallery-field/).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#related)

## Related

Link copied

- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Features: [Options Page](https://www.advancedcustomfields.com/resources/options-page/)
- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- Guides: [Register multiple options pages](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/#)