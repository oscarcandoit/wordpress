---
url: https://developer.wordpress.org/reference/hooks/deleted_user
scraped_at: 2025-10-20T03:20:32.356Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/deleted_user/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

deleted\_user


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)deleted\_user

Search

# do\_action( ‘deleted\_user’, int$id, int\|null$reassign, WP\_User$user )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/deleted_user/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/deleted_user/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/deleted_user/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/deleted_user/#source)
- [Related](https://developer.wordpress.org/reference/hooks/deleted_user/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/deleted_user/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/deleted_user/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/deleted_user/#wp--skip-link--target)

Fires immediately after a user is deleted from the site.

## [Description](https://developer.wordpress.org/reference/hooks/deleted_user/\#description)

Note that on a Multisite installation the user may not have been deleted from the database depending on whether `wp_delete_user()` or `wpmu_delete_user()` was called.

## [Parameters](https://developer.wordpress.org/reference/hooks/deleted_user/\#parameters)

`$id` int

ID of the deleted user.

`$reassign` int\|null

ID of the user to reassign posts and links to.

Default null, for no reassignment.

`$user` [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)

[WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object of the deleted user.

## [More Information](https://developer.wordpress.org/reference/hooks/deleted_user/\#more-information)

The `deleted_user` action/hook can be used to perform additional actions after a user is deleted. For example, you can delete rows from custom tables created by a plugin.

This hook runs after a user is deleted. The hook `delete_user` (delete vs deleted) runs before a user is deleted. Choose the appropriate hook for your needs. If you need access to user meta or fields from the user table, use `delete_user`.

## [Source](https://developer.wordpress.org/reference/hooks/deleted_user/\#source)

`wp-admin/includes/user.php`
[Copy](https://developer.wordpress.org/reference/hooks/deleted_user/#)

```php
do_action( 'deleted_user', $id, $reassign, $user );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/user.php#L463) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/user.php#L463-L463)

## [Related](https://developer.wordpress.org/reference/hooks/deleted_user/\#related)

| Used by | Description |
| --- | --- |
| [wpmu\_delete\_user()](https://developer.wordpress.org/reference/functions/wpmu_delete_user/) `wp-admin/includes/ms.php` | Deletes a user and all of their posts from the network. |
| [wp\_delete\_user()](https://developer.wordpress.org/reference/functions/wp_delete_user/) `wp-admin/includes/user.php` | Delete user and optionally reassign posts and links to another user. |

## [Changelog](https://developer.wordpress.org/reference/hooks/deleted_user/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | Added the `$user` parameter. |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/deleted_user/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/deleted_user/#comment-content-4583)



The same issue exist for the documentation for the ‘delete\_user’ hook: ` do_action( 'delete_user', $id, $reassign, $user ); `





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fdeleted_user%2F%3Freplytocom%3D4583%23feedback-editor-4583)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fdeleted_user%2F) before being able to contribute a note or feedback.

Notifications