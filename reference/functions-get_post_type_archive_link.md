---
url: https://developer.wordpress.org/reference/functions/get_post_type_archive_link
scraped_at: 2025-10-20T03:18:59.797Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_post\_type\_archive\_link()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_post\_type\_archive\_link()

Search

# get\_post\_type\_archive\_link( string$post\_type ): string\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#wp--skip-link--target)

Retrieves the permalink for a post type archive.

## [Parameters](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#parameters)

`$post_type` stringrequired

Post type.

## [Return](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#return)

string\|false The post type archive permalink. False if the post type does not exist or does not have an archive.

## [Source](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)

[Copy](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)

```php
function get_post_type_archive_link( $post_type ) {
	global $wp_rewrite;

	$post_type_obj = get_post_type_object( $post_type );

	if ( ! $post_type_obj ) {
		return false;
	}

	if ( 'post' === $post_type ) {
		$show_on_front  = get_option( 'show_on_front' );
		$page_for_posts = get_option( 'page_for_posts' );

		if ( 'page' === $show_on_front && $page_for_posts ) {
			$link = get_permalink( $page_for_posts );
		} else {
			$link = get_home_url();
		}
		/** This filter is documented in wp-includes/link-template.php */
		return apply_filters( 'post_type_archive_link', $link, $post_type );
	}

	if ( ! $post_type_obj->has_archive ) {
		return false;
	}

	if ( get_option( 'permalink_structure' ) && is_array( $post_type_obj->rewrite ) ) {
		$struct = ( true === $post_type_obj->has_archive ) ? $post_type_obj->rewrite['slug'] : $post_type_obj->has_archive;
		if ( $post_type_obj->rewrite['with_front'] ) {
			$struct = $wp_rewrite->front . $struct;
		} else {
			$struct = $wp_rewrite->root . $struct;
		}
		$link = home_url( user_trailingslashit( $struct, 'post_type_archive' ) );
	} else {
		$link = home_url( '?post_type=' . $post_type );
	}

	/**
	 * Filters the post type archive permalink.
	 *
	 * @since 3.1.0
	 *
	 * @param string $link      The post type archive permalink.
	 * @param string $post_type Post type name.
	 */
	return apply_filters( 'post_type_archive_link', $link, $post_type );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L1302) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L1302-L1349)

## [Hooks](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#hooks)

[apply\_filters( ‘post\_type\_archive\_link’, string$link, string$post\_type )](https://developer.wordpress.org/reference/hooks/post_type_archive_link/)

Filters the post type archive permalink.

## [Related](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#related)

| Uses | Description |
| --- | --- |
| [get\_home\_url()](https://developer.wordpress.org/reference/functions/get_home_url/) `wp-includes/link-template.php` | Retrieves the URL for a given site where the front end is accessible. |
| [user\_trailingslashit()](https://developer.wordpress.org/reference/functions/user_trailingslashit/) `wp-includes/link-template.php` | Retrieves a trailing-slashed string if the site is set for adding trailing slashes. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |
| [get\_permalink()](https://developer.wordpress.org/reference/functions/get_permalink/) `wp-includes/link-template.php` | Retrieves the full permalink for the current post or post ID. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [get\_post\_type\_object()](https://developer.wordpress.org/reference/functions/get_post_type_object/) `wp-includes/post.php` | Retrieves a post type object by name. |

[Show 5 more](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#) [Show less](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)

| Used by | Description |
| --- | --- |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::value\_as\_wp\_post\_nav\_menu\_item()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/value_as_wp_post_nav_menu_item/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Get the value emulated into a [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) and set up as a nav\_menu\_item. |
| [WP\_Customize\_Nav\_Menus::load\_available\_items\_query()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/load_available_items_query/) `wp-includes/class-wp-customize-nav-menus.php` | Performs the post\_type and taxonomy queries for loading available menu items. |
| [wp\_nav\_menu\_item\_post\_type\_meta\_box()](https://developer.wordpress.org/reference/functions/wp_nav_menu_item_post_type_meta_box/) `wp-admin/includes/nav-menu.php` | Displays a meta box for a post type menu item. |
| [wp\_list\_categories()](https://developer.wordpress.org/reference/functions/wp_list_categories/) `wp-includes/category-template.php` | Displays or retrieves the HTML list of categories. |
| [get\_post\_type\_archive\_feed\_link()](https://developer.wordpress.org/reference/functions/get_post_type_archive_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for a post type archive feed. |
| [wp\_admin\_bar\_edit\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_edit_menu/) `wp-includes/admin-bar.php` | Provides an edit link for posts and terms. |
| [wp\_setup\_nav\_menu\_item()](https://developer.wordpress.org/reference/functions/wp_setup_nav_menu_item/) `wp-includes/nav-menu.php` | Decorates a menu item object with the shared navigation menu item properties. |

[Show 2 more](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#) [Show less](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#changelog)

| Version | Description |
| --- | --- |
| [4.5.0](https://developer.wordpress.org/reference/since/4.5.0/) | Support for posts was added. |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#comment-content-3526)



In the event that `get_post_type_archive_link()` does not work or returns false, double check if you have included the argument `has_archive => true` when registering your post type.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_type_archive_link%2F%3Freplytocom%3D3526%23feedback-editor-3526)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#comment-content-541)



**Example**





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)




```php
<a href="<?php echo get_post_type_archive_link( 'movies' ); ?>">Movies Archive</a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_type_archive_link%2F%3Freplytocom%3D541%23feedback-editor-541)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#comment-content-6570)



This is the example for WordPress function that returns the URL of the archive page for a specific post type. It is used to retrieve the permalink for the post type’s archive. (For example, get the archive link for post type is **“Book”**)





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/#)




```php
$archive_link = get_post_type_archive_link( 'book' );

if ( $archive_link ) {
       echo 'Archive Link: <a href="' . esc_url( $archive_link ) . '" rel="nofollow ugc">Books Archive</a>';
} else {
       echo 'The "book" post type does not have an archive.';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_type_archive_link%2F%3Freplytocom%3D6570%23feedback-editor-6570)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_type_archive_link%2F) before being able to contribute a note or feedback.

Notifications