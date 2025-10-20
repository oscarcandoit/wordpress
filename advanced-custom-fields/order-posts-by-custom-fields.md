---
url: https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields
scraped_at: 2025-10-20T02:32:30.485Z
---

# Order posts by custom fields

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#overview)

## Overview

Link copied

This article will demonstrate how to retrieve and sort an array of post objects from the database using native WP functions. There are many ways to query posts in WP, however, this article will make use of the common [get\_posts](https://codex.wordpress.org/Template_Tags/get_posts) function, [WP\_Query](https://codex.wordpress.org/Class_Reference/WP_Query) Object and [pre\_get\_posts](https://codex.wordpress.org/Plugin_API/Action_Reference/pre_get_posts) filter.

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#getting-started)

## Getting started

Link copied

If you are already familiar with the above function, object and filter you may skip this section.

The [WP\_Query](https://www.advancedcustomfields.com/blog/wp-query/) object is used to query posts and will return an object containing an array of $post objects and many useful methods.

The [get\_posts](https://codex.wordpress.org/Template_Tags/get_posts) function makes use of the above WP\_Query object, however, it only returns an array of $post objects making it a simpler way to find and loop over posts.

The [pre\_get\_post](https://codex.wordpress.org/Plugin_API/Action_Reference/pre_get_posts) filter is called after the query object is created, but before the actual query is run.

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#getposts)

### get\_posts

Link copied

This example will use the get\_posts function to load all the ‘events’ posts ordered by a custom field value of ‘start\_date’.

```php
<?php

// get posts
$posts = get_posts(array(
    'post_type'         => 'event',
    'posts_per_page'    => -1,
    'meta_key'          => 'start_date',
    'orderby'           => 'meta_value',
    'order'             => 'DESC'
));

if( $posts ): ?>

    <ul>

    <?php foreach( $posts as $post ):

        setup_postdata( $post )

        ?>
        <li>
            <a href="<?php the_permalink(); ?>"><?php the_title(); ?> (date: <?php the_field('start_date'); ?>)</a>
        </li>

    <?php endforeach; ?>

    </ul>

    <?php wp_reset_postdata(); ?>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#wpquery)

### WP\_Query

Link copied

This example will use the WP\_Query object to load all the ‘events’ posts ordered by a custom field ‘featured’. In this case, ‘featured’ is a True / False custom field and the result will show featured posts above the rest.

```php
<?php

// query
$the_query = new WP_Query(array(
    'post_type'         => 'event',
    'posts_per_page'    => -1,
    'meta_key'          => 'featured',
    'orderby'           => 'meta_value',
    'order'             => 'DESC'
));

?>
<?php if( $the_query->have_posts() ): ?>
    <ul>
    <?php while( $the_query->have_posts() ) : $the_query->the_post();

        $class = get_field('featured') ? 'class="featured"' : '';

        ?>
        <li <?php echo $class; ?>>
            <a href="<?php the_permalink(); ?>"><?php the_title(); ?></a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>

<?php wp_reset_query();   // Restore global post data stomped by the_post(). ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#pregetposts)

## pre\_get\_posts

Link copied

This example shows how to modify the current posts query. This is useful to modify an existing post type archive. This filter should be used in the functions.php file and requires some logic to avoid modifying all queries.

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#functionsphp)

#### functions.php

Link copied

```php
<?php

function my_pre_get_posts( $query ) {

    // do not modify queries in the admin
    if( is_admin() ) {

        return $query;

    }


    // only modify queries for 'event' post type
    if( isset($query->query_vars['post_type']) && $query->query_vars['post_type'] == 'event' ) {

        $query->set('orderby', 'meta_value');
        $query->set('meta_key', 'start_date');
        $query->set('order', 'DESC');

    }


    // return
    return $query;

}

add_action('pre_get_posts', 'my_pre_get_posts');

?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#related)

## Related

Link copied

- Guides: [How to Query Posts by Custom Fields](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/)
- Guides: [Creating a WP archive with custom field filter](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/)
- Basic: [acf\_get\_field\_groups()](https://www.advancedcustomfields.com/resources/acf_get_field_groups/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Sort a Repeater Field](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/)

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

[Got it](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/#)