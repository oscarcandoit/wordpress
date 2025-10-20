---
url: https://www.advancedcustomfields.com/resources/custom-location-rules
scraped_at: 2025-10-20T02:23:16.364Z
---

# Custom location rules

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#introduction)

## Introduction

Link copied

Location rules are used to determine which field groups appear on which admin screen. They are defined when editing a Field Group and consist of a location type, a comparison operator, and a value.

One example of a location rule would be "Post Type == Post".

[![The Field Group Locations metabox](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-example.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-example.png) The Field Group Locations metabox

A diverse set of location types are included within the Advanced Custom Fields plugin to satisfy the needs of most websites. In addition to these, extra location types may be defined to provide bespoke logic for the location of a Field Group.

This guide will walk through the process of creating and registering a custom location type.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#requirements)

## Requirements

Link copied

The `ACF_Location` class mentioned in this guide requires version 5.9.0 or above. If not already, please consider updating to take advantage of this great feature!

For those using a previous version, please checkout [this guide](https://www.advancedcustomfields.com/resources/custom-location-rules--v5-8/) instead.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#getting-started)

## Getting Started

Link copied

To create a custom location type, simply extend the `ACF_Location` class and some of its methods. Then register it with the `acf_register_location_type()` function.

The following is a simplified example demonstrating a custom location type that when selected would randomly show the Field Group 50% of the time.

```php
class My_Location extends ACF_Location {
    function initialize() {
        $this->name = '50_50';
        $this->label = __( 'Fifty Fifty' );
    }
    function match() {
        return rand( 0, 1 );
    }
}
acf_register_location_type( 'My_Location' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#acflocation)

## ACF\_Location

Link copied

The `ACF_Location` class contains multiple properties and methods, not all of which need to be customized. Before jumping into the working example, please familiarize yourself with the available properties and methods listed below.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#properties)

### Properties

Link copied

- **name**


(String) A unique name that identifies the location type. For example ‘post\_author’.


A location type name may only contain lowercase alphanumeric characters and underscores.


```php
$this->name = 'post_author';
```

- **label**


(String) The display label for your location type shown when editing a Field Group. For example ‘Post Author’.


```php
$this->label = __('Post Author');
```

- **category**


(String) (Optional) The group where this location type appears in the location type dropdown.


Accepts "post", "page", "user", "forms" or a custom label. Defaults to "post".


```php
$this->category = 'post';
```

- **public**


(Bool) (Optional) Whether or not the location rule is publicly selectable. Defaults to true.


```php
$this->public = true;
```

- **object\_type**


(String) (Optional) The object type related to this location.


Accepts an object type discoverable by `acf_get_object_type()` such as "post", "user", "block", etc. Defining this property allows ACF to display an icon in the Field Groups admin table column. Defaults to an empty string that represents "Various".


```php
$this->object_type = 'post';
```


[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#methods)

### Methods

Link copied

- **initialize**


Called during registration to initialize properties.


```php
public function initialize() {
      $this->name = 'post_author';
      // Define all other properties here.
}
```

- **match**


Compares the provided location rule against the current screen args and returns true for a positive match.
Returning true will allow the Field Group to appear on the current screen. Returning false will prevent the Field Group from appearing on the current screen.


```php
public function match( $rule, $screen, $field_group ) {
      return false;
}
```

- **get\_operators**


(Optional) Returns an array of operators to choose from when editing a rule.


If omitted, the default "is equal to" and "is not equal to" operators will be used.


```php
public function get_operators( $rule ) {
      return array(
          '==' => __( "is equal to" ),
          '!=' => __( "is not equal to" )
      );
}
```

- **get\_values**


(Optional) Returns an array of possible values to choose from when editing a rule.


```php
public function get_values( $rule ) {
      return array(
          'foo' => 'Foo',
          'bar' => 'Bar'
      );
}
```

- **get\_object\_subtype**


(Optional) Similar the the object\_type property, this method allows ACF to display a more accurate icon in the Field Groups admin table column.


Returns one or more subtypes that are related to this location.


Valid object subtypes include post types and taxonomies. Defaults to an empty string.


```php
public function get_object_subtype( $rule ) {
      return 'category';
}
```


[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#example)

## Example

Link copied

Let’s put some of these properties and methods to good use and create a custom location type called "Post Author". This location type will allow a Field Group to appear when editing a Post based on the Post’s Author attribute.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#1-setup)

### 1\. Setup

Link copied

Our first task is to define a new `ACF_Location` class, using the `initialize()` method to setup the location type’s properties. In this example, we will work within the theme file **includes/class-my-acf-location-post-author.php**.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#includesclass-my-acf-location-post-authorphp)

#### includes/class-my-acf-location-post-author.php

Link copied

```php
<?php

if( ! defined( 'ABSPATH' ) ) exit;

class My_ACF_Location_Post_Author extends ACF_Location {

    public function initialize() {
        $this->name = 'post_author';
        $this->label = __( "Post Author", 'acf' );
        $this->category = 'post';
        $this->object_type = 'post';
    }
}
```

Next, let’s include and register this location type from the `functions.php` file.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_init_location_types');
function my_acf_init_location_types() {

    // Check function exists, then include and register the custom location type class.
    if( function_exists('acf_register_location_type') ) {
        include_once( 'includes/class-my-acf-location-post-author.php' );
        acf_register_location_type( 'My_ACF_Location_Post_Author' );
    }
}
```

Presto 🎉. We can edit a Field Group and select the new location type.

[![Screenshot of selecting the Post Author location rule type](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-type.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-type.png) Selecting the “Post Author” location rule type

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#2-customizing-drop-downs)

### 2\. Customizing drop-downs

Link copied

With our custom location type registered, we can now turn our focus to customizing the _operator_ and _value_ drop-downs – the two settings that appear next to the selected location type.

In this example, we will leave the _operator_ drop-down as-is which will show the default "is equal to" (==) and "is not equal to" (!=) choices. We will, however, customize the _value_ drop-down to display a list of all possible users.

WordPress’ [get\_users()](https://www.advancedcustomfields.com/resources/custom-location-rules/#) function makes this task quite simple. The following snippet will populate an array of choices using the user’s ID as the option value, and the user’s Display Name as the option label.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#includesclass-my-acf-location-post-authorphp)

#### includes/class-my-acf-location-post-author.php

Link copied

```php
public function get_values( $rule ) {
    $choices = array();

    // Load all users, loop over them and append to chcoices.
    $users = get_users();
    if( $users ) {
        foreach( $users as $user ) {
            $choices[ $user->ID ] = $user->display_name;
        }
    }
    return $choices;
}
```

Our custom location type is starting to take shape! It is now possible to create a Location Rule that reads "Post Author == Elliot" 🙌.

[![Screenshot of selecting the Post Author location rule value](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-value.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-value.png) Selecting the “Post Author” location rule value

Lastly, we need to define the logic that compares a rule (such as "Post Author == Elliot") to the current screen.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#3-calculating-a-match)

### 3\. Calculating a match

Link copied

When viewing a WordPress edit screen, Advanced Custom Fields will calculate which Field Groups appear based on their location rules. Each location rule’s type is consulted to determine whether or not the rule matches the current screen args.

The logic for this "matching" is defined in the `match()` method. This method accepts 3 parameters including the rule conditions, the current screen arguments and also the Field Group who’s visibility is being calculated. All that is required from this method is to return a boolean value reflecting the matching result.

In this example, we will compare the selected rule value (a user ID) to the Post’s author attribute. We also need to remember that this location type is only relevant when editing a Post, and not a User, Term, Widget, etc.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#includesclass-my-acf-location-post-authorphp)

#### includes/class-my-acf-location-post-author.php

Link copied

```php
public function match( $rule, $screen, $field_group ) {

    // Check screen args for "post_id" which will exist when editing a post.
    // Return false for all other edit screens.
    if( isset($screen['post_id']) ) {
        $post_id = $screen['post_id'];
    } else {
        return false;
    }

    // Load the post object for this edit screen.
    $post = get_post( $post_id );
    if( !$post ) {
        return false;
    }

    // Compare the Post's author attribute to rule value.
    $result = ( $post->post_author == $rule['value'] );

    // Return result taking into account the operator type.
    if( $rule['operator'] == '!=' ) {
        return !$result;
    }
    return $result;
}
```

Congratulations 🎉 The Post Author location type is now complete! A Field Group using this location type will display only when editing a Post where the Post’s Author is "Eliot".

[![The 'Post Author' location type matching correctly for the rule 'Post Author == Elliot'](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-complete.png)](https://www.advancedcustomfields.com/wp-content/uploads/2022/02/acf-location-rule-complete.png) The “Post Author” location type matching correctly for the rule “Post Author == Elliot”

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#complete-code)

### Complete code

Link copied

For reference, here is the complete code written for the custom "Post Author" location type.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#includesclass-my-acf-location-post-authorphp)

#### includes/class-my-acf-location-post-author.php

Link copied

```php
<?php

if( ! defined( 'ABSPATH' ) ) exit;

class My_ACF_Location_Post_Author extends ACF_Location {

    public function initialize() {
        $this->name = 'post_author';
        $this->label = __( "Post Author", 'acf' );
        $this->category = 'post';
        $this->object_type = 'post';
    }

    public function get_values( $rule ) {
        $choices = array();

        // Load all users, loop over them and append to chcoices.
        $users = get_users();
        if( $users ) {
            foreach( $users as $user ) {
                $choices[ $user->ID ] = $user->display_name;
            }
        }
        return $choices;
    }

    public function match( $rule, $screen, $field_group ) {

        // Check screen args for "post_id" which will exist when editing a post.
        // Return false for all other edit screens.
        if( isset($screen['post_id']) ) {
            $post_id = $screen['post_id'];
        } else {
            return false;
        }

        // Load the post object for this edit screen.
        $post = get_post( $post_id );
        if( !$post ) {
            return false;
        }

        // Compare the Post's author attribute to rule value.
        $result = ( $post->post_author == $rule['value'] );

        // Return result taking into account the operator type.
        if( $rule['operator'] == '!=' ) {
            return !$result;
        }
        return $result;
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_init_location_types');
function my_acf_init_location_types() {

    // Check function exists, then include and register the custom location type class.
    if( function_exists('acf_register_location_type') ) {
        include_once( 'includes/class-my-acf-location-post-author.php' );
        acf_register_location_type( 'My_ACF_Location_Post_Author' );
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#wrapping-up)

## Wrapping Up

Link copied

The `ACF_Location` class makes light work of creating custom location rules. In only a few lines of code we have been able to:

- Register a new location type that can be selected within a Field Group’s location rules.
- Customize the values displayed in the location rule _value_ dropdown.
- Calculate whether or not a rule matches the current edit screen.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules/#related)

## Related

Link copied

- Guides: [Custom location rules](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Known Issues](https://www.advancedcustomfields.com/resources/known-issues/)

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

[Got it](https://www.advancedcustomfields.com/resources/custom-location-rules/#)