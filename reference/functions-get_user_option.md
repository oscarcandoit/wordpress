---
url: https://developer.wordpress.org/reference/functions/get_user_option
scraped_at: 2025-10-20T03:25:45.423Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_user_option/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_user\_option()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_user\_option()

Search

# get\_user\_option( string$option, int$user, string$deprecated = '' ): mixed

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_user_option/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_user_option/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_user_option/#return)
- [More Information](https://developer.wordpress.org/reference/functions/get_user_option/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/get_user_option/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_user_option/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_user_option/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_user_option/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_user_option/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_user_option/#wp--skip-link--target)

Retrieves user option that can be either per Site or per Network.

## [Description](https://developer.wordpress.org/reference/functions/get_user_option/\#description)

If the user ID is not given, then the current user will be used instead. If the user ID is given, then the user data will be retrieved. The filter for the result, will also pass the original option name and finally the user data object as the third parameter.

The option will first check for the per site name and then the per Network name.

## [Parameters](https://developer.wordpress.org/reference/functions/get_user_option/\#parameters)

`$option` stringrequired

User option name.

`$user` intoptional

User ID.

`$deprecated` stringoptional

Use [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) to check for an option in the options table.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/get_user_option/\#return)

mixed User option value on success, false on failure.

## [More Information](https://developer.wordpress.org/reference/functions/get_user_option/\#more-information)

##### [Usage:](https://developer.wordpress.org/reference/functions/get_user_option/\#usage)

`wp-includes/user.php`
[Copy](https://developer.wordpress.org/reference/functions/get_user_option/#)

```php
get_user_option( $option, $user );
```

## [Source](https://developer.wordpress.org/reference/functions/get_user_option/\#source)

`wp-includes/user.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_user_option/#)

[Copy](https://developer.wordpress.org/reference/functions/get_user_option/#)

```php
function get_user_option( $option, $user = 0, $deprecated = '' ) {
	global $wpdb;

	if ( ! empty( $deprecated ) ) {
		_deprecated_argument( __FUNCTION__, '3.0.0' );
	}

	if ( empty( $user ) ) {
		$user = get_current_user_id();
	}

	$user = get_userdata( $user );
	if ( ! $user ) {
		return false;
	}

	$prefix = $wpdb->get_blog_prefix();
	if ( $user->has_prop( $prefix . $option ) ) { // Blog-specific.
		$result = $user->get( $prefix . $option );
	} elseif ( $user->has_prop( $option ) ) { // User-specific and cross-blog.
		$result = $user->get( $option );
	} else {
		$result = false;
	}

	/**
	 * Filters a specific user option value.
	 *
	 * The dynamic portion of the hook name, `$option`, refers to the user option name.
	 *
	 * @since 2.5.0
	 *
	 * @param mixed   $result Value for the user's option.
	 * @param string  $option Name of the option being retrieved.
	 * @param WP_User $user   WP_User object of the user whose option is being retrieved.
	 */
	return apply_filters( "get_user_option_{$option}", $result, $option, $user );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/user.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/user.php#L736) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/user.php#L736-L773)

## [Hooks](https://developer.wordpress.org/reference/functions/get_user_option/\#hooks)

[apply\_filters( “get\_user\_option\_{$option}”, mixed$result, string$option, WP\_User$user )](https://developer.wordpress.org/reference/hooks/get_user_option_option/)

Filters a specific user option value.

## [Related](https://developer.wordpress.org/reference/functions/get_user_option/\#related)

| Uses | Description |
| --- | --- |
| [wpdb::get\_blog\_prefix()](https://developer.wordpress.org/reference/classes/wpdb/get_blog_prefix/) `wp-includes/class-wpdb.php` | Gets blog prefix. |
| [get\_userdata()](https://developer.wordpress.org/reference/functions/get_userdata/) `wp-includes/pluggable.php` | Retrieves user info by user ID. |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_current\_user\_id()](https://developer.wordpress.org/reference/functions/get_current_user_id/) `wp-includes/user.php` | Gets the current user’s ID. |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_user_option/#) [Show less](https://developer.wordpress.org/reference/functions/get_user_option/#)

| Used by | Description |
| --- | --- |
| [wp\_localize\_community\_events()](https://developer.wordpress.org/reference/functions/wp_localize_community_events/) `wp-includes/script-loader.php` | Localizes community events data that needs to be passed to dashboard.js. |
| [wp\_ajax\_get\_community\_events()](https://developer.wordpress.org/reference/functions/wp_ajax_get_community_events/) `wp-admin/includes/ajax-actions.php` | Handles Ajax requests for community events |
| [wp\_edit\_attachments\_query\_vars()](https://developer.wordpress.org/reference/functions/wp_edit_attachments_query_vars/) `wp-admin/includes/post.php` | Returns the query variables for the current attachments request. |
| [WP\_Screen::render\_per\_page\_options()](https://developer.wordpress.org/reference/classes/wp_screen/render_per_page_options/) `wp-admin/includes/class-wp-screen.php` | Renders the items per page option. |
| [WP\_Screen::render\_screen\_meta()](https://developer.wordpress.org/reference/classes/wp_screen/render_screen_meta/) `wp-admin/includes/class-wp-screen.php` | Renders the screen’s help section. |
| [get\_hidden\_columns()](https://developer.wordpress.org/reference/functions/get_hidden_columns/) `wp-admin/includes/screen.php` | Get a list of hidden columns. |
| [get\_hidden\_meta\_boxes()](https://developer.wordpress.org/reference/functions/get_hidden_meta_boxes/) `wp-admin/includes/screen.php` | Gets an array of IDs of hidden meta boxes. |
| [WP\_List\_Table::get\_items\_per\_page()](https://developer.wordpress.org/reference/classes/wp_list_table/get_items_per_page/) `wp-admin/includes/class-wp-list-table.php` | Gets the number of items to display on a single page. |
| [admin\_color\_scheme\_picker()](https://developer.wordpress.org/reference/functions/admin_color_scheme_picker/) `wp-admin/includes/misc.php` | Displays the default admin color scheme picker (Used in user-edit.php). |
| [wp\_color\_scheme\_settings()](https://developer.wordpress.org/reference/functions/wp_color_scheme_settings/) `wp-admin/includes/misc.php` |  |
| [install\_plugins\_favorites\_form()](https://developer.wordpress.org/reference/functions/install_plugins_favorites_form/) `wp-admin/includes/plugin-install.php` | Shows a username form for the favorites page. |
| [display\_plugins\_table()](https://developer.wordpress.org/reference/functions/display_plugins_table/) `wp-admin/includes/plugin-install.php` | Displays plugin content based on plugin list. |
| [wp\_dashboard\_quick\_press()](https://developer.wordpress.org/reference/functions/wp_dashboard_quick_press/) `wp-admin/includes/dashboard.php` | Displays the Quick Draft widget. |
| [default\_password\_nag\_handler()](https://developer.wordpress.org/reference/functions/default_password_nag_handler/) `wp-admin/includes/user.php` |  |
| [default\_password\_nag\_edit\_user()](https://developer.wordpress.org/reference/functions/default_password_nag_edit_user/) `wp-admin/includes/user.php` |  |
| [default\_password\_nag()](https://developer.wordpress.org/reference/functions/default_password_nag/) `wp-admin/includes/user.php` |  |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [do\_meta\_boxes()](https://developer.wordpress.org/reference/functions/do_meta_boxes/) `wp-admin/includes/template.php` | Meta-Box template function. |
| [wp\_edit\_posts\_query()](https://developer.wordpress.org/reference/functions/wp_edit_posts_query/) `wp-admin/includes/post.php` | Runs the query to fetch the posts for listing on the edit posts page. |
| [postbox\_classes()](https://developer.wordpress.org/reference/functions/postbox_classes/) `wp-admin/includes/post.php` | Returns the list of classes to be used by a meta box. |
| [wp\_ajax\_query\_themes()](https://developer.wordpress.org/reference/functions/wp_ajax_query_themes/) `wp-admin/includes/ajax-actions.php` | Handles getting themes from [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) via AJAX. |
| [wp\_nav\_menu\_setup()](https://developer.wordpress.org/reference/functions/wp_nav_menu_setup/) `wp-admin/includes/nav-menu.php` | Register nav menu meta boxes and advanced menu items. |
| [wp\_initial\_nav\_menu\_meta\_boxes()](https://developer.wordpress.org/reference/functions/wp_initial_nav_menu_meta_boxes/) `wp-admin/includes/nav-menu.php` | Limit the amount of meta boxes to pages, posts, links, and categories for first time users. |
| [enqueue\_comment\_hotkeys\_js()](https://developer.wordpress.org/reference/functions/enqueue_comment_hotkeys_js/) `wp-admin/includes/comment.php` | Enqueues comment shortcuts jQuery script. |
| [auth\_redirect()](https://developer.wordpress.org/reference/functions/auth_redirect/) `wp-includes/pluggable.php` | Checks if a user is logged in, if not it redirects them to the login page. |
| [user\_can\_richedit()](https://developer.wordpress.org/reference/functions/user_can_richedit/) `wp-includes/general-template.php` | Determines whether the user can access the visual editor. |
| [\_get\_admin\_bar\_pref()](https://developer.wordpress.org/reference/functions/_get_admin_bar_pref/) `wp-includes/admin-bar.php` | Retrieves the admin bar display preference of a user. |
| [wp\_user\_settings()](https://developer.wordpress.org/reference/functions/wp_user_settings/) `wp-includes/option.php` | Saves and restores user interface settings stored in a cookie. |
| [get\_all\_user\_settings()](https://developer.wordpress.org/reference/functions/get_all_user_settings/) `wp-includes/option.php` | Retrieves all user interface settings. |
| [wp\_style\_loader\_src()](https://developer.wordpress.org/reference/functions/wp_style_loader_src/) `wp-includes/script-loader.php` | Administration Screen CSS for changing the styles. |

[Show 25 more](https://developer.wordpress.org/reference/functions/get_user_option/#) [Show less](https://developer.wordpress.org/reference/functions/get_user_option/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_user_option/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_user_option/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/get_user_option/#comment-content-1157)



**Basic Example**





`wp-includes/user.php`
[Copy](https://developer.wordpress.org/reference/functions/get_user_option/#)




```php
$bar = get_user_option( 'show_admin_bar_front', get_current_user_id() );

if (  $bar == 'true' ) {
   	echo 'The admin bar is enabled';
} else {
   	echo 'The admin bar is disabled';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_user_option%2F%3Freplytocom%3D1157%23feedback-editor-1157)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_user_option%2F) before being able to contribute a note or feedback.

Notifications