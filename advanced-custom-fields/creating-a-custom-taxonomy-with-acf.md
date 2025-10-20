---
url: https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf
scraped_at: 2025-10-20T02:32:02.942Z
---

# Creating a Custom Taxonomy with ACF

Last updated Nov 13, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#overview)

## Overview

Link copied

Taxonomies in WordPress allow for the classification and organization of structured data. WordPress comes with the “Posts” post type, which already has two default taxonomies: Categories and Tags.

- Categories allow for hierarchical organization with parent-child relationships.
- Tags are non-hierarchical and do not have parent-child relationships.

But what if you need a custom taxonomy unique to your data structure? In this video, we show how to use ACF to register and associate custom taxonomies with a custom post type. Following this tutorial, you’ll extend the “Car” post type we registered in [Creating a Custom Post Type with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/) and assign two new taxonomies: “Manufacturer” and “Make.” You’ll also see how to create manufacturers and output all the information in our [Twenty Nineteen child theme](https://github.com/colorful-tones/acf-demo-child-theme).

Creating a Custom Taxonomy with ACF - YouTube

[Photo image of WP Engine Builders](https://www.youtube.com/channel/UCh1WuL54XFb9ZI6m6goFv1g?embeds_referring_euri=https%3A%2F%2Fwww.advancedcustomfields.com%2F&embeds_referring_origin=https%3A%2F%2Fwww.advancedcustomfields.com)

WP Engine Builders

6.33K subscribers

[Creating a Custom Taxonomy with ACF](https://www.youtube.com/watch?v=Je_-9TrlASI)

WP Engine Builders

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

0:00

0:00 / 4:14
•Live

•

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#step-1-registering-custom-taxonomies)

## Step 1: Registering Custom Taxonomies

Link copied

The step-by-step instructions below illustrate how to create two custom taxonomies and then use them in the “Car” custom post type we created in [our previous video](https://youtu.be/EG4WcVeMU-0).

First, we’ll use ACF to create a custom taxonomy for “Manufacturers.” In the WordPress admin, navigate to **ACF > Taxonomies** and click **Add New**.

Start by creating the “Manufacturers” taxonomy. Enter the following into the required fields:

- **Plural Label:** Manufacturers
- **Singular Label:** Manufacturer
- **Taxonomy Key:** manufacturer
- **Post Types:** Car

You can enter multiple “Post Types” if you’d like the custom taxonomy to be available for more than one.

Check the **Hierarchical** toggle to ensure the taxonomy allows for nested parent-child relationships. This will allow content editors to enter the manufacturer with the specific vehicle brand nested within it, such as “Kia – Seltos” or “Ford – Focus”.

Toggling on “Advanced Configuration” will show many more options you can use for your custom taxonomy. These options are covered in our documentation on [Registering a Custom Taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/).

![The custom taxonomy editing screen in ACF, showing the options described in the text of the article. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/11/ACF-Custom-Taxonomy-Edit-Taxonomy-Screen-1.png)

Click **Save Changes** to save your custom taxonomy.

The next step is create the “Make” taxonomy. Repeat the process outlined above, but use the following information for our required fields:

- **Plural Label:** Makes
- **Singular Label:** Make
- **Taxonomy Key:** make
- **Post Type:** Car

We want our editors to assign freeform tags for this taxonomy, so we won’t enable the “Hierarchical” toggle.

Click **Save Changes** to save the “Makes” custom taxonomy.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#step-2-assigning-custom-taxonomies-to-posts)

## Step 2: Assigning Custom Taxonomies to Posts

Link copied

Now that you’ve registered your two new custom taxonomies and assigned them to the post type, when you edit a “Car” post, you should see the additional options for your taxonomies in the sidebar. This is where you’ll assign each car’s Manufacturer and Make.

![Adding custom taxonomies to a custom post type. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/11/Adding-taxonomies-to-posts.png)

Next, we’ll discover how to display these taxonomies in our child theme.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#step-3-displaying-custom-taxonomies)

## Step 3: Displaying Custom Taxonomies

Link copied

With custom taxonomies registered and assigned to the post type, the next step is to create custom template logic to display this new information in the child theme.

The [ACF demo child theme](https://github.com/colorful-tones/acf-demo-child-theme) demonstrates the necessary template files and logic for displaying your custom post type. The demo theme will automatically register the “Car” post type, the vehicle details fields group, and the “Manufacturer” and “Make” taxonomies. There is even a full XML import that allows you to replicate a fully functioning car dealership site.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#conclusion)

## Conclusion

Link copied

If you’ve followed along with the tutorials, you should have a [custom post type](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/) registered with custom fields and taxonomies. We hope you’re starting to see the flexibility and simplicity of using ACF to create custom data structures. Be sure to check out [all of our videos](https://www.youtube.com/playlist?list=PLmHWEf9to377wJBJ3i_W9t6kMiLw3MTx-) and we encourage you to experiment with the final demo code.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#related)

## Related

Link copied

- Guides: [Registering a Custom Taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/)
- Videos: [Creating a Custom Post Type with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/)
- Tutorials: [Registering a Custom Post Type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/)
- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/#)