---
url: https://developer.wordpress.org/reference/hooks/admin_title
scraped_at: 2025-10-20T03:17:34.380Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/admin_title/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

admin\_title


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)admin\_title

Search

# apply\_filters( ‘admin\_title’, string$admin\_title, string$title )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/admin_title/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/admin_title/#source)
- [Changelog](https://developer.wordpress.org/reference/hooks/admin_title/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/admin_title/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/admin_title/#wp--skip-link--target)

Filters the title tag content for an admin page.

## [Parameters](https://developer.wordpress.org/reference/hooks/admin_title/\#parameters)

`$admin_title` string

The page title, with extra context added.

`$title` string

The original page title.

## [Source](https://developer.wordpress.org/reference/hooks/admin_title/\#source)

`wp-admin/admin-header.php`
[Copy](https://developer.wordpress.org/reference/hooks/admin_title/#)

```php
$admin_title = apply_filters( 'admin_title', $admin_title, $title );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/admin-header.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/admin-header.php#L89) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/admin-header.php#L89-L89)

## [Changelog](https://developer.wordpress.org/reference/hooks/admin_title/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/admin_title/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/admin_title/#comment-content-7118)



How to customize the WordPress admin title using the `apply_filters` hook with multiple conditions. The `admin_title` filter allows you to modify the title displayed in the admin area based on different criteria.





`wp-admin/admin-header.php`
[Expand code](https://developer.wordpress.org/reference/hooks/admin_title/#)

[Copy](https://developer.wordpress.org/reference/hooks/admin_title/#)




```php
function wpdocs_admin_title_filter( $admin_title, $title ) {
       // Example condition: Modify title if user is on the dashboard
       if ( is_admin() && 'Dashboard' === $title ) {
           $admin_title = __( 'welcome to Dashboard' );
       }

       // Example condition: Modify title for specific post type edit page
       if ( is_admin() && isset( $_GET['post_type'] ) && 'product' === $_GET['post_type'] ) {
           $admin_title = __( 'Editing Products' ) . ' - ' . $title;
       }

       // Example condition: Modify title based on user role
       if ( is_admin() && current_user_can( 'administrator' ) ) {
           $admin_title = __( 'Admin:' ) . ' ' . $title;
       }

       return $admin_title;
}

add_filter( 'admin_title', 'wpdocs_admin_title_filter', 10, 2 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_title%2F%3Freplytocom%3D7118%23feedback-editor-7118)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_title%2F) before being able to contribute a note or feedback.

Notifications