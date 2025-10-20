---
url: https://www.advancedcustomfields.com/resources/bidirectional-relationships
scraped_at: 2025-10-20T02:32:39.701Z
---

# Bidirectional Relationships

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#overview)

## Overview

Link copied

In a bidirectional relationship, each object (post, page, [custom post type](https://www.advancedcustomfields.com/blog/wordpress-custom-post-type-relationships/), user, or taxonomy) has a relationship field that refers to the other object. The relationship data is stored in an ACF field on both objects making it easier to query.

Currently, the Bidirectional setting is only available for the [Relationship](https://www.advancedcustomfields.com/resources/relationship/), [User](https://www.advancedcustomfields.com/resources/user/), [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/), and [Post Object](https://www.advancedcustomfields.com/resources/post-object/) fields

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#setup)

## Setup

Link copied

When editing a field group, supported field types will display a new “Advanced” tab with a Bidirectional toggle.

![Bidirectional field setting.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/acf_bidirectional.png)

When enabled, you’ll be able to select one or more target fields which will be updated on each selected value for that field, back to the item being updated. This is a powerful and complicated feature. As such, it requires some thought about the connections you wish to make between fields across different item types. Here are some examples:

A Relationship field displayed on the `wc_product` post type called “Related Products”. Enabling bidirectional, and setting the `Target Field` to the same field (“This Field”) will automatically add the `wc_product` Post ID being edited to the related products field on each of the selected values for related products.
A user field displayed on a post type “Business Sectors”, where the user selected indicates who to contact about that business sector. If you enable bidirectional and set the `Target Field` to a relationship field output on a user, updating the business sector will automatically get all sectors they are responsible for on their author page.

The main complexity with bidirectional fields lies in determining where a field will be displayed in the edit screens. ACF supports showing the same field across multiple places, such as posts, users, taxonomies, option pages, blocks, etc., so the “item ID” being updated will vary depending on where it’s currently being displayed. This is usually a post ID, but could be a user ID or taxonomy term ID. However, you can’t save a user ID to a Post Object field, so the `Target Field` for a field displayed on a user profile must be a User field to be updated.

Bidirectional enabled fields will therefore only update their targets when they’re displayed on a Post, User, or Taxonomy, and not on options pages, blocks, widgets, or any other location type which doesn’t resolve to a post ID, user ID, or taxonomy term ID. Whenever ACF tries to update a `Target Field` it will ensure the item type being updated is compatible with the target field type. If not, it will skip the update.

You also can’t chain bidirectional updates; only the selected `Target Fields` will be updated with the currently editing item ID. If the `Target Field` also has bidirectionality enabled, it will not be updated past the original target field.

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#known-issues)

## Known Issues

Link copied

The bidirectional setting will currently only enable one-way syncing of the data to the target field, and not configure any reverse bidirectionality (unless you select `This Field` as the `Target Field`). If you wish to enable two-way syncing of data between two different fields, you’ll need to enable the bidirectional setting on the `Target Field` field as well, and set its target back to the original field.

Bidirectional fields currently only support `Target Fields` which are top level fields, and not fields contained within any other type of field, including Group fields.

Currently, while you can select a field which only allows single values, or a limited number of values, this is not respected when the field is being updated from a bidirectional origin field. This means, for example, if you’re trying to make a one-to-many relationship from a “User” field on a post, and more than one User references that post, it will not automatically be removed from the other User which previously had it selected, until you manually save the Post. This should not cause any display or templating errors, as the fields which are set to singular values will only return one value inside `get_field`, but may lead to confusion in the UI.

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#legacy-code-implementation)

## Legacy Code Implementation

Link copied

Previous to ACF 6.2 the only way to create a bidirectional relationship was with code.

[View code](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#)

The following snippet adds a function to hook into the acf/update\_value filter (run before a value is saved). It will update the custom field value of each selected post to include the current post’s ID as well as removing the current post’s ID from previously selected posts (which are no longer selected).

This function does not contain any hard-coded field names so it will work with any relationship field. The only change required is within the add\_filter() parameter. It contains the name of the relationship field which in the example below is called ‘related\_posts’.

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#functionsphp)

#### functions.php

Link copied

```php
function bidirectional_acf_update_value( $value, $post_id, $field  ) {

    // vars
    $field_name = $field['name'];
    $field_key = $field['key'];
    $global_name = 'is_updating_' . $field_name;


    // bail early if this filter was triggered from the update_field() function called within the loop below
    // - this prevents an infinite loop
    if( !empty($GLOBALS[ $global_name ]) ) return $value;


    // set global variable to avoid infinite loop
    // - could also remove_filter() then add_filter() again, but this is simpler
    $GLOBALS[ $global_name ] = 1;


    // loop over selected posts and add this $post_id
    if( is_array($value) ) {

        foreach( $value as $post_id2 ) {

            // load existing related posts
            $value2 = get_field($field_name, $post_id2, false);


            // allow for selected posts to not contain a value
            if( empty($value2) ) {

                $value2 = array();

            }


            // bail early if the current $post_id is already found in selected post's $value2
            if( in_array($post_id, $value2) ) continue;


            // append the current $post_id to the selected post's 'related_posts' value
            $value2[] = $post_id;


            // update the selected post's value (use field's key for performance)
            update_field($field_key, $value2, $post_id2);

        }

    }


    // find posts which have been removed
    $old_value = get_field($field_name, $post_id, false);

    if( is_array($old_value) ) {

        foreach( $old_value as $post_id2 ) {

            // bail early if this value has not been removed
            if( is_array($value) && in_array($post_id2, $value) ) continue;


            // load existing related posts
            $value2 = get_field($field_name, $post_id2, false);


            // bail early if no value
            if( empty($value2) ) continue;


            // find the position of $post_id within $value2 so we can remove it
            $pos = array_search($post_id, $value2);


            // remove
            unset( $value2[ $pos] );


            // update the un-selected post's value (use field's key for performance)
            update_field($field_key, $value2, $post_id2);

        }

    }


    // reset global varibale to allow this filter to function as per normal
    $GLOBALS[ $global_name ] = 0;


    // return
    return $value;

}

add_filter('acf/update_value/name=related_posts', 'bidirectional_acf_update_value', 10, 3);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#related)

## Related

Link copied

- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)
- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)

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

[Got it](https://www.advancedcustomfields.com/resources/bidirectional-relationships/#)