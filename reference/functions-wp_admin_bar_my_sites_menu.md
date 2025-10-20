---
url: https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu
scraped_at: 2025-10-20T03:21:07.562Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_admin\_bar\_my\_sites\_menu()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_admin\_bar\_my\_sites\_menu()

Search

# wp\_admin\_bar\_my\_sites\_menu( WP\_Admin\_Bar$wp\_admin\_bar )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#wp--skip-link--target)

Adds the “My Sites/\[Site Name\]” menu and all submenus.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/\#parameters)

`$wp_admin_bar` [WP\_Admin\_Bar](https://developer.wordpress.org/reference/classes/wp_admin_bar/)required

The [WP\_Admin\_Bar](https://developer.wordpress.org/reference/classes/wp_admin_bar/) instance.

## [Source](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/\#source)

`wp-includes/admin-bar.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#)

```php
function wp_admin_bar_my_sites_menu( $wp_admin_bar ) {
	// Don't show for logged out users or single site mode.
	if ( ! is_user_logged_in() || ! is_multisite() ) {
		return;
	}

	// Show only when the user has at least one site, or they're a super admin.
	if ( count( $wp_admin_bar->user->blogs ) < 1 && ! current_user_can( 'manage_network' ) ) {
		return;
	}

	if ( $wp_admin_bar->user->active_blog ) {
		$my_sites_url = get_admin_url( $wp_admin_bar->user->active_blog->blog_id, 'my-sites.php' );
	} else {
		$my_sites_url = admin_url( 'my-sites.php' );
	}

	$wp_admin_bar->add_node(
		array(
			'id'    => 'my-sites',
			'title' => __( 'My Sites' ),
			'href'  => $my_sites_url,
		)
	);

	if ( current_user_can( 'manage_network' ) ) {
		$wp_admin_bar->add_group(
			array(
				'parent' => 'my-sites',
				'id'     => 'my-sites-super-admin',
			)
		);

		$wp_admin_bar->add_node(
			array(
				'parent' => 'my-sites-super-admin',
				'id'     => 'network-admin',
				'title'  => __( 'Network Admin' ),
				'href'   => network_admin_url(),
			)
		);

		$wp_admin_bar->add_node(
			array(
				'parent' => 'network-admin',
				'id'     => 'network-admin-d',
				'title'  => __( 'Dashboard' ),
				'href'   => network_admin_url(),
			)
		);

		if ( current_user_can( 'manage_sites' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'network-admin',
					'id'     => 'network-admin-s',
					'title'  => __( 'Sites' ),
					'href'   => network_admin_url( 'sites.php' ),
				)
			);
		}

		if ( current_user_can( 'manage_network_users' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'network-admin',
					'id'     => 'network-admin-u',
					'title'  => __( 'Users' ),
					'href'   => network_admin_url( 'users.php' ),
				)
			);
		}

		if ( current_user_can( 'manage_network_themes' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'network-admin',
					'id'     => 'network-admin-t',
					'title'  => __( 'Themes' ),
					'href'   => network_admin_url( 'themes.php' ),
				)
			);
		}

		if ( current_user_can( 'manage_network_plugins' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'network-admin',
					'id'     => 'network-admin-p',
					'title'  => __( 'Plugins' ),
					'href'   => network_admin_url( 'plugins.php' ),
				)
			);
		}

		if ( current_user_can( 'manage_network_options' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'network-admin',
					'id'     => 'network-admin-o',
					'title'  => __( 'Settings' ),
					'href'   => network_admin_url( 'settings.php' ),
				)
			);
		}
	}

	// Add site links.
	$wp_admin_bar->add_group(
		array(
			'parent' => 'my-sites',
			'id'     => 'my-sites-list',
			'meta'   => array(
				'class' => current_user_can( 'manage_network' ) ? 'ab-sub-secondary' : '',
			),
		)
	);

	/**
	 * Filters whether to show the site icons in toolbar.
	 *
	 * Returning false to this hook is the recommended way to hide site icons in the toolbar.
	 * A truthy return may have negative performance impact on large multisites.
	 *
	 * @since 6.0.0
	 *
	 * @param bool $show_site_icons Whether site icons should be shown in the toolbar. Default true.
	 */
	$show_site_icons = apply_filters( 'wp_admin_bar_show_site_icons', true );

	foreach ( (array) $wp_admin_bar->user->blogs as $blog ) {
		switch_to_blog( $blog->userblog_id );

		if ( true === $show_site_icons && has_site_icon() ) {
			$blavatar = sprintf(
				'<img class="blavatar" src="%s" srcset="%s 2x" alt="" width="16" height="16"%s />',
				esc_url( get_site_icon_url( 16 ) ),
				esc_url( get_site_icon_url( 32 ) ),
				( wp_lazy_loading_enabled( 'img', 'site_icon_in_toolbar' ) ? ' loading="lazy"' : '' )
			);
		} else {
			$blavatar = '<div class="blavatar"></div>';
		}

		$blogname = $blog->blogname;

		if ( ! $blogname ) {
			$blogname = preg_replace( '#^(https?://)?(www.)?#', '', get_home_url() );
		}

		$menu_id = 'blog-' . $blog->userblog_id;

		if ( current_user_can( 'read' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'my-sites-list',
					'id'     => $menu_id,
					'title'  => $blavatar . $blogname,
					'href'   => admin_url(),
				)
			);

			$wp_admin_bar->add_node(
				array(
					'parent' => $menu_id,
					'id'     => $menu_id . '-d',
					'title'  => __( 'Dashboard' ),
					'href'   => admin_url(),
				)
			);
		} else {
			$wp_admin_bar->add_node(
				array(
					'parent' => 'my-sites-list',
					'id'     => $menu_id,
					'title'  => $blavatar . $blogname,
					'href'   => home_url(),
				)
			);
		}

		if ( current_user_can( get_post_type_object( 'post' )->cap->create_posts ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => $menu_id,
					'id'     => $menu_id . '-n',
					'title'  => get_post_type_object( 'post' )->labels->new_item,
					'href'   => admin_url( 'post-new.php' ),
				)
			);
		}

		if ( current_user_can( 'edit_posts' ) ) {
			$wp_admin_bar->add_node(
				array(
					'parent' => $menu_id,
					'id'     => $menu_id . '-c',
					'title'  => __( 'Manage Comments' ),
					'href'   => admin_url( 'edit-comments.php' ),
				)
			);
		}

		$wp_admin_bar->add_node(
			array(
				'parent' => $menu_id,
				'id'     => $menu_id . '-v',
				'title'  => __( 'Visit Site' ),
				'href'   => home_url( '/' ),
			)
		);

		restore_current_blog();
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/admin-bar.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/admin-bar.php#L545) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/admin-bar.php#L545-L759)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/\#hooks)

[apply\_filters( ‘wp\_admin\_bar\_show\_site\_icons’, bool$show\_site\_icons )](https://developer.wordpress.org/reference/hooks/wp_admin_bar_show_site_icons/)

Filters whether to show the site icons in toolbar.

## [Related](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/\#related)

| Uses | Description |
| --- | --- |
| [has\_site\_icon()](https://developer.wordpress.org/reference/functions/has_site_icon/) `wp-includes/general-template.php` | Determines whether the site has a Site Icon. |
| [get\_site\_icon\_url()](https://developer.wordpress.org/reference/functions/get_site_icon_url/) `wp-includes/general-template.php` | Returns the Site Icon URL. |
| [is\_user\_logged\_in()](https://developer.wordpress.org/reference/functions/is_user_logged_in/) `wp-includes/pluggable.php` | Determines whether the current visitor is a logged in user. |
| [get\_admin\_url()](https://developer.wordpress.org/reference/functions/get_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for a given site. |
| [network\_admin\_url()](https://developer.wordpress.org/reference/functions/network_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the network. |
| [get\_home\_url()](https://developer.wordpress.org/reference/functions/get_home_url/) `wp-includes/link-template.php` | Retrieves the URL for a given site where the front end is accessible. |
| [WP\_Admin\_Bar::add\_node()](https://developer.wordpress.org/reference/classes/wp_admin_bar/add_node/) `wp-includes/class-wp-admin-bar.php` | Adds a node to the menu. |
| [WP\_Admin\_Bar::add\_group()](https://developer.wordpress.org/reference/classes/wp_admin_bar/add_group/) `wp-includes/class-wp-admin-bar.php` | Adds a group to a toolbar menu node. |
| [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) `wp-includes/ms-blogs.php` | Switches the current blog. |
| [restore\_current\_blog()](https://developer.wordpress.org/reference/functions/restore_current_blog/) `wp-includes/ms-blogs.php` | Restores the current blog, after calling [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) . |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [is\_multisite()](https://developer.wordpress.org/reference/functions/is_multisite/) `wp-includes/load.php` | Determines whether Multisite is enabled. |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current site. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post\_type\_object()](https://developer.wordpress.org/reference/functions/get_post_type_object/) `wp-includes/post.php` | Retrieves a post type object by name. |

[Show 12 more](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#) [Show less](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_admin_bar_my_sites_menu%2F) before being able to contribute a note or feedback.

Notifications