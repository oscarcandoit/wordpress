---
url: https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme
scraped_at: 2025-10-20T02:24:53.777Z
---

# Building Layouts With the Flexible Content Field in a Theme

Last updated Apr 20, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#overview)

## Overview

Link copied

ACF’s [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/) fields allow you to create multiple groups of fields known as layouts. You can then use these to give content editors more control over how data is rendered.

In this article, I’ll give you a complete use case and show how you can leverage the Flexible Content field to create swappable site sections and integrate it all in a theme.

Think of Flexible Content as a way to make WordPress layout patterns, but with [ACF PRO](https://www.advancedcustomfields.com/pro/) fields and subfields. Generally, the idea is to create atomic blocks, elements, units–or whatever you prefer to call the smaller pieces of UI–and compose them into whole flexible patterns. Ideally, these patterns are a starting point for editors to kickstart their content writing experience.

I’ve created a fictitious company site to demonstrate how to compose layouts with Flexible Content fields. [Qorp](https://qorp.wpengine.com/) is a new tech company that needs a site for its trendy new tech.

What is the tech? Nobody truly knows 🤪.

Qorp would like the ability to add and remove sections below their blog posts. Also, they want to be able to place them in any order. This is one example where Flexible Content fields can really shine. Below, I’ve included an image capturing the visual mixing and matching that Qorp required for their single blog posts.

There are three sections: Call to Action, Trust Signals, and Related Posts, all built with layouts created within a Flexible Content field. ACF makes it simple for Qorp’s content team to switch them around, add more of one layout, or remove them entirely if that’s what’s needed for a particular post.

![View of different layouts being matched in sections.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/flexible-content-layout-overview.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#setting-up-our-flexible-content-field)

## Setting Up Our Flexible Content Field

Link copied

The first thing we want to do is create a new field group with a Flexible Content field and give it a name. I named my field group: “Single Post: wrap-up sections” and my field “Sections.”

Next, make sure to set the **Location Rules** to **Post Type** – **is equal to** – **Post**. This ensures our fields only show when Qorp is editing a “Post” post type. Be sure to choose Flexible Content as the parent field type. I also recommend prefixing your Flexible Content field’s Name, e.g., `qorp_post_sections`.

![ACF field group edit screen with Settings > Location Rules highlighted.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/fc-field-group-settings-1.png)

New Flexible Content field group with Post Type = Post as the Location Rules.

![ACF field group edit screen with Name and Field Type highlighted.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/fc-field-group-name-label-2.png)

At this point, we’ve got our Flexible Content field showing for our Qorp content creators, but there’s nothing on the frontend yet.

![A screenshot of the Qorp blog. As we haven't added any subfields within the Flexible Content field, it only displays the current post, without the call to action, related posts, and trust signals sections.  ](https://www.advancedcustomfields.com/wp-content/uploads/2023/01/Qorp-blog.png)

The Flexible Content field won’t do the client much good until we give them some layouts in the next section.

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#creating-subfields-within-the-flexible-content-field)

## Creating Subfields Within the Flexible Content Field

Link copied

Now that we’ve established our Flexible Content field, we’ll want to create our layouts. Remember, layouts are the nested field groups within a Flexible Content field which can be used to present the data differently for each layout.

Based on our design, we have the following sections we need to account for: Call to Action, Trust Signals, and Related Posts.

- **Call to Action:** This features a small descriptive text, often called an eyebrow, followed by a heading and a button.


  - Label: Call to action
  - Name: `call_to_action`
  - Layout: Block
  - Fields:

    - Label: Eyebrow / Name: `eyebrow` / Type: Text
    - Label: Heading / Name: `heading` / Type: Text
    - Label: Button / Name: `button` / Type: Group
    - Button sub-fields:

      - Label: Button text / Name: `button_text` / Type: Text
      - Label: Button link / Name: `button_link` / Type: URL

![Flexible Content subfields for Call to Action section.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/fc-field-group-section-1.png)

Since we’ve added our first layout, there’s something to see now when our clients look at their posts. There’s only one section so far, but we’re on our way.

- **Trust Signals:** A heading with affiliated company logos underneath.


  - Label: Trust Signals
  - Name: `trust_signals`
  - Layout: Block
  - Fields:

    - Label: Logo / Name: `logo` / Type: Repeater
    - Repeater sub-fields:

      - Label: Logo / Name: `logo` / Type: Image

![Flexible Content subfields for the Trust Signals section, which is used to display affiliated company logos.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/fc-field-group-section-2.png)

Now that we’ve added a subfield for the Trust Signals section, we can see it has appeared on our client’s posts beneath their CTA.

- **Related Posts:** Manually curated posts related to the current post, which the Qorp editorial team can set.


  - Label: Related Posts
  - Name: `related_posts`
  - Layout: Block
  - Fields:

    - Label: Posts / Name: `posts` / Type: Relationship

![The Flexible Content field for the Related Posts section.](https://www.advancedcustomfields.com/wp-content/uploads/2022/12/fc-field-group-section-3.png)

When we look at the frontend, we can see the Related Posts field displaying as it should.

With all of the layouts in place, our clients at Qorp can easily rearrange the layouts to suit the needs of the post.

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#output-flexible-content-fields-in-a-block-theme)

## Output Flexible Content Fields in a Block Theme

Link copied

Next, we’ll walk through outputting the Flexible Content field data within a block theme. If you’re new to block themes, I recommend you check out “ [Introduction to block theme development](https://learn.wordpress.org/tutorial/introduction-to-block-theme-development-for-beginners/)“. WordPress is remarkable, as even block themes allow us to use classic template hierarchy and functionality. We’ll lean on these to output our post metadata. We can add a `single.php` template file ( [complete source code](https://github.com/colorful-tones/qorp/blob/main/themes/qorp-theme/single.php)) with the following logic:

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#singlephp)

#### single.php

Link copied

```php
get_header();

/* Start the Loop */
while ( have_posts() ) :
    the_post();

    get_template_part( 'template-parts/content/content-single' );

    // ACF - Flexible Content fields.
    $sections = get_field( 'qorp_post_sections' );

    if ( $sections ) :
        foreach ( $sections as $section ) :
            $template = str_replace( '_', '-', $section['acf_fc_layout'] );
            get_template_part( 'flexible-content/sections/' . $template, '', $section );
        endforeach;
    endif;

endwhile; // End of the loop.

get_footer();
```

The bulk of this logic is referencing other template files, but we’re grabbing our `qorp_post_sections` and then looping through them and calling separate template files based on which Flexible Content layout is returned.

Here are the template files:

- [qorp-theme/flexible-content/sections/call-to-action.php](https://github.com/colorful-tones/qorp/blob/main/themes/qorp-theme/flexible-content/sections/call-to-action.php)
- [qorp-theme/flexible-content/sections/related-posts.php](https://github.com/colorful-tones/qorp/blob/main/themes/qorp-theme/flexible-content/sections/related-posts.php)
- [qorp-theme/flexible-content/sections/trust-signals.php](https://github.com/colorful-tones/qorp/blob/main/themes/qorp-theme/flexible-content/sections/trust-signals.php)

All of the [source code for the Qorp site](https://github.com/colorful-tones/qorp) is on GitHub. You can also see an example of the final output on [Qorp’s site](https://qorp.wpengine.com/officia-qui-culpa-esse/). Also, be sure to check out the final fields ( [layouts.json](https://github.com/colorful-tones/qorp/blob/main/plugins/qorp-plugin/acf-fields/layouts.json)) within the [qorp-plugin](https://github.com/colorful-tones/qorp/tree/main/plugins/qorp-plugin).

ACF’s Flexible Content fields give you the power to offer your clients flexibility for their content, while ensuring they don’t go too far afield from the way their site is supposed to look.

Below 👇 is a video that demonstrates the editorial flow for using these Flexible Content fields.

ACF PRO Flexible Content field demonstration - create page builder-like sections and drag-n-drop. - YouTube

[Photo image of WP Engine Builders](https://www.youtube.com/channel/UCh1WuL54XFb9ZI6m6goFv1g?embeds_referring_euri=https%3A%2F%2Fwww.advancedcustomfields.com%2F)

WP Engine Builders

6.33K subscribers

[ACF PRO Flexible Content field demonstration - create page builder-like sections and drag-n-drop.](https://www.youtube.com/watch?v=t7pjoKGGTUI)

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

0:00 / 3:00
•Live

•

The Flexible Content field type is arguably one of the most powerful field types in [ACF PRO](https://www.advancedcustomfields.com/pro/). We’ve seen just how powerful it can be when we looked at how the agency [Rareloop uses it to create a page builder experience](https://www.advancedcustomfields.com/blog/rareloop-acf-case-study/) for their clients.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#related)

## Related

Link copied

- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- : [Frequently Asked Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/)
- Videos: [Getting Started with ACF Custom Fields & Field Groups](https://www.advancedcustomfields.com/resources/getting-started-with-acf-custom-fields-field-groups/)
- Field Types: [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)

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

[Got it](https://www.advancedcustomfields.com/resources/building-layouts-with-the-flexible-content-field-in-a-theme/#)