---
url: https://developer.wordpress.org/plugins/users/working-with-user-metadata
scraped_at: 2025-10-20T03:18:39.009Z
---

[Skip to content](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Working with User Metadata


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Users](https://developer.wordpress.org/plugins/users/)Working with User Metadata

Search

# Working with User Metadata

## In this article

Table of Contents

- [Introduction](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#introduction)
- [Manipulating User Metadata](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#manipulating-user-metadata)
  - [via a Form Field](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#via-a-form-field)
  - [Programmatically](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#programmatically)

[↑ Back to top](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#wp--skip-link--target)

## [Introduction](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#introduction)

WordPress’ `users` table was designed to contain only the essential information about the user.

As of WP 4.7 the table contains: `ID`, `user_login`, `user_pass`, `user_nicename`, `user_email`, `user_url`, `user_registered`, `user_activation_key`, `user_status` and `display_name`.

Because of this, to store additional data, the `usermeta` table was introduced, which can store any arbitrary amount of data about a user.

Both tables are tied together using one-to-many relationship based on the `ID` in the `users` table.

## [Manipulating User Metadata](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#manipulating-user-metadata)

There are two main ways for manipulating User Metadata.

1. A form field in the user’s profile screen.
2. Programmatically, via a function call.

### [via a Form Field](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#via-a-form-field)

The form field option is suitable for cases where the user will have access to the WordPress admin area, in which he will be able to view and edit profiles.

Before we dive into an example, it’s important to understand the hooks involved in the process and why they are there.

#### [show\_user\_profile hook](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#show_user_profile-hook)

This action hook is fired whenever a user edits **it’s own** user profile.

**Remember,** a user that doesn’t have the capability of editing his own profile won’t fire this hook.

#### [edit\_user\_profile hook](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#edit_user_profile-hook)

This action hook is fired whenever a user edits a user profile of **somebody else**.

**Remember,** a user that doesn’t have the capability for editing 3rd party profiles won’t fire this hook.

#### [Example Form Field](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#example-form-field)

In the example below we will be adding a birthday field to the all profile screens. Saving it to the database on profile updates.

``
[Expand code](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

[Copy](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

```php
/**
 * The field on the editing screens.
 *
 * @param $user WP_User user object
 */
function wporg_usermeta_form_field_birthday( $user ) {
    ?>
    <h3>It's Your Birthday</h3>
    <table class="form-table">
        <tr>
            <th>
                <label for="birthday">Birthday</label>
            </th>
            <td>
                <input type="date"
                       class="regular-text ltr"
                       id="birthday"
                       name="birthday"
                       value="<?= esc_attr( get_user_meta( $user->ID, 'birthday', true ) ) ?>"
                       title="Please use YYYY-MM-DD as the date format."
                       pattern="(19[0-9][0-9]|20[0-9][0-9])-(1[0-2]|0[1-9])-(3[01]|[21][0-9]|0[1-9])"
                       required>
                <p class="description">
                    Please enter your birthday date.
                </p>
            </td>
        </tr>
    </table>
    <?php
}

/**
 * The save action.
 *
 * @param $user_id int the ID of the current user.
 *
 * @return bool Meta ID if the key didn't exist, true on successful update, false on failure.
 */
function wporg_usermeta_form_field_birthday_update( $user_id ) {
    // check that the current user have the capability to edit the $user_id
    if ( ! current_user_can( 'edit_user', $user_id ) ) {
        return false;
    }

    // create/update user meta for the $user_id
    return update_user_meta(
        $user_id,
        'birthday',
        $_POST['birthday']
    );
}

// Add the field to user's own profile editing screen.
add_action(
    'show_user_profile',
    'wporg_usermeta_form_field_birthday'
);

// Add the field to user profile editing screen.
add_action(
    'edit_user_profile',
    'wporg_usermeta_form_field_birthday'
);

// Add the save action to user's own profile editing screen update.
add_action(
    'personal_options_update',
    'wporg_usermeta_form_field_birthday_update'
);

// Add the save action to user profile editing screen update.
add_action(
    'edit_user_profile_update',
    'wporg_usermeta_form_field_birthday_update'
);
```

### [Programmatically](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#programmatically)

This option is suitable for cases where you’re building a custom user area and/or plan to disable access to the WordPress admin area.

The functions available for manipulating User Metadata are: `[add\_user\_meta()](https://developer.wordpress.org/reference/functions/add_user_meta/)`, `[update\_user\_meta()](https://developer.wordpress.org/reference/functions/update_user_meta/)`, `[delete\_user\_meta()](https://developer.wordpress.org/reference/functions/delete_user_meta/)` and `[get\_user\_meta()](https://developer.wordpress.org/reference/functions/get_user_meta/)`.

#### [Add](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#add)

``
[Copy](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

```php
add_user_meta(
    int $user_id,
    string $meta_key,
    mixed $meta_value,
    bool $unique = false
);
```

Please refer to the Function Reference about `[add\_user\_meta()](https://developer.wordpress.org/reference/functions/add_user_meta/)` for full explanation about the used parameters.

#### [Update](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#update)

``
[Copy](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

```php
update_user_meta(
    int $user_id,
    string $meta_key,
    mixed $meta_value,
    mixed $prev_value = ''
);
```

Please refer to the Function Reference about `[update\_user\_meta()](https://developer.wordpress.org/reference/functions/update_user_meta/)` for full explanation about the used parameters.

#### [Delete](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#delete)

``
[Copy](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

```php
delete_user_meta(
    int $user_id,
    string $meta_key,
    mixed $meta_value = ''
);
```

Please refer to the Function Reference about `[delete\_user\_meta()](https://developer.wordpress.org/reference/functions/delete_user_meta/)` for full explanation about the used parameters.

#### [Get](https://developer.wordpress.org/plugins/users/working-with-user-metadata/\#get)

``
[Copy](https://developer.wordpress.org/plugins/users/working-with-user-metadata/#)

```php
get_user_meta(
    int $user_id,
    string $key = '',
    bool $single = false
);
```

Please refer to the Function Reference about `[get\_user\_meta()](https://developer.wordpress.org/reference/functions/get_user_meta/)` for full explanation about the used parameters.

Please note, if you pass only the `$user_id`, the function will retrieve all Metadata as an associative array.

You can render User Metadata anywhere in your plugin or theme.

First published

September 24, 2014

Last updated

November 17, 2022

[PreviousRoles and CapabilitiesPrevious: Roles and Capabilities](https://developer.wordpress.org/plugins/users/roles-and-capabilities/)

[NextWorking with UsersNext: Working with Users](https://developer.wordpress.org/plugins/users/working-with-users/)

Notifications