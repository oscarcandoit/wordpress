---
url: https://www.advancedcustomfields.com/resources/get-values-widget
scraped_at: 2025-10-20T02:16:36.957Z
---

# Get values from a widget

Last updated Mar 25, 2015

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#overview)

## Overview

Link copied

All the template functions ( [get\_field](https://www.advancedcustomfields.com/resources/get_field/ "get_field()"), [the\_field](https://www.advancedcustomfields.com/resources/the_field/ "the_field()"), [etc](https://www.advancedcustomfields.com/resources/#functions)) can be used to load values from a widget, however, a second parameter is required to target the term. This is similar to passing through a `$post_id` parameter to target a specific post object.

The `$post_id` parameter needed is a string containing the the word ‘widget\_’ and the widget’s ID in the following format; `"widget_{$widget_id}"`

To display custom field values within a widget, you will need to use a filter to modify the HTML arguments. If the widget is custom made, you can also customize the HTML output within the `widget` function in your widget class.

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#examples)

## Requirements

Link copied

Custom fields for comments requires at least ACF version 5

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#basic-parameter-use)

### Basic parameter use

Link copied

This example shows how the second parameter is used to target the specific comment.

```php
<p><?php the_field('field_name', 'widget_' . $widget_id); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#basic-widget-customization)

### Basic widget customization

Link copied

This example shows how to customize the ‘Text’ widget to display with a background color and show an image. Because widgets do not yet contain actions or callbacks to add extra HTML, we must use a filter ( `dynamic_sidebar_params`) to modify the `before_widget` and `after_widget` HTML.

The following code is placed in the functions.php file.

```php
add_filter('dynamic_sidebar_params', 'my_dynamic_sidebar_params');

function my_dynamic_sidebar_params( $params ) {

    // get widget vars
    $widget_name = $params[0]['widget_name'];
    $widget_id = $params[0]['widget_id'];


    // bail early if this widget is not a Text widget
    if( $widget_name != 'Text' ) {

        return $params;

    }


    // add color style to before_widget
    $color = get_field('color', 'widget_' . $widget_id);

    if( $color ) {

        $params[0]['before_widget'] .= '<style type="text/css">';
        $params[0]['before_widget'] .= sprintf('#%s { background-color: %s; }', $widget_id, $color);
        $params[0]['before_widget'] .= '</style>';

    }


    // add image to after_widget
    $image = get_field('image', 'widget_' . $widget_id);

    if( $image ) {

        $params[0]['after_widget'] = '<img src="' . $image['url'] . '">' . $params[0]['after_widget'];
    }


    // return
    return $params;

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-widget/#related)

## Related

Link copied

- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from an options page](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/)
- Guides: [How to get values from a comment](https://www.advancedcustomfields.com/resources/get-values-comment/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Guides: [Adding fields to Media Attachments](https://www.advancedcustomfields.com/resources/adding-fields-media-attachments/)

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

[Got it](https://www.advancedcustomfields.com/resources/get-values-widget/#)