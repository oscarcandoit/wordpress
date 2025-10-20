---
url: https://www.advancedcustomfields.com/resources/user
scraped_at: 2025-10-20T02:28:20.992Z
---

# User

Last updated Feb 5, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#description)

## Description

Link copied

The User field allows the selection of one or more users.

This field type is useful for creating relationships between data objects. It stores its value as the WordPress user ID, and can return the full `WP_User` data on retrieval.

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#screenshots)

## Screenshots

Link copied

![Creating a User field in an ACF field group. The tab shown depicts General settings for the field: Field Type, Field Label, Field Name, Filter by Role, Return Format (a radio button with choices of User Array, User Object, and User ID), and Select Multiple.The other tabs are Validation, Presentation, Conditional Logic, and Advanced.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/User-Field-General-Settings-Revised-New.png)

Creating a User field in an ACF field group.

![The User field UI as it might appear to content editors, with users sorted by role. The Editor and Contributor roles are showing here, with two entries in each. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/User-Field-UI-1.png)

The User field UI as it might appear to content editors, with users sorted by role.

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#changelog)

## Changelog

Link copied

- Added `return_format` setting in version 5.6.9.

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#settings)

## Settings

Link copied

- **Filter by Role**


Filters the available users by one or more user roles. Defaults to an empty string.

- **Return Format**


Specifies the returned value format. Defaults to “User Array” in the plugin’s UI, and ‘array’ in PHP. “User Array” returns an array of user data, “User Object” returns the `WP_User` object, and “User ID” returns the user ID.

- **Select Multiple**


Allows content editors to select multiple values. Defaults to off.

- **Required**


Enabling this prevents the field from accepting empty values. Defaults to off.

- **Allow Null**


Allows an empty value to be saved. Defaults to off.

- **Instructions**


Shows instructions when submitting data.

- **Conditional Logic**


Enabling this setting allows you to customize the logic which determines if the current field should be visible. Groups of conditional logic rules can be created to allow for multiple and/or statements.

- **Bidirectional**


Found on the Advanced tab, enabling this setting allows you to update a value in the target fields for each value selected for this field, adding or removing the Post ID, Taxonomy ID, or User ID of the item being updated.


_For programmatic documentation, please see our [guide to registering fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)_.

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#display-a-single-selected-user)

### Display a single selected user

Link copied

This example demonstrates how to display a selected user (‘multiple’ = false, return\_format = ‘array’).

```php
<?php
$user = get_field("user_field");
if( $user ): ?>
<div class="author-box">
    <img src="<?php echo esc_attr($user['user_avatar']); ?>" alt="author-avatar" />
    <h3><?php echo $user['display_name']; ?></h3>
    <?php if( $user['user_description'] ): ?>
        <p><?php echo $user['user_description']; ?></p>
    <?php endif; ?>
</div>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#display-multiple-selected-users)

### Display multiple selected users

Link copied

This example demonstrates how to display multiple selected users in a list. (‘multiple’ = true, return\_format = ‘object’).

```php
<?php
$users = get_field("volunteers");
if( $users ): ?>
<ul class="volunteers-list">
    <?php foreach( $users as $user ): ?>
        <li>
            <img src="<?php echo esc_attr( get_avatar($user->ID) ); ?>" alt="author-avatar" />
            <a href="<?php echo esc_attr($user->user_url); ?>"><?php echo $user->display_name; ?></a>
        </li>
    <?php endforeach; ?>
</ul>
<?php endif; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/user/#related)

## Related

Link copied

- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)

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

[Got it](https://www.advancedcustomfields.com/resources/user/#)