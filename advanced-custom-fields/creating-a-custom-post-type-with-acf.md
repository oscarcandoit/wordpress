---
url: https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf
scraped_at: 2025-10-20T02:32:06.933Z
---

# Creating a Custom Post Type with ACF

Last updated Nov 13, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#overview)

## Overview

Link copied

WordPress is a powerful CMS, but out-of-the-box it can lack flexibility when handling content types beyond standard posts and pages. While the default post types work well for typical blog content and static pages, you might need custom post types to organize more complex information. In this video, we’ll show how to use the Advanced Custom Fields (ACF) plugin to create a custom post type called “Cars” and associate additional data with it.

Creating a Custom Post Type with ACF - YouTube

[Photo image of WP Engine Builders](https://www.youtube.com/channel/UCh1WuL54XFb9ZI6m6goFv1g?embeds_referring_euri=https%3A%2F%2Fwww.advancedcustomfields.com%2F&embeds_referring_origin=https%3A%2F%2Fwww.advancedcustomfields.com)

WP Engine Builders

6.33K subscribers

[Creating a Custom Post Type with ACF](https://www.youtube.com/watch?v=EG4WcVeMU-0)

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

0:00 / 9:05
•Live

•

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#why-create-a-custom-post-type)

## Why Create a Custom Post Type?

Link copied

The default WordPress post types like Posts and Pages work well for simple content structures. However, they’re limited when managing posts with more complex data needs, such as products, events, portfolio items, or staff and team member listings. Custom post types provide flexibility, allowing you to structure and display complex information tailored to your website’s needs.

In this guide, we’ll create a “Car” custom post type that can handle specific car data, including details like price, mileage, and miles per gallon (MPG).

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#step-1-register-a-custom-post-type-for-cars)

## Step 1: Register a Custom Post Type for Cars

Link copied

Our first step is to register a new post type called “Car” in the ACF plugin. Follow these steps:

1. In the WordPress admin, go to **ACF > Post Types** and select **Add New**.

2. Fill in essential details:

   - **Plural Label**: Cars
   - **Singular Label**: Car
3. ACF will automatically generate the post type key for you, but you can modify this if you wish. In the **Advanced Configuration** section, you can optionally add an icon representing the “Car” post type in the WordPress admin menu.

4. Click **Save Changes** to save your custom post type.


**For more details and advanced options including visibility, URLs, permissions, and REST API settings, please see [ACF’s guide on registering custom post types](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/ "ACF's guide on registering custom post types").**

![The UI for creating a custom post type in ACF. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/10/ACF-Add-Custom-Post-Type.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#step-2-add-your-first-car-post)

## Step 2: Add Your First Car Post

Link copied

Once the “Car” post type is registered, you can add your first post:

1. In the **Cars** section of the WordPress admin, click **Add Car**.

2. Enter the post’s title, add a description, and assign a featured image.

3. Save your post.


At this point, the post displays basic information, but doesn’t show the specific car details we want to include. To get those, we’ll need to create a child theme and then add ACF custom fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#step-3-create-a-child-theme-to-customize-display)

## Step 3: Create a Child Theme to Customize Display

Link copied

To customize how the custom post type displays, you’ll need to [create a child theme](https://wpengine.com/resources/create-child-theme-wordpress/). This allows you to add custom templates without modifying the original theme.

1. Create a new folder in your `wp-content/themes` directory named “ACF Demo.”

2. Inside the folder, create two files: `functions.php` and `style.css`.


After activating your child theme in the WordPress admin, you’ll have a dedicated space for customizations.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#step-4-register-custom-fields-for-the-custom-post-type)

## Step 4: Register Custom Fields for the Custom Post Type

Link copied

Now that you have your Car post type and child theme, it’s time to register custom fields for your car-specific information.

1. Navigate to **ACF > Field Groups** and choose **Add New**.

2. Name the field group “Vehicle details.”

3. Under **Location Rules**, set the group to appear only when the “Post Type” is equal to “Car”.

4. Add the following fields:


- **Price**: Use a [Text](https://www.advancedcustomfields.com/resources/text/) field. Click on the **Presentation** tab and enter “$” in the “Prepend” section.
- **Mileage**: Use a [Number](https://www.advancedcustomfields.com/resources/number/) field, and click the **Presentation** tab. Enter **miles** in the “Append” section to make it clear for editors.
- **Miles Per Gallon (MPG)**: Use a [Group](https://www.advancedcustomfields.com/resources/group/) field, and create sub fields for **City MPG** and **Highway MPG** using Text fields.

After configuring the fields and location rules, be sure to save your field group.

![The field group for the "Car" custom post type. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/10/ACF-Custom-Post-Type-Car-Field-Group.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#step-5-output-custom-field-data-in-the-theme)

## Step 5: Output Custom Field Data in the Theme

Link copied

With your fields ready, the next step is to display this information on your WordPress site. The steps below outline the process for how to do this.

1. Copy the `single.php` file from the original theme and paste it into your child theme folder.

2. Rename it to `single-car.php` to tailor it specifically to “Car” posts.

3. In `single-car.php`, Remove any unnecessary logic and instead reference the custom field values for Price, Mileage, and MPG.

4. Consider using HTML and CSS in `single-car.php` to further customize how this information appears.


For a more in-depth view on the exact modifications made, please make sure to check out the [full codebase on GitHub](https://github.com/colorful-tones/acf-demo-child-theme), and experiment with adding and removing your own field types.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#final-thoughts)

## Final Thoughts

Link copied

With these steps, you’ve successfully created a custom post type, added specialized fields, and customized how the content is displayed. ACF provides highly tailored data management with over 30 custom fields and custom post type creation directly in the plugin’s UI.

ACF also lets you register and manage [custom taxonomies](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/) in WordPress, allowing for more precise and flexible content organization, enhancing user experience, search engine optimization, and content management by providing tailored categorization beyond the default categories and tags. The next video shows to [create custom taxonomies with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/) and add them to custom post types.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#related)

## Related

Link copied

- Videos: [Creating a Custom Taxonomy with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- : [Frequently Asked Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Guides: [How to Create an Options Page](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/#)