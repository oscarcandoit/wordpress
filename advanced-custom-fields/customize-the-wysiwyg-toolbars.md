---
url: https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars
scraped_at: 2025-10-20T02:16:22.318Z
---

# Customize the WYSIWYG toolbars

Last updated May 16, 2014

[Link to heading#](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#description)

## Description

Link copied

The WYSIWYG field contains an option to define the toolbar (buttons) which are rendered onto the tinyMCE object.

By default, you can select ‘Full’ or ‘Basic’, however, it is possible to extend these toolbars to create your own, edit existing and even remove the existing choices.

[Link to heading#](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#requirements)

## Requirements

Link copied

- ACF version 3.5.8 or above

[Link to heading#](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#the-filter)

## The Filter

Link copied

The filter to modify the toolbars is: **acf/fields/wysiwyg/toolbars**

The WYSIWYG field uses an array (which can be modified as shown below) to hold a list of toolbars. Each toolbar comprises of a name and up to 4 rows of buttons. With this filter, you can add, edit and remove toolbars. This filter allows you to modify this very array.

Once a new toolbar is added to the list, it will then appear in the WYSIWYG field’s options when editing the field group. Once selected, the field will use the available rows to output the desired buttons

[Link to heading#](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#usage)

## Usage

Link copied

```php
<?php

add_filter( 'acf/fields/wysiwyg/toolbars' , 'my_toolbars'  );
function my_toolbars( $toolbars )
{
    // Uncomment to view format of $toolbars
    /*
    echo '< pre >';
        print_r($toolbars);
    echo '< /pre >';
    die;
    */

    // Add a new toolbar called "Very Simple"
    // - this toolbar has only 1 row of buttons
    $toolbars['Very Simple' ] = array();
    $toolbars['Very Simple' ][1] = array('bold' , 'italic' , 'underline' );

    // Edit the "Full" toolbar and remove 'code'
    // - delet from array code from http://stackoverflow.com/questions/7225070/php-array-delete-by-value-not-key
    if( ($key = array_search('code' , $toolbars['Full' ][2])) !== false )
    {
        unset( $toolbars['Full' ][2][$key] );
    }

    // remove the 'Basic' toolbar completely
    unset( $toolbars['Basic' ] );

    // return $toolbars - IMPORTANT!
    return $toolbars;
}

?>
```

- Use this filter in your functions.php file

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

[Link to heading#](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#related)

## Related

Link copied

- Content: [Wysiwyg Editor](https://www.advancedcustomfields.com/resources/wysiwyg-editor/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Guides: [Dynamically Populate a Select Field’s Choices](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)

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

[Got it](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/#)