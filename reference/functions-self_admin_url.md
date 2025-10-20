---
url: https://developer.wordpress.org/reference/functions/self_admin_url
scraped_at: 2025-10-20T03:15:06.148Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/self_admin_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

self\_admin\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)self\_admin\_url()

Search

# self\_admin\_url( string$path = '', string$scheme = 'admin' ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/self_admin_url/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/self_admin_url/#return)
- [Source](https://developer.wordpress.org/reference/functions/self_admin_url/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/self_admin_url/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/self_admin_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/self_admin_url/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/self_admin_url/#wp--skip-link--target)

Retrieves the URL to the admin area for either the current site or the network depending on context.

## [Parameters](https://developer.wordpress.org/reference/functions/self_admin_url/\#parameters)

`$path` stringoptional

Path relative to the admin URL.

Default: `''`

`$scheme` stringoptional

The scheme to use. Default is `'admin'`, which obeys [force\_ssl\_admin()](https://developer.wordpress.org/reference/functions/force_ssl_admin/) and [is\_ssl()](https://developer.wordpress.org/reference/functions/is_ssl/) . `'http'` or `'https'` can be passed to force those schemes.

Default: `'admin'`

## [Return](https://developer.wordpress.org/reference/functions/self_admin_url/\#return)

string Admin URL link with optional path appended.

## [Source](https://developer.wordpress.org/reference/functions/self_admin_url/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/self_admin_url/#)

[Copy](https://developer.wordpress.org/reference/functions/self_admin_url/#)

```php
function self_admin_url( $path = '', $scheme = 'admin' ) {
	if ( is_network_admin() ) {
		$url = network_admin_url( $path, $scheme );
	} elseif ( is_user_admin() ) {
		$url = user_admin_url( $path, $scheme );
	} else {
		$url = admin_url( $path, $scheme );
	}

	/**
	 * Filters the admin URL for the current site or network depending on context.
	 *
	 * @since 4.9.0
	 *
	 * @param string $url    The complete URL including scheme and path.
	 * @param string $path   Path relative to the URL. Blank string if no path is specified.
	 * @param string $scheme The scheme to use.
	 */
	return apply_filters( 'self_admin_url', $url, $path, $scheme );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L3889) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L3889-L3908)

## [Hooks](https://developer.wordpress.org/reference/functions/self_admin_url/\#hooks)

[apply\_filters( ‘self\_admin\_url’, string$url, string$path, string$scheme )](https://developer.wordpress.org/reference/hooks/self_admin_url/)

Filters the admin URL for the current site or network depending on context.

## [Related](https://developer.wordpress.org/reference/functions/self_admin_url/\#related)

| Uses | Description |
| --- | --- |
| [is\_network\_admin()](https://developer.wordpress.org/reference/functions/is_network_admin/) `wp-includes/load.php` | Determines whether the current request is for the network administrative interface. |
| [is\_user\_admin()](https://developer.wordpress.org/reference/functions/is_user_admin/) `wp-includes/load.php` | Determines whether the current request is for a user admin screen. |
| [network\_admin\_url()](https://developer.wordpress.org/reference/functions/network_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the network. |
| [user\_admin\_url()](https://developer.wordpress.org/reference/functions/user_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current user. |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current site. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/self_admin_url/#) [Show less](https://developer.wordpress.org/reference/functions/self_admin_url/#)

| Used by | Description |
| --- | --- |
| [core\_auto\_updates\_settings()](https://developer.wordpress.org/reference/functions/core_auto_updates_settings/) `wp-admin/update-core.php` | Display WordPress auto-updates settings. |
| [WP\_REST\_Plugins\_Controller::is\_filesystem\_available()](https://developer.wordpress.org/reference/classes/wp_rest_plugins_controller/is_filesystem_available/) `wp-includes/rest-api/endpoints/class-wp-rest-plugins-controller.php` | Determine if the endpoints are available. |
| [do\_block\_editor\_incompatible\_meta\_box()](https://developer.wordpress.org/reference/functions/do_block_editor_incompatible_meta_box/) `wp-admin/includes/template.php` | Renders a “fake” meta box with an information message, shown on the block editor, when an incompatible meta box is found. |
| [wp\_load\_press\_this()](https://developer.wordpress.org/reference/functions/wp_load_press_this/) `wp-admin/press-this.php` |  |
| [wp\_print\_plugin\_file\_tree()](https://developer.wordpress.org/reference/functions/wp_print_plugin_file_tree/) `wp-admin/includes/misc.php` | Outputs the formatted file list for the plugin file editor. |
| [wp\_print\_theme\_file\_tree()](https://developer.wordpress.org/reference/functions/wp_print_theme_file_tree/) `wp-admin/includes/misc.php` | Outputs the formatted file list for the theme file editor. |
| [WP\_Customize\_Manager::customize\_pane\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_pane_settings/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings for parent window. |
| [WP\_Customize\_Theme\_Control::content\_template()](https://developer.wordpress.org/reference/classes/wp_customize_theme_control/content_template/) `wp-includes/customize/class-wp-customize-theme-control.php` | Render a JS template for theme display. |
| [customize\_themes\_print\_templates()](https://developer.wordpress.org/reference/functions/customize_themes_print_templates/) `wp-admin/includes/theme.php` | Prints JS templates for the theme-browsing UI in the Customizer. |
| [wp\_print\_request\_filesystem\_credentials\_modal()](https://developer.wordpress.org/reference/functions/wp_print_request_filesystem_credentials_modal/) `wp-admin/includes/file.php` | Prints the filesystem credentials modal when needed. |
| [File\_Upload\_Upgrader::\_\_construct()](https://developer.wordpress.org/reference/classes/file_upload_upgrader/__construct/) `wp-admin/includes/class-file-upload-upgrader.php` | Construct the upgrader for a form. |
| [WP\_Plugins\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/single_row/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [install\_themes\_upload()](https://developer.wordpress.org/reference/functions/install_themes_upload/) `wp-admin/includes/theme-install.php` | Displays a form to upload themes from zip files. |
| [Language\_Pack\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/language_pack_upgrader_skin/bulk_footer/) `wp-admin/includes/class-language-pack-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Theme\_Upgrader\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_upgrader_skin/after/) `wp-admin/includes/class-theme-upgrader-skin.php` | Performs an action following a single theme update. |
| [Plugin\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_installer_skin/after/) `wp-admin/includes/class-plugin-installer-skin.php` | Performs an action following a plugin install. |
| [Bulk\_Theme\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/bulk_theme_upgrader_skin/bulk_footer/) `wp-admin/includes/class-bulk-theme-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Theme\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_installer_skin/after/) `wp-admin/includes/class-theme-installer-skin.php` | Performs an action following a single theme install. |
| [Bulk\_Plugin\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/bulk_plugin_upgrader_skin/bulk_footer/) `wp-admin/includes/class-bulk-plugin-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Plugin\_Upgrader\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_upgrader_skin/after/) `wp-admin/includes/class-plugin-upgrader-skin.php` | Performs an action following a single plugin update. |
| [update\_option\_new\_admin\_email()](https://developer.wordpress.org/reference/functions/update_option_new_admin_email/) `wp-admin/includes/misc.php` | Sends a confirmation request email when a change of site admin email address is attempted. |
| [send\_confirmation\_on\_profile\_email()](https://developer.wordpress.org/reference/functions/send_confirmation_on_profile_email/) `wp-includes/user.php` | Sends a confirmation request email when a change of user email address is attempted. |
| [WP\_Theme\_Install\_List\_Table::install\_theme\_info()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/install_theme_info/) `wp-admin/includes/class-wp-theme-install-list-table.php` | Prints the info for a theme (to be used in the theme installer modal). |
| [WP\_Theme\_Install\_List\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/get_views/) `wp-admin/includes/class-wp-theme-install-list-table.php` |  |
| [WP\_Theme\_Install\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/single_row/) `wp-admin/includes/class-wp-theme-install-list-table.php` | Prints a theme from the WordPress.org API. |
| [wp\_plugin\_update\_row()](https://developer.wordpress.org/reference/functions/wp_plugin_update_row/) `wp-admin/includes/update.php` | Displays update information for a plugin. |
| [wp\_theme\_update\_row()](https://developer.wordpress.org/reference/functions/wp_theme_update_row/) `wp-admin/includes/update.php` | Displays update information for a theme. |
| [install\_dashboard()](https://developer.wordpress.org/reference/functions/install_dashboard/) `wp-admin/includes/plugin-install.php` | Displays the Featured tab of Add Plugins screen. |
| [install\_plugins\_upload()](https://developer.wordpress.org/reference/functions/install_plugins_upload/) `wp-admin/includes/plugin-install.php` | Displays a form to upload plugins from zip files. |
| [install\_plugin\_install\_status()](https://developer.wordpress.org/reference/functions/install_plugin_install_status/) `wp-admin/includes/plugin-install.php` | Determines the status we can perform on a plugin. |
| [install\_plugin\_information()](https://developer.wordpress.org/reference/functions/install_plugin_information/) `wp-admin/includes/plugin-install.php` | Displays plugin information in dialog box form. |
| [WP\_Plugin\_Install\_List\_Table::display\_rows()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/display_rows/) `wp-admin/includes/class-wp-plugin-install-list-table.php` | Generates the list table rows. |
| [WP\_Plugin\_Install\_List\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/get_views/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [wp\_link\_manager\_disabled\_message()](https://developer.wordpress.org/reference/functions/wp_link_manager_disabled_message/) `wp-admin/includes/bookmark.php` | Outputs the ‘disabled’ message for the WordPress Link Manager. |
| [core\_upgrade\_preamble()](https://developer.wordpress.org/reference/functions/core_upgrade_preamble/) `wp-admin/update-core.php` | Display upgrade WordPress for downloading latest or upgrading automatically form. |
| [list\_plugin\_updates()](https://developer.wordpress.org/reference/functions/list_plugin_updates/) `wp-admin/update-core.php` | Display the upgrade plugins form. |
| [list\_theme\_updates()](https://developer.wordpress.org/reference/functions/list_theme_updates/) `wp-admin/update-core.php` | Display the upgrade themes form. |
| [do\_core\_upgrade()](https://developer.wordpress.org/reference/functions/do_core_upgrade/) `wp-admin/update-core.php` | Upgrades WordPress core display. |
| [get\_edit\_user\_link()](https://developer.wordpress.org/reference/functions/get_edit_user_link/) `wp-includes/link-template.php` | Retrieves the edit user link. |
| [wp\_admin\_bar\_wp\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_wp_menu/) `wp-includes/admin-bar.php` | Adds the WordPress logo menu. |

[Show 35 more](https://developer.wordpress.org/reference/functions/self_admin_url/#) [Show less](https://developer.wordpress.org/reference/functions/self_admin_url/#)

## [Changelog](https://developer.wordpress.org/reference/functions/self_admin_url/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fself_admin_url%2F) before being able to contribute a note or feedback.

Notifications