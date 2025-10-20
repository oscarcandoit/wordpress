---
url: https://www.advancedcustomfields.com/resources/relationship
scraped_at: 2025-10-20T02:32:43.216Z
---

# Relationship

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#description)

## Description

Link copied

The Relationship field provides a dual-column component to select one or more posts, pages or [custom post type](https://www.advancedcustomfields.com/blog/wordpress-custom-post-type-relationships/) items, providing search, post type and taxonomy filtering controls to help find results.

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#screenshots)

## Screenshots

Link copied

![Creating a Relationship field in an ACF field group. The tab shown depicts General settings for the field: Field Type, Field Label, Field Name, Filter by Post Type, Filter by Post Status, Filter by Taxonomy, a set of buttons to select which of the above filters will be used in the component, and Return Format. The other tabs are Validation, Presentation, Conditional Logic, and Advanced.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Relationships-General-Settings-Revised-1.png)

Creating a Relationship field in an ACF field group.

![The Relationship field UI as it might appear to content editors. Existing posts, pages, etc., are shown in the left-hand column. Selecting them will move them to the right-hand column. A search box and dropdown menus that enable filtering make it easier to search for the object with which to establish a relationship.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Relationship-Field-UI-Revised-1.png)

The Relationship field UI as it might appear to content editors.

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#settings)

## Settings

Link copied

- **Filter by Post Type**


Filters the selectable results by post type. When left empty, all post types are shown. Results are grouped by post type, so selected post types may be positioned in a specific order.

- **Filter by Post Status**


Filters the selectable results by status, i.e, Published, Draft, etc. Shows posts of every status if left empty.

- **Filter by Taxonomy**


Filters the selectable results via one or more taxonomy terms.

- **Filters**


Specifies which filters are displayed in the component. Select from “Search”, “Post Type”, and/or “Taxonomy”.

- **Return Format**
Specifies the returned value format. Choose from Post Object ( `WP_Post`) or Post ID (integer).

- **Required**


Found on the Validation tab, this requires an input be entered, preventing the field from accepting empty values. Defaults to off.

- **Minimum Posts**


Sets a limit on how many posts are required.

- **Maximum Posts**


Sets a limit on how many posts are allowed.

- **Instructions**


Shows instructions when submitting data.

- **Elements**


Specifies which elements are displayed in each result. Select from “Featured Image”.

- **Conditional Logic**


Enabling this setting allows you to customize the logic which determines if the current field should be visible. Groups of conditional logic rules can be created to allow for multiple and/or statements.

- **Bidirectional**


Found on the Advanced tab, enabling this setting allows you to update a value in the target fields for each value selected for this field, adding or removing the Post ID, Taxonomy ID, or User ID of the item being updated. Please see [Bidirectional Relationships](https://www.advancedcustomfields.com/resources/bidirectional-relationships/) for more information on using this setting to create bidirectional relationships directly in ACF’s UI.


[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#template-usage)

## Template usage

Link copied

The Relationship field will return an array of items where each item is either a `WP_Post` object or an integer value depending on the Return Format set.

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#display-list-of-posts-with-setuppostdata)

### Display list of posts (with setup\_postdata)

Link copied

This example demonstrates how to loop over a Post Object value and display a list of clickable links. Here, we use a special function named `setup_postdata()` to enable the use of WordPress template functions. The field in this example uses Post Object as the Return Format, and is a multiple value.

```php
<?php
$featured_posts = get_field('featured_posts');
if( $featured_posts ): ?>
    <ul>
    <?php foreach( $featured_posts as $post ):

        // Setup this post for WP functions (variable must be named $post).
        setup_postdata($post); ?>
        <li>
            <a href="<?php the_permalink(); ?>"><?php the_title(); ?></a>
            <span>A custom field from this post: <?php the_field( 'field_name' ); ?></span>
        </li>
    <?php endforeach; ?>
    </ul>
    <?php
    // Reset the global post object so that the rest of the page works correctly.
    wp_reset_postdata(); ?>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#display-list-of-posts-without-setuppostdata)

### Display list of posts (without setup\_postdata)

Link copied

This example demonstrates how to loop over a Post Object value and display a list of clickable links. Here, the global post variable is never changed, so all “post” related functions need a second parameter to specify which object. The field in this example uses Post Object as the Return Format, and is a multiple value.

```php
<?php
$featured_posts = get_field('featured_posts');
if( $featured_posts ): ?>
    <ul>
    <?php foreach( $featured_posts as $featured_post ):
        $permalink = get_permalink( $featured_post->ID );
        $title = get_the_title( $featured_post->ID );
        $custom_field = get_field( 'field_name', $featured_post->ID );
        ?>
        <li>
            <a href="<?php echo esc_url( $permalink ); ?>"><?php echo esc_html( $title ); ?></a>
            <span>A custom field from this post: <?php echo esc_html( $custom_field ); ?></span>
        </li>
    <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#customization)

### Customization

Link copied

The Relationship field contains filters to customize the [posts displayed](https://www.advancedcustomfields.com/resources/acf-fields-relationship-query/), and the [text displayed](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/) for each post.

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#reverse-query)

### Reverse query

Link copied

It is possible to perform a reverse query on a post (post A) to find all the posts (post B, post C) which have selected it (post A). To learn more about a reverse query, please read [this in-depth tutorial](https://www.advancedcustomfields.com/resources/tutorials/querying-relationship-fields/).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/relationship/#related)

## Related

Link copied

- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Guides: [Bidirectional Relationships](https://www.advancedcustomfields.com/resources/bidirectional-relationships/)
- Basic: [acf\_get\_field\_groups()](https://www.advancedcustomfields.com/resources/acf_get_field_groups/)

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

[Got it](https://www.advancedcustomfields.com/resources/relationship/#)