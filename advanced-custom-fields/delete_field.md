---
url: https://www.advancedcustomfields.com/resources/delete_field
scraped_at: 2025-10-20T02:22:10.343Z
---

# delete\_field()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#description)

## Description

Link copied

Deletes the value of a specific field.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#parameters)

## Parameters

Link copied

```php
delete_field($selector, [$post_id]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#return)

## Return

Link copied

_(bool)_ True on successful delete, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#delete-via-field-name)

### Delete via field name

Link copied

This example shows how to delete the value of a field called ‘test’ on the current post being viewed.

```php
// Delete value.
delete_field('test');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#delete-via-field-key)

### Delete via field key

Link copied

This example shows how to achieve the same as above using the field’s key instead of its name.

```php
// Delete value.
delete_field('field_123456');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#delete-a-value-from-different-objects)

### Delete a value from different objects

Link copied

This example shows a variety of **$post\_id** values to delete a value from a post, user, term and option.

```php
$post_id = false; // current post
$post_id = 1; // post ID = 1
$post_id = "user_2"; // user ID = 2
$post_id = "category_3"; // category term ID = 3
$post_id = "event_4"; // event (custom taxonomy) term ID = 4
$post_id = "option"; // options page
$post_id = "options"; // same as above

delete_field( 'my_field', $post_id );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#delete-from-multiple-posts)

### Delete from multiple posts

Link copied

This example shows how load all posts that contain a custom field (called ‘color’) and then delete those values from each post. Note that the foreach loop uses a variable called $p instead of $post to avoid any collisions with the global $post object.

```php
// Query posts.
$posts = get_posts(array(
    'post_type'         => 'post',
    'posts_per_page'    => -1,
    'meta_key'          => 'color'
));

// Loop over results and delete.
if( $posts ) {
    foreach( $posts as $p ) {
        delete_field('color', $p->ID);
    }
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_field/#related)

## Related

Link copied

- Functions: [update\_field()](https://www.advancedcustomfields.com/resources/update_field/)
- Functions: [delete\_row()](https://www.advancedcustomfields.com/resources/delete_row/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)

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

[Got it](https://www.advancedcustomfields.com/resources/delete_field/#)