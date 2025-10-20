---
url: https://www.advancedcustomfields.com/resources/working-with-nested-repeaters
scraped_at: 2025-10-20T02:24:14.762Z
---

# Working with Nested Repeaters

Last updated Mar 9, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#overview)

## Overview

Link copied

Creating and displaying nested repeater / flexible content fields is very easy using the Advanced Custom Fields plugin. This article will demonstrate how to build a simple to-do list that uses a nested repeater to output groups of items.

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#field-group)

## Field group

Link copied

Below is a screenshot showing the field group used for this to-do list, and the location rules indicating when this field group should appear.

[![This screenshot shows the ACF field group used for this to-do list. It consists of a Repeater Field with two subfields: a Text field to indicate the name of the task and a True/False field to indicate whether or not the task has been completed.](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/Nested-Repeater-Input-Edit-Field-Group.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/Nested-Repeater-Input-Edit-Field-Group.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#data)

## Data

Link copied

Below is a screenshot showing a page which this field group appears on. As shown above, a page template of “To-do List” was used as a location rule to attach the field group to the page.

[![This screenshot shows a page in the WordPress admin on which the to-do list field group appears.](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/Nested-Repeater-Fields-Edit-Page-To-Do-List.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/Nested-Repeater-Fields-Edit-Page-To-Do-List.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#template)

## Template

Link copied

Now that we have created the field group and entered data for our to-do list, we can now loop over and display the data in our template. This tutorial assumes a template file for “To-do List” exists, so let’s edit that file. In the following code we will be using these functions:

- [`have_rows()`](https://www.advancedcustomfields.com/resources/functions/have_rows/ "have_rows()") – allows us to loop through the available rows in a repeater / flexible content field
- [`get_sub_field()`](https://www.advancedcustomfields.com/resources/functions/get_sub_field/ "get_sub_field()") – returns the value of a sub field (from the current repeater in “has\_sub\_field”)
- [`the_sub_field()`](https://www.advancedcustomfields.com/resources/functions/the_sub_field/ "the_sub_field()") – displays the value of a sub field (from the current repeater in “has\_sub\_field”)

```php
<?php

/**
 * Template Name: To-do List
 */

get_header(); ?>

    <div id="primary">
        <div id="content" role="main">

            <?php while ( have_posts() ) : the_post(); ?>

                <h1><?php the_title(); ?></h1>
                <?php the_content(); ?>

                <?php

                // check for rows (parent repeater)
                if( have_rows('to-do_lists') ): ?>
                    <div id="to-do-lists">
                    <?php

                    // loop through rows (parent repeater)
                    while( have_rows('to-do_lists') ): the_row(); ?>
                        <div>
                            <h3><?php the_sub_field('title'); ?></h3>
                            <?php

                            // check for rows (sub repeater)
                            if( have_rows('items') ): ?>
                                <ul>
                                <?php

                                // loop through rows (sub repeater)
                                while( have_rows('items') ): the_row();

                                    // display each item as a list - with a class of completed ( if completed )
                                    ?>
                                    <li <?php if( get_sub_field('completed') ){ echo 'class="completed"'; } ?>><?php the_sub_field('name'); ?></li>
                                <?php endwhile; ?>
                                </ul>
                            <?php endif; //if( get_sub_field('items') ): ?>
                        </div>

                    <?php endwhile; // while( has_sub_field('to-do_lists') ): ?>
                    </div>
                <?php endif; // if( get_field('to-do_lists') ): ?>

            <?php endwhile; // end of the loop. ?>

        </div><!-- #content -->
    </div><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

Here is a screenshot showing the HTML produced from the above code.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/04/nested-repeaters-markup.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/04/nested-repeaters-markup.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#conclusion)

## Conclusion

Link copied

Working with nested repeaters is easy, but can sometimes become confusing. To make life easier, try to use simple field names. Remember that sub fields can also use the same names as the ancestors so there’s no need to for long unique field names.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#related)

## Related

Link copied

- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Querying relationship fields](https://www.advancedcustomfields.com/resources/querying-relationship-fields/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Field Types: [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/)
- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)

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

[Got it](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/#)