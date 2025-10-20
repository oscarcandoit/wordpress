---
url: https://www.advancedcustomfields.com/resources/register-fields-via-php
scraped_at: 2025-10-20T02:17:47.957Z
---

# Register fields via PHP

Last updated Nov 16, 2021

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#overview)

## Overview

Link copied

This article will discuss how to register fields and field groups via the functions.php file. There are many benefits to using PHP to register fields, the main of which is customization and distribution. The ability to define fields within the theme’s files allows developers to avoid any data loss when working across multiple environments (dev/staging/live). It also reduces calls to the database and can speed up your website.

If you only require a solution for distribution across multiple environments, please familiarize yourself with the [local json feature](https://www.advancedcustomfields.com/resources/local-json/ "Local JSON") as this solves the issue with minimal effort.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#getting-started)

## Getting started

Link copied

Adding field groups and fields is easy. ACF can even generate the PHP code for you from the `Import / Export` menu page within the WP dashboard!

👨‍💻 Note: It is important to remember that each field group’s `key` and each field’s `key` **must** be unique. The `key` is a reference for ACF to find, save and load data. If 2 fields or 2 groups are added using the same `key`, the later will override the original.

👨‍💻 Note: Field Groups and Fields registered via code will not be visible/editable via the “Edit Field Groups” admin page.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#functions)

## Functions

Link copied

Here is a list of functions which will be used in the examples below. You can find these functions and more in the `core/local.php` file.

| Name | Description |
| --- | --- |
| `acf_add_local_field_group( $field_group )` | Adds a field group to the local cache |
| `acf_add_local_field( $field )` | Adds a field to the local cache |
| `acf_get_local_field( $key )` | Get a local field |
| `acf_remove_local_field( $key )` | Remove a local field |

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#example)

## Example

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#basic)

### Basic

Link copied

This example demonstrates how to add a field group.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_local_field_group') ):

acf_add_local_field_group(array (
    'key' => 'group_1',
    'title' => 'My Group',
    'fields' => array (
        array (
            'key' => 'field_1',
            'label' => 'Sub Title',
            'name' => 'sub_title',
            'type' => 'text',
            'prefix' => '',
            'instructions' => '',
            'required' => 0,
            'conditional_logic' => 0,
            'wrapper' => array (
                'width' => '',
                'class' => '',
                'id' => '',
            ),
            'default_value' => '',
            'placeholder' => '',
            'prepend' => '',
            'append' => '',
            'maxlength' => '',
            'readonly' => 0,
            'disabled' => 0,
        )
    ),
    'location' => array (
        array (
            array (
                'param' => 'post_type',
                'operator' => '==',
                'value' => 'post',
            ),
        ),
    ),
    'menu_order' => 0,
    'position' => 'normal',
    'style' => 'default',
    'label_placement' => 'top',
    'instruction_placement' => 'label',
    'hide_on_screen' => '',
));

endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#minimal)

### Minimal

Link copied

Each field contains many settings which can be removed to minimize your code. In this case ACF will merge in the missing default settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_local_field_group') ):

acf_add_local_field_group(array(
    'key' => 'group_1',
    'title' => 'My Group',
    'fields' => array (
        array (
            'key' => 'field_1',
            'label' => 'Sub Title',
            'name' => 'sub_title',
            'type' => 'text',
        )
    ),
    'location' => array (
        array (
            array (
                'param' => 'post_type',
                'operator' => '==',
                'value' => 'post',
            ),
        ),
    ),
));

endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#individual)

### Individual

Link copied

It is possible to add a field group and field individually. This makes it possible for a field to be defined as a variable and added to multiple field groups. Please note the `$field` must contain a `parent` setting which matches the key of either the field group, or another parent field ( repeater / flexible content ).

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_local_field_group') ):

acf_add_local_field_group(array(
    'key' => 'group_1',
    'title' => 'My Group',
    'fields' => array (),
    'location' => array (
        array (
            array (
                'param' => 'post_type',
                'operator' => '==',
                'value' => 'post',
            ),
        ),
    ),
));

acf_add_local_field(array(
    'key' => 'field_1',
    'label' => 'Sub Title',
    'name' => 'sub_title',
    'type' => 'text',
    'parent' => 'group_1'
));

endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#add-within-an-action)

### Add within an action

Link copied

The functions above can be used in the root of the `functions.php` file or within the [acf/init](https://www.advancedcustomfields.com/resources/acf-init/) action. This action was added in ACF v5.2.7 and is recommended.

The benefit of using this action is that the function is guaranteed to exist, and won’t run unless ACF is active.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#functionsphp)

#### functions.php

Link copied

```php
function my_acf_add_local_field_groups() {

    acf_add_local_field_group(array(
        'key' => 'group_1',
        'title' => 'My Group',
        'fields' => array (
            array (
                'key' => 'field_1',
                'label' => 'Sub Title',
                'name' => 'sub_title',
                'type' => 'text',
            )
        ),
        'location' => array (
            array (
                array (
                    'param' => 'post_type',
                    'operator' => '==',
                    'value' => 'post',
                ),
            ),
        ),
    ));

}

add_action('acf/init', 'my_acf_add_local_field_groups');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#group-settings)

## Group Settings

Link copied

Below is a list of available settings for a field group. Please note these settings can be viewed when editing a field group, and exported for minimal effort.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#group-settings)

#### Group Settings

Link copied

```php
$group = array(

    /* (string) Unique identifier for field group. Must begin with 'group_' */
    'key' => 'group_1',

    /* (string) Visible in metabox handle */
    'title' => 'My Group',

    /* (array) An array of fields */
    'fields' => array(),

    /* (array) An array containing 'rule groups' where each 'rule group' is an array containing 'rules'.
    Each group is considered an 'or', and each rule is considered an 'and'. */
    'location' => array(
        array(
            array(
                'param' => 'post_type',
                'operator' => '==',
                'value' => 'post',
            ),
        ),
    ),

    /* (int) Field groups are shown in order from lowest to highest. Defaults to 0 */
    'menu_order' => 0,

    /* (string) Determines the position on the edit screen. Defaults to normal. Choices of 'acf_after_title', 'normal' or 'side' */
    'position' => 'normal',

    /* (string) Determines the metabox style. Defaults to 'default'. Choices of 'default' or 'seamless' */
    'style' => 'default',

    /* (string) Determines where field labels are places in relation to fields. Defaults to 'top'.
    Choices of 'top' (Above fields) or 'left' (Beside fields) */
    'label_placement' => 'top',

    /* (string) Determines where field instructions are places in relation to fields. Defaults to 'label'.
    Choices of 'label' (Below labels) or 'field' (Below fields) */
    'instruction_placement' => 'label',

    /* (array) An array of elements to hide on the screen */
    'hide_on_screen' => '',
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#field-settings)

## Field Settings

Link copied

Below is a list of available generic settings for a field. In addition to these generic settings, each field is also given field type specific settings which are listed down the page.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#field-settings)

#### Field Settings

Link copied

```php
$field = array (

    /* (string) Unique identifier for the field. Must begin with 'field_' */
    'key' => 'field_1',

    /* (string) Visible when editing the field value */
    'label' => 'Sub Title',

    /* (string) Used to save and load data. Single word, no spaces. Underscores and dashes allowed */
    'name' => 'sub_title',

    /* (string) Type of field (text, textarea, image, etc) */
    'type' => 'text',

    /* (string) Instructions for authors. Shown when submitting data */
    'instructions' => '',

    /* (int) Whether or not the field value is required. Defaults to 0 */
    'required' => 0,

    /* (mixed) Conditionally hide or show this field based on other field's values.
    Best to use the ACF UI and export to understand the array structure. Defaults to 0 */
    'conditional_logic' => 0,

    /* (array) An array of attributes given to the field element */
    'wrapper' => array (
        'width' => '',
        'class' => '',
        'id' => '',
    ),

    /* (mixed) A default value used by ACF if no value has yet been saved */
    'default_value' => '',
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#field-type-settings)

## Field type settings

Link copied

Below is a list of extra settings available to each field type.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#basic)

### Basic

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#text-field-settings)

#### Text field settings

Link copied

```php
$text_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

    /* (string) Appears before the input. Defaults to '' */
    'prepend' => '',

    /* (string) Appears after the input. Defaults to '' */
    'append' => '',

    /* (string) Restricts the character limit. Defaults to '' */
    'maxlength' => '',

    /* (bool) Makes the input readonly. Defaults to 0 */
    'readonly' => 0,

    /* (bool) Makes the input disabled. Defaults to 0 */
    'disabled' => 0,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#textarea-field-settings)

#### Textarea field settings

Link copied

```php
$textarea_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

    /* (string) Restricts the character limit. Defaults to '' */
    'maxlength' => '',

    /* (int) Restricts the number of rows and height. Defaults to '' */
    'rows' => '',

    /* (new_lines) Decides how to render new lines. Detauls to 'wpautop'.
    Choices of 'wpautop' (Automatically add paragraphs), 'br' (Automatically add <br>) or '' (No Formatting) */
    'new_lines' => '',

    /* (bool) Makes the input readonly. Defaults to 0 */
    'readonly' => 0,

    /* (bool) Makes the input disabled. Defaults to 0 */
    'disabled' => 0,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#number-field-settings)

#### Number field settings

Link copied

```php
$number_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

    /* (string) Appears before the input. Defaults to '' */
    'prepend' => '',

    /* (string) Appears after the input. Defaults to '' */
    'append' => '',

    /* (int) Minimum number value. Defaults to '' */
    'min' => '',

    /* (int) Maximum number value. Defaults to '' */
    'max' => '',

    /* (int) Step size increments. Defaults to '' */
    'step' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#email-field-settings)

#### Email field settings

Link copied

```php
$email_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

    /* (string) Appears before the input. Defaults to '' */
    'prepend' => '',

    /* (string) Appears after the input. Defaults to '' */
    'append' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#url-field-settings)

#### Url field settings

Link copied

```php
$url_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#password-field-settings)

#### Password field settings

Link copied

```php
$password_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Appears within the input. Defaults to '' */
    'placeholder' => '',

    /* (string) Appears before the input. Defaults to '' */
    'prepend' => '',

    /* (string) Appears after the input. Defaults to '' */
    'append' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#content)

### Content

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#wysiwyg-field-settings)

#### WYSIWYG field settings

Link copied

```php
$wysiwyg_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Specify which tabs are available. Defaults to 'all'.
    Choices of 'all' (Visual & Text), 'visual' (Visual Only) or text (Text Only) */
    'tabs' => 'all',

    /* (string) Specify the editor's toolbar. Defaults to 'full'.
    Choices of 'full' (Full), 'basic' (Basic) or a custom toolbar (https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/) */
    'toolbar' => 'full',

    /* (bool) Show the media upload button. Defaults to 1 */
    'media_upload' => 1,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#oembed-field-settings)

#### oEmbed field settings

Link copied

```php
$oembed_field = array(

    /* ... Insert generic settings here ... */

    /* (int) Specify the width of the oEmbed element. Can be overridden by CSS */
    'width' => '',

    /* (int) Specify the height of the oEmbed element. Can be overridden by CSS */
    'height' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#image-field-settings)

#### Image field settings

Link copied

```php
$image_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Specify the type of value returned by get_field(). Defaults to 'array'.
    Choices of 'array' (Image Array), 'url' (Image URL) or 'id' (Image ID) */
    'return_format' => 'array',

    /* (string) Specify the image size shown when editing. Defaults to 'thumbnail'. */
    'preview_size' => 'thumbnail',

    /* (string) Restrict the image library. Defaults to 'all'.
    Choices of 'all' (All Images) or 'uploadedTo' (Uploaded to post) */
    'library' => 'all',

    /* (int) Specify the minimum width in px required when uploading. Defaults to 0 */
    'min_width' => 0,

    /* (int) Specify the minimum height in px required when uploading. Defaults to 0 */
    'min_height' => 0,

    /* (int) Specify the minimum filesize in MB required when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'min_size' => 0,

    /* (int) Specify the maximum width in px allowed when uploading. Defaults to 0 */
    'max_width' => 0,

    /* (int) Specify the maximum height in px allowed when uploading. Defaults to 0 */
    'max_height' => 0,

    /* (int) Specify the maximum filesize in MB in px allowed when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'max_size' => 0,

    /* (string) Comma separated list of file type extensions allowed when uploading. Defaults to '' */
    'mime_types' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#file-field-settings)

#### File field settings

Link copied

```php
$file_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Specify the type of value returned by get_field(). Defaults to 'array'.
    Choices of 'array' (File Array), 'url' (File URL) or 'id' (File ID) */
    'return_format' => 'array',

    /* (string) Specify the file size shown when editing. Defaults to 'thumbnail'. */
    'preview_size' => 'thumbnail',

    /* (string) Restrict the file library. Defaults to 'all'.
    Choices of 'all' (All Files) or 'uploadedTo' (Uploaded to post) */
    'library' => 'all',

    /* (int) Specify the minimum filesize in MB required when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'min_size' => 0,

    /* (int) Specify the maximum filesize in MB in px allowed when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'max_size' => 0,

    /* (string) Comma separated list of file type extensions allowed when uploading. Defaults to '' */
    'mime_types' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#gallery-field-settings)

#### Gallery field settings

Link copied

```php
$gallery_field = array(

    /* ... Insert generic settings here ... */

    /* (int) Specify the minimum attachments required to be selected. Defaults to 0 */
    'min' => 0,

    /* (int) Specify the maximum attachments allowed to be selected. Defaults to 0 */
    'max' => 0,

    /* (string) Specify the image size shown when editing. Defaults to 'thumbnail'. */
    'preview_size' => 'thumbnail',

    /* (string) Restrict the image library. Defaults to 'all'.
    Choices of 'all' (All Images) or 'uploadedTo' (Uploaded to post) */
    'library' => 'all',

    /* (int) Specify the minimum width in px required when uploading. Defaults to 0 */
    'min_width' => 0,

    /* (int) Specify the minimum height in px required when uploading. Defaults to 0 */
    'min_height' => 0,

    /* (int) Specify the minimum filesize in MB required when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'min_size' => 0,

    /* (int) Specify the maximum width in px allowed when uploading. Defaults to 0 */
    'max_width' => 0,

    /* (int) Specify the maximum height in px allowed when uploading. Defaults to 0 */
    'max_height' => 0,

    /* (int) Specify the maximum filesize in MB in px allowed when uploading. Defaults to 0
    The unit may also be included. eg. '256KB' */
    'max_size' => 0,

    /* (string) Comma separated list of file type extensions allowed when uploading. Defaults to '' */
    'mime_types' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#choice)

### Choice

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#select-field-settings)

#### Select field settings

Link copied

```php
$select_field = array(

    /* ... Insert generic settings here ... */

    /* (array) Array of choices where the key ('red') is used as value and the value ('Red') is used as label */
    'choices' => array(
        'red'   => 'Red'
    ),

    /* (bool) Allow a null (blank) value to be selected. Defaults to 0 */
    'allow_null' => 0,

    /* (bool) Allow mulitple choices to be selected. Defaults to 0 */
    'multiple' => 0,

    /* (bool) Use the select2 interfacte. Defaults to 0 */
    'ui' => 0,

    /* (bool) Load choices via AJAX. The ui setting must also be true for this to work. Defaults to 0 */
    'ajax' => 0,

    /* (string) Appears within the select2 input. Defaults to '' */
    'placeholder' => '',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#checkbox-field-settings)

#### Checkbox field settings

Link copied

```php
$checkbox_field = array(

    /* ... Insert generic settings here ... */

    /* (array) Array of choices where the key ('red') is used as value and the value ('Red') is used as label */
    'choices' => array(
        'red'   => 'Red'
    ),

    /* (string) Specify the layout of the checkbox inputs. Defaults to 'vertical'.
    Choices of 'vertical' or 'horizontal' */
    'layout' => 'vertical',

    /* (bool) Whether to allow custom options to be added by the user. Default false. */
    'allow_custom' => false,

    /* (bool) Whether to allow custom options to be saved to the field choices. Default false. */
    'save_custom' => false,

    /* (bool) Adds a "Toggle all" checkbox to the list. Default false. */
    'toggle' => false,

    /* (string) Specify how the value is formatted when loaded. Default 'value'.
    Choices of 'value', 'label' or 'array' */
    'return_format' => 'value',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#radio-field-settings)

#### Radio field settings

Link copied

```php
$radio_field = array(

    /* ... Insert generic settings here ... */

    /* (array) Array of choices where the key ('red') is used as value and the value ('Red') is used as label */
    'choices' => array(
        'red'   => 'Red'
    ),

    /* (bool) Allow a custom choice to be entered via a text input */
    'other_choice' => 0,

    /* (bool) Allow the custom value to be added to this field's choices. Defaults to 0.
    Will not work with PHP registered fields, only DB fields */
    'save_other_choice' => 0,

    /* (string) Specify the layout of the checkbox inputs. Defaults to 'vertical'.
    Choices of 'vertical' or 'horizontal' */
    'layout' => 0,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#true--false-field-settings)

#### True / False field settings

Link copied

```php
$true_false_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Text shown along side the checkbox */
    'message' => 0,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#relational)

## Relational

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#post-object-field-settings)

#### Post Object field settings

Link copied

```php
$post_object_field = array(

    /* ... Insert generic settings here ... */

    /* (mixed) Specify an array of post types to filter the available choices. Defaults to '' */
    'post_type' => '',

    /* (mixed) Specify an array of taxonomies to filter the available choices. Defaults to '' */
    'taxonomy' => '',

    /* (bool) Allow a null (blank) value to be selected. Defaults to 0 */
    'allow_null' => 0,

    /* (bool) Allow mulitple choices to be selected. Defaults to 0 */
    'multiple' => 0,

    /* (string) Specify the type of value returned by get_field(). Defaults to 'object'.
    Choices of 'object' (Post object) or 'id' (Post ID) */
    'return_format' => 'object',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#page-link-field-settings)

#### Page Link field settings

Link copied

```php
$page_link_field = array(

    /* ... Insert generic settings here ... */

    /* (mixed) Specify an array of post types to filter the available choices. Defaults to '' */
    'post_type' => '',

    /* (mixed) Specify an array of taxonomies to filter the available choices. Defaults to '' */
    'taxonomy' => '',

    /* (bool) Allow a null (blank) value to be selected. Defaults to 0 */
    'allow_null' => 0,

    /* (bool) Allow mulitple choices to be selected. Defaults to 0 */
    'multiple' => 0,

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#relationship-field-settings)

#### Relationship field settings

Link copied

```php
$relationship_field = array(

    /* ... Insert generic settings here ... */

    /* (mixed) Specify an array of post types to filter the available choices. Defaults to '' */
    'post_type' => '',

    /* (mixed) Specify an array of taxonomies to filter the available choices. Defaults to '' */
    'taxonomy' => '',

    /* (array) Specify the available filters used to search for posts.
    Choices of 'search' (Search input), 'post_type' (Post type select) and 'taxonomy' (Taxonomy select) */
    'filters' => array('search', 'post_type', 'taxonomy'),

    /* (array) Specify the visual elements for each post.
    Choices of 'featured_image' (Featured image icon) */
    'elements' => array(),

    /* (int) Specify the minimum posts required to be selected. Defaults to 0 */
    'min' => 0,

    /* (int) Specify the maximum posts allowed to be selected. Defaults to 0 */
    'max' => 0,

    /* (string) Specify the type of value returned by get_field(). Defaults to 'object'.
    Choices of 'object' (Post object) or 'id' (Post ID) */
    'return_format' => 'object',

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#taxonomy-field-settings)

#### Taxonomy field settings

Link copied

```php
$taxonomy_field = array(

    /* ... Insert generic settings here ... */

    /* (string) Specify the taxonomy to select terms from. Defaults to 'category' */
    'taxonomy' => '',

    /* (array) Specify the appearance of the taxonomy field. Defaults to 'checkbox'
    Choices of 'checkbox' (Checkbox inputs), 'multi_select' (Select field - multiple), 'radio' (Radio inputs) or 'select' (Select field) */
    'field_type' => 'checkbox',

    /* (bool) Allow a null (blank) value to be selected. Defaults to 0 */
    'allow_null' => 0,

    /* (bool) Allow selected terms to be saved as relatinoships to the post */
    'load_save_terms'   => 0,

    /* (string) Specify the type of value returned by get_field(). Defaults to 'id'.
    Choices of 'object' (Term object) or 'id' (Term ID) */
    'return_format'     => 'id',

    /* (bool) Allow new terms to be added via a popup window */
    'add_term'          => 1

);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#user-field-settings)

#### User field settings

Link copied

```php
$user_field = array(

    /* ... Insert generic settings here ... */

    /* (array) Array of roles to limit the users available for selection */
    'role' => array(),

    /* (bool) Allow a null (blank) value to be selected. Defaults to 0 */
    'allow_null' => 0,

    /* (bool) Allow mulitple choices to be selected. Defaults to 0 */
    'multiple' => 0,

);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/register-fields-via-php/#related)

## Related

Link copied

- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Register multiple options pages](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Functions: [acf\_register\_form()](https://www.advancedcustomfields.com/resources/acf_register_form/)

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

[Got it](https://www.advancedcustomfields.com/resources/register-fields-via-php/#)