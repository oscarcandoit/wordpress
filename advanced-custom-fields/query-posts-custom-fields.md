---
url: https://www.advancedcustomfields.com/resources/query-posts-custom-fields
scraped_at: 2025-10-20T02:32:21.473Z
---

# How to Query Posts by Custom Fields

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#overview)

## Overview

Link copied

This article demonstrates how to retrieve an array of post objects from the database using native WordPress functions. There are many ways to query posts in WordPress, however, this article will make use of the common [get\_posts](https://developer.wordpress.org/reference/functions/get_posts/) function, [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) object and [pre\_get\_posts](https://developer.wordpress.org/reference/hooks/pre_get_posts/) filter.

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#getting-started)

## Getting Started

Link copied

You can skip this section if you’re already familiar with the above function, object, and filter.

The [WP\_Query](https://www.advancedcustomfields.com/blog/wp-query/) object is used to query posts and will return an object containing an array of `$post` objects and many useful methods.

The [get\_posts](https://developer.wordpress.org/reference/functions/get_posts/) function makes use of the above `WP_Query` object. However, it _only_ returns an array of `$post` objects, making it a simpler way to find and loop over posts.

The [pre\_get\_post](https://developer.wordpress.org/reference/hooks/pre_get_posts/) filter is called after the query object is created, but before the actual query is run.

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#example)

### Example

Link copied

This example demonstrates how to query all posts and display them in a list. Please note the functions `setup_postdata()` and `wp_reset_postdata()` are used to allow functions such as `the_permalink()` and `the_title()` to work as expected.

```php
<?php

$posts = get_posts(array(
    'posts_per_page'    => -1,
    'post_type'         => 'post'
));

if( $posts ): ?>

    <ul>

    <?php foreach( $posts as $post ):

        setup_postdata( $post );

        ?>
        <li>
            <a href="<?php the_permalink(); ?>"><?php the_title(); ?></a>
        </li>

    <?php endforeach; ?>

    </ul>

    <?php wp_reset_postdata(); ?>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#custom-field-parameters)

## Custom Field Parameters

Link copied

Both the `get_posts` function and `WP_Query` object accept arguments to perform basic and advanced queries on custom field values. There is both a basic and advanced way to query which are explained below. You can read more about acceptable parameters in the [WP codex](https://developer.wordpress.org/reference/classes/wp_query/#custom-field-post-meta-parameters).

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#basic-query-example)

### Basic Query Example

Link copied

This example shows the arguments to find all posts where a custom field called ‘color’ has a value of ‘red’.

```php
$posts = get_posts(array(
    'posts_per_page'    => -1,
    'post_type'     => 'post',
    'meta_key'      => 'color',
    'meta_value'    => 'red'
));
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#advanced-query-example)

### Advanced Query Example

Link copied

This example shows arguments to find all posts where a custom field called ‘color’ has a value of ‘red’ or ‘orange’, and another custom field called ‘featured’ (checkbox) is checked.

```php
$posts = get_posts(array(
    'posts_per_page'    => -1,
    'post_type'     => 'post',
    'meta_query'    => array(
        'relation'      => 'AND',
        array(
            'key'       => 'color',
            'value'     => array('red', 'orange'),
            'compare'   => 'IN',
        ),
        array(
            'key'       => 'featured',
            'value'     => '1',
            'compare'   => '=',
        ),
    ),
));
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#examples)

## Examples

Link copied

Below you will find an assortment of examples. Please note these examples use the `WP_Query` object rather than the `get_posts` function, but the arguments and logic remain the same.

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#1-single-custom-field-value)

### 1\. Single custom field value

Link copied

In this example, we will find all posts that have a `post_type` of ‘event’ where the custom field ‘location’ is equal to ‘Melbourne’. The custom field (‘location’ in this case) could be a Text, Radio Button, or Select field (i.e., something that saves a single text value).

```php
<?php

// args
$args = array(
    'posts_per_page'    => -1,
    'post_type'     => 'event',
    'meta_key'      => 'location',
    'meta_value'    => 'Melbourne'
);

// query
$the_query = new WP_Query( $args );

?>
<?php if( $the_query->have_posts() ): ?>
    <ul>
    <?php while( $the_query->have_posts() ) : $the_query->the_post(); ?>
        <li>
            <a href="<?php the_permalink(); ?>">
                <img src="<?php the_field('event_thumbnail'); ?>" />
                <?php the_title(); ?>
            </a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>

<?php wp_reset_query();   // Restore global post data stomped by the_post(). ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#2-multiple-custom-field-text-based-values)

### 2\. Multiple custom field text-based values

Link copied

In this example, we will find all posts that have a `post_type` of ‘event’ where the custom field ‘location’ is equal to ‘Melbourne’, and the custom field ‘attendees’ is higher than 100. The custom field (‘attendees’ in this case) could be a Number, Text, Radio Button, or Select field (i.e., something that saves a single text value).

```php
<?php

// args
$args = array(
    'posts_per_page'    => -1,
    'post_type'     => 'event',
    'meta_query'    => array(
        'relation'      => 'AND',
        array(
            'key'       => 'location',
            'value'     => 'Melbourne',
            'compare'   => '='
        ),
        array(
            'key'       => 'attendees',
            'value'     => 100,
            'type'      => 'NUMERIC',
            'compare'   => '>'
        )
    )
);

// query
$the_query = new WP_Query( $args );

?>
<?php if( $the_query->have_posts() ): ?>
    <ul>
    <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
        <li>
            <a href="<?php the_permalink(); ?>">
                <img src="<?php the_field('event_thumbnail'); ?>" />
                <?php the_title(); ?>
            </a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>

<?php wp_reset_query();   // Restore global post data stomped by the_post(). ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#3-multiple-custom-field-array-based-values-)

### 3\. Multiple custom field array-based values

Link copied

In this example, we will find all posts that have a `post_type` of ‘event’ where the custom field ‘location’ is equal to ‘Melbourne’ or ‘Sydney’. The custom field (‘location’ in this case) could be a Multi-Select or Checkbox field (i.e., something that saves a serialized array value).

```php
<?php

// args
$args = array(
    'posts_per_page'    => -1,
    'post_type'     => 'event',
    'meta_query'    => array(
        'relation'      => 'OR',
        array(
            'key'       => 'location',
            'value'     => 'Melbourne',
            'compare'   => 'LIKE'
        ),
        array(
            'key'       => 'location',
            'value'     => 'Sydney',
            'compare'   => 'LIKE'
        )
    )
);

// query
$the_query = new WP_Query( $args );

?>
<?php if( $the_query->have_posts() ): ?>
    <ul>
    <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
        <li>
            <a href="<?php the_permalink(); ?>">
                <img src="<?php the_field('event_thumbnail'); ?>" />
                <?php the_title(); ?>
            </a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>

<?php wp_reset_query();   // Restore global post data stomped by the_post(). ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#4-sub-custom-field-values)

### 4\. Sub custom field values

Link copied

In this example, we will find all events that have a ‘city’ or either ‘Melbourne’ or ‘Sydney’. Each ‘city’ is added as a new row to a repeater field called ‘location’.

To successfully query sub field values, we need to remember that the row number is not known (there may be 1, 2, or even 3 rows of Repeater field data). Therefore, we need to use a LIKE clause in our SQL query to allow for a WILDCARD in the meta\_key search. To do this, we create a custom filter to replace the standard ‘=’ with ‘LIKE’.

**Update:** Since the [changed behavior of `esc_sql()` in WordPress 4.8.3](https://make.wordpress.org/core/2017/10/31/changed-behaviour-of-esc_sql-in-wordpress-4-8-3/), it is not easy to use the `%` character as a placeholder for the following search and replace. Instead, we recommend that you use the `$` character as shown below.

**Note:** This method requires hooking into the `posts_where` filter, which is not guaranteed to run on all post queries. To overcome this, set `suppress_filters` to false in the argument array passed to `get_posts()` or `WP_Query`.

```php
<?php

// filter
function my_posts_where( $where ) {

    $where = str_replace("meta_key = 'locations_$", "meta_key LIKE 'locations_%", $where);

    return $where;
}

add_filter('posts_where', 'my_posts_where');

// vars
$city = 'Melbourne';

// args
$args = array(
    'posts_per_page'    => -1,
    'post_type'     => 'event',
    'meta_query'    => array(
        'relation'      => 'OR',
        array(
            'key'       => 'locations_$_city',
            'compare'   => '=',
            'value'     => 'Melbourne',
        ),
        array(
            'key'       => 'locations_$_city',
            'compare'   => '=',
            'value'     => 'Sydney',
        )
    )
);

// query
$the_query = new WP_Query( $args );

?>
<?php if( $the_query->have_posts() ): ?>
    <ul>
    <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
        <li>
            <a href="<?php the_permalink(); ?>"><?php the_title(); ?></a>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>

<?php wp_reset_query();   // Restore global post data stomped by the_post(). ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#dynamic-get-parameters)

### Dynamic $\_GET parameters

Link copied

This example shows how to use `$_GET` parameters (from the URL) to modify the query of a post type archive. This example assumes a post type exists for ‘event’ and that its archive exists at the url `www.website.com/events`.

The event post type contains a select field called ‘city’ with values such as ‘melbourne’ and ‘sydney’. By adding a parameter to the url, the query will be modified and only posts that match the ‘city’ will be shown: `www.website.com/events?city=melbourne`.

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#functionsphp)

#### functions.php

Link copied

```php
function my_pre_get_posts( $query ) {

    // do not modify queries in the admin
    if( is_admin() ) {

        return $query;

    }


    // only modify queries for 'event' post type
    if( isset($query->query_vars['post_type']) && $query->query_vars['post_type'] == 'event' ) {

        // allow the url to alter the query
        if( isset($_GET['city']) ) {

            $query->set('meta_key', 'city');
            $query->set('meta_value', $_GET['city']);

        }

    }


    // return
    return $query;

}

add_action('pre_get_posts', 'my_pre_get_posts');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#related)

## Related

Link copied

- Guides: [Order posts by custom fields](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/)
- Guides: [Creating a WP archive with custom field filter](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/)
- Basic: [acf\_get\_field\_groups()](https://www.advancedcustomfields.com/resources/acf_get_field_groups/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Filters: [acf/fields/post\_object/query](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/)

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

[Got it](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/#)