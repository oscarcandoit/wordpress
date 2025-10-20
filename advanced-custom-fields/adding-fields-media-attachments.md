---
url: https://www.advancedcustomfields.com/resources/adding-fields-media-attachments
scraped_at: 2025-10-20T02:17:16.647Z
---

# Adding fields to Media Attachments

Last updated Jul 8, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#overview)

## Overview

Link copied

This guide will demonstrate how to add custom fields to a WordPress Attachment and how to then display these fields.

All the template functions ( [get\_field()](https://www.advancedcustomfields.com/resources/get_field/ "get_field()"), [the\_field()](https://www.advancedcustomfields.com/resources/the_field/ "the_field()"), etc) can be used to load values from a media attachment, however, a second parameter is required to target the attachment.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#changelog)

## Changelog

Link copied

- Added attachment types to location rule in version 5.6.0

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#adding-fields)

## Adding fields

Link copied

The Advanced Custom Fields plugin makes it very easy to add custom fields to an Attachment, please follow the steps below.

1. From the **Custom Fields** admin screen, click the **Add New** button to create a new field group
2. Add the fields you would like to see when editing an Attachment
3. Under **Locations**, select the **Attachment** rule and choose ‘All’ (to show this field group on all attachments) or a specific attachment type (to show this field group only for specific attachments)

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-field-group.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-field-group.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#editing-fields)

## Editing fields

Link copied

Once you have created a field group and assigned it to appear for an Attachment edit screen, editing the field values is done by one of the following:

- Navigating to the **Media > Library** admin page and selecting an attachment.
- Using the **Add Media** button when editing a post’s content.
- Using an ACF [image field](https://www.advancedcustomfields.com/resources/image/) or [file field](https://www.advancedcustomfields.com/resources/file/) to select an attachment.

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

WP stores each Attachment as a post object in the `wp_posts` table. ACF will store all custom field values in the `wp_postmeta` table.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-edit.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-edit.jpg)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#displaying-fields)

## Displaying fields

Link copied

Customizing the HTML for a WordPress Attachment will differ depending on the context. Attachments are used in many ways by different themes. The following example uses a [file field](https://www.advancedcustomfields.com/resources/file/) (from a post edit screen) to select an Attachment. The selected Attachment (.pdf) has been assigned a ‘Thumbnail’ which is displayed with the file info below.

Note how the Attachment ID is used to load the field value from the selected Attachment.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#singlephp)

#### single.php

Link copied

```php
<?php

// load selected file (from post)
$file = get_field('file');

if( $file ):

    // load selected thumbnail (from attachment)
    $thumbnail = get_field('thumbnail', $file['ID']);

    ?>
    <h2>Read more</h2>
    <div class="file">
        <a href="<?php echo $file['url']; ?>">
            <?php if( $thumbnail ): ?>
                <img class="thumbnail" src="<?php echo $thumbnail['url']; ?>" alt="<?php echo $thumbnail['alt']; ?>" />
            <?php endif; ?>
            <span><?php echo $file['filename']; ?></span>
        </a>
    </div>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#result)

### Result

Link copied

Here is an example of the above code in action. Note the `<img>` tag created with the Attachment’s **Thumbnail** value **.**

[![](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-display.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/03/acf-adding-fields-to-attachments-display.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#display-a-field)

### Display a field

Link copied

This example will display a field value from an Attachment (attachment ID = 12)

```php
<p><?php the_field('field_name', 12); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#retrieve-a-field)

### Retrieve a field

Link copied

This example will load a field value from an Attachment (attachment ID = 12)

```php
<?php

$variable = get_field('field_name', 12);

// do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#retrieve-from-another-image-custom-field)

### Retrieve from another image custom field

Link copied

This example will show how to load a selected image from a custom field, and then load a custom field from that image.

```php
<?php

// get an image field
$image = get_field('image');

// each image contains a custom field called 'link'
$link = get_field('link', $image['ID']);

// render
?>
<a href="<?php echo $link; ?>">
    <img src="<?php echo $image['url']; ?>" alt="<?php echo $image['alt']; ?>" />
</a>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#working-with-the-repeater-field)

### Working with the Repeater Field

Link copied

This example will show how to loop over an attachment field’s repeater field value (attachment ID = 123).

Note that when inside of a `have_rows` loop, you do not need to use the `$post_id` parameter for any sub field functions ( [get\_sub\_field()](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()"), [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()"))

```php
<?php if( have_rows('repeater', 123) ): ?>

    <ul>

    <?php while( have_rows('repeater', 123) ): the_row(); ?>

        <li><?php the_sub_field('title'); ?></li>

    <?php endwhile; ?>

    </ul>

<?php endif; ?>
```

Save

Save

Save

Save

Save

Save

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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#related)

## Related

Link copied

- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Adding fields to Menu Items](https://www.advancedcustomfields.com/resources/adding-fields-menu-items/)
- Guides: [Adding fields to Menus](https://www.advancedcustomfields.com/resources/adding-fields-menus/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)

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

[Got it](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/#)