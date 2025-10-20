---
url: https://developer.wordpress.org/reference/functions/admin_url
scraped_at: 2025-10-20T03:12:30.020Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/admin_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

admin\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)admin\_url()

Search

# admin\_url( string$path = '', string$scheme = 'admin' ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/admin_url/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/admin_url/#return)
- [Source](https://developer.wordpress.org/reference/functions/admin_url/#source)
- [Related](https://developer.wordpress.org/reference/functions/admin_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/admin_url/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/admin_url/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/admin_url/#wp--skip-link--target)

Retrieves the URL to the admin area for the current site.

## [Parameters](https://developer.wordpress.org/reference/functions/admin_url/\#parameters)

`$path` stringoptional

Path relative to the admin URL.

Default: `''`

`$scheme` stringoptional

The scheme to use. Default is `'admin'`, which obeys [force\_ssl\_admin()](https://developer.wordpress.org/reference/functions/force_ssl_admin/) and [is\_ssl()](https://developer.wordpress.org/reference/functions/is_ssl/) .

`'http'` or `'https'` can be passed to force those schemes.

Default: `'admin'`

## [Return](https://developer.wordpress.org/reference/functions/admin_url/\#return)

string Admin URL link with optional path appended.

## [Source](https://developer.wordpress.org/reference/functions/admin_url/\#source)

`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)

```php
function admin_url( $path = '', $scheme = 'admin' ) {
	return get_admin_url( null, $path, $scheme );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L3564) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L3564-L3566)

## [Related](https://developer.wordpress.org/reference/functions/admin_url/\#related)

| Uses | Description |
| --- | --- |
| [get\_admin\_url()](https://developer.wordpress.org/reference/functions/get_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for a given site. |

| Used by | Description |
| --- | --- |
| [WP\_Plugin\_Dependencies::check\_plugin\_dependencies\_during\_ajax()](https://developer.wordpress.org/reference/classes/wp_plugin_dependencies/check_plugin_dependencies_during_ajax/) `wp-includes/class-wp-plugin-dependencies.php` | Checks plugin dependencies after a plugin is installed via AJAX. |
| [WP\_Plugin\_Dependencies::display\_admin\_notice\_for\_unmet\_dependencies()](https://developer.wordpress.org/reference/classes/wp_plugin_dependencies/display_admin_notice_for_unmet_dependencies/) `wp-includes/class-wp-plugin-dependencies.php` | Displays an admin notice if dependencies are not installed. |
| [WP\_Widget\_Media::get\_l10n\_defaults()](https://developer.wordpress.org/reference/classes/wp_widget_media/get_l10n_defaults/) `wp-includes/widgets/class-wp-widget-media.php` | Returns the default localized strings used by the widget. |
| [wp\_admin\_bar\_edit\_site\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_edit_site_menu/) `wp-includes/admin-bar.php` | Adds the “Edit Site” link to the Toolbar. |
| [get\_default\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_default_block_editor_settings/) `wp-includes/block-editor.php` | Returns the default block editor settings. |
| [deactivated\_plugins\_notice()](https://developer.wordpress.org/reference/functions/deactivated_plugins_notice/) `wp-admin/includes/plugin.php` | Renders an admin notice when a plugin was deactivated during an update. |
| [rest\_add\_application\_passwords\_to\_index()](https://developer.wordpress.org/reference/functions/rest_add_application_passwords_to_index/) `wp-includes/rest-api.php` | Adds Application Passwords info to the REST API index. |
| [WP\_Site\_Health::get\_test\_authorization\_header()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_authorization_header/) `wp-admin/includes/class-wp-site-health.php` | Tests if the Authorization header has the expected values. |
| [WP\_Automatic\_Updater::send\_plugin\_theme\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_plugin_theme_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Sends an email upon the completion or failure of a plugin or theme background update. |
| [wp\_dashboard\_site\_health()](https://developer.wordpress.org/reference/functions/wp_dashboard_site_health/) `wp-admin/includes/dashboard.php` | Displays the Site Health Status widget. |
| [WP\_Site\_Health::wp\_cron\_scheduled\_check()](https://developer.wordpress.org/reference/classes/wp_site_health/wp_cron_scheduled_check/) `wp-admin/includes/class-wp-site-health.php` | Runs the scheduled event to check and update the latest site health status for the website. |
| [WP\_Privacy\_Requests\_Table::get\_admin\_url()](https://developer.wordpress.org/reference/classes/wp_privacy_requests_table/get_admin_url/) `wp-admin/includes/class-wp-privacy-requests-table.php` | Normalizes the admin URL to the current page (by request\_type). |
| [WP\_Privacy\_Data\_Removal\_Requests\_List\_Table::column\_email()](https://developer.wordpress.org/reference/classes/wp_privacy_data_removal_requests_list_table/column_email/) `wp-admin/includes/class-wp-privacy-data-removal-requests-list-table.php` | Outputs the Actions column. |
| [WP\_Privacy\_Data\_Removal\_Requests\_List\_Table::column\_next\_steps()](https://developer.wordpress.org/reference/classes/wp_privacy_data_removal_requests_list_table/column_next_steps/) `wp-admin/includes/class-wp-privacy-data-removal-requests-list-table.php` | Outputs the Next steps column. |
| [WP\_Privacy\_Data\_Export\_Requests\_List\_Table::column\_email()](https://developer.wordpress.org/reference/classes/wp_privacy_data_export_requests_list_table/column_email/) `wp-admin/includes/class-wp-privacy-data-export-requests-list-table.php` | Actions column. |
| [WP\_Privacy\_Data\_Export\_Requests\_List\_Table::column\_next\_steps()](https://developer.wordpress.org/reference/classes/wp_privacy_data_export_requests_list_table/column_next_steps/) `wp-admin/includes/class-wp-privacy-data-export-requests-list-table.php` | Displays the next steps column. |
| [WP\_Recovery\_Mode::handle\_exit\_recovery\_mode()](https://developer.wordpress.org/reference/classes/wp_recovery_mode/handle_exit_recovery_mode/) `wp-includes/class-wp-recovery-mode.php` | Handles a request to exit Recovery Mode. |
| [paused\_themes\_notice()](https://developer.wordpress.org/reference/functions/paused_themes_notice/) `wp-admin/includes/theme.php` | Renders an admin notice in case some themes have been paused due to errors. |
| [WP\_Site\_Health::get\_test\_wordpress\_version()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_wordpress_version/) `wp-admin/includes/class-wp-site-health.php` | Tests for WordPress version and outputs it. |
| [WP\_Site\_Health::get\_test\_plugin\_version()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_plugin_version/) `wp-admin/includes/class-wp-site-health.php` | Tests if plugins are outdated, or unnecessary. |
| [WP\_Site\_Health::get\_test\_theme\_version()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_theme_version/) `wp-admin/includes/class-wp-site-health.php` | Tests if themes are outdated, or unnecessary. |
| [WP\_Site\_Health::get\_test\_https\_status()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_https_status/) `wp-admin/includes/class-wp-site-health.php` | Tests if the site is serving content over HTTPS. |
| [paused\_plugins\_notice()](https://developer.wordpress.org/reference/functions/paused_plugins_notice/) `wp-admin/includes/plugin.php` | Renders an admin notice in case some plugins have been paused due to errors. |
| [validate\_plugin\_requirements()](https://developer.wordpress.org/reference/functions/validate_plugin_requirements/) `wp-admin/includes/plugin.php` | Validates the plugin requirements for WordPress version and PHP version. |
| [wp\_default\_packages\_inline\_scripts()](https://developer.wordpress.org/reference/functions/wp_default_packages_inline_scripts/) `wp-includes/script-loader.php` | Adds inline scripts required for the WordPress JavaScript packages. |
| [the\_block\_editor\_meta\_boxes()](https://developer.wordpress.org/reference/functions/the_block_editor_meta_boxes/) `wp-admin/includes/post.php` | Renders the meta boxes forms. |
| [\_wp\_privacy\_send\_request\_confirmation\_notification()](https://developer.wordpress.org/reference/functions/_wp_privacy_send_request_confirmation_notification/) `wp-includes/user.php` | Notifies the site administrator via email when a request is confirmed. |
| [WP\_Privacy\_Policy\_Content::notice()](https://developer.wordpress.org/reference/classes/wp_privacy_policy_content/notice/) `wp-admin/includes/class-wp-privacy-policy-content.php` | Adds a notice with a link to the guide when editing the privacy policy page. |
| [WP\_Privacy\_Policy\_Content::policy\_text\_changed\_notice()](https://developer.wordpress.org/reference/classes/wp_privacy_policy_content/policy_text_changed_notice/) `wp-admin/includes/class-wp-privacy-policy-content.php` | Outputs a warning when some privacy info has changed. |
| [wp\_load\_press\_this()](https://developer.wordpress.org/reference/functions/wp_load_press_this/) `wp-admin/press-this.php` |  |
| [wp\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_edit_theme_plugin_file/) `wp-admin/includes/file.php` | Attempts to edit a file for a theme or plugin. |
| [WP\_Widget\_Media\_Audio::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_media_audio/__construct/) `wp-includes/widgets/class-wp-widget-media-audio.php` | Constructor. |
| [WP\_Widget\_Media\_Video::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_media_video/__construct/) `wp-includes/widgets/class-wp-widget-media-video.php` | Constructor. |
| [WP\_Widget\_Media\_Image::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_media_image/__construct/) `wp-includes/widgets/class-wp-widget-media-image.php` | Constructor. |
| [wp\_print\_community\_events\_markup()](https://developer.wordpress.org/reference/functions/wp_print_community_events_markup/) `wp-admin/includes/dashboard.php` | Prints the markup for the Community Events section of the Events and News Dashboard widget. |
| [WP\_Customize\_Manager::is\_cross\_domain()](https://developer.wordpress.org/reference/classes/wp_customize_manager/is_cross_domain/) `wp-includes/class-wp-customize-manager.php` | Determines whether the admin and the frontend are on different domains. |
| [wp\_ajax\_install\_theme()](https://developer.wordpress.org/reference/functions/wp_ajax_install_theme/) `wp-admin/includes/ajax-actions.php` | Handles installing a theme via AJAX. |
| [wp\_ajax\_install\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_install_plugin/) `wp-admin/includes/ajax-actions.php` | Handles installing a plugin via AJAX. |
| [WP\_Customize\_Manager::get\_return\_url()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_return_url/) `wp-includes/class-wp-customize-manager.php` | Gets URL to link the user to when closing the Customizer. |
| [WP\_Customize\_Manager::customize\_pane\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_pane_settings/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings for parent window. |
| [WP\_Posts\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/handle_row_actions/) `wp-admin/includes/class-wp-posts-list-table.php` | Generates and displays row action links. |
| [network\_step1()](https://developer.wordpress.org/reference/functions/network_step1/) `wp-admin/includes/network.php` | Prints step 1 for Network installation process. |
| [WP\_Automatic\_Updater::send\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Sends an email upon the completion or failure of a background core update. |
| [wp\_prepare\_themes\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_themes_for_js/) `wp-admin/includes/theme.php` | Prepares themes for JavaScript. |
| [get\_theme\_update\_available()](https://developer.wordpress.org/reference/functions/get_theme_update_available/) `wp-admin/includes/theme.php` | Retrieves the update link if there is a theme update available. |
| [WP\_Plugins\_List\_Table::no\_items()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/no_items/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [Theme\_Upgrader\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_upgrader_skin/after/) `wp-admin/includes/class-theme-upgrader-skin.php` | Performs an action following a single theme update. |
| [Plugin\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_installer_skin/after/) `wp-admin/includes/class-plugin-installer-skin.php` | Performs an action following a plugin install. |
| [Theme\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_installer_skin/after/) `wp-admin/includes/class-theme-installer-skin.php` | Performs an action following a single theme install. |
| [WP\_List\_Table::comments\_bubble()](https://developer.wordpress.org/reference/classes/wp_list_table/comments_bubble/) `wp-admin/includes/class-wp-list-table.php` | Displays a comment count bubble. |
| [wp\_image\_editor()](https://developer.wordpress.org/reference/functions/wp_image_editor/) `wp-admin/includes/image-edit.php` | Loads the WP image-editing interface. |
| [wp\_welcome\_panel()](https://developer.wordpress.org/reference/functions/wp_welcome_panel/) `wp-admin/includes/dashboard.php` | Displays a welcome panel to introduce users to WordPress. |
| [wp\_dashboard\_quota()](https://developer.wordpress.org/reference/functions/wp_dashboard_quota/) `wp-admin/includes/dashboard.php` | Displays file upload quota on dashboard. |
| [wp\_dashboard\_quick\_press()](https://developer.wordpress.org/reference/functions/wp_dashboard_quick_press/) `wp-admin/includes/dashboard.php` | Displays the Quick Draft widget. |
| [wp\_dashboard\_recent\_drafts()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_drafts/) `wp-admin/includes/dashboard.php` | Show recent drafts of the user on the dashboard. |
| [menu\_page\_url()](https://developer.wordpress.org/reference/functions/menu_page_url/) `wp-admin/includes/plugin.php` | Gets the URL to access a particular menu page based on the slug it was registered with. |
| [wp\_install\_defaults()](https://developer.wordpress.org/reference/functions/wp_install_defaults/) `wp-admin/includes/upgrade.php` | Creates the initial content for a newly-installed site. |
| [iframe\_header()](https://developer.wordpress.org/reference/functions/iframe_header/) `wp-admin/includes/template.php` | Generic Iframe header for use with Thickbox. |
| [WP\_Themes\_List\_Table::no\_items()](https://developer.wordpress.org/reference/classes/wp_themes_list_table/no_items/) `wp-admin/includes/class-wp-themes-list-table.php` |  |
| [media\_upload\_type\_form()](https://developer.wordpress.org/reference/functions/media_upload_type_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for a given media type. |
| [media\_upload\_type\_url\_form()](https://developer.wordpress.org/reference/functions/media_upload_type_url_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for external media. |
| [media\_upload\_gallery\_form()](https://developer.wordpress.org/reference/functions/media_upload_gallery_form/) `wp-admin/includes/media.php` | Adds gallery form to upload iframe. |
| [media\_upload\_library\_form()](https://developer.wordpress.org/reference/functions/media_upload_library_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for the media library. |
| [media\_upload\_flash\_bypass()](https://developer.wordpress.org/reference/functions/media_upload_flash_bypass/) `wp-admin/includes/media.php` | Displays the multi-file uploader message. |
| [media\_upload\_max\_image\_resize()](https://developer.wordpress.org/reference/functions/media_upload_max_image_resize/) `wp-admin/includes/media.php` | Displays the checkbox to scale images. |
| [media\_upload\_form()](https://developer.wordpress.org/reference/functions/media_upload_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form. |
| [wp\_iframe()](https://developer.wordpress.org/reference/functions/wp_iframe/) `wp-admin/includes/media.php` | Outputs the iframe to display the media upload page. |
| [get\_upload\_iframe\_src()](https://developer.wordpress.org/reference/functions/get_upload_iframe_src/) `wp-admin/includes/media.php` | Retrieves the upload iframe source URL. |
| [\_admin\_notice\_post\_locked()](https://developer.wordpress.org/reference/functions/_admin_notice_post_locked/) `wp-admin/includes/post.php` | Outputs the HTML for the notice to say that someone else is editing or has taken over editing of this post. |
| [wp\_ajax\_query\_themes()](https://developer.wordpress.org/reference/functions/wp_ajax_query_themes/) `wp-admin/includes/ajax-actions.php` | Handles getting themes from [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) via AJAX. |
| [wp\_prepare\_revisions\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_revisions_for_js/) `wp-admin/includes/revision.php` | Prepare revisions for JavaScript. |
| [update\_core()](https://developer.wordpress.org/reference/functions/update_core/) `wp-admin/includes/update-core.php` | Upgrades the core of WordPress. |
| [post\_submit\_meta\_box()](https://developer.wordpress.org/reference/functions/post_submit_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post submit form fields. |
| [WP\_Comments\_List\_Table::column\_author()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/column_author/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/get_views/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [Walker\_Nav\_Menu\_Edit::start\_el()](https://developer.wordpress.org/reference/classes/walker_nav_menu_edit/start_el/) `wp-admin/includes/class-walker-nav-menu-edit.php` | Start the element output. |
| [Custom\_Image\_Header::step\_1()](https://developer.wordpress.org/reference/classes/custom_image_header/step_1/) `wp-admin/includes/class-custom-image-header.php` | Displays first step of custom header image page. |
| [Custom\_Image\_Header::help()](https://developer.wordpress.org/reference/classes/custom_image_header/help/) `wp-admin/includes/class-custom-image-header.php` | Adds contextual help. |
| [Custom\_Background::admin\_page()](https://developer.wordpress.org/reference/classes/custom_background/admin_page/) `wp-admin/includes/class-custom-background.php` | Displays the custom background page. |
| [wp\_customize\_url()](https://developer.wordpress.org/reference/functions/wp_customize_url/) `wp-includes/theme.php` | Returns a URL to load the Customizer. |
| [wp\_customize\_support\_script()](https://developer.wordpress.org/reference/functions/wp_customize_support_script/) `wp-includes/theme.php` | Prints a script to check whether or not the Customizer is supported, and apply either the no-customize-support or customize-support class to the body. |
| [\_wp\_customize\_loader\_settings()](https://developer.wordpress.org/reference/functions/_wp_customize_loader_settings/) `wp-includes/theme.php` | Adds settings for the customize-loader script. |
| [wp\_safe\_redirect()](https://developer.wordpress.org/reference/functions/wp_safe_redirect/) `wp-includes/pluggable.php` | Performs a safe (local) redirect, using [wp\_redirect()](https://developer.wordpress.org/reference/functions/wp_redirect/) . |
| [wp\_notify\_postauthor()](https://developer.wordpress.org/reference/functions/wp_notify_postauthor/) `wp-includes/pluggable.php` | Notifies an author (and/or others) of a comment/trackback/pingback on a post. |
| [wp\_notify\_moderator()](https://developer.wordpress.org/reference/functions/wp_notify_moderator/) `wp-includes/pluggable.php` | Notifies the moderator of the site about a new comment that is awaiting approval. |
| [check\_admin\_referer()](https://developer.wordpress.org/reference/functions/check_admin_referer/) `wp-includes/pluggable.php` | Ensures intent by verifying that a user was referred from another admin page with the correct security nonce. |
| [wp\_heartbeat\_settings()](https://developer.wordpress.org/reference/functions/wp_heartbeat_settings/) `wp-includes/general-template.php` | Default settings for heartbeat. |
| [register\_admin\_color\_schemes()](https://developer.wordpress.org/reference/functions/register_admin_color_schemes/) `wp-includes/general-template.php` | Registers the default admin color schemes. |
| [wp\_admin\_css\_uri()](https://developer.wordpress.org/reference/functions/wp_admin_css_uri/) `wp-includes/general-template.php` | Displays the URL of a WordPress admin CSS file. |
| [wp\_register()](https://developer.wordpress.org/reference/functions/wp_register/) `wp-includes/general-template.php` | Displays the Registration or Admin link. |
| [wp\_admin\_bar\_dashboard\_view\_site\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_dashboard_view_site_menu/) `wp-includes/deprecated.php` | Add the “Dashboard”/”Visit Site” menu. |
| [WP\_Nav\_Menu\_Widget::form()](https://developer.wordpress.org/reference/classes/wp_nav_menu_widget/form/) `wp-includes/widgets/class-wp-nav-menu-widget.php` | Outputs the settings form for the Navigation Menu widget. |
| [WP\_Embed::maybe\_run\_ajax\_cache()](https://developer.wordpress.org/reference/classes/wp_embed/maybe_run_ajax_cache/) `wp-includes/class-wp-embed.php` | If a post/page was saved, then output JavaScript to make an Ajax request that will call [WP\_Embed::cache\_oembed()](https://developer.wordpress.org/reference/classes/wp_embed/cache_oembed/). |
| [self\_admin\_url()](https://developer.wordpress.org/reference/functions/self_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for either the current site or the network depending on context. |
| [get\_dashboard\_url()](https://developer.wordpress.org/reference/functions/get_dashboard_url/) `wp-includes/link-template.php` | Retrieves the URL to the user’s dashboard. |
| [network\_admin\_url()](https://developer.wordpress.org/reference/functions/network_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the network. |
| [get\_edit\_post\_link()](https://developer.wordpress.org/reference/functions/get_edit_post_link/) `wp-includes/link-template.php` | Retrieves the edit post link for post. |
| [get\_delete\_post\_link()](https://developer.wordpress.org/reference/functions/get_delete_post_link/) `wp-includes/link-template.php` | Retrieves the delete posts link for post. |
| [get\_edit\_comment\_link()](https://developer.wordpress.org/reference/functions/get_edit_comment_link/) `wp-includes/link-template.php` | Retrieves the edit comment link. |
| [get\_edit\_bookmark\_link()](https://developer.wordpress.org/reference/functions/get_edit_bookmark_link/) `wp-includes/link-template.php` | Displays the edit bookmark link. |
| [get\_edit\_term\_link()](https://developer.wordpress.org/reference/functions/get_edit_term_link/) `wp-includes/link-template.php` | Retrieves the URL for editing a given term. |
| [get\_allowed\_http\_origins()](https://developer.wordpress.org/reference/functions/get_allowed_http_origins/) `wp-includes/http.php` | Retrieves list of allowed HTTP origins. |
| [wp\_admin\_bar\_site\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_site_menu/) `wp-includes/admin-bar.php` | Adds the “Site Name” menu. |
| [wp\_admin\_bar\_my\_sites\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/) `wp-includes/admin-bar.php` | Adds the “My Sites/\[Site Name\]” menu and all submenus. |
| [wp\_admin\_bar\_new\_content\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_new_content_menu/) `wp-includes/admin-bar.php` | Adds “Add New” menu. |
| [wp\_admin\_bar\_comments\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_comments_menu/) `wp-includes/admin-bar.php` | Adds edit comments link with awaiting moderation count bubble. |
| [wp\_admin\_bar\_appearance\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_appearance_menu/) `wp-includes/admin-bar.php` | Adds appearance submenu items to the “Site Name” menu. |
| [wp\_user\_settings()](https://developer.wordpress.org/reference/functions/wp_user_settings/) `wp-includes/option.php` | Saves and restores user interface settings stored in a cookie. |
| [wp\_redirect\_admin\_locations()](https://developer.wordpress.org/reference/functions/wp_redirect_admin_locations/) `wp-includes/canonical.php` | Redirects a variety of shorthand URLs to the admin. |
| [maybe\_add\_existing\_user\_to\_blog()](https://developer.wordpress.org/reference/functions/maybe_add_existing_user_to_blog/) `wp-includes/ms-functions.php` | Adds a new user to a blog by visiting /newbloguser/{key}/. |
| [wp\_default\_scripts()](https://developer.wordpress.org/reference/functions/wp_default_scripts/) `wp-includes/script-loader.php` | Registers all WordPress scripts. |
| [\_WP\_Editors::editor\_js()](https://developer.wordpress.org/reference/classes/_wp_editors/editor_js/) `wp-includes/class-wp-editor.php` | Print (output) the TinyMCE configuration and initialization scripts. |
| [wp\_print\_media\_templates()](https://developer.wordpress.org/reference/functions/wp_print_media_templates/) `wp-includes/media-template.php` | Prints the templates used in the media manager. |

[Show 108 more](https://developer.wordpress.org/reference/functions/admin_url/#) [Show less](https://developer.wordpress.org/reference/functions/admin_url/#)

## [Changelog](https://developer.wordpress.org/reference/functions/admin_url/\#changelog)

| Version | Description |
| --- | --- |
| [2.6.0](https://developer.wordpress.org/reference/since/2.6.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/admin_url/\#user-contributed-notes)

1. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-959)



**Examples**





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
<?php echo admin_url(); ?>
```





Output: [http://example.com/wp-admin/](http://example.com/wp-admin/) (or https protocol when appropriate)





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
// Generate URL to admin's "Categories" page, and force https
<?php echo admin_url( 'edit-tags.php?taxonomy=category', 'https' ); ?>
```





Output: [https://example.com/wp-admin/edit-tags.php?taxonomy=category](https://example.com/wp-admin/edit-tags.php?taxonomy=category)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D959%23feedback-editor-959)

2. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-5663)



If you are looking for the post edit url for admin end and you have the post id (suppose `$post_id`) with you, then you can use the following code for getting the url.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
$post_id = 1731; // For example
$post_url = add_query_arg( array(
   	'post' => $post_id,
   	'action' => 'edit',
), admin_url( 'post.php' ) );

// returns http://example.com/wp-admin/post.php?post=1731&action=edit
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D5663%23feedback-editor-5663)

3. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-958)



**Default Usage**





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
<?php $url = admin_url(); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D958%23feedback-editor-958)

4. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-6560)



The presence of a leading slash in the path doesn’t affect the output, as it will be internally removed. Thus, both calls to `admin_url()` will yield the same result:





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
admin_url( 'test' );  // returns http://example.com/wp-admin/test
admin_url( '/test' ); // returns http://example.com/wp-admin/test
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D6560%23feedback-editor-6560)

5. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-6344)



Logout Users based on specific capabilities and role





`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/admin_url/#)

[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
if ( ! current_user_can( 'edit_posts' ) && ! is_admin() ) {
   	$redirect_url = site_url();
} else {
   	$redirect_url = '/wp-login.php';
}

function wpdocs_redirect_after_logout() {
   	global $redirect_url;

   	wp_safe_redirect( $redirect_url );

   	exit;
}
add_action( 'wp_logout', 'wpdocs_redirect_after_logout' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D6344%23feedback-editor-6344)

6. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/admin_url/#comment-content-957)



**Usage**





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/admin_url/#)




```php
<?php admin_url( $path, $scheme ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F%3Freplytocom%3D957%23feedback-editor-957)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadmin_url%2F) before being able to contribute a note or feedback.

Notifications