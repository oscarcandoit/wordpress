---
url: https://developer.wordpress.org/reference/hooks/insert_user_meta
scraped_at: 2025-10-20T03:14:11.708Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/insert_user_meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

insert\_user\_meta


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)insert\_user\_meta

Search

# apply\_filters( ‘insert\_user\_meta’, array$meta, WP\_User$user, bool$update, array$userdata )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/insert_user_meta/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/insert_user_meta/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/insert_user_meta/#source)
- [Related](https://developer.wordpress.org/reference/hooks/insert_user_meta/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/insert_user_meta/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/insert_user_meta/#wp--skip-link--target)

Filters a user’s meta values and keys immediately after the user is created or updated and before any user meta is inserted or updated.

## [Description](https://developer.wordpress.org/reference/hooks/insert_user_meta/\#description)

Does not include contact methods. These are added using `wp_get_user_contact_methods( $user )`.

For custom meta fields, see the [‘insert\_custom\_user\_meta’](https://developer.wordpress.org/reference/hooks/insert_custom_user_meta/) filter.

## [Parameters](https://developer.wordpress.org/reference/hooks/insert_user_meta/\#parameters)

`$meta` array

Default meta values and keys for the user.

- `nickname` string
The user’s nickname. Default is the user’s username.

- `first_name` string
The user’s first name.

- `last_name` string
The user’s last name.

- `description` string
The user’s description.

- `rich_editing` string
Whether to enable the rich-editor for the user. Default `'true'`.

- `syntax_highlighting` string
Whether to enable the rich code editor for the user. Default `'true'`.

- `comment_shortcuts` string
Whether to enable keyboard shortcuts for the user. Default `'false'`.

- `admin_color` string
The color scheme for a user’s admin screen. Default `'fresh'`.

- `use_ssl` int\|bool
Whether to force SSL on the user’s admin area. `0|false` if SSL is not forced.

- `show_admin_bar_front` string
Whether to show the admin bar on the front end for the user.


Default `'true'`.

- `locale` string
User’s locale. Default empty.


`$user` [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)

User object.

`$update` bool

Whether the user is being updated rather than created.

`$userdata` array

The raw array of data passed to [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) .More Arguments from wp\_insert\_user( … $userdata )An array, object, or [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object of user data arguments.

- `ID` int
User ID. If supplied, the user will be updated.

- `user_pass` string
The plain-text user password for new users.


Hashed password for existing users.

- `user_login` string
The user’s login username.

- `user_nicename` string
The URL-friendly user name.

- `user_url` string
The user URL.

- `user_email` string
The user email address.

- `display_name` string
The user’s display name.


Default is the user’s username.

- `nickname` string
The user’s nickname.


Default is the user’s username.

- `first_name` string
The user’s first name. For new users, will be used to build the first part of the user’s display name if `$display_name` is not specified.

- `last_name` string
The user’s last name. For new users, will be used to build the second part of the user’s display name if `$display_name` is not specified.

- `description` string
The user’s biographical description.

- `rich_editing` string
Whether to enable the rich-editor for the user.


Accepts `'true'` or `'false'` as a string literal, not boolean. Default `'true'`.

- `syntax_highlighting` string
Whether to enable the rich code editor for the user.


Accepts `'true'` or `'false'` as a string literal, not boolean. Default `'true'`.

- `comment_shortcuts` string
Whether to enable comment moderation keyboard shortcuts for the user. Accepts `'true'` or `'false'` as a string literal, not boolean. Default `'false'`.

- `admin_color` string
Admin color scheme for the user. Default `'fresh'`.

- `use_ssl` bool
Whether the user should always access the admin over https. Default false.

- `user_registered` string
Date the user registered in UTC. Format is ‘Y-m-d H:i:s’.

- `user_activation_key` string
Password reset key. Default empty.

- `spam` bool
Multisite only. Whether the user is marked as spam.


Default false.

- `show_admin_bar_front` string
Whether to display the Admin Bar for the user on the site’s front end. Accepts `'true'` or `'false'` as a string literal, not boolean. Default `'true'`.

- `role` string
User’s role.

- `locale` string
User’s locale. Default empty.

- `meta_input` array
Array of custom user meta values keyed by meta key.


Default empty.


## [Source](https://developer.wordpress.org/reference/hooks/insert_user_meta/\#source)

`wp-includes/user.php`
[Copy](https://developer.wordpress.org/reference/hooks/insert_user_meta/#)

```php
$meta = apply_filters( 'insert_user_meta', $meta, $user, $update, $userdata );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/user.php#L2527) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/user.php#L2527-L2527)

## [Related](https://developer.wordpress.org/reference/hooks/insert_user_meta/\#related)

| Used by | Description |
| --- | --- |
| [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) `wp-includes/user.php` | Inserts a user into the database. |

## [Changelog](https://developer.wordpress.org/reference/hooks/insert_user_meta/\#changelog)

| Version | Description |
| --- | --- |
| [5.8.0](https://developer.wordpress.org/reference/since/5.8.0/) | The `$userdata` parameter was added. |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Finsert_user_meta%2F) before being able to contribute a note or feedback.

Notifications