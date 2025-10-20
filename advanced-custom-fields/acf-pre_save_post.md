---
url: https://www.advancedcustomfields.com/resources/acf-pre_save_post
scraped_at: 2025-10-20T02:30:02.622Z
---

# acf/pre\_save\_post

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#description)

## Description

Link copied

This filter allows you to modify the $post\_id before any custom field data is saved from the front end form ( [acf\_form()](https://www.advancedcustomfields.com/resources/creating-a-front-end-form/ "Creating a front end form")). This filter is used in the tutorial [Using acf\_form to create a new post](https://www.advancedcustomfields.com/resources/using-acf_form-to-create-a-new-post/ "Using acf_form to create a new post").

This filter is not required to create a new post due to the `new_post` argument added to [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/ "acf_form()") in v5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#changelog)

## Changelog

Link copied

- Added in v4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#parameters)

## Parameters

Link copied

| Name | Type | Description |
| --- | --- | --- |
| `post_id` | int | The post ID to which all the $\_POST data (values) will be saved to |

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#usage)

## Usage

Link copied

This code could be used in the functions.php file, or on the page template which features the front end form (above the acf\_form\_head function)

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#functionsphp)

#### functions.php

Link copied

```php
<?php

function my_pre_save_post( $post_id ) {

    // check if this is to be a new post
    if( $post_id != 'new' ) {

        return $post_id;

    }

    // Create a new post
    $post = array(
        'post_status'  => 'draft' ,
        'post_title'  => 'A title, maybe a $_POST variable' ,
        'post_type'  => 'post' ,
    );

    // insert the post
    $post_id = wp_insert_post( $post );

    // return the new ID
    return $post_id;

}

add_filter('acf/pre_save_post' , 'my_pre_save_post', 10, 1 );

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#related)

## Related

Link copied

- Functions: [acf\_form\_head()](https://www.advancedcustomfields.com/resources/acf_form_head/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-pre_save_post/#)