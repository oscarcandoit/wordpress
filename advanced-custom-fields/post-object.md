---
url: https://www.advancedcustomfields.com/resources/post-object
scraped_at: 2025-10-20T02:26:06.099Z
---

# Post Object

Last updated Aug 9, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#description)

## Description

Link copied

The Post Object field creates an interactive dropdown to select one or more posts, pages, or custom post type items. This field type uses the Select2 library to enable search and AJAX functionality.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#screenshots)

## Screenshots

Link copied

![Creating a Post Object field in an ACF field group. The tab shown depicts General settings for the field: Field Type, Field Label, Field Name, Filter by Post Type, Filter by Post Status, Filter by Taxonomy, Return Format, and Select Multiple. The other tabs are Validation, Presentation, Conditional Logic, and Advanced.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Post-Object-General-Settings-Revised-1.png)

Creating a Post Object field in an ACF field group.

![How the Post Object field might appear to content editors. A dropdown menu displays the posts and pages available. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/07/Post-Object-UI-1.png)

How the Post Object field might appear to content editors.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#settings)

## Settings

Link copied

- **Filter by Post Type**


Filters the selectable results by post type. When left empty, all post types are shown. Results are grouped by post type, so selected post types may be positioned in a specific order.

- **Filter by Post Status**


Filters the selectable results by status of the post, i.e, Published, Draft, etc. Shows posts of every status if left empty.

- **Filter by Taxonomy**


Filters the selectable results via one or more taxonomy terms.

- **Return Format**
Specifies the returned value format. Choose from Post Object ( `WP_Post`) or Post ID (integer).

- **Select Multiple**
Allows content editors to select more than one choice and reorder the selected choices by dragging and dropping. Defaults to off.

- **Required**


Found on the Validation tab, this requires an input be entered, preventing the field from accepting empty values. Defaults to off.

- **Allow Null**


When enabled, this allows the current selection to be cleared and an empty value to be saved. Defaults to off.

- **Instructions**


Shows instructions when submitting data.

- **Conditional Logic**


Enabling this setting allows you to customize the logic which determines if the current field should be visible. Groups of conditional logic rules can be created to allow for multiple and/or statements.

- **Bidirectional**


Found on the Advanced tab, enabling this setting allows you to update a value in the target fields for each value selected for this field, adding or removing the Post ID, Taxonomy ID, or User ID of the item being updated. Please see [Bidirectional Relationships](https://www.advancedcustomfields.com/resources/bidirectional-relationships/) for more information on using this setting to create bidirectional relationships directly in ACF’s UI.


[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#template-usage)

## Template usage

Link copied

Depending on the chosen field settings, the Post Object field will return either a single value, or an array where each value is a `WP_Post` object or an integer.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#display-selected-post)

### Display selected post

Link copied

This example demonstrates how to display basic data (such as the post\_title) from a Post Object value. The field in this example uses Post Object as the Return Format and is a single value.

```php
<?php
$featured_post = get_field('featured_post');
if( $featured_post ): ?>
    <h3><?php echo esc_html( $featured_post->post_title ); ?></h3>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#display-list-of-posts-with-setuppostdata)

### Display list of posts (with setup\_postdata)

Link copied

This example demonstrates how to loop over a Post Object value and display a list of clickable links. Here, we use a special function named `setup_postdata()` to enable the use of WordPress template functions. The field in this example uses Post Object as the Return Format and is a multiple value.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#display-list-of-posts-without-setuppostdata)

### Display list of posts (without setup\_postdata)

Link copied

This example demonstrates how to loop over a Post Object value and display a list of clickable links. Here, the global post variable is never changed, so all “post” related functions need a second parameter to specify which object. The field in this example uses Post Object as the Return Format and is a multiple value.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#customization)

### Customization

Link copied

The Post Object field contains PHP filters to customize the [posts displayed](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/), and the [text displayed](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/) for each post.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/post-object/#related)

## Related

Link copied

- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Page Link](https://www.advancedcustomfields.com/resources/page-link/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Guides: [Bidirectional Relationships](https://www.advancedcustomfields.com/resources/bidirectional-relationships/)

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

[Got it](https://www.advancedcustomfields.com/resources/post-object/#)