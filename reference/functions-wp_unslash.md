---
url: https://developer.wordpress.org/reference/functions/wp_unslash
scraped_at: 2025-10-20T03:18:20.579Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_unslash/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_unslash()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_unslash()

Search

# wp\_unslash( string\|array$value ): string\|array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_unslash/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_unslash/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_unslash/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_unslash/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_unslash/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_unslash/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_unslash/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_unslash/#wp--skip-link--target)

Removes slashes from a string or recursively removes slashes from strings within an array.

## [Description](https://developer.wordpress.org/reference/functions/wp_unslash/\#description)

This should be used to remove slashes from data passed to core API that expects data to be unslashed.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_unslash/\#parameters)

`$value` string\|arrayrequired

String or array of data to unslash.

## [Return](https://developer.wordpress.org/reference/functions/wp_unslash/\#return)

string\|array Unslashed `$value`, in the same type as supplied.

## [Source](https://developer.wordpress.org/reference/functions/wp_unslash/\#source)

`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_unslash/#)

```php
function wp_unslash( $value ) {
	return stripslashes_deep( $value );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L5787) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L5787-L5789)

## [Related](https://developer.wordpress.org/reference/functions/wp_unslash/\#related)

| Uses | Description |
| --- | --- |
| [stripslashes\_deep()](https://developer.wordpress.org/reference/functions/stripslashes_deep/) `wp-includes/formatting.php` | Navigates through an array, object, or scalar, and removes slashes from the values. |

| Used by | Description |
| --- | --- |
| [WP\_Automatic\_Updater::has\_fatal\_error()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/has_fatal_error/) `wp-admin/includes/class-wp-automatic-updater.php` | Performs a loopback request to check for potential fatal errors. |
| [WP\_Plugin\_Dependencies::check\_plugin\_dependencies\_during\_ajax()](https://developer.wordpress.org/reference/classes/wp_plugin_dependencies/check_plugin_dependencies_during_ajax/) `wp-includes/class-wp-plugin-dependencies.php` | Checks plugin dependencies after a plugin is installed via AJAX. |
| [wp\_ajax\_activate\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_activate_plugin/) `wp-admin/includes/ajax-actions.php` | Handles activating a plugin via AJAX. |
| [\_wp\_filter\_post\_meta\_footnotes()](https://developer.wordpress.org/reference/functions/_wp_filter_post_meta_footnotes/) `wp-includes/blocks.php` | Strips all HTML from the content of footnotes, and sanitizes the ID. |
| [wp\_autosave\_post\_revisioned\_meta\_fields()](https://developer.wordpress.org/reference/functions/wp_autosave_post_revisioned_meta_fields/) `wp-admin/includes/post.php` | Autosaves the revisioned meta fields. |
| [wp\_get\_theme\_preview\_path()](https://developer.wordpress.org/reference/functions/wp_get_theme_preview_path/) `wp-includes/theme-previews.php` | Filters the blog option to return the path for the previewed theme. |
| [wp\_attach\_theme\_preview\_middleware()](https://developer.wordpress.org/reference/functions/wp_attach_theme_preview_middleware/) `wp-includes/theme-previews.php` | Adds a middleware to `apiFetch` to set the theme for the preview. |
| [WP\_Site\_Health::check\_for\_page\_caching()](https://developer.wordpress.org/reference/classes/wp_site_health/check_for_page_caching/) `wp-admin/includes/class-wp-site-health.php` | Checks if site has page cache enabled or not. |
| [wp\_filter\_global\_styles\_post()](https://developer.wordpress.org/reference/functions/wp_filter_global_styles_post/) `wp-includes/kses.php` | Sanitizes global styles user content removing unsafe rules. |
| [get\_self\_link()](https://developer.wordpress.org/reference/functions/get_self_link/) `wp-includes/feed.php` | Returns the link for the currently displayed feed. |
| [WP\_MS\_Sites\_List\_Table::site\_states()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/site_states/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Determines whether to output comma-separated site states. |
| [WP\_MS\_Sites\_List\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/get_views/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Gets links to filter sites by status. |
| [WP\_Site\_Health::get\_test\_rest\_availability()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_rest_availability/) `wp-admin/includes/class-wp-site-health.php` | Tests if the REST API is accessible. |
| [WP\_Site\_Health::can\_perform\_loopback()](https://developer.wordpress.org/reference/classes/wp_site_health/can_perform_loopback/) `wp-admin/includes/class-wp-site-health.php` | Runs a loopback test on the site. |
| [wp\_initialize\_site()](https://developer.wordpress.org/reference/functions/wp_initialize_site/) `wp-includes/ms-site.php` | Runs the initialization routine for a given site. |
| [WP\_Privacy\_Requests\_Table::process\_bulk\_action()](https://developer.wordpress.org/reference/classes/wp_privacy_requests_table/process_bulk_action/) `wp-admin/includes/class-wp-privacy-requests-table.php` | Process bulk actions. |
| [\_wp\_personal\_data\_handle\_actions()](https://developer.wordpress.org/reference/functions/_wp_personal_data_handle_actions/) `wp-admin/includes/privacy-tools.php` | Handle list table actions. |
| [wp\_xmlrpc\_server::set\_term\_custom\_fields()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/set_term_custom_fields/) `wp-includes/class-wp-xmlrpc-server.php` | Sets custom fields for a term. |
| [wp\_start\_scraping\_edited\_file\_errors()](https://developer.wordpress.org/reference/functions/wp_start_scraping_edited_file_errors/) `wp-includes/load.php` | Starts scraping edited file errors. |
| [WP\_Customize\_Manager::handle\_load\_themes\_request()](https://developer.wordpress.org/reference/classes/wp_customize_manager/handle_load_themes_request/) `wp-includes/class-wp-customize-manager.php` | Loads themes into the theme browsing/installation UI. |
| [wp\_ajax\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_ajax_edit_theme_plugin_file/) `wp-admin/includes/ajax-actions.php` | Handles editing a theme or plugin file via AJAX. |
| [wp\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_edit_theme_plugin_file/) `wp-admin/includes/file.php` | Attempts to edit a file for a theme or plugin. |
| [wp\_ajax\_get\_community\_events()](https://developer.wordpress.org/reference/functions/wp_ajax_get_community_events/) `wp-admin/includes/ajax-actions.php` | Handles Ajax requests for community events |
| [WP\_Customize\_Nav\_Menus::ajax\_insert\_auto\_draft\_post()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/ajax_insert_auto_draft_post/) `wp-includes/class-wp-customize-nav-menus.php` | Ajax handler for adding a new auto-draft post. |
| [wp\_ajax\_delete\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_plugin/) `wp-admin/includes/ajax-actions.php` | Handles deleting a plugin via AJAX. |
| [wp\_ajax\_search\_plugins()](https://developer.wordpress.org/reference/functions/wp_ajax_search_plugins/) `wp-admin/includes/ajax-actions.php` | Handles searching plugins via AJAX. |
| [wp\_ajax\_install\_theme()](https://developer.wordpress.org/reference/functions/wp_ajax_install_theme/) `wp-admin/includes/ajax-actions.php` | Handles installing a theme via AJAX. |
| [wp\_ajax\_update\_theme()](https://developer.wordpress.org/reference/functions/wp_ajax_update_theme/) `wp-admin/includes/ajax-actions.php` | Handles updating a theme via AJAX. |
| [wp\_ajax\_delete\_theme()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_theme/) `wp-admin/includes/ajax-actions.php` | Handles deleting a theme via AJAX. |
| [wp\_ajax\_install\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_install_plugin/) `wp-admin/includes/ajax-actions.php` | Handles installing a plugin via AJAX. |
| [wp\_get\_raw\_referer()](https://developer.wordpress.org/reference/functions/wp_get_raw_referer/) `wp-includes/functions.php` | Retrieves unvalidated referer from the ‘\_wp\_http\_referer’ URL query variable or the HTTP referer. |
| [WP\_Customize\_Selective\_Refresh::handle\_render\_partials\_request()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/handle_render_partials_request/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Handles the Ajax request to return the rendered partials for the requested placements. |
| [WP\_REST\_Server::serve\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Handles serving a REST API request. |
| [wp\_ajax\_save\_wporg\_username()](https://developer.wordpress.org/reference/functions/wp_ajax_save_wporg_username/) `wp-admin/includes/ajax-actions.php` | Handles saving the user’s WordPress.org username via AJAX. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/sanitize/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Sanitize an input. |
| [WP\_Customize\_Nav\_Menus::ajax\_load\_available\_items()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/ajax_load_available_items/) `wp-includes/class-wp-customize-nav-menus.php` | Ajax handler for loading available menu items. |
| [WP\_Customize\_Nav\_Menus::ajax\_search\_available\_items()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/ajax_search_available_items/) `wp-includes/class-wp-customize-nav-menus.php` | Ajax handler for searching available menu items. |
| [WP\_Terms\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/handle_row_actions/) `wp-admin/includes/class-wp-terms-list-table.php` | Generates and displays row action links. |
| [WP\_MS\_Users\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/handle_row_actions/) `wp-admin/includes/class-wp-ms-users-list-table.php` | Generates and displays row action links. |
| [WP\_MS\_Users\_List\_Table::column\_username()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/column_username/) `wp-admin/includes/class-wp-ms-users-list-table.php` | Handles the username column output. |
| [WP\_User\_Search::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_user_search/__construct/) `wp-admin/includes/deprecated.php` | PHP5 Constructor – Sets up the object properties. |
| [WP\_Customize\_Manager::unsanitized\_post\_values()](https://developer.wordpress.org/reference/classes/wp_customize_manager/unsanitized_post_values/) `wp-includes/class-wp-customize-manager.php` | Gets dirty pre-sanitized setting values in the current customized state. |
| [WP\_Customize\_Widgets::register\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/register_settings/) `wp-includes/class-wp-customize-widgets.php` | Inspects the incoming customized data for any widget settings, and dynamically adds them up-front so widgets will be initialized properly. |
| [wp\_ajax\_update\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_update_plugin/) `wp-admin/includes/ajax-actions.php` | Handles updating a plugin via AJAX. |
| [WP\_Session\_Tokens::create()](https://developer.wordpress.org/reference/classes/wp_session_tokens/create/) `wp-includes/class-wp-session-tokens.php` | Generates a session token and attaches session information to it. |
| [wp\_ajax\_parse\_embed()](https://developer.wordpress.org/reference/functions/wp_ajax_parse_embed/) `wp-admin/includes/ajax-actions.php` | Applies Ajax handlers to a string. |
| [wp\_ajax\_parse\_media\_shortcode()](https://developer.wordpress.org/reference/functions/wp_ajax_parse_media_shortcode/) `wp-admin/includes/ajax-actions.php` |  |
| [retrieve\_password()](https://developer.wordpress.org/reference/functions/retrieve_password/) `wp-includes/user.php` | Handles sending a password retrieval email to a user. |
| [validate\_another\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_another_blog_signup/) `wp-signup.php` | Validates a new site sign-up for an existing user. |
| [validate\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_blog_signup/) `wp-signup.php` | Validates new site signup. |
| [display\_setup\_form()](https://developer.wordpress.org/reference/functions/display_setup_form/) `wp-admin/install.php` | Displays installer setup form. |
| [WP\_MS\_Users\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-users-list-table.php` |  |
| [wp\_prepare\_themes\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_themes_for_js/) `wp-admin/includes/theme.php` | Prepares themes for JavaScript. |
| [WP\_Plugins\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/__construct/) `wp-admin/includes/class-wp-plugins-list-table.php` | Constructor. |
| [WP\_Plugins\_List\_Table::no\_items()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/no_items/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [install\_theme\_search\_form()](https://developer.wordpress.org/reference/functions/install_theme_search_form/) `wp-admin/includes/theme-install.php` | Displays search form for searching themes. |
| [install\_theme\_information()](https://developer.wordpress.org/reference/functions/install_theme_information/) `wp-admin/includes/theme-install.php` | Displays theme information in dialog box form. |
| [Plugin\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_installer_skin/after/) `wp-admin/includes/class-plugin-installer-skin.php` | Performs an action following a plugin install. |
| [stream\_preview\_image()](https://developer.wordpress.org/reference/functions/stream_preview_image/) `wp-admin/includes/image-edit.php` | Streams image in post to browser, along with enqueued changes in `$_REQUEST['history']`. |
| [wp\_save\_image()](https://developer.wordpress.org/reference/functions/wp_save_image/) `wp-admin/includes/image-edit.php` | Saves image to post, along with enqueued changes in `$_REQUEST['history']`. |
| [WP\_MS\_Themes\_List\_Table::\_search\_callback()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/_search_callback/) `wp-admin/includes/class-wp-ms-themes-list-table.php` |  |
| [WP\_Theme\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/prepare_items/) `wp-admin/includes/class-wp-theme-install-list-table.php` |  |
| [install\_search\_form()](https://developer.wordpress.org/reference/functions/install_search_form/) `wp-admin/includes/plugin-install.php` | Displays a search form for searching plugins. |
| [install\_plugin\_install\_status()](https://developer.wordpress.org/reference/functions/install_plugin_install_status/) `wp-admin/includes/plugin-install.php` | Determines the status we can perform on a plugin. |
| [install\_plugin\_information()](https://developer.wordpress.org/reference/functions/install_plugin_information/) `wp-admin/includes/plugin-install.php` | Displays plugin information in dialog box form. |
| [wp\_dashboard\_rss\_control()](https://developer.wordpress.org/reference/functions/wp_dashboard_rss_control/) `wp-admin/includes/dashboard.php` | Sets up the RSS dashboard widget control and $args to be used as input to [wp\_widget\_rss\_form()](https://developer.wordpress.org/reference/functions/wp_widget_rss_form/) . |
| [edit\_user()](https://developer.wordpress.org/reference/functions/edit_user/) `wp-admin/includes/user.php` | Edit user settings based on contents of $\_POST |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [\_admin\_search\_query()](https://developer.wordpress.org/reference/functions/_admin_search_query/) `wp-admin/includes/template.php` | Displays the search query. |
| [WP\_Themes\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_themes_list_table/prepare_items/) `wp-admin/includes/class-wp-themes-list-table.php` |  |
| [WP\_Themes\_List\_Table::\_js\_vars()](https://developer.wordpress.org/reference/classes/wp_themes_list_table/_js_vars/) `wp-admin/includes/class-wp-themes-list-table.php` | Send required variables to JavaScript land |
| [WP\_Users\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_users_list_table/single_row/) `wp-admin/includes/class-wp-users-list-table.php` | Generates HTML for a single row on the users.php admin panel. |
| [WP\_MS\_Sites\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Prepares the list of sites for display. |
| [WP\_Users\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_users_list_table/prepare_items/) `wp-admin/includes/class-wp-users-list-table.php` | Prepares the users list for display. |
| [media\_upload\_form\_handler()](https://developer.wordpress.org/reference/functions/media_upload_form_handler/) `wp-admin/includes/media.php` | Handles form submissions for the legacy media uploader. |
| [wp\_media\_upload\_handler()](https://developer.wordpress.org/reference/functions/wp_media_upload_handler/) `wp-admin/includes/media.php` | Handles the process of uploading media. |
| [wp\_create\_post\_autosave()](https://developer.wordpress.org/reference/functions/wp_create_post_autosave/) `wp-admin/includes/post.php` | Creates autosave data for the specified post from `$_POST` data. |
| [add\_meta()](https://developer.wordpress.org/reference/functions/add_meta/) `wp-admin/includes/post.php` | Adds post meta data defined in the `$_POST` superglobal for a post with given ID. |
| [update\_meta()](https://developer.wordpress.org/reference/functions/update_meta/) `wp-admin/includes/post.php` | Updates post meta data by meta ID. |
| [edit\_post()](https://developer.wordpress.org/reference/functions/edit_post/) `wp-admin/includes/post.php` | Updates an existing post with values provided in `$_POST`. |
| [get\_default\_post\_to\_edit()](https://developer.wordpress.org/reference/functions/get_default_post_to_edit/) `wp-admin/includes/post.php` | Returns default post information to use when populating the “Write Post” form. |
| [post\_exists()](https://developer.wordpress.org/reference/functions/post_exists/) `wp-admin/includes/post.php` | Determines if a post exists based on title, content, date and type. |
| [wp\_ajax\_send\_attachment\_to\_editor()](https://developer.wordpress.org/reference/functions/wp_ajax_send_attachment_to_editor/) `wp-admin/includes/ajax-actions.php` | Handles sending an attachment to the editor via AJAX. |
| [wp\_ajax\_send\_link\_to\_editor()](https://developer.wordpress.org/reference/functions/wp_ajax_send_link_to_editor/) `wp-admin/includes/ajax-actions.php` | Handles sending a link to the editor via AJAX. |
| [wp\_ajax\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API via AJAX. |
| [wp\_ajax\_query\_themes()](https://developer.wordpress.org/reference/functions/wp_ajax_query_themes/) `wp-admin/includes/ajax-actions.php` | Handles getting themes from [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) via AJAX. |
| [wp\_ajax\_save\_widget()](https://developer.wordpress.org/reference/functions/wp_ajax_save_widget/) `wp-admin/includes/ajax-actions.php` | Handles saving a widget via AJAX. |
| [wp\_ajax\_date\_format()](https://developer.wordpress.org/reference/functions/wp_ajax_date_format/) `wp-admin/includes/ajax-actions.php` | Handles formatting a date via AJAX. |
| [wp\_ajax\_time\_format()](https://developer.wordpress.org/reference/functions/wp_ajax_time_format/) `wp-admin/includes/ajax-actions.php` | Handles formatting a time via AJAX. |
| [wp\_ajax\_save\_attachment()](https://developer.wordpress.org/reference/functions/wp_ajax_save_attachment/) `wp-admin/includes/ajax-actions.php` | Handles updating attachment attributes via AJAX. |
| [wp\_ajax\_add\_meta()](https://developer.wordpress.org/reference/functions/wp_ajax_add_meta/) `wp-admin/includes/ajax-actions.php` | Handles adding meta via AJAX. |
| [wp\_ajax\_wp\_link\_ajax()](https://developer.wordpress.org/reference/functions/wp_ajax_wp_link_ajax/) `wp-admin/includes/ajax-actions.php` | Handles internal linking via AJAX. |
| [wp\_ajax\_find\_posts()](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/) `wp-admin/includes/ajax-actions.php` | Handles querying posts for the Find Posts modal via AJAX. |
| [wp\_ajax\_widgets\_order()](https://developer.wordpress.org/reference/functions/wp_ajax_widgets_order/) `wp-admin/includes/ajax-actions.php` | Handles saving the widgets order via AJAX. |
| [wp\_ajax\_add\_link\_category()](https://developer.wordpress.org/reference/functions/wp_ajax_add_link_category/) `wp-admin/includes/ajax-actions.php` | Handles adding a link category via AJAX. |
| [wp\_ajax\_nopriv\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_nopriv_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API in the no-privilege context via AJAX . |
| [wp\_ajax\_ajax\_tag\_search()](https://developer.wordpress.org/reference/functions/wp_ajax_ajax_tag_search/) `wp-admin/includes/ajax-actions.php` | Handles tag search via AJAX. |
| [wp\_insert\_link()](https://developer.wordpress.org/reference/functions/wp_insert_link/) `wp-admin/includes/bookmark.php` | Inserts a link into the database, or updates an existing link. |
| [get\_default\_link\_to\_edit()](https://developer.wordpress.org/reference/functions/get_default_link_to_edit/) `wp-admin/includes/bookmark.php` | Retrieves the default link for editing. |
| [WP\_Terms\_List\_Table::column\_name()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/column_name/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [WP\_Terms\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/prepare_items/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [request\_filesystem\_credentials()](https://developer.wordpress.org/reference/functions/request_filesystem_credentials/) `wp-admin/includes/file.php` | Displays a form to the user to request for their FTP/SSH details in order to connect to the filesystem. |
| [WP\_Customize\_Manager::customize\_preview\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_preview_settings/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings for preview frame. |
| [WP\_Customize\_Manager::save()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save/) `wp-includes/class-wp-customize-manager.php` | Handles customize\_save WP Ajax request to save/update a changeset. |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [WP\_Customize\_Manager::doing\_ajax()](https://developer.wordpress.org/reference/classes/wp_customize_manager/doing_ajax/) `wp-includes/class-wp-customize-manager.php` | Returns true if it’s an Ajax request. |
| [spawn\_cron()](https://developer.wordpress.org/reference/functions/spawn_cron/) `wp-includes/cron.php` | Sends a request to run cron through HTTP request that doesn’t halt page loading. |
| [\_wp\_customize\_include()](https://developer.wordpress.org/reference/functions/_wp_customize_include/) `wp-includes/theme.php` | Includes and instantiates the [WP\_Customize\_Manager](https://developer.wordpress.org/reference/classes/wp_customize_manager/) class. |
| [WP::send\_headers()](https://developer.wordpress.org/reference/classes/wp/send_headers/) `wp-includes/class-wp.php` | Sends additional HTTP headers for caching, content type, etc. |
| [wp\_original\_referer\_field()](https://developer.wordpress.org/reference/functions/wp_original_referer_field/) `wp-includes/functions.php` | Retrieves or displays original referer hidden field for forms. |
| [wp\_get\_referer()](https://developer.wordpress.org/reference/functions/wp_get_referer/) `wp-includes/functions.php` | Retrieves referer from ‘\_wp\_http\_referer’ or HTTP referer. |
| [wp\_get\_original\_referer()](https://developer.wordpress.org/reference/functions/wp_get_original_referer/) `wp-includes/functions.php` | Retrieves original referer that was posted, if it exists. |
| [wp\_update\_term()](https://developer.wordpress.org/reference/functions/wp_update_term/) `wp-includes/taxonomy.php` | Updates term based on arguments provided. |
| [wp\_insert\_term()](https://developer.wordpress.org/reference/functions/wp_insert_term/) `wp-includes/taxonomy.php` | Adds a new term to the database. |
| [term\_exists()](https://developer.wordpress.org/reference/functions/term_exists/) `wp-includes/taxonomy.php` | Determines whether a taxonomy term exists. |
| [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) `wp-includes/user.php` | Inserts a user into the database. |
| [wp\_signon()](https://developer.wordpress.org/reference/functions/wp_signon/) `wp-includes/user.php` | Authenticates and logs a user in with ‘remember’ capability. |
| [post\_password\_required()](https://developer.wordpress.org/reference/functions/post_password_required/) `wp-includes/post-template.php` | Determines whether the post requires password and whether a correct password has been provided. |
| [\_wp\_link\_page()](https://developer.wordpress.org/reference/functions/_wp_link_page/) `wp-includes/post-template.php` | Helper function for [wp\_link\_pages()](https://developer.wordpress.org/reference/functions/wp_link_pages/) . |
| [trackback\_url\_list()](https://developer.wordpress.org/reference/functions/trackback_url_list/) `wp-includes/post.php` | Does trackbacks for a list of URLs. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wpmu\_log\_new\_registrations()](https://developer.wordpress.org/reference/functions/wpmu_log_new_registrations/) `wp-includes/ms-functions.php` | Logs the user email, IP, and registration date of a new site. |
| [newblog\_notify\_siteadmin()](https://developer.wordpress.org/reference/functions/newblog_notify_siteadmin/) `wp-includes/ms-functions.php` | Notifies the network admin that a new site has been activated. |
| [newuser\_notify\_siteadmin()](https://developer.wordpress.org/reference/functions/newuser_notify_siteadmin/) `wp-includes/ms-functions.php` | Notifies the network admin that a new user has been activated. |
| [wpmu\_welcome\_notification()](https://developer.wordpress.org/reference/functions/wpmu_welcome_notification/) `wp-includes/ms-functions.php` | Notifies the site administrator that their site activation was successful. |
| [install\_blog()](https://developer.wordpress.org/reference/functions/install_blog/) `wp-includes/ms-deprecated.php` | Install an empty blog. |
| [wpmu\_validate\_blog\_signup()](https://developer.wordpress.org/reference/functions/wpmu_validate_blog_signup/) `wp-includes/ms-functions.php` | Processes new site registrations. |
| [wp\_update\_nav\_menu\_item()](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/) `wp-includes/nav-menu.php` | Saves the properties of a menu item or create a new one. |
| [wp\_xmlrpc\_server::blogger\_getPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getpost/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post. |
| [wp\_xmlrpc\_server::blogger\_getRecentPosts()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getrecentposts/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the list of recent posts. |
| [wp\_xmlrpc\_server::wp\_setOptions()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_setoptions/) `wp-includes/class-wp-xmlrpc-server.php` | Updates blog options. |
| [wp\_xmlrpc\_server::set\_custom\_fields()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/set_custom_fields/) `wp-includes/class-wp-xmlrpc-server.php` | Sets custom fields for post. |
| [WP\_Customize\_Widgets::get\_post\_value()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/get_post_value/) `wp-includes/class-wp-customize-widgets.php` | Retrieves an unslashed post value or return a default. |
| [wp\_update\_comment()](https://developer.wordpress.org/reference/functions/wp_update_comment/) `wp-includes/comment.php` | Updates an existing comment in the database. |
| [wp\_insert\_comment()](https://developer.wordpress.org/reference/functions/wp_insert_comment/) `wp-includes/comment.php` | Inserts a comment into the database. |
| [sanitize\_comment\_cookies()](https://developer.wordpress.org/reference/functions/sanitize_comment_cookies/) `wp-includes/comment.php` | Sanitizes the cookies sent to the user already. |
| [wp\_allow\_comment()](https://developer.wordpress.org/reference/functions/wp_allow_comment/) `wp-includes/comment.php` | Validates whether this comment is allowed to be made. |
| [check\_comment()](https://developer.wordpress.org/reference/functions/check_comment/) `wp-includes/comment.php` | Checks whether a comment passes internal checks to be allowed to add. |
| [delete\_metadata()](https://developer.wordpress.org/reference/functions/delete_metadata/) `wp-includes/meta.php` | Deletes metadata for the specified object. |
| [add\_metadata()](https://developer.wordpress.org/reference/functions/add_metadata/) `wp-includes/meta.php` | Adds metadata for the specified object. |
| [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/) `wp-includes/meta.php` | Updates metadata for the specified object. If no value already exists for the specified object ID and metadata key, the metadata will be added. |

[Show 136 more](https://developer.wordpress.org/reference/functions/wp_unslash/#) [Show less](https://developer.wordpress.org/reference/functions/wp_unslash/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_unslash/\#changelog)

| Version | Description |
| --- | --- |
| [3.6.0](https://developer.wordpress.org/reference/since/3.6.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_unslash/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_unslash/#comment-content-1416)



**Example**



This function can be used in replacement of [stripslashes\_deep()](https://developer.wordpress.org/reference/functions/stripslashes_deep/) . As it is a recursive function, when an array is given, it will remove slashes in all sub-arrays too.





`wp-includes/formatting.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_unslash/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_unslash/#)




```php
$arr = array(
   	"Is your name O\'reilly?",
   	"Person\'s Assets"
);

$arr = wp_unslash( $arr );
/*
    Outputs:
    array(
         "Is your name O'reilly?",
         "Person's Assets"
    );
*/
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unslash%2F%3Freplytocom%3D1416%23feedback-editor-1416)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/wp_unslash/#comment-content-5251)



This function was called when we try to read `$_COOKIES`:





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_unslash/#)




```php
$viewed_products = ! empty( $_COOKIE['woocommerce_recently_viewed'] ) ? (array) explode( '|', wp_unslash( $_COOKIE['woocommerce_recently_viewed'] ) ) : array(); // @codingStandardsIgnoreLine
$viewed_products = array_reverse( array_filter( array_map( 'absint', $viewed_products ) ) );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unslash%2F%3Freplytocom%3D5251%23feedback-editor-5251)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_unslash/#comment-content-5640)



It’s unfortunate that we have to invoke this function to undo the garbling of the input values performed by WordPress itself. The [bug reports](https://core.trac.wordpress.org/ticket/18322) for fixing the problem have been thrashing about for years, and it’s unclear whether the problem will ever be fixed, or how. In the meantime here’s one way to deal with it, using a technique which should survive without having to revisit code in the event that WP ever bites the bullet and removes the unwanted escaping.



- add a hidden field with an apostrophe but no backslash in the value ( _e.g._, “foo’bar”)
- when processing the posted form, test that value as returned in `$_POST`
- if the value contains a backslash character, make a copy of `$_POST` using `wp_unslash()`
- otherwise, WP has abandoned the practice of escaping the posted values, so no unslashing is needed

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unslash%2F%3Freplytocom%3D5640%23feedback-editor-5640)

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_unslash%2F) before being able to contribute a note or feedback.

Notifications