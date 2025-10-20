---
url: https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields
scraped_at: 2025-10-20T02:17:37.311Z
---

# Adding custom javascript to fields

Last updated Aug 4, 2018

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#overview)

## Overview

Link copied

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

✋ We’ve launched a new JavaScript API full of powerful functions, actions and filters! If you are using ACF 5.7 or above, please checkout our [JavaScript API](https://www.advancedcustomfields.com/resources/javascript-api/).

This article will cover how to add custom JS to interact with and modify ACF fields and settings. Similar to the many WordPress actions and filters available in PHP, ACF adopts a similar model for it’s Javascript.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#getting-started)

## Getting Started

Link copied

There are two methods to add custom javascript to the WordPress dashboard; include a script file or append an inline script. It is recommended that you include a JS file if you intend to write lots of functionality.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#include)

### Include

Link copied

To include a JS file within the dashboard, you can make use of the wp\_enqueue\_script function like so.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#functionsphp)

#### functions.php

Link copied

```php
function my_admin_enqueue_scripts() {

    wp_enqueue_script( 'my-admin-js', get_template_directory_uri() . '/js/example.js', array(), '1.0.0', true );

}

add_action('acf/input/admin_enqueue_scripts', 'my_admin_enqueue_scripts');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#inline)

### Inline

Link copied

To append inline JS within the dashboard, you can make use of the `acf/input/admin_footer` action. This action is run in the footer of any admin page where ACF fields may exist.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#functionsphp)

#### functions.php

Link copied

```php
function my_acf_input_admin_footer() {

?>
<script type="text/javascript">
(function($) {

    // JS here

})(jQuery);
</script>
<?php

}

add_action('acf/input/admin_footer', 'my_acf_input_admin_footer');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#actions)

## Actions

Link copied

Below is a list of all available JS actions. Hooking into an action is made possible by a JS function called `add_action` on the `acf` object. If you are using the **ready** action, it is a good idea to also hook into the **append** action with the same functionality.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#ready)

### Ready

Link copied

Called when the document is ready once the page has initially loaded.

```js
acf.add_action('ready', function( $el ){

    // $el will be equivalent to $('body')


    // find a specific field
    var $field = $('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `ready_field` and `ready_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#append)

### Append

Link copied

Called when new HTML is appended to the page. This occurs when adding a new repeater row, adding a new flexible content layout and when new field groups are loaded via AJAX. If you are using the append action, it is a good idea to also hook into this action with the same functionality.

```js
acf.add_action('append', function( $el ){

    // $el will be equivalent to the new element being appended $('tr.row')


    // find a specific field
    var $field = $el.find('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `append_field` and `append_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#load)

### Load

Link copied

Called when the window has loaded all assets. This action is desired over ‘ready’ when the width and height if an image is needed for logic.

```js
acf.add_action('load', function( $el ){

    // $el will be equivalent to $('body')


    // find a specific field
    var $field = $el.find('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `load_field` and `load_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#remove)

### Remove

Link copied

Called when HTML is removed from the page. This occurs when removing a repeater row or removing a flexible content layout.

```js
acf.add_action('remove', function( $el ){

    // $el will be equivalent to the new element being removed $('tr.row')


    // find a specific field
    var $field = $el.find('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `remove_field` and `remove_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#sortstart)

### sortstart

Link copied

Called when HTML has begun to move around the page via drag/drop. This occurs when reordering a repeater row or reordering a flexible content layout.

```js
acf.add_action('sortstart', function( $el ){

    // $el will be equivalent to the new element being moved $('tr.row')


    // find a specific field
    var $field = $el.find('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `sortstart_field` and `sortstart_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#sortstop)

### sortstop

Link copied

Called when HTML has finished being moved around the page via drag/drop. This occurs when reordering a repeater row or reordering a flexible content layout.

```js
acf.add_action('sortstop', function( $el ){

    // $el will be equivalent to the new element being moved $('tr.row')


    // find a specific field
    var $field = $el.find('#my-wrapper-id');


    // do something to $field

});
```

This action also fires on each field via the actions `sortstop_field` and `sortstop_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#hidefield)

### hide\_field

Link copied

Called when a field has been hidden via either a tab or by conditional logic.

```js
acf.add_action('hide_field', function( $field, context ){

    // context is a string of either 'tab' or 'conditional_logic'

    // do something to $field

});
```

This action also fires on a field specific basis `hide_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#showfield)

### show\_field

Link copied

Called when a field has been shown via either a tab or by conditional logic.

```js
acf.add_action('show_field', function( $field, context ){

    // context is a string of either 'tab' or 'conditional_logic'

    // do something to $field

});
```

This action also fires on a field specific basis `show_field/type={$field_type}`.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#datepickerinit)

### date\_picker\_init

Link copied

Called when a date picker has been initialized. Added in v5.5.8

```js
acf.add_action('date_picker_init', function( $input, args, $field ){

    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#datetimepickerinit)

### date\_time\_picker\_init

Link copied

Called when a date time picker has been initialized. Added in v5.5.8

```js
acf.add_action('date_time_picker_init', function( $input, args, $field ){

    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#timepickerinit)

### time\_picker\_init

Link copied

Called when a time picker has been initialized. Added in v5.5.8

```js
acf.add_action('time_picker_init', function( $input, args, $field ){

    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#select2init)

### select2\_init

Link copied

Called when a Select2 element has been initialized. By default, ACF includes the Select2 v3 library which requires a hidden input to be used for Select2 initialization. It is possible to include the Select2 v4 library, and if so, the $input arg will supply a ‘select’ element instead of a hidden input due to changes in the library. Added in v5.5.8

```js
acf.add_action('select2_init', function( $input, args, settings, $field ){

    // $input (jQuery) hidden input element
    // args (object) args given to the select2 function
    // settings (object) settings given to the acf.select2 function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#wysiwygtinymceinit)

### wysiwyg\_tinymce\_init

Link copied

Called when a WYSIWYG tinymce element has been initialized. Added in v5.5.8

```js
acf.add_action('wysiwyg_tinymce_init', function( ed, id, mceInit, $field ){

    // ed (object) tinymce object returned by the init function
    // id (string) identifier for the tinymce instance
    // mceInit (object) args given to the tinymce function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#wysiwygquicktagsinit)

### wysiwyg\_quicktags\_init

Link copied

Called when a WYSIWYG quickktags element has been initialized. Each tinymce instance can also contain a ‘text’ edit mode that shows basic ‘quicktag’ buttons. Added in v5.5.8

```js
acf.add_action('wysiwyg_quicktags_init', function( qtag, id, qtInit, $field ){

    // qtag (object) quick tag object returned by the init function
    // id (string) identifier for the qtag instance
    // qtInit (object) args given to the quick tag function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#googlemapinit)

### google\_map\_init

Link copied

Called when a Google Map element has been initialized. Added in v5.5.11

```js
acf.add_action('google_map_init', function( map, marker, $field ){

    // map (object) google map object returned by the google.maps.Map() function
    // marker (object) marker object returned by the google.maps.Marker() function
    // $field (jQuery) field element

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#filters)

## Filters

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#validationcomplete)

### validation\_complete

Link copied

This filter allows the validation JSON response to be customized. Called after AJAX validation is complete but before errors are shown or the form is submitted.

```js
acf.add_filter('validation_complete', function( json, $form ){

    // if errors?
    if( json.errors ) {



    }


    // return
    return json;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#wysiwygtinymcesettings)

### wysiwyg\_tinymce\_settings

Link copied

This filter allows the tinyMCE settings to be customized for each WYSIWYG field. Called before the tinyMCE instance is created.

```js
acf.add_filter('wysiwyg_tinymce_settings', function( mceInit, id, $field ){

    // do something to mceInit


    // return
    return mceInit;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#wysiwygquicktagssettings)

### wysiwyg\_quicktags\_settings

Link copied

This filter allows the quicktags settings to be customized for each WYSIWYG field. Called before the text instance is created.

```js
acf.add_filter('wysiwyg_quicktags_settings', function( qtInit, id, $field ){

    // do something to qtInit


    // return
    return qtInit;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#datepickerargs)

### date\_picker\_args

Link copied

This filter allows the date picker settings to be customized for each date picker field. Called before the date picker instance is created. A full list of settings can be found here: [https://api.jqueryui.com/datepicker/](https://api.jqueryui.com/datepicker/)

```js
acf.add_filter('date_picker_args', function( args, $field ){

    // do something to args


    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#datetimepickerargs)

### date\_time\_picker\_args

Link copied

This filter allows the date time picker settings to be customized for each date time picker field. Called before the date time picker instance is created. A full list of settings can be found here: [http://trentrichardson.com/examples/timepicker/](http://trentrichardson.com/examples/timepicker/)

```js
acf.add_filter('date_time_picker_args', function( args, $field ){

    // do something to args


    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#timepickerargs)

### time\_picker\_args

Link copied

This filter allows the time picker settings to be customized for each time picker field. Called before the time picker instance is created. A full list of settings can be found here: [http://trentrichardson.com/examples/timepicker/](http://trentrichardson.com/examples/timepicker/)

```js
acf.add_filter('time_picker_args', function( args, $field ){

    // do something to args


    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#googlemapargs)

### google\_map\_args

Link copied

This filter allows the google maps settings to be customized for each googe maps field. Called before the map instance is created.

```js
acf.add_filter('google_map_args', function( args, $field ){

    // do something to args


    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#select2args)

### select2\_args

Link copied

This filter allows the select2 settings to be customized for each select field. Called before the select2 instance is created.

```js
acf.add_filter('select2_args', function( args, $select, settings, $field ){

    // do something to args


    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#select2ajaxdata)

### select2\_ajax\_data

Link copied

This filter allows the data sent in an ajax request to be customized for each select field. Called before the select2 ajax request is created.

```js
acf.add_filter('select2_ajax_data', function( data, args, $input, $field ){

    // do something to data


    // return
    return data;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#colorpickerargs)

### color\_picker\_args

Link copied

This filter allows the color picker (wpColorPicker) settings to be customized for each color picker field. This filter is called before the wpColorPicker instance is created. Added in v 5.3.6

```js
acf.add_filter('color_picker_args', function( args, $field ){

    // do something to args
    args.palettes = ['#5ee8bf', '#2f353e', '#f55e4f']


    // return
    return args;

});
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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#related)

## Related

Link copied

- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)
- Guides: [JavaScript API](https://www.advancedcustomfields.com/resources/javascript-api/)
- Actions: [acf/input/admin\_enqueue\_scripts](https://www.advancedcustomfields.com/resources/acf-input-admin_enqueue_scripts/)
- Actions: [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/acf-input-admin_head/)
- Guides: [Moving WP elements (such as the content editor) within ACF fields](https://www.advancedcustomfields.com/resources/moving-wp-elements-content-editor-within-acf-fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/#)