---
url: https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8
scraped_at: 2025-10-20T02:27:23.094Z
---

# Custom location rules

Last updated Oct 30, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#overview)

## Overview

Link copied

Each field group contains a set of location rules. These rules are used to decide where to show the field group throughout the WP admin. It is possible to create your own location rules, or even modify existing rules using the following filters.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#change-log)

## Change Log

Link copied

- **5.8.0** – Added `$field_group` parameter to `'acf/location/match_rule'` filter.
- **5.3.5** – Added `'acf/location/screen'` filter.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#adding-a-new-rule)

## Adding a new rule

Link copied

Adding a custom location rule consists of 4 simple steps. 3 of these are to define the rule settings and the last is to use these settings to match the rule to the edit screen.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#1-adding-a-custom-rule-type)

### 1\. Adding a custom rule type

Link copied

![](https://www.advancedcustomfields.com/wp-content/uploads/2013/01/location-types1.png)

When editing a field group, the ‘types’ drop down is the first dropdown in the location rule row.

Note that the list is broken into groups. This is important to keep in mind when editing the choices for this dropdown. Use the ‘acf/location/rule\_types’ filter to customize this list. Here is an example of adding “user” to the ‘Basic’ group in the dropdown choices:

```php
add_filter('acf/location/rule_types', 'acf_location_rules_types');

function acf_location_rules_types( $choices ) {

    $choices['Basic']['user'] = 'User';

    return $choices;

}
```

- Tip: use a print\_r or var\_dump to get a better idea of the $choices array.

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#2-add-custom-rule-operators)

### 2\. Add custom rule operators

Link copied

![](https://www.advancedcustomfields.com/wp-content/uploads/2013/01/location-operators1.png)

This step is optional and not required for your custom location rule to work. When editing a field group, the ‘operators’ drop down is the second dropdown in the location rule row.

By default, this list has ‘==’ and ‘!=’ operators. This can also be customized with the ‘acf/location/rule\_operators’ filter. To add in ‘<‘ and ‘>’ operators, you could use something like this:

```php
add_filter('acf/location/rule_operators', 'acf_location_rules_operators');

function acf_location_rules_operators( $choices ) {

    $choices['<'] = 'is less than';
    $choices['>'] = 'is greater than';

    return $choices;

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#3-add-custom-rule-values)

### 3\. Add custom rule values

Link copied

![](https://www.advancedcustomfields.com/wp-content/uploads/2013/01/location-value.png)

When editing a field group, the ‘values’ drop down is the third dropdown in the location rule row. This list is dynamically updated based on the ‘type’.

This list must have a choice to select from. To populate this list, use the ‘acf/location/rule\_values/$type’ filter. Please note that the variable $type in the filter name should match the ‘type’ value.

This code will populate the list with all the available users. The list will save the user\_id but display the user display\_name:

```php
add_filter('acf/location/rule_values/user', 'acf_location_rule_values_user');

function acf_location_rule_values_user( $choices ) {

    $users = get_users();

    if( $users ) {

        foreach( $users as $user ) {

            $choices[ $user->data->ID ] = $user->data->display_name;

        }

    }

    return $choices;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#4-matching-the-rule)

### 4\. Matching the rule

Link copied

After following the above steps, you should now have a custom location rule applied to your field group. The last step is to create a function for matching this rule to an edit screen.

When viewing an edit screen (page / post / user / taxonomy / attachment / etc), ACF will find all available field groups and run matching functions on the field group’s location rules. These matching functions will return either true or false and determine if a field group gets shown or not.

To create a location rule\_match function for your custom location rule, use the ‘acf/location/rule\_match/$type’ filter. Please note that the variable $type in the filter name should match the ‘type’ value.

This filter accepts 3 parameters:

1. $match – the true / false variable which must be returned
2. $rule – the current rule that you are matching against. This is an array with keys for ‘param’, ‘operator’, ‘value’.
3. $options – an array of data about the current edit screen (post\_id, page\_template, post\_type, etc). This array will also include any data posted in an ajax call (ajax calls are made on a post / page when you change the category, page\_template, etc)

The following code will create a rule\_match for ‘user’ where if the current\_user is equal to the user selected (in the field group’s rule) the field group will be shown (unless another rule did not match)

```php
add_filter('acf/location/rule_match/user', 'acf_location_rule_match_user', 10, 4);
function acf_location_rule_match_user( $match, $rule, $options, $field_group )
{
    $current_user = wp_get_current_user();
    $selected_user = (int) $rule['value'];

    if($rule['operator'] == "==")
    {
        $match = ( $current_user->ID == $selected_user );
    }
    elseif($rule['operator'] == "!=")
    {
        $match = ( $current_user->ID != $selected_user );
    }

    return $match;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#modifying-the-rulematch-options)

## Modifying the rule\_match options

Link copied

The above `rule_match` filter contains a parameter called `$options`. This parameter contains an array of information about the current edit screen such as post\_id, post\_parent, etc.

It is possible to modify this array by hooking into the filter `acf/location/screen` and either edit or append screen data.

```php
add_filter('acf/location/screen', 'acf_location_screen_options', 10, 1);

function acf_location_screen_options( $options ) {
    $options['foo'] = 'bar';
    return $options;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#wrapping-up)

## Wrapping up

Link copied

The above filters give you the ability to create custom location rules for you custom field groups. Honestly, the possibilities are endless in terms of what you can compare.

These filters could also be used in a plugin. Such as creating location rules for the post\_template plugin!

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

[Link to heading#](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#related)

## Related

Link copied

- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Custom location rules](https://www.advancedcustomfields.com/resources/custom-location-rules/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Features: [Conditional Logic](https://www.advancedcustomfields.com/resources/conditional-logic/)

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

[Got it](https://www.advancedcustomfields.com/resources/custom-location-rules-v5-8/#)