---
url: https://www.advancedcustomfields.com/resources/querying-relationship-fields
scraped_at: 2025-10-20T02:32:26.594Z
---

# Querying relationship fields

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#overview)

## Overview

Link copied

This tutorial will cover the techniques to query relationship fields in both directions. The example used will be “Doctors” and “Locations”.

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#screenshots)

## Screenshots

Link copied

To save time, this tutorial will not cover the setup process for the 2 post types and their custom fields. However, the screenshots bellow show the data we will be working with.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/locations-list.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/locations-list.png)

List of location post types


[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/locations-single.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/locations-single.png)

Each location has an address field


[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/doctors-list.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/doctors-list.png)

List of doctor post types


[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/doctor-single.png)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/doctor-single.png)

Each doctor post type has an image and a location field


[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#archive-doctorphp)

## archive-doctor.php

Link copied

First, we will create a template file in our theme to display all the doctors. This file is called “archive-doctor” and can be viewed by going to the url “http://website.com/?post\_type=doctor” or “http://website.com/doctor” depending on your permalink structure.

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#screenshot)

### Screenshot

Link copied

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/archive-doctor-700x714.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/archive-doctor.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#code)

### Code

Link copied

```php
<?php
/**
 * The template for displaying Archive pages.
 *
 * Theme: Twenty Eleven
 */

get_header(); ?>

    <section id="primary">
        <div id="content" role="main">

        <?php if ( have_posts() ) : ?>

            <header class="page-header">
                <h1 class="page-title">Doctors</h1>
            </header>

            <?php twentyeleven_content_nav( 'nav-above' ); ?>

            <?php /* Start the Loop */ ?>
            <?php while ( have_posts() ) : the_post(); ?>

                <article>
                    <header class="entry-header">
                        <?php

                        $photo = get_field('photo');

                        ?>
                        <h1 class="entry-title">
                            <a href="<?php the_permalink(); ?>">
                                <img class="alignleft" src="<?php echo $photo['url']; ?>" alt="<?php echo $photo['alt']; ?>" width="50" />
                                <?php the_title(); ?>
                            </a>
                        </h1>
                    </header>
                </article>

            <?php endwhile; ?>

            <?php twentyeleven_content_nav( 'nav-below' ); ?>

        <?php endif; ?>

        </div><!-- #content -->
    </section><!-- #primary -->

<?php get_sidebar(); ?>
<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#single-doctorphp)

## single-doctor.php

Link copied

Next, we will create a template file to view each doctor’s information. On this template page, we will show links to the locations where this doctor works.

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#screenshot)

### Screenshot

Link copied

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/single-doctor-700x555.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/single-doctor.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#code)

### Code

Link copied

```php
<?php
/**
 * The Template for displaying single posts.
 *
 * Theme: Twenty Eleven
 */

get_header(); ?>

    <div id="primary">
        <div id="content" role="main">

            <?php while ( have_posts() ) : the_post(); ?>

                <article>
                    <header class="entry-header">
                        <h1 class="entry-title"><?php the_title(); ?></h1>
                    </header>

                    <div class="entry-content">
                        <h2>Photo</h2>
                        <?php

                        $photo = get_field('photo');

                        ?>
                        <img class="alignleft" src="<?php echo $photo['url']; ?>" alt="<?php echo $photo['alt']; ?>" />

                        <h2>Works at</h2>
                        <?php

                        $locations = get_field('location');

                        ?>
                        <?php if( $locations ): ?>
                            <ul>
                            <?php foreach( $locations as $location ): ?>
                                <li>
                                    <a href="<?php echo get_permalink( $location->ID ); ?>">
                                        <?php echo get_the_title( $location->ID ); ?>
                                    </a>
                                </li>
                            <?php endforeach; ?>
                            </ul>
                        <?php endif; ?>

                    </div>

                </article>

            <?php endwhile; // end of the loop. ?>

        </div><!-- #content -->
    </div><!-- #primary -->

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#single-locationphp)

## single-location.php

Link copied

Last but not least, we will create the single location template file (as we can now navigate to this page from a doctor). So far, we have created a simple “forward facing” relationship between locations and doctors. Now we will do the opposite. On each location page, we will query the WP database for all the doctors that work in that location.

This will be accomplished by using the “get\_posts” function. This function makes use of the [`WP_Query`](http://codex.wordpress.org/Class_Reference/WP_Query "Class Reference/WP Query") class to fetch posts. See [the parameters section](http://codex.wordpress.org/Class_Reference/WP_Query#Parameters "Class Reference/WP Query") of the [`WP_Query`](https://www.advancedcustomfields.com/blog/wp-query/) documentation for a list of parameters that this function accepts.

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#screenshot)

### Screenshot

Link copied

[![](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/single-location-700x517.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2012/09/single-location.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#code)

### Code

Link copied

```php
<?php
/**
 * The Template for displaying single posts.
 *
 * Theme: Twenty Eleven
 */

get_header(); ?>

    <div id="primary">
        <div id="content" role="main">

            <?php while ( have_posts() ) : the_post(); ?>

                <article>
                    <header class="entry-header">
                        <h1 class="entry-title"><?php the_title(); ?></h1>
                    </header>

                    <div class="entry-content">
                        <h2>Address</h2>
                        <p><?php the_field('address'); ?></p>

                        <h2>Doctors that work here</h2>
                        <?php

                        /*
                        *  Query posts for a relationship value.
                        *  This method uses the meta_query LIKE to match the string "123" to the database value a:1:{i:0;s:3:"123";} (serialized array)
                        */

                        $doctors = get_posts(array(
                            'post_type' => 'doctor',
                            'meta_query' => array(
                                array(
                                    'key' => 'location', // name of custom field
                                    'value' => '"' . get_the_ID() . '"', // matches exactly "123", not just 123. This prevents a match for "1234"
                                    'compare' => 'LIKE'
                                )
                            )
                        ));

                        ?>
                        <?php if( $doctors ): ?>
                            <ul>
                            <?php foreach( $doctors as $doctor ): ?>
                                <?php

                                $photo = get_field('photo', $doctor->ID);

                                ?>
                                <li>
                                    <a href="<?php echo get_permalink( $doctor->ID ); ?>">
                                        <img src="<?php echo $photo['url']; ?>" alt="<?php echo $photo['alt']; ?>" width="30" />
                                        <?php echo get_the_title( $doctor->ID ); ?>
                                    </a>
                                </li>
                            <?php endforeach; ?>
                            </ul>
                        <?php endif; ?>

                    </div>

                </article>

            <?php endwhile; // end of the loop. ?>

        </div><!-- #content -->
    </div><!-- #primary -->

<?php get_footer(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#understanding-the-query)

### Understanding the query

Link copied

The above “get\_posts” query finds all posts that are of the type “doctor”. It then finds the “location” custom field for each doctor and runs a LIKE query on the value.

The relationship field saves it’s data as a serialized array. If you are not familiar with this format, please look up the stored value in your database. It will look something like this:

- a:2:{i:0;s:2:”35″;i:1;s:2:”33″;}

This serialized array has 2 values, the first is “35”, the second is “33”. As this is the “location” field for a “doctor”, these 2 numbers must be the ID’s of location post types.

In our query, the LIKE value was ‘”‘ . get\_the\_ID() . ‘”‘, if the location ID was 35 then the LIKE value would become ‘”35″‘. In this case, the query would match against the doctor’s location value (the serialized array shown above) and the doctor will be returned.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#related)

## Related

Link copied

- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Guides: [Working with Nested Repeaters](https://www.advancedcustomfields.com/resources/working-with-nested-repeaters/)
- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)
- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)

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

[Got it](https://www.advancedcustomfields.com/resources/querying-relationship-fields/#)