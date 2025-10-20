---
url: https://developer.wordpress.org/reference/functions/get_admin_url
scraped_at: 2025-10-20T03:19:50.455Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_admin_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_admin\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_admin\_url()

Search

# get\_admin\_url( int\|null$blog\_id = null, string$path = '', string$scheme = 'admin' ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_admin_url/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_admin_url/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_admin_url/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_admin_url/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_admin_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_admin_url/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_admin_url/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_admin_url/#wp--skip-link--target)

Retrieves the URL to the admin area for a given site.

## [Parameters](https://developer.wordpress.org/reference/functions/get_admin_url/\#parameters)

`$blog_id` int\|nulloptional

Site ID. Default null (current site).

Default: `null`

`$path` stringoptional

Path relative to the admin URL.

Default: `''`

`$scheme` stringoptional

The scheme to use. Accepts `'http'` or `'https'`, to force those schemes. Default `'admin'`, which obeys [force\_ssl\_admin()](https://developer.wordpress.org/reference/functions/force_ssl_admin/) and [is\_ssl()](https://developer.wordpress.org/reference/functions/is_ssl/) .

Default: `'admin'`

## [Return](https://developer.wordpress.org/reference/functions/get_admin_url/\#return)

string Admin URL link with optional path appended.

## [Source](https://developer.wordpress.org/reference/functions/get_admin_url/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_admin_url/#)

[Copy](https://developer.wordpress.org/reference/functions/get_admin_url/#)

```php
function get_admin_url( $blog_id = null, $path = '', $scheme = 'admin' ) {
	$url = get_site_url( $blog_id, 'wp-admin/', $scheme );

	if ( $path && is_string( $path ) ) {
		$url .= ltrim( $path, '/' );
	}

	/**
	 * Filters the admin area URL.
	 *
	 * @since 2.8.0
	 * @since 5.8.0 The `$scheme` parameter was added.
	 *
	 * @param string      $url     The complete admin area URL including scheme and path.
	 * @param string      $path    Path relative to the admin area URL. Blank string if no path is specified.
	 * @param int|null    $blog_id Site ID, or null for the current site.
	 * @param string|null $scheme  The scheme to use. Accepts 'http', 'https',
	 *                             'admin', or null. Default 'admin', which obeys force_ssl_admin() and is_ssl().
	 */
	return apply_filters( 'admin_url', $url, $path, $blog_id, $scheme );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L3580) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L3580-L3600)

## [Hooks](https://developer.wordpress.org/reference/functions/get_admin_url/\#hooks)

[apply\_filters( ‘admin\_url’, string$url, string$path, int\|null$blog\_id, string\|null$scheme )](https://developer.wordpress.org/reference/hooks/admin_url/)

Filters the admin area URL.

## [Related](https://developer.wordpress.org/reference/functions/get_admin_url/\#related)

| Uses | Description |
| --- | --- |
| [get\_site\_url()](https://developer.wordpress.org/reference/functions/get_site_url/) `wp-includes/link-template.php` | Retrieves the URL for a given site where WordPress application files (e.g. wp-blog-header.php or the wp-admin/ folder) are accessible. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [wp\_load\_press\_this()](https://developer.wordpress.org/reference/functions/wp_load_press_this/) `wp-admin/press-this.php` |  |
| [WP\_MS\_Sites\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/handle_row_actions/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Generates and displays row action links. |
| [\_access\_denied\_splash()](https://developer.wordpress.org/reference/functions/_access_denied_splash/) `wp-admin/includes/ms.php` | Displays an access denied message when a user tries to view a site’s dashboard they do not have access to. |
| [get\_dashboard\_url()](https://developer.wordpress.org/reference/functions/get_dashboard_url/) `wp-includes/link-template.php` | Retrieves the URL to the user’s dashboard. |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current site. |
| [wp\_admin\_bar\_my\_sites\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/) `wp-includes/admin-bar.php` | Adds the “My Sites/\[Site Name\]” menu and all submenus. |
| [wp\_xmlrpc\_server::initialise\_blog\_option\_info()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/initialise_blog_option_info/) `wp-includes/class-wp-xmlrpc-server.php` | Sets up blog options property. |

[Show 2 more](https://developer.wordpress.org/reference/functions/get_admin_url/#) [Show less](https://developer.wordpress.org/reference/functions/get_admin_url/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_admin_url/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_admin_url/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/get_admin_url/#comment-content-877)



This will return the url to wp-admin **with a slash**:



Example: `http://www.mysite.com/wp-admin/`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_admin_url%2F%3Freplytocom%3D877%23feedback-editor-877)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_admin_url/#comment-content-5700)



To get the URL for the network admin, use [`network_admin_url()`](https://developer.wordpress.org/reference/functions/network_admin_url/).





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_admin_url%2F%3Freplytocom%3D5700%23feedback-editor-5700)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_admin_url%2F) before being able to contribute a note or feedback.

Notifications