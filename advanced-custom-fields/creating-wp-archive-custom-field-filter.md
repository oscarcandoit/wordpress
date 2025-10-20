---
url: https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter
scraped_at: 2025-10-20T02:24:06.058Z
---

# Creating a WP archive with custom field filter

Last updated Nov 18, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#overview)

## Overview

Link copied

This video tutorial will cover the basics of creating a WP archive that displays posts filtered by a checkbox custom field. Please watch the video first, and use the code below to kick start your project!

![](https://fast.wistia.com/embed/medias/agkbpna1ef/swatch)

![Video Thumbnail](https://fast.wistia.com/embed/medias/agkbpna1ef/swatch)

![Video Thumbnail](https://embed-ssl.wistia.com/deliveries/b15165169579832ce2f31df12cac93f803a4bca1.webp?image_crop_resized=1280x720)

Click for sound

11:50

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#usage)

## Usage

Link copied

This snippet of code is placed within the functions.php file and modifies the WP\_Query args based on the available `$_GET` params.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#functionsphp)

#### functions.php

Link copied

```php
// array of filters (field key => field name)
$GLOBALS['my_query_filters'] = array(
    'field_1'   => 'city',
    'field_2'   => 'bedrooms'
);

// action
add_action('pre_get_posts', 'my_pre_get_posts', 10, 1);

function my_pre_get_posts( $query ) {

    // bail early if is in admin
    if( is_admin() ) return;


    // bail early if not main query
    // - allows custom code / plugins to continue working
    if( !$query->is_main_query() ) return;


    // get meta query
    $meta_query = $query->get('meta_query');


    // loop over filters
    foreach( $GLOBALS['my_query_filters'] as $key => $name ) {

        // continue if not found in url
        if( empty($_GET[ $name ]) ) {

            continue;

        }


        // get the value for this filter
        // eg: http://www.website.com/events?city=melbourne,sydney
        $value = explode(',', $_GET[ $name ]);


        // append meta query
        $meta_query[] = array(
            'key'       => $name,
            'value'     => $value,
            'compare'   => 'IN',
        );

    }


    // update meta query
    $query->set('meta_query', $meta_query);

}
```

This snippet of code is used within a template file that is shown on the archive page for your post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#archive-propertyphp)

#### archive-property.php

Link copied

```php
<div id="archive-filters">
<?php foreach( $GLOBALS['my_query_filters'] as $key => $name ):

    // get the field's settings without attempting to load a value
    $field = get_field_object($key, false, false);


    // set value if available
    if( isset($_GET[ $name ]) ) {

        $field['value'] = explode(',', $_GET[ $name ]);

    }


    // create filter
    ?>
    <div class="filter" data-filter="<?php echo $name; ?>">
        <?php create_field( $field ); ?>
    </div>

<?php endforeach; ?>
</div>

<script type="text/javascript">
(function($) {

    // change
    $('#archive-filters').on('change', 'input[type="checkbox"]', function(){

        // vars
        var url = '<?php echo home_url('property'); ?>';
            args = {};


        // loop over filters
        $('#archive-filters .filter').each(function(){

            // vars
            var filter = $(this).data('filter'),
                vals = [];


            // find checked inputs
            $(this).find('input:checked').each(function(){

                vals.push( $(this).val() );

            });


            // append to args
            args[ filter ] = vals.join(',');

        });


        // update url
        url += '?';


        // loop over args
        $.each(args, function( name, value ){

            url += name + '=' + value + '&';

        });


        // remove last &
        url = url.slice(0, -1);


        // reload page
        window.location.replace( url );


    });

})(jQuery);
</script>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#related)

## Related

Link copied

- Guides: [Order posts by custom fields](https://www.advancedcustomfields.com/resources/order-posts-by-custom-fields/)
- Guides: [How to Query Posts by Custom Fields](https://www.advancedcustomfields.com/resources/query-posts-custom-fields/)
- Basic: [acf\_get\_field\_groups()](https://www.advancedcustomfields.com/resources/acf_get_field_groups/)
- Filters: [acf/fields/post\_object/query](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/)
- Guides: [Querying relationship fields](https://www.advancedcustomfields.com/resources/querying-relationship-fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/creating-wp-archive-custom-field-filter/#)