---
url: https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields
scraped_at: 2025-10-20T02:16:40.543Z
---

# Moving WP elements (such as the content editor) within ACF fields

Last updated Mar 31, 2015

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#overview)

## Overview

Link copied

This article will demonstrate a solution for moving core WordPress elements within ACF fields. This concept uses a message field as a blank placeholder into which the elements are moved via jQuery.

Here’s a look at what the interface can look like when moving the WP editor within a field group. On the left shows a normal edit page and on the right shows the WP editor moved within a field group and most importantly below a field called ‘Sub Title’.

[![](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-before.png)](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-before.png)

Before


[![](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-after.png)](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-after.png)

After


[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#instructions)

## Instructions

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#the-placeholder)

### The placeholder

Link copied

Assuming you have a field group already setup, go ahead and create a message field in the desired location and give it a label which will relate to the WP element(s) it will soon hold.

[![acf-moving-elements-field-group](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-field-group-700x622.png)](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-field-group.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#the-code)

### The code

Link copied

Custom CSS/JS can easily be added using the [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/acfinputadmin_head/ "acf/input/admin_head") action. The following will target the ACF placeholder field, and move the WP content editor ( `#postdivrich`) within it. There is also some style to remove a grey background from the element making it sit more naturally within the ACF field.

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/input/admin_head', 'my_acf_admin_head');

function my_acf_admin_head() {

    ?>
    <script type="text/javascript">
    (function($) {

        $(document).ready(function(){

            $('.acf-field-54cf2c4fcfbfe .acf-input').append( $('#postdivrich') );

        });

    })(jQuery);
    </script>
    <style type="text/css">
        .acf-field #wp-content-editor-tools {
            background: transparent;
            padding-top: 0;
        }
    </style>
    <?php

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#note)

### Note

Link copied

Please note that each field has a unique key and can be found by simply inspecting the field element on the page. Different versions of ACF (4 and 5) may reveal slightly different field classes, so please double check your jQuery selector is correct before using the code.

[![acf-moving-elements-selector](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-selector-700x540.png)](https://www.advancedcustomfields.com/wp-content/uploads/2015/02/acf-moving-elements-selector.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#conclusion)

## Conclusion

Link copied

The concept here is quite simple, but can be used in complex ways to create a more seamless content editing experience.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#related)

## Related

Link copied

- Guides: [Adding custom javascript to fields](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/)
- Actions: [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/acf-input-admin_head/)
- Actions: [acf/field\_group/admin\_head](https://www.advancedcustomfields.com/resources/acf-field_group-admin_head/)
- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)

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

[Got it](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/#)