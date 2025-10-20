---
url: https://www.advancedcustomfields.com/resources/get-values-comment
scraped_at: 2025-10-20T02:16:27.641Z
---

# How to get values from a comment

Last updated Mar 16, 2015

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#overview)

## Overview

Link copied

To display custom field values within comments, you will need to setup a custom callback function for the `wp_list_comments()` function. This is well explained in an article [Creating a custom comment list](http://blog.josemcastaneda.com/2013/05/29/custom-comment/).

All template functions can be used with a comment, however, a second parameter is required to target the specific comment. This is similar to passing through a `$post_id` value to target a specific post object.

The second parameter can be given in either of 2 formats:

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#comment-object)

### Comment Object

Link copied

The comment object can be passed as the `$post_id` parameter. This is the most simple way to load a value from a comment object. You will be passed a comment object when using a custom callback for the `wp_list_comments()` function.

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#comment-string)

### Comment String

Link copied

The comment string can be passed as the `$post_id` parameter and is constructed from the comment’s ID. In code, this looks like `"comment_{$comment->comment_ID}"` ``

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#examples)

## Requirements

Link copied

Custom fields for comments requires at least ACF version 5

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#basic-parameter-use)

### Basic parameter use

Link copied

This example shows how the second parameter is used to target the specific comment.

```php
<p><?php the_field('field_name', $comment); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#custom-comment-list)

### Custom comment list

Link copied

This example shows how to create a custom comment list callback and display some custom fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#singlephp)

#### single.php

Link copied

```php
<?php comments_template(); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#commentsphp)

#### comments.php

Link copied

```php
<?php

wp_list_comments(array(
    'callback'    => 'my_comment_template'
));

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#functionsphp)

#### functions.php

Link copied

```php
<?php

function my_comment_template( $comment, $args, $depth ) {

    ?>
    <div class="comment">

        <?php if( get_field('upload_image', $comment) ): ?>

            <img src="<?php the_field('image', $comment); ?>" />

        <?php endif; ?>

    </div>

    <?php
}

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-comment/#related)

## Related

Link copied

- Guides: [Get values from a widget](https://www.advancedcustomfields.com/resources/get-values-widget/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from an options page](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/)
- Guides: [Get values from another post](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)

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

[Got it](https://www.advancedcustomfields.com/resources/get-values-comment/#)