---
url: https://www.advancedcustomfields.com/resources/javascript-api
scraped_at: 2025-10-20T02:29:03.042Z
---

# JavaScript API

Last updated Mar 21, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#introduction)

## Introduction

Link copied

Welcome to the Advanced Custom Fields JavaScript API. Here you will find documentation for our JavaScript library including functions, actions and filters and models.

Our library makes extensive use of jQuery and follows a similar style to [Backbone.js](http://backbonejs.org/#Getting-started). Before reading any further, make sure you are confident with [JavaScript basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics), [jQuery events](https://learn.jquery.com/events/event-basics/) and [WP hooks](https://www.smashingmagazine.com/2016/01/get-started-with-hooks-wordpress/).

Similar to other JS libraries, we place all of our JS goodies in a global object called **acf**. This makes it super easy to interact with ACF functionality, take a look for yourself.

```php
// get localized data
var postID = acf.get('post_id');

// add an action
acf.addAction('prepare', function(){
    // ...
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#accessing-the-acf-global)

## Accessing the ACF Global

Link copied

The `acf` global is registered by ACF when it enqueues the JS dependencies necessary for ACF to function. If you enqueue a script that uses ACF and get an `acf is not defined` error, it’s likely because your script is enqueued before ACF has had a chance to load.

You can avoid this issue by making sure that ACF has loaded the `acf-input` script. If you’re using [wp\_register\_script()](https://developer.wordpress.org/reference/functions/wp_register_script/) to load your javascript files, you can do this by adding the `acf-input` handle into the `$deps` array like so:

```php
wp_register_script( 'your-script-handle', $url, array( 'acf-input' ) );
```

You can then check if the `acf` global is available to your script with something like the following:

```php
jQuery( document ).ready( function( $ ) {
    if ( typeof acf !== 'undefined' ) {
        console.log( 'ACF is defined', acf );
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions)

## Functions

Link copied

The **acf** object contains many helpful functions some of which are documented below. For a full list of available functions, please inspect the **acf** object in your console log.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-get)

### get acf.get(name)

Link copied

Returns localized data for a given name. Localized data is registered in PHP and passed to JS through an inline script in the footer. You can register PHP data for localization by using the `acf_localize_data(array( 'foo' => 'bar' ));` function.

```php
var postID = acf.get('post_id');
var acfVersion = acf.get('acf_version');
var foo = acf.get('bar');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-set)

### set acf.set(name, value)

Link copied

Sets a value for later use with `acf.get()`. Returns the **acf** object for chaining.

```php
var value = 'bar';
acf.set('foo', value);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-has)

### has acf.has(name)

Link copied

Returns true if data exists for the given name.

```php
if( acf.has('foo') ) {
    // do something
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-parseargs)

### parseArgs acf.parseArgs(args, defaults)

Link copied

Similar to the WP function [wp\_parse\_args()](https://codex.wordpress.org/Function_Reference/wp_parse_args), this is a generic utility for merging together an object of arguments and an object of default values.

```php
// var maybeArgs = { ... }
var args = acf.parseArgs(maybeArgs, {
    foo:    'bar',
    html:   '',
});
// console.log( args.foo );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-__)

### \_\_ acf.\_\_(text)

Link copied

Returns the translation of text. If there is no translation, the original text is returned. Translation data is registered in PHP and passed to JS through an inline script in the head. You can register translations in PHP by using the `acf_localize_text()` function.

```php php
acf_localize_text(array(
    'Select thing' => __('Select thing', 'my-textdomain')
));
```

```js php
var text = acf.__('Select thing');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-addaction)

### addAction acf.addAction(action, callback, priority, context)

Link copied

Similar to the WP function [add\_action()](https://codex.wordpress.org/ko:Function_Reference/add_action), this is used to listen for a specific action and register a callback function.

```js php
acf.addAction('new_field', function( field ){
    field.$el.addClass('i-was-here');
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-addfilter)

### addFilter acf.addFilter(filter, callback, priority, context)

Link copied

Similar to the WP function [add\_filter()](https://codex.wordpress.org/ko:Function_Reference/add_filter), this is used to listen for a specific filter and register a callback function to modify the first argument.

```js php
acf.addFilter('select2_args', function( options, $select ){
    options.foo = 'bar';
    return options;
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-doaction)

### doAction acf.doAction(action, \[arg1, arg2, arg3, ...\])

Link copied

Similar to the WP function [do\_action()](https://codex.wordpress.org/ko:Function_Reference/do_action), this is used to trigger an action. Any callbacks registered for this action will be triggered.

```js php
acf.doAction('my_action', dataObject, someOtherVariable);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-applyfilters)

### applyFilters acf.applyFilters(filter, \[arg1, arg2, arg3, ...\])

Link copied

Similar to the WP function [apply\_filters()](https://codex.wordpress.org/ko:Function_Reference/apply_filters), this is used to apply a filter. Any callbacks registered for this filter will be called to modify the first argument.

```js php
var foo = acf.applyFilters('my_filter', 'bar');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-findfield)

### findField acf.findField( key )

Link copied

Returns a field jQuery object for a given field key.

```js php
var $field = acf.findField('field_123');
$field.addClass('my-class')
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-getfield)

### getField acf.getField( key )

Link copied

Returns a field instance for a given field key or jQuery element.

```js php
var field = acf.getField('field_123');
field.$el.addClass('my-class')
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-findfields)

### findFields acf.findFields( args )

Link copied

Returns a collection of jQuery objects for the given args.

```js php
// available args
var args = {
    key: '',                    // The field key (field_123)
    name: '',                   // The field name (my_field)
    type: '',                   // The field type (image, text)
    is: '',                     // jQuery selector (:visible)
    parent: false,              // jQuery element to search within
    sibling: false,             // jQuery element to search alongside
    limit: false,               // limit the number of jQuery elements returned
};

// example
var $fields = acf.findFields({
    type: 'image'
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#functions-getfields)

### getFields acf.getFields( args )

Link copied

Returns an array of field instances for the given args (see acf.findFields for list of args) or a collection of jQuery elements.

```js php
var fields = acf.getFields({
    type: 'image'
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions)

## Actions

Link copied

Actions are called at specific times during a page to allow for customisation. Below is a list of available JS actions somewhat in order of execution that you can hook into using the `acf.addAction()` function.

> ✋ If using the “pre 5.7” function **acf.add\_action()**, please be aware that any **field instance** parameter documented bellow will appear as a **jQuery element** for compatibility. This change is discussed in more detail later in the [Compatibility](https://www.advancedcustomfields.com/resources/javascript-api/#compatibility) section.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-prepare)

### prepare

Link copied

Triggered from an inline script in the footer allowing you to perform customisation to the page as early as possible (before the `$(document).ready` event).

```js php
acf.addAction('prepare', function(){
    $('#my-element').hide();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-ready)

### ready

Link copied

Triggered during the `$(document).ready()` event.

```js php
acf.addAction('ready', function(){
    $('#my-element').hide();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-load)

### load

Link copied

Triggered during the `$(window).load()` event.

```js php
acf.addAction('load', function(){
    $('#my-element').hide();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-resize)

### resize

Link copied

Triggered during the `$(window).resize()` event.

```js php
acf.addAction('resize', function(){
    $('#my-element').resizeWidth();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-unload)

### unload

Link copied

Triggered during the `$(window).unload()` event.

```js php
acf.addAction('unload', function(){
    $('#my-element').remove();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-append)

### append

Link copied

Triggered when new HTML is added to the page such as within a media modal popup. The jQuery element being appended is passed as a parameter.

```js php
acf.addAction('append', function( $el ){
    $el.find('.my-element').hide();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-remove)

### remove

Link copied

Triggered when HTML is removed from the page. For example, when removing a repeater row. The jQuery element being removed is passed as a parameter.

```js php
acf.addAction('remove', function( $el ){
    $el.find('.my-element').doThing();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-new_field)

### new\_field

Link copied

Triggered when a field is first initialised (either during “prepare” or “append”). This action is recommended over other ‘field’ actions if you wish to customize a field. This field action can also be targeted using a specific type, name or key.

```js php
var myCallback = function( field ){

    // add class to this field
    field.$el.addClass('my-class');

    // add click event to this field's button
    field.on('click', 'button', function( e ){
        e.preventDefault();
        alert('Special event');
    });
};

acf.addAction('new_field', myCallback);
acf.addAction('new_field/type=image', myCallback);          // image fields
acf.addAction('new_field/name=hero_image', myCallback);     // fields named "hero_image"
acf.addAction('new_field/key=field_123456', myCallback);    // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-prepare_field)

### prepare\_field

Link copied

Triggered during the “prepare” action for each field. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('prepare_field', myCallback);                     // all fields
acf.addAction('prepare_field/type=image', myCallback);          // image fields
acf.addAction('prepare_field/name=hero_image', myCallback);     // fields named "hero_image"
acf.addAction('prepare_field/key=field_123456', myCallback);    // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-ready_field)

### ready\_field

Link copied

Triggered during the “ready” action for each field. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('ready_field', myCallback);                   // all fields
acf.addAction('ready_field/type=image', myCallback);        // image fields
acf.addAction('ready_field/name=hero_image', myCallback);   // fields named "hero_image"
acf.addAction('ready_field/key=field_123456', myCallback);  // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-load_field)

### load\_field

Link copied

Triggered during the “load” action for each field. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('load_field', myCallback);                    // all fields
acf.addAction('load_field/type=image', myCallback);         // image fields
acf.addAction('load_field/name=hero_image', myCallback);    // fields named "hero_image"
acf.addAction('load_field/key=field_123456', myCallback);   // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-append_field)

### append\_field

Link copied

Triggered during the “append” action for each field. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('append_field', myCallback);                  // all fields
acf.addAction('append_field/type=image', myCallback);       // image fields
acf.addAction('append_field/name=hero_image', myCallback);  // fields named "hero_image"
acf.addAction('append_field/key=field_123456', myCallback); // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-remove_field)

### remove\_field

Link copied

Triggered when a field is removed. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('remove_field', myCallback);                  // all fields
acf.addAction('remove_field/type=image', myCallback);       // image fields
acf.addAction('remove_field/name=hero_image', myCallback);  // fields named "hero_image"
acf.addAction('remove_field/key=field_123456', myCallback); // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-hide_field)

### hide\_field

Link copied

Triggered when a field is hidden. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('hide_field', myCallback);                    // all fields
acf.addAction('hide_field/type=image', myCallback);         // image fields
acf.addAction('hide_field/name=hero_image', myCallback);    // fields named "hero_image"
acf.addAction('hide_field/key=field_123456', myCallback);   // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-show_field)

### show\_field

Link copied

Triggered when a hidden field is shown. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('show_field', myCallback);                    // all fields
acf.addAction('show_field/type=image', myCallback);         // image fields
acf.addAction('show_field/name=hero_image', myCallback);    // fields named "hero_image"
acf.addAction('show_field/key=field_123456', myCallback);   // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-disable_field)

### disable\_field

Link copied

Triggered when a field is disabled (conditional logic). This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('disable_field', myCallback);                     // all fields
acf.addAction('disable_field/type=image', myCallback);          // image fields
acf.addAction('disable_field/name=hero_image', myCallback);     // fields named "hero_image"
acf.addAction('disable_field/key=field_123456', myCallback);    // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-enable_field)

### enable\_field

Link copied

Triggered when a disabled field is enabled (conditional logic). This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('enable_field', myCallback);                      // all fields
acf.addAction('enable_field/type=image', myCallback);           // image fields
acf.addAction('enable_field/name=hero_image', myCallback);      // fields named "hero_image"
acf.addAction('enable_field/key=field_123456', myCallback); // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-invalid_field)

### invalid\_field

Link copied

Triggered when a field value fails validation. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('invalid_field', myCallback);                     // all fields
acf.addAction('invalid_field/type=image', myCallback);          // image fields
acf.addAction('invalid_field/name=hero_image', myCallback);     // fields named "hero_image"
acf.addAction('invalid_field/key=field_123456', myCallback);    // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-valid_field)

### valid\_field

Link copied

Triggered when an invalid field value passes validation. This field action can also be targeted using a specific type, name or key.

```js php
acf.addAction('valid_field', myCallback);                       // all fields
acf.addAction('valid_field/type=image', myCallback);            // image fields
acf.addAction('valid_field/name=hero_image', myCallback);       // fields named "hero_image"
acf.addAction('valid_field/key=field_123456', myCallback);  // field with key "field_123456"
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-date_picker_init)

### date\_picker\_init

Link copied

Called when a date picker has been initialized. Added in v5.5.8

```js php
acf.addAction('date_picker_init', function( $input, args, field ){
    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-date_time_picker_init)

### date\_time\_picker\_init

Link copied

Called when a date time picker has been initialized. Added in v5.5.8

```js php
acf.addAction('date_time_picker_init', function( $input, args, field ){
    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-time_picker_init)

### time\_picker\_init

Link copied

Called when a time picker has been initialized. Added in v5.5.8

```js php
acf.addAction('time_picker_init', function( $input, args, field ){
    // $input (jQuery) text input element
    // args (object) args given to the datepicker function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-select2_init)

### select2\_init

Link copied

Called when a Select2 element has been initialized. Added in v5.5.8

```js php
acf.addAction('select2_init', function( $select, args, settings, field ){
    // $select (jQuery) select element
    // args (object) args given to the select2 function
    // settings (object) settings given to the acf.select2 function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-wysiwyg_tinymce_init)

### wysiwyg\_tinymce\_init

Link copied

Called when a WYSIWYG tinymce element has been initialized. Added in v5.5.8

```js php
acf.addAction('wysiwyg_tinymce_init', function( ed, id, mceInit, field ){
    // ed (object) tinymce object returned by the init function
    // id (string) identifier for the tinymce instance
    // mceInit (object) args given to the tinymce function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-wysiwyg_quicktags_init)

### wysiwyg\_quicktags\_init

Link copied

Called when a WYSIWYG quickktags element has been initialized. Each tinymce instance can also contain a ‘text’ edit mode that shows basic ‘quicktag’ buttons. Added in v5.5.8

```js php
acf.addAction('wysiwyg_quicktags_init', function( qtag, id, qtInit, field ){
    // qtag (object) quick tag object returned by the init function
    // id (string) identifier for the qtag instance
    // qtInit (object) args given to the quick tag function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#actions-google_map_init)

### google\_map\_init

Link copied

Called when a Google Map element has been initialized. Added in v5.5.11

```js php
acf.addAction('google_map_init', function( map, marker, field ){
    // map (object) google map object returned by the google.maps.Map() function
    // marker (object) marker object returned by the google.maps.Marker() function
    // field (object) field instance
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters)

## Filters

Link copied

Filters are called at specific times to allow for customisation. Below is a list of available JS filters that you can hook into using the `acf.addFilter()` function.

> ✋ If using the “pre 5.7” function **acf.add\_filter()**, please be aware that any **field instance** parameter documented bellow will appear as a **jQuery element** for compatibility. This change is discussed in more detail later in the [Compatibility](https://www.advancedcustomfields.com/resources/javascript-api/#compatibility) section.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-validation_complete)

### validation\_complete

Link copied

This filter allows the validation JSON response to be customized. Called after AJAX validation is complete but before errors are shown or the form is submitted.

```js php
acf.add_filter('validation_complete', function( json, $form ){

    // check errors
    if( json.errors ) {
        // do something
    }

    // return
    return json;
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-wysiwyg_tinymce_settings)

### wysiwyg\_tinymce\_settings

Link copied

This filter allows the tinyMCE settings to be customized for each WYSIWYG field. Called before the tinyMCE instance is created.

```js php
acf.add_filter('wysiwyg_tinymce_settings', function( mceInit, id, field ){

    // do something to mceInit

    // return
    return mceInit;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-wysiwyg_quicktags_settings)

### wysiwyg\_quicktags\_settings

Link copied

This filter allows the quicktags settings to be customized for each WYSIWYG field. Called before the text instance is created.

```js php
acf.add_filter('wysiwyg_quicktags_settings', function( qtInit, id, field ){

    // do something to qtInit

    // return
    return qtInit;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-date_picker_args)

### date\_picker\_args

Link copied

This filter allows the date picker settings to be customized for each date picker field. Called before the date picker instance is created. A full list of settings can be found here: https://api.jqueryui.com/datepicker/

```js php
acf.add_filter('date_picker_args', function( args, field ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-date_time_picker_args)

### date\_time\_picker\_args

Link copied

This filter allows the date time picker settings to be customized for each date time picker field. Called before the date time picker instance is created. A full list of settings can be found here: http://trentrichardson.com/examples/timepicker/

```js php
acf.add_filter('date_time_picker_args', function( args, field ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-time_picker_args)

### time\_picker\_args

Link copied

This filter allows the time picker settings to be customized for each time picker field. Called before the time picker instance is created. A full list of settings can be found here: http://trentrichardson.com/examples/timepicker/

```js php
acf.add_filter('time_picker_args', function( args, field ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-google_map_args)

### google\_map\_args

Link copied

This filter allows the google maps settings to be customized for each google maps field. Called before the map instance is created.

```js php
acf.add_filter('google_map_args', function( args, field ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-google_map_marker_args)

### google\_map\_marker\_args

Link copied

This filter allows the google maps marker settings to be customized for each google maps field. Called before the map instance is created.

```js php
acf.add_filter('google_map_marker_args', function( args, field ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-google_map_result)

### google\_map\_result

Link copied

This filter allows the google maps field value to be modified after an API request has been made and a result has been returned.

```js php
acf.add_filter('google_map_result', function( result, geocoderResult, map, field ){

    // do something to result

    // return
    return result;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-select2_args)

### select2\_args

Link copied

This filter allows the select2 settings to be customized for each select field before the select2 instance is created.

```js php
acf.add_filter('select2_args', function( args, $select, settings, field, instance ){

    // do something to args

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-select2_escape_markup)

### select2\_escape\_markup

Link copied

This filter allows the result of default HTML escaping for select2 templates and selections to be modified. Available since ACF 6.2.8.

```js php
acf.add_filter('select2_escape_markup', function( escaped_value, original_value, $select, settings, field, instance ){

    // do something to the original_value to override the default escaping, then return it.
    // this value should still have some kind of escaping for security, but you may wish to allow specific HTML.
    if (field.data( 'name' ) == "select2_with_html") {
        return my_custom_escaping_method( original_value );
    }

    // return
    return escaped_value;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-select2_ajax_data)

### select2\_ajax\_data

Link copied

This filter allows the data sent in an ajax request to be customized for each select field.

```js php
acf.add_filter('select2_ajax_data', function( data, args, $input, field, instance ){

    // do something to data

    // return
    return data;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-select2_ajax_results)

### select2\_ajax\_results

Link copied

This filter allows the data returned from an ajax request to be customized for each select field.

```js php
acf.add_filter('select2_ajax_results', function( json, params, instance ){

    // do something to json

    // return
    return json;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#filters-color_picker_args)

### color\_picker\_args

Link copied

This filter allows the color picker (wpColorPicker) settings to be customized for each color picker field. This filter is called before the wpColorPicker instance is created. Added in v 5.3.6

```js php
acf.add_filter('color_picker_args', function( args, field ){

    // do something to args
    args.palettes = ['#5ee8bf', '#2f353e', '#f55e4f']

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models)

## Models

Link copied

Models are the heart of ACF functionality. The **acf.Model** function provides convenient scaffolding for creating new instances to store data, add event listeners, and perform logic. A model can be created as a “once off” instance, or extended into a “class” for repeated use (such as the **acf.Field** class discussed later).

The following is a contrived example, but it demonstrates defining a model with a custom method, setting an attribute, and firing an event keyed to changes in that specific attribute.

```js php
var sidebar = new acf.Model({
    wait: 'ready',
    data: {
        color: '#ffffff'
    },
    events: {
        'click .select-color':  'onClick'
    },
    initialize: function(){
        this.$el = $('#sidebar');
    }
    onClick: function( e, $el ){

        // get color from data attribute on '.select-color' element
        this.set('color', $el.data('color'));

        // render
        this.render();
    },
    render: function(){
        this.$el.css('background-color', this.get('color'));
    }
});

// interact directly with the sidebar variable
var color = sidebar.get('color');
```

All models and those that extend the base model have access to the following properties and functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-cid)

### cid model.cid

Link copied

A special property of models, the cid or “client id” is a unique identifier automatically assigned to all models when they’re first created.

```js php
var instance = new acf.Model();
var id = instance.cid; // acf-123
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-data)

### data model.data

Link copied

The data object used by get(), set() and has() to store data on the instance.

```js php
var instance = new acf.Model({
    data: {
        color: '#ffffff',
        active: false
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-events)

### events model.events

Link copied

A list of “jQuery events” that will be bound to methods in the format {“event selector” : “callback”}.
The callback is scoped to the instance and the jQuery element is passed through as a second parameter.

```js php
var instance = new acf.Model({
    events: {
        'change': 'onChange',
        'change input[type="text"]': 'onChangeText',
    },
    onChange: function(e, $el){
        e.preventDefault();
        var val = $el.val();
        // do something
    },
    onChangeText: function(e, $el){
        // do something for just text inputs and then call the normal change callback
        this.onChange(e, $el);
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-actions)

### actions model.actions

Link copied

A list of actions that will be bound to methods in the format {“name” : “callback”}.

```js php
var instance = new acf.Model({
    actions: {
        'append': 'onAppend',
    },
    onAppend: function($el){
        // $el has been added to the DOM.
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-filters)

### filters model.filters

Link copied

A list of filters that will be bound to methods in the format {“name” : “callback”}.

```js php
var instance = new acf.Model({
    filters: {
        'things': 'filterThings',
    },
    filterThings: function( things ){
        things.push('zar');
        return things;
    }
});
var things = acf.applyFilters('things', ['foo', 'bar']);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-priority)

### priority model.priority

Link copied

The priority used for the above actions and filters. Defaults to 10.

```js php
var instance = new acf.Model({
    actions: {
        'ready': 'onReady',
    },
    priority: 99,
    onReady: function(){
        // runs after other 'ready' callbacks
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-wait)

### wait model.wait

Link copied

Delays initialization until a specific action such as ‘ready’ or ‘load’.

```js php
var instance = new acf.Model({
    wait: 'ready',
    initialize: function(){
        // runs during the 'ready' action when all elements have been rendered
        this.$el = $('#some-element');
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-initialize)

### initialize model.initialize()

Link copied

The “constructor” function which is called when creating an instance of a model.

```js php
var instance = new acf.Model({
    initialize: function(){
        this.doSomething();
    }
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-get)

### get model.get(name)

Link copied

Returns a value from the instance data.

```js php
var foo = instance.get('foo');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-set)

### set model.set(name, value)

Link copied

Stores a value in the instance data.

```js php
var value = 'bar';
instance.set('foo', value);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-has)

### has model.has(name)

Link copied

Returns true if data exists for the given name.

```js php
if( instance.has('foo') ) {
    // do something
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-on)

### on model.on(event, selector, callback) or model.on(event, callback)

Link copied

Adds an event listener to the instance.

```js php
instance.on('change', 'input[type="text"]', function( e ){
    // similar to jQuery, "this" is scoped to the DOM element.
    // get input val
    var val = $(this).val();
    instance.doSomething( val );
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-$)

### $ model.$(selector)

Link copied

Runs the jQuery.$ function scoped to model.$el

```js php
var $button = instance.$('.my-button');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-$el)

### $el model.$el

Link copied

The jQuery element for this instance used for adding events.

```js php
instance.$el.addClass('new-class');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#models-extend)

### extend model.extend(args)

Link copied

The **acf.Model** class can be extended to create your own class. Take the following example.

```js php
var Person = acf.Model.extend({
    data: {
        firstName: '',
        lastName: ''
    },
    // the 'changed' and 'changed:name' events trigger when changing data
    events: {
        'changed':  'render'
    },
    setup: function( props ){

        // store data
        $.extend(this.data, props);

        // create element
        this.$el = $('<div class="person"></div>');
    },
    initialize: function(){
        this.show();
        this.render();
    },
    show: function(){
        $('body').append( this.$el );
    },
    hide: function(){
        this.$el.remove();
    },
    render: function(){
        this.$el.html( this.get('firstName') + ' ' + this.get('lastName') );
    }
});

var person1 = new Person({ firstName: 'John', lastName: 'Smith' });
var person2 = new Person({ firstName: 'Jane', lastName: 'West' });

person2.set('lastName', 'Smith');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field)

## acf.Field

Link copied

We use models to bring our fields to life. Each field is given an instance of the **acf.Field** model allowing a uniform way to interact with fields.

The **acf.Field** model extends from the **acf.Model** model meaning that it inherits all the properties and functions mentioned above.

The following is a contrived example, but it demonstrates how to interact with a field instance.

```js php
// get the field instance
var field = acf.getField('field_123456');

// show error if no value
if( !field.val() ) {
    field.showError('Please add a value');
}

// add an event
field.on('click', '.disable-button', function( e ){
    field.disable();
});

// add class
field.$el.addClass('my-field');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-type)

### type field.type

Link copied

The field type name (“image”, “text”, etc).

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-val)

### val field.val(\[value\])

Link copied

Returns the field’s value or sets a new value if one is given.

```js php
if( !field.val() ) {
    field.val('Default value');
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-$control)

### $control field.$control()

Link copied

Some fields (such as the image field) use a “control” element to wrap the “input” and pass data attributes. This function returns this “control” jQuery element.

```js php
field.$control().addClass('customized');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-$input)

### $input field.$input()

Link copied

Most fields (such as the text field) use an “input” element to collect and send values. This function returns this “input” jQuery element.

```js php
field.$input().focus();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-disable)

### disable field.disable()

Link copied

Disables the field’s input elements.

```js php
field.disable();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-enable)

### enable field.enable()

Link copied

Enables the field’s input elements.

```js php
field.enable();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-hide)

### hide field.hide()

Link copied

Hides the field element.

```js php
field.hide();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-show)

### show field.show()

Link copied

Shows the field element.

```js php
field.show();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-remove)

### remove field.remove()

Link copied

Removes the field from the DOM and unregisters all assigned events, actions and filters.

```js php
field.remove();
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-parent)

### parent field.parent()

Link copied

Returns the field’s parent instance or false if no parent.

```js php
var parent = field.parent();
if( parent ) {
    parent.doSomething();
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-shownotice)

### showNotice field.showNotice( args )

Link copied

Displays a text notice within the field.

```js php
field.showNotice({
    text: "Please select at least one of these items",
    type: '',       // warning, error, success
    dismiss: true,  // allow notice to be dismissed
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-removenotice)

### removeNotice field.removeNotice()

Link copied

Removes the field’s current notice.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-events)

### Events

Link copied

The **acf.Field** model triggers custom events which can be listened to just like a jQuery change event. These events are similar to the [Field Actions](https://www.advancedcustomfields.com/resources/javascript-api/#actions-field-actions) but allow you to listen directly to a specific field instance.

| Name | Description |
| --- | --- |
| `removeField` | Triggered when a field is removed. |
| `hideField` | Triggered when a field is hidden. |
| `showField` | Triggered when a hidden field is shown. |
| `disableField` | Triggered when a field is disabled. |
| `enableField` | Triggered when a disabled field is enabled. |
| `invalidField` | Triggered when a field value fails validation. |
| `validField` | Triggered when an invalid field value passes validation. |
| `sortstartField` | Triggered when a field is being moved in the DOM. |
| `sortstopField` | Triggered when a field has finished being moved in the DOM. |

The following example shows how to listen to a field event.

```js php
// get the field instance
var field = acf.getField('field_123456');

// do something on show
field.on('showField', function(){
    field.doSomething();
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.field-extend)

### extend field.extend( props )

Link copied

The **acf.Field** model can be extended to create your own field type “class”. This makes developing custom field type easier than ever before.

Here is an example of the **URL Field** class taken from the ACF source code. Please note that the class is “registered” using the `acf.registerFieldType( Field )` function which is needed for ACF to correctly select this “class” during initialization.

```js php
(function($){

    var Field = acf.Field.extend({
        type: 'url',
        events: {
            'keyup input[type="url"]': 'onkeyup'
        },
        $control: function(){
            return this.$('.acf-input-wrap');
        },
        $input: function(){
            return this.$('input[type="url"]');
        },
        initialize: function(){
            this.render();
        },
        isValid: function(){

            // vars
            var val = this.val();

            // url
            if( val.indexOf('://') !== -1 ) {
                return true;
            }

            // protocol relative url
            if( val.indexOf('//') === 0 ) {
                return true;
            }

            // return
            return false;
        },
        render: function(){

            // add class
            if( this.isValid() ) {
                this.$control().addClass('-valid');
            } else {
                this.$control().removeClass('-valid');
            }
        },
        onkeyup: function( e, $el ){
            this.render();
        }
    });

    acf.registerFieldType( Field );

})(jQuery);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition)

## acf.Condition

Link copied

The **acf.Condition** model is used to define the different types of conditional logic available for use between fields. Similar to **acf.Field**, this model can be extended to create new condition types.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-type)

### type condition.type

Link copied

The condition’s private ID used for storage/lookup. Must be unique like “hasValue”, “hasNoValue”, etc.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-operator)

### operator condition.operator

Link copied

The condition’s public ID used in HTML attributes. Should best match a programatic operator like “==”, “!=”, etc.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-label)

### label condition.label

Link copied

The condition’s label visible in the dropdown when selecting a conditional rule.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-fieldtypes)

### fieldTypes condition.fieldTypes

Link copied

An array of field types that this condition applies to. Example \[‘text’, ‘textarea’\].

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-match)

### match condition.match(rule, field)

Link copied

This function is called to determine if the condition is true or false. Must return a boolean value. See the following example taken from the “Has any value” rule.

```js php
// taken from the "Has any value" rule
{
    match: function( rule, field ){
        // return true if field has any value
        return (field.val() ? true : false);
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-choices)

### choices condition.choices(fieldObject)

Link copied

This function is called to return the available choices for this condition. The selected “field object” is passed through as a parameter which can be used to lookup settings (the selectEqualTo model looks up the field’s “choices” textarea setting). The function can return either an array of choices (which will result in a dropdown being created) or custom HTML.

```js php
// taken from the "EqualTo" rule
{
    choices: function( fieldObject ){
        return '<input type="text" />';
    }
}

// taken from the "trueFalseEqualTo" rule
{
    choices: function( fieldObject ){
        return [\
            {\
                id:     1,\
                text:   'Checked'\
            }\
        ];
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-extend)

### extend condition.extend( props )

Link copied

The **acf.Condition** model can be extended to create your own condition type “class”. This makes developing custom conditions super easy.

Here is an example of the **lessThan** class taken from the ACF source code. Please note that the class is “registered” using the `acf.registerConditionType( Condition )` function which is needed for ACF to correctly select this “class” during initialization.

```js php
(function($){

    var LessThan = GreaterThan.extend({
        type: 'lessThan',
        operator: '<',
        label: __('Value is less than'),
        match: function( rule, field ){
            var val = field.val();
            if( val instanceof Array ) {
                val = val.length;
            }
            return isLessThan( val, rule.value );
        },
        choices: function( fieldObject ){
            return '<input type="number" />';
        }
    });

    acf.registerConditionType( LessThan );

})(jQuery);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#acf.condition-registerconditionforfieldtype)

### registerConditionForFieldType acf.registerConditionForFieldType(conditionType, fieldType)

Link copied

Connects an registered condition type to a registered field type. This can be used to add basic condition types to your own custom field type.

```js php
(function($){

    var Field = acf.Field.extend({
        type: 'my_custom_field',
        // ...
    });

    acf.registerFieldType( Field );

    acf.registerConditionForFieldType('hasValue', 'my_custom_field');
    acf.registerConditionForFieldType('hasNoValue', 'my_custom_field');

})(jQuery);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#compatibility)

## Compatibility

Link copied

The **acf** object extends a “compatibility layer” where we keep any deprecated or changed functions and properties. This allows our library to stay organised as well as provide compatibility with existing code. The biggest changes to our library that requires backwards compatibility are those to the “hook” functions `acf.add_action()` and `acf.add_filter()`.

Prior to version 5.7, all callbacks for Field Actions or Field Filters would receive a jQuery element parameter. This has changed in version 5.7 as these same actions now receive a field instance.

To provide backwards compatibility, we didn’t change the hook names, but we did change the function names. This allows us to apply a “compatibility layer” to the parameters depending on which function you use. To better illustrate, please look at the following backwards compatible functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#compatibility-add_action)

### add\_action acf.add\_action(action, callback, priority, context)

Link copied

An alias of `acf.AddAction()` with a twist. Any action that would normally receive a field instance will receive a jQuery element.

```js php
// old: acf.add_action
acf.add_action('ready_field', function( $field ){
    $field.addClass('old-way');
});

// new: acf.addAction
acf.addAction('ready_field', function( field ){
    field.$el.addClass('new-way');
});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#compatibility-add_filter)

### add\_filter acf.add\_filter(filter, callback, priority, context)

Link copied

An alias of `acf.addFilter()` with a twist. Any filter that would normally receive a field instance will receive a jQuery element.

```js php
// old: acf.add_filter
acf.add_filter('color_picker_args', function( args, $field ){

    // do something to the field
    $field.addClass('old-way');

    // return
    return args;

});

// new: acf.addAction
acf.addFilter('color_picker_args', function( args, field ){

    // do something to the field
    field.$el.addClass('new-way');

    // return
    return args;

});
```

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#changelog)

## Changelog

Link copied

- Rebuilt JS library in version 5.7

[Link to heading#](https://www.advancedcustomfields.com/resources/javascript-api/#further-reading)

## Further Reading

Link copied

Believe it or not, this documentation only scrapes the surface of the ACF JavaScript API! If you are interested in learning more about a specific function, finding the full list of models or are in need of more code examples, please take a look at the `acf-input.js` source code located in the plugin folder **assets/js/acf-input.js**.

Happy coding,
The ACF team.

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

[Got it](https://www.advancedcustomfields.com/resources/javascript-api/#)