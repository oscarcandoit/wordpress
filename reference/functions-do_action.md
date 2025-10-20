---
url: https://developer.wordpress.org/reference/functions/do_action
scraped_at: 2025-10-20T03:40:04.319Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/do_action/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

do\_action()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)do\_action()

Search

# do\_action( string$hook\_name, mixed$arg )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/do_action/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/do_action/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/do_action/#source)
- [Related](https://developer.wordpress.org/reference/functions/do_action/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/do_action/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/do_action/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/do_action/#wp--skip-link--target)

Calls the callback functions that have been added to an action hook.

## [Description](https://developer.wordpress.org/reference/functions/do_action/\#description)

This function invokes all functions attached to action hook `$hook_name`.

It is possible to create new action hooks by simply calling this function, specifying the name of the new hook using the `$hook_name` parameter.

You can pass extra arguments to the hooks, much like you can with `apply_filters()`.

Example usage:

`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/do_action/#)

[Copy](https://developer.wordpress.org/reference/functions/do_action/#)

```php
// The action callback function.
function example_callback( $arg1, $arg2 ) {
    // (maybe) do something with the args.
}
add_action( 'example_action', 'example_callback', 10, 2 );

/*
 * Trigger the actions by calling the 'example_callback()' function
 * that's hooked onto `example_action` above.
 *
 * - 'example_action' is the action hook.
 * - $arg1 and $arg2 are the additional arguments passed to the callback.
do_action( 'example_action', $arg1, $arg2 );
```

## [Parameters](https://developer.wordpress.org/reference/functions/do_action/\#parameters)

`$hook_name` stringrequired

The name of the action to be executed.

`$arg` mixedoptional

Additional arguments which are passed on to the functions hooked to the action. Default empty.

## [Source](https://developer.wordpress.org/reference/functions/do_action/\#source)

`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/do_action/#)

[Copy](https://developer.wordpress.org/reference/functions/do_action/#)

```php
function do_action( $hook_name, ...$arg ) {
	global $wp_filter, $wp_actions, $wp_current_filter;

	if ( ! isset( $wp_actions[ $hook_name ] ) ) {
		$wp_actions[ $hook_name ] = 1;
	} else {
		++$wp_actions[ $hook_name ];
	}

	// Do 'all' actions first.
	if ( isset( $wp_filter['all'] ) ) {
		$wp_current_filter[] = $hook_name;
		$all_args            = func_get_args(); // phpcs:ignore PHPCompatibility.FunctionUse.ArgumentFunctionsReportCurrentValue.NeedsInspection
		_wp_call_all_hook( $all_args );
	}

	if ( ! isset( $wp_filter[ $hook_name ] ) ) {
		if ( isset( $wp_filter['all'] ) ) {
			array_pop( $wp_current_filter );
		}

		return;
	}

	if ( ! isset( $wp_filter['all'] ) ) {
		$wp_current_filter[] = $hook_name;
	}

	if ( empty( $arg ) ) {
		$arg[] = '';
	} elseif ( is_array( $arg[0] ) && 1 === count( $arg[0] ) && isset( $arg[0][0] ) && is_object( $arg[0][0] ) ) {
		// Backward compatibility for PHP4-style passing of `array( &$this )` as action `$arg`.
		$arg[0] = $arg[0][0];
	}

	$wp_filter[ $hook_name ]->do_action( $arg );

	array_pop( $wp_current_filter );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L482) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L482-L520)

## [Related](https://developer.wordpress.org/reference/functions/do_action/\#related)

| Uses | Description |
| --- | --- |
| [\_wp\_call\_all\_hook()](https://developer.wordpress.org/reference/functions/_wp_call_all_hook/) `wp-includes/plugin.php` | Calls the ‘all’ hook, which will process the functions hooked into it. |

| Used by | Description |
| --- | --- |
| [wp\_admin\_notice()](https://developer.wordpress.org/reference/functions/wp_admin_notice/) `wp-includes/functions.php` | Outputs an admin notice. |
| [wp\_trigger\_error()](https://developer.wordpress.org/reference/functions/wp_trigger_error/) `wp-includes/functions.php` | Generates a user-level error/warning/notice/deprecation message. |
| [\_deprecated\_class()](https://developer.wordpress.org/reference/functions/_deprecated_class/) `wp-includes/functions.php` | Marks a class as deprecated and informs when it has been used. |
| [wp\_cache\_set\_last\_changed()](https://developer.wordpress.org/reference/functions/wp_cache_set_last_changed/) `wp-includes/functions.php` | Sets last changed date for the specified cache group to now. |
| [\_wp\_get\_iframed\_editor\_assets()](https://developer.wordpress.org/reference/functions/_wp_get_iframed_editor_assets/) `wp-includes/block-editor.php` | Collect the block editor assets that need to be loaded into the editor’s iframe. |
| [WP\_REST\_Menu\_Items\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Creates a single nav menu item. |
| [WP\_REST\_Menu\_Items\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Updates a single nav menu item. |
| [WP\_REST\_Menu\_Items\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Deletes a single nav menu item. |
| [WP\_REST\_Menus\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Creates a single term in a taxonomy. |
| [WP\_REST\_Menus\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Updates a single term from a taxonomy. |
| [WP\_REST\_Menus\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Deletes a single term from a taxonomy. |
| [WP\_REST\_Menus\_Controller::handle\_auto\_add()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/handle_auto_add/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Updates the menu’s auto add from a REST request. |
| [WP\_REST\_Widgets\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_widgets_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-widgets-controller.php` | Deletes a widget. |
| [WP\_REST\_Widgets\_Controller::save\_widget()](https://developer.wordpress.org/reference/classes/wp_rest_widgets_controller/save_widget/) `wp-includes/rest-api/endpoints/class-wp-rest-widgets-controller.php` | Saves the widget in the request object. |
| [WP\_REST\_Sidebars\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_sidebars_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-sidebars-controller.php` | Updates a sidebar. |
| [WP\_REST\_Templates\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_templates_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php` | Updates a single template. |
| [WP\_REST\_Templates\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_templates_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php` | Creates a single template. |
| [wp\_render\_widget()](https://developer.wordpress.org/reference/functions/wp_render_widget/) `wp-includes/widgets.php` | Calls the render callback of a widget and returns the output. |
| [WP\_REST\_Application\_Passwords\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_application_passwords_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-application-passwords-controller.php` | Creates an application password. |
| [WP\_REST\_Application\_Passwords\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_application_passwords_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-application-passwords-controller.php` | Updates an application password. |
| [WP\_Application\_Passwords::delete\_application\_password()](https://developer.wordpress.org/reference/classes/wp_application_passwords/delete_application_password/) `wp-includes/class-wp-application-passwords.php` | Deletes an application password. |
| [WP\_Application\_Passwords::delete\_all\_application\_passwords()](https://developer.wordpress.org/reference/classes/wp_application_passwords/delete_all_application_passwords/) `wp-includes/class-wp-application-passwords.php` | Deletes all application passwords for the given user. |
| [WP\_Application\_Passwords::create\_new\_application\_password()](https://developer.wordpress.org/reference/classes/wp_application_passwords/create_new_application_password/) `wp-includes/class-wp-application-passwords.php` | Creates a new application password. |
| [WP\_Application\_Passwords::update\_application\_password()](https://developer.wordpress.org/reference/classes/wp_application_passwords/update_application_password/) `wp-includes/class-wp-application-passwords.php` | Updates an application password. |
| [wp\_authenticate\_application\_password()](https://developer.wordpress.org/reference/functions/wp_authenticate_application_password/) `wp-includes/user.php` | Authenticates the user using an application password. |
| [wp\_after\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_after_insert_post/) `wp-includes/post.php` | Fires actions after a post, its terms and meta data has been saved. |
| [WP\_Application\_Passwords\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_application_passwords_list_table/column_default/) `wp-admin/includes/class-wp-application-passwords-list-table.php` | Generates content for a single row of the table |
| [WP\_Application\_Passwords\_List\_Table::print\_js\_template\_row()](https://developer.wordpress.org/reference/classes/wp_application_passwords_list_table/print_js_template_row/) `wp-admin/includes/class-wp-application-passwords-list-table.php` | Prints the JavaScript template for the new row item. |
| [wp\_is\_authorize\_application\_password\_request\_valid()](https://developer.wordpress.org/reference/functions/wp_is_authorize_application_password_request_valid/) `wp-admin/includes/user.php` | Checks if the Authorize Application Password request is valid. |
| [core\_auto\_updates\_settings()](https://developer.wordpress.org/reference/functions/core_auto_updates_settings/) `wp-admin/update-core.php` | Display WordPress auto-updates settings. |
| [wp\_check\_comment\_disallowed\_list()](https://developer.wordpress.org/reference/functions/wp_check_comment_disallowed_list/) `wp-includes/comment.php` | Checks if a comment contains disallowed characters or words. |
| [wp\_sitemaps\_get\_server()](https://developer.wordpress.org/reference/functions/wp_sitemaps_get_server/) `wp-includes/sitemaps.php` | Retrieves the current Sitemaps server instance. |
| [do\_favicon()](https://developer.wordpress.org/reference/functions/do_favicon/) `wp-includes/functions.php` | Displays the favicon.ico file content. |
| [WP\_REST\_Attachments\_Controller::insert\_attachment()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/insert_attachment/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Inserts the attachment post in the database. Does not update the attachment meta. |
| [WP\_MS\_Sites\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/extra_tablenav/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Displays extra controls between bulk actions and pagination. |
| [WP\_Recovery\_Mode\_Key\_Service::generate\_and\_store\_recovery\_mode\_key()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_key_service/generate_and_store_recovery_mode_key/) `wp-includes/class-wp-recovery-mode-key-service.php` | Creates a recovery mode key. |
| [wp\_body\_open()](https://developer.wordpress.org/reference/functions/wp_body_open/) `wp-includes/general-template.php` | Fires the wp\_body\_open action. |
| [wp\_maybe\_transition\_site\_statuses\_on\_update()](https://developer.wordpress.org/reference/functions/wp_maybe_transition_site_statuses_on_update/) `wp-includes/ms-site.php` | Triggers actions on site status updates. |
| [wp\_prepare\_site\_data()](https://developer.wordpress.org/reference/functions/wp_prepare_site_data/) `wp-includes/ms-site.php` | Prepares site data for insertion or update in the database. |
| [wp\_insert\_site()](https://developer.wordpress.org/reference/functions/wp_insert_site/) `wp-includes/ms-site.php` | Inserts a new site into the database. |
| [wp\_update\_site()](https://developer.wordpress.org/reference/functions/wp_update_site/) `wp-includes/ms-site.php` | Updates a site in the database. |
| [wp\_delete\_site()](https://developer.wordpress.org/reference/functions/wp_delete_site/) `wp-includes/ms-site.php` | Deletes a site from the database. |
| [WP\_REST\_Autosaves\_Controller::create\_post\_autosave()](https://developer.wordpress.org/reference/classes/wp_rest_autosaves_controller/create_post_autosave/) `wp-includes/rest-api/endpoints/class-wp-rest-autosaves-controller.php` | Creates autosave for the specified post. |
| [wp\_common\_block\_scripts\_and\_styles()](https://developer.wordpress.org/reference/functions/wp_common_block_scripts_and_styles/) `wp-includes/script-loader.php` | Handles the enqueueing of block scripts and styles that are common to both the editor and the front-end. |
| [the\_block\_editor\_meta\_box\_post\_form\_hidden\_fields()](https://developer.wordpress.org/reference/functions/the_block_editor_meta_box_post_form_hidden_fields/) `wp-admin/includes/post.php` | Renders the hidden form required for the meta boxes form. |
| [register\_and\_do\_post\_meta\_boxes()](https://developer.wordpress.org/reference/functions/register_and_do_post_meta_boxes/) `wp-admin/includes/meta-boxes.php` | Registers the default post meta boxes, and runs the `do_meta_boxes` actions. |
| [wp\_privacy\_process\_personal\_data\_export\_page()](https://developer.wordpress.org/reference/functions/wp_privacy_process_personal_data_export_page/) `wp-admin/includes/privacy-tools.php` | Intercept personal data exporter page Ajax responses in order to assemble the personal data export file. |
| [wp\_privacy\_generate\_personal\_data\_export\_file()](https://developer.wordpress.org/reference/functions/wp_privacy_generate_personal_data_export_file/) `wp-admin/includes/privacy-tools.php` | Generate the personal data export file. |
| [WP\_Privacy\_Requests\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_privacy_requests_table/column_default/) `wp-admin/includes/class-wp-privacy-requests-table.php` | Handles the default column. |
| [wp\_privacy\_process\_personal\_data\_erasure\_page()](https://developer.wordpress.org/reference/functions/wp_privacy_process_personal_data_erasure_page/) `wp-admin/includes/privacy-tools.php` | Mark erasure requests as completed after processing is finished. |
| [WP\_Customize\_Manager::trash\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/trash_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Trashes or deletes a changeset post. |
| [clean\_taxonomy\_cache()](https://developer.wordpress.org/reference/functions/clean_taxonomy_cache/) `wp-includes/taxonomy.php` | Cleans the caches for a taxonomy. |
| [wp\_enqueue\_code\_editor()](https://developer.wordpress.org/reference/functions/wp_enqueue_code_editor/) `wp-includes/general-template.php` | Enqueues assets needed by the code editor for the given settings. |
| [WP\_Roles::init\_roles()](https://developer.wordpress.org/reference/classes/wp_roles/init_roles/) `wp-includes/class-wp-roles.php` | Initializes all of the available roles. |
| [\_WP\_Editors::print\_default\_editor\_scripts()](https://developer.wordpress.org/reference/classes/_wp_editors/print_default_editor_scripts/) `wp-includes/class-wp-editor.php` | Print (output) all editor scripts and default settings. |
| [WP\_Customize\_Manager::\_publish\_changeset\_values()](https://developer.wordpress.org/reference/classes/wp_customize_manager/_publish_changeset_values/) `wp-includes/class-wp-customize-manager.php` | Publishes the values of a changeset. |
| [WP\_Customize\_Manager::save\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Saves the post for the loaded changeset. |
| [\_wp\_customize\_publish\_changeset()](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/) `wp-includes/theme.php` | Publishes a snapshot’s changes. |
| [WP\_REST\_Users\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Deletes a single user. |
| [WP\_REST\_Users\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Creates a single user. |
| [WP\_REST\_Users\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Updates a single user. |
| [WP\_REST\_Revisions\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_revisions_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php` | Deletes a single revision. |
| [WP\_REST\_Attachments\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Creates a single attachment. |
| [WP\_REST\_Attachments\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Updates a single attachment. |
| [WP\_REST\_Terms\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Deletes a single term from a taxonomy. |
| [WP\_REST\_Terms\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Creates a single term in a taxonomy. |
| [WP\_REST\_Terms\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Updates a single term from a taxonomy. |
| [WP\_REST\_Posts\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Creates a single post. |
| [WP\_REST\_Posts\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Updates a single post. |
| [WP\_REST\_Posts\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Deletes a single post. |
| [WP\_REST\_Comments\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Updates a comment. |
| [WP\_REST\_Comments\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Deletes a comment. |
| [WP\_REST\_Comments\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Creates a comment. |
| [WP\_Locale\_Switcher::change\_locale()](https://developer.wordpress.org/reference/classes/wp_locale_switcher/change_locale/) `wp-includes/class-wp-locale-switcher.php` | Changes the site’s locale to the given one. |
| [WP\_Locale\_Switcher::switch\_to\_locale()](https://developer.wordpress.org/reference/classes/wp_locale_switcher/switch_to_locale/) `wp-includes/class-wp-locale-switcher.php` | Switches the translations according to the given locale. |
| [WP\_Locale\_Switcher::restore\_previous\_locale()](https://developer.wordpress.org/reference/classes/wp_locale_switcher/restore_previous_locale/) `wp-includes/class-wp-locale-switcher.php` | Restores the translations according to the previous locale. |
| [wp\_check\_comment\_flood()](https://developer.wordpress.org/reference/functions/wp_check_comment_flood/) `wp-includes/comment.php` | Checks whether comment flooding is occurring. |
| [WP\_Term\_Query::parse\_query()](https://developer.wordpress.org/reference/classes/wp_term_query/parse_query/) `wp-includes/class-wp-term-query.php` | Parse arguments passed to the term query with default query parameters. |
| [clean\_network\_cache()](https://developer.wordpress.org/reference/functions/clean_network_cache/) `wp-includes/ms-network.php` | Removes a network from the object cache. |
| [\_deprecated\_hook()](https://developer.wordpress.org/reference/functions/_deprecated_hook/) `wp-includes/functions.php` | Marks a deprecated action or filter hook as deprecated and throws a notice. |
| [ms\_load\_current\_site\_and\_network()](https://developer.wordpress.org/reference/functions/ms_load_current_site_and_network/) `wp-includes/ms-load.php` | Identifies the network and site of a requested domain and path and populates the corresponding network and site global objects as part of the multisite bootstrap process. |
| [rest\_get\_server()](https://developer.wordpress.org/reference/functions/rest_get_server/) `wp-includes/rest-api.php` | Retrieves the current REST server instance. |
| [WP\_Metadata\_Lazyloader::queue\_objects()](https://developer.wordpress.org/reference/classes/wp_metadata_lazyloader/queue_objects/) `wp-includes/class-wp-metadata-lazyloader.php` | Adds objects to the metadata lazy-load queue. |
| [unregister\_taxonomy()](https://developer.wordpress.org/reference/functions/unregister_taxonomy/) `wp-includes/taxonomy.php` | Unregisters a taxonomy. |
| [unregister\_post\_type()](https://developer.wordpress.org/reference/functions/unregister_post_type/) `wp-includes/post.php` | Unregisters a post type. |
| [WP\_Customize\_Selective\_Refresh::handle\_render\_partials\_request()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/handle_render_partials_request/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Handles the Ajax request to return the rendered partials for the requested placements. |
| [enqueue\_embed\_scripts()](https://developer.wordpress.org/reference/functions/enqueue_embed_scripts/) `wp-includes/embed.php` | Enqueues embed iframe default CSS and JS. |
| [get\_password\_reset\_key()](https://developer.wordpress.org/reference/functions/get_password_reset_key/) `wp-includes/user.php` | Creates, stores, then returns a password reset key for user. |
| [wp\_handle\_comment\_submission()](https://developer.wordpress.org/reference/functions/wp_handle_comment_submission/) `wp-includes/comment.php` | Handles the submission of a comment, usually posted to wp-comments-post.php via a comment form. |
| [update\_network\_option()](https://developer.wordpress.org/reference/functions/update_network_option/) `wp-includes/option.php` | Updates the value of a network option that was already added. |
| [add\_network\_option()](https://developer.wordpress.org/reference/functions/add_network_option/) `wp-includes/option.php` | Adds a new network option. |
| [delete\_network\_option()](https://developer.wordpress.org/reference/functions/delete_network_option/) `wp-includes/option.php` | Removes a network option by name. |
| [wp\_ajax\_delete\_inactive\_widgets()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_inactive_widgets/) `wp-admin/includes/ajax-actions.php` | Handles removing inactive widgets via AJAX. |
| [WP\_Customize\_Nav\_Menu\_Item\_Control::content\_template()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_control/content_template/) `wp-includes/customize/class-wp-customize-nav-menu-item-control.php` | JS/Underscore template for the control UI. |
| [\_deprecated\_constructor()](https://developer.wordpress.org/reference/functions/_deprecated_constructor/) `wp-includes/functions.php` | Marks a constructor as deprecated and informs when it has been used. |
| [WP\_Posts\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_default/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the default column output. |
| [WP\_Links\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_links_list_table/column_default/) `wp-admin/includes/class-wp-links-list-table.php` | Handles the default column output. |
| [WP\_MS\_Themes\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/column_default/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Handles default column output. |
| [wp\_ajax\_crop\_image()](https://developer.wordpress.org/reference/functions/wp_ajax_crop_image/) `wp-admin/includes/ajax-actions.php` | Handles cropping an image via AJAX. |
| [WP\_MS\_Sites\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/column_default/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Handles output for the default column. |
| [WP\_MS\_Sites\_List\_Table::column\_plugins()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/column_plugins/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Handles the plugins column output. |
| [WP\_Media\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_media_list_table/column_default/) `wp-admin/includes/class-wp-media-list-table.php` | Handles output for the default column. |
| [WP\_Customize\_Manager::set\_post\_value()](https://developer.wordpress.org/reference/classes/wp_customize_manager/set_post_value/) `wp-includes/class-wp-customize-manager.php` | Overrides a setting’s value in the current customized state. |
| [wp\_media\_attach\_action()](https://developer.wordpress.org/reference/functions/wp_media_attach_action/) `wp-admin/includes/media.php` | Encapsulates the logic for Attach/Detach actions. |
| [WP\_Customize\_Panel::maybe\_render()](https://developer.wordpress.org/reference/classes/wp_customize_panel/maybe_render/) `wp-includes/class-wp-customize-panel.php` | Check capabilities and render the panel. |
| [retrieve\_password()](https://developer.wordpress.org/reference/functions/retrieve_password/) `wp-includes/user.php` | Handles sending a password retrieval email to a user. |
| [login\_footer()](https://developer.wordpress.org/reference/functions/login_footer/) `wp-login.php` | Outputs the footer for the login page. |
| [login\_header()](https://developer.wordpress.org/reference/functions/login_header/) `wp-login.php` | Outputs the login page header. |
| [show\_user\_form()](https://developer.wordpress.org/reference/functions/show_user_form/) `wp-signup.php` | Displays the fields for the new user account registration form. |
| [signup\_another\_blog()](https://developer.wordpress.org/reference/functions/signup_another_blog/) `wp-signup.php` | Shows a form for returning users to sign up for another site. |
| [confirm\_another\_blog\_signup()](https://developer.wordpress.org/reference/functions/confirm_another_blog_signup/) `wp-signup.php` | Shows a message confirming that the new site has been created. |
| [signup\_user()](https://developer.wordpress.org/reference/functions/signup_user/) `wp-signup.php` | Shows a form for a visitor to sign up for a new user account. |
| [confirm\_user\_signup()](https://developer.wordpress.org/reference/functions/confirm_user_signup/) `wp-signup.php` | Shows a message confirming that the new user has been registered and is awaiting activation. |
| [signup\_blog()](https://developer.wordpress.org/reference/functions/signup_blog/) `wp-signup.php` | Shows a form for a user or visitor to sign up for a new site. |
| [confirm\_blog\_signup()](https://developer.wordpress.org/reference/functions/confirm_blog_signup/) `wp-signup.php` | Shows a message confirming that the new site has been registered and is awaiting activation. |
| [do\_signup\_header()](https://developer.wordpress.org/reference/functions/do_signup_header/) `wp-signup.php` | Prints signup\_header via wp\_head. |
| [show\_blog\_form()](https://developer.wordpress.org/reference/functions/show_blog_form/) `wp-signup.php` | Generates and displays the Sign-up and Create Site forms. |
| [display\_setup\_form()](https://developer.wordpress.org/reference/functions/display_setup_form/) `wp-admin/install.php` | Displays installer setup form. |
| [WP\_Automatic\_Updater::update()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/update/) `wp-admin/includes/class-wp-automatic-updater.php` | Updates an item, if appropriate. |
| [WP\_Automatic\_Updater::run()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/run/) `wp-admin/includes/class-wp-automatic-updater.php` | Kicks off the background update process, looping through all pending updates. |
| [Language\_Pack\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/language_pack_upgrader/bulk_upgrade/) `wp-admin/includes/class-language-pack-upgrader.php` | Upgrades several language packs at once. |
| [Core\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/core_upgrader/upgrade/) `wp-admin/includes/class-core-upgrader.php` | Upgrades WordPress core. |
| [Plugin\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/bulk_upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades several plugins at once. |
| [Theme\_Upgrader::install()](https://developer.wordpress.org/reference/classes/theme_upgrader/install/) `wp-admin/includes/class-theme-upgrader.php` | Install a theme package. |
| [Theme\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/bulk_upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades several themes at once. |
| [Plugin\_Upgrader::install()](https://developer.wordpress.org/reference/classes/plugin_upgrader/install/) `wp-admin/includes/class-plugin-upgrader.php` | Install a plugin package. |
| [WP\_Upgrader::run()](https://developer.wordpress.org/reference/classes/wp_upgrader/run/) `wp-admin/includes/class-wp-upgrader.php` | Runs an upgrade/installation. |
| [delete\_theme()](https://developer.wordpress.org/reference/functions/delete_theme/) `wp-admin/includes/theme.php` | Removes a theme. |
| [WP\_Screen::set\_current\_screen()](https://developer.wordpress.org/reference/classes/wp_screen/set_current_screen/) `wp-admin/includes/class-wp-screen.php` | Makes the screen object the current screen. |
| [WP\_Plugins\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/single_row/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [grant\_super\_admin()](https://developer.wordpress.org/reference/functions/grant_super_admin/) `wp-includes/capabilities.php` | Grants Super Admin privileges. |
| [revoke\_super\_admin()](https://developer.wordpress.org/reference/functions/revoke_super_admin/) `wp-includes/capabilities.php` | Revokes Super Admin privileges. |
| [wpmu\_delete\_user()](https://developer.wordpress.org/reference/functions/wpmu_delete_user/) `wp-admin/includes/ms.php` | Deletes a user and all of their posts from the network. |
| [update\_user\_status()](https://developer.wordpress.org/reference/functions/update_user_status/) `wp-includes/ms-deprecated.php` | Update the status of a user in the database. |
| [WP\_MS\_Themes\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/single_row/) `wp-admin/includes/class-wp-ms-themes-list-table.php` |  |
| [populate\_options()](https://developer.wordpress.org/reference/functions/populate_options/) `wp-admin/includes/schema.php` | Create WordPress options and set the default values. |
| [WP\_Theme\_Install\_List\_Table::display()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/display/) `wp-admin/includes/class-wp-theme-install-list-table.php` | Displays the theme install table. |
| [wp\_plugin\_update\_row()](https://developer.wordpress.org/reference/functions/wp_plugin_update_row/) `wp-admin/includes/update.php` | Displays update information for a plugin. |
| [wp\_theme\_update\_row()](https://developer.wordpress.org/reference/functions/wp_theme_update_row/) `wp-admin/includes/update.php` | Displays update information for a theme. |
| [wp\_dashboard\_right\_now()](https://developer.wordpress.org/reference/functions/wp_dashboard_right_now/) `wp-admin/includes/dashboard.php` | Dashboard widget that displays some basic stats about the site. |
| [wp\_network\_dashboard\_right\_now()](https://developer.wordpress.org/reference/functions/wp_network_dashboard_right_now/) `wp-admin/includes/dashboard.php` |  |
| [wp\_dashboard\_setup()](https://developer.wordpress.org/reference/functions/wp_dashboard_setup/) `wp-admin/includes/dashboard.php` | Registers dashboard widgets. |
| [wp\_upgrade()](https://developer.wordpress.org/reference/functions/wp_upgrade/) `wp-admin/includes/upgrade.php` | Runs WordPress Upgrade functions. |
| [wp\_install()](https://developer.wordpress.org/reference/functions/wp_install/) `wp-admin/includes/upgrade.php` | Installs the site. |
| [register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) `wp-includes/option.php` | Registers a setting and its data. |
| [unregister\_setting()](https://developer.wordpress.org/reference/functions/unregister_setting/) `wp-includes/option.php` | Unregisters a setting. |
| [uninstall\_plugin()](https://developer.wordpress.org/reference/functions/uninstall_plugin/) `wp-admin/includes/plugin.php` | Uninstalls a single plugin. |
| [deactivate\_plugins()](https://developer.wordpress.org/reference/functions/deactivate_plugins/) `wp-admin/includes/plugin.php` | Deactivates a single plugin or multiple plugins. |
| [delete\_plugins()](https://developer.wordpress.org/reference/functions/delete_plugins/) `wp-admin/includes/plugin.php` | Removes directory and files of a plugin for a list of plugins. |
| [activate\_plugin()](https://developer.wordpress.org/reference/functions/activate_plugin/) `wp-admin/includes/plugin.php` | Attempts activation of plugin in a “sandbox” and redirects on success. |
| [edit\_user()](https://developer.wordpress.org/reference/functions/edit_user/) `wp-admin/includes/user.php` | Edit user settings based on contents of $\_POST |
| [wp\_delete\_user()](https://developer.wordpress.org/reference/functions/wp_delete_user/) `wp-admin/includes/user.php` | Delete user and optionally reassign posts and links to another user. |
| [WP\_Plugin\_Install\_List\_Table::display\_tablenav()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/display_tablenav/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [\_wp\_admin\_html\_begin()](https://developer.wordpress.org/reference/functions/_wp_admin_html_begin/) `wp-admin/includes/template.php` | Prints out the beginning of the admin HTML header. |
| [iframe\_header()](https://developer.wordpress.org/reference/functions/iframe_header/) `wp-admin/includes/template.php` | Generic Iframe header for use with Thickbox. |
| [iframe\_footer()](https://developer.wordpress.org/reference/functions/iframe_footer/) `wp-admin/includes/template.php` | Generic Iframe footer for use with Thickbox. |
| [get\_inline\_data()](https://developer.wordpress.org/reference/functions/get_inline_data/) `wp-admin/includes/template.php` | Adds hidden fields with the data for use in the inline editor for posts and pages. |
| [WP\_Users\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_users_list_table/extra_tablenav/) `wp-admin/includes/class-wp-users-list-table.php` | Outputs the controls to allow user roles to be changed in bulk. |
| [edit\_form\_image\_editor()](https://developer.wordpress.org/reference/functions/edit_form_image_editor/) `wp-admin/includes/media.php` | Displays the image and editor in the post editor |
| [media\_upload\_form()](https://developer.wordpress.org/reference/functions/media_upload_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form. |
| [wp\_iframe()](https://developer.wordpress.org/reference/functions/wp_iframe/) `wp-admin/includes/media.php` | Outputs the iframe to display the media upload page. |
| [\_admin\_notice\_post\_locked()](https://developer.wordpress.org/reference/functions/_admin_notice_post_locked/) `wp-admin/includes/post.php` | Outputs the HTML for the notice to say that someone else is editing or has taken over editing of this post. |
| [wp\_create\_post\_autosave()](https://developer.wordpress.org/reference/functions/wp_create_post_autosave/) `wp-admin/includes/post.php` | Creates autosave data for the specified post from `$_POST` data. |
| [bulk\_edit\_posts()](https://developer.wordpress.org/reference/functions/bulk_edit_posts/) `wp-admin/includes/post.php` | Processes the post data for the bulk editing of posts. |
| [wp\_ajax\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API via AJAX. |
| [wp\_ajax\_save\_widget()](https://developer.wordpress.org/reference/functions/wp_ajax_save_widget/) `wp-admin/includes/ajax-actions.php` | Handles saving a widget via AJAX. |
| [update\_core()](https://developer.wordpress.org/reference/functions/update_core/) `wp-admin/includes/update-core.php` | Upgrades the core of WordPress. |
| [wp\_ajax\_nopriv\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_nopriv_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API in the no-privilege context via AJAX . |
| [post\_comment\_status\_meta\_box()](https://developer.wordpress.org/reference/functions/post_comment_status_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays comments status form fields. |
| [page\_attributes\_meta\_box()](https://developer.wordpress.org/reference/functions/page_attributes_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays page attributes form fields. |
| [link\_submit\_meta\_box()](https://developer.wordpress.org/reference/functions/link_submit_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays link create form fields. |
| [post\_submit\_meta\_box()](https://developer.wordpress.org/reference/functions/post_submit_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post submit form fields. |
| [attachment\_submit\_meta\_box()](https://developer.wordpress.org/reference/functions/attachment_submit_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays attachment submit form fields. |
| [wp\_insert\_link()](https://developer.wordpress.org/reference/functions/wp_insert_link/) `wp-admin/includes/bookmark.php` | Inserts a link into the database, or updates an existing link. |
| [wp\_delete\_link()](https://developer.wordpress.org/reference/functions/wp_delete_link/) `wp-admin/includes/bookmark.php` | Deletes a specified link from the database. |
| [WP\_Media\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_media_list_table/extra_tablenav/) `wp-admin/includes/class-wp-media-list-table.php` |  |
| [WP\_Comments\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/column_default/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/extra_tablenav/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Terms\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/inline_edit/) `wp-admin/includes/class-wp-terms-list-table.php` | Outputs the hidden row displayed when inline editing |
| [Walker\_Nav\_Menu\_Edit::start\_el()](https://developer.wordpress.org/reference/classes/walker_nav_menu_edit/start_el/) `wp-admin/includes/class-walker-nav-menu-edit.php` | Start the element output. |
| [wp\_nav\_menu\_update\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_nav_menu_update_menu_items/) `wp-admin/includes/nav-menu.php` | Saves nav menu items. |
| [WP\_Posts\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/inline_edit/) `wp-admin/includes/class-wp-posts-list-table.php` | Outputs the hidden row displayed when inline editing |
| [WP\_Posts\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/extra_tablenav/) `wp-admin/includes/class-wp-posts-list-table.php` |  |
| [Custom\_Image\_Header::step\_1()](https://developer.wordpress.org/reference/classes/custom_image_header/step_1/) `wp-admin/includes/class-custom-image-header.php` | Displays first step of custom header image page. |
| [confirm\_delete\_users()](https://developer.wordpress.org/reference/functions/confirm_delete_users/) `wp-admin/includes/ms.php` |  |
| [do\_activate\_header()](https://developer.wordpress.org/reference/functions/do_activate_header/) `wp-activate.php` | Adds an action hook specific to this page. |
| [WP\_User::add\_role()](https://developer.wordpress.org/reference/classes/wp_user/add_role/) `wp-includes/class-wp-user.php` | Adds role to user. |
| [WP\_User::remove\_role()](https://developer.wordpress.org/reference/classes/wp_user/remove_role/) `wp-includes/class-wp-user.php` | Removes role from user. |
| [WP\_User::set\_role()](https://developer.wordpress.org/reference/classes/wp_user/set_role/) `wp-includes/class-wp-user.php` | Sets the role of the user. |
| [WP\_Customize\_Manager::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_preview_init/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings. |
| [WP\_Customize\_Manager::start\_previewing\_theme()](https://developer.wordpress.org/reference/classes/wp_customize_manager/start_previewing_theme/) `wp-includes/class-wp-customize-manager.php` | If the theme to be previewed isn’t the active theme, add filter callbacks to swap it out at runtime. |
| [WP\_Customize\_Manager::stop\_previewing\_theme()](https://developer.wordpress.org/reference/classes/wp_customize_manager/stop_previewing_theme/) `wp-includes/class-wp-customize-manager.php` | Stops previewing the selected theme. |
| [WP\_Customize\_Manager::wp\_loaded()](https://developer.wordpress.org/reference/classes/wp_customize_manager/wp_loaded/) `wp-includes/class-wp-customize-manager.php` | Registers styles/scripts and initialize the preview of each setting |
| [check\_theme\_switched()](https://developer.wordpress.org/reference/functions/check_theme_switched/) `wp-includes/theme.php` | Checks if a theme has been changed and runs ‘after\_switch\_theme’ hook on the next WP load. |
| [switch\_theme()](https://developer.wordpress.org/reference/functions/switch_theme/) `wp-includes/theme.php` | Switches the theme. |
| [wp\_set\_password()](https://developer.wordpress.org/reference/functions/wp_set_password/) `wp-includes/pluggable.php` | Updates the user’s password with a new hashed one. |
| [wp\_verify\_nonce()](https://developer.wordpress.org/reference/functions/wp_verify_nonce/) `wp-includes/pluggable.php` | Verifies that a correct security nonce was used with time limit. |
| [wp\_set\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_set_auth_cookie/) `wp-includes/pluggable.php` | Sets the authentication cookies based on user ID. |
| [wp\_clear\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_clear_auth_cookie/) `wp-includes/pluggable.php` | Removes all of the cookies associated with authentication. |
| [auth\_redirect()](https://developer.wordpress.org/reference/functions/auth_redirect/) `wp-includes/pluggable.php` | Checks if a user is logged in, if not it redirects them to the login page. |
| [check\_admin\_referer()](https://developer.wordpress.org/reference/functions/check_admin_referer/) `wp-includes/pluggable.php` | Ensures intent by verifying that a user was referred from another admin page with the correct security nonce. |
| [check\_ajax\_referer()](https://developer.wordpress.org/reference/functions/check_ajax_referer/) `wp-includes/pluggable.php` | Verifies the Ajax request to prevent processing requests external of the blog. |
| [wp\_authenticate()](https://developer.wordpress.org/reference/functions/wp_authenticate/) `wp-includes/pluggable.php` | Authenticates a user, confirming the login credentials are valid. |
| [wp\_logout()](https://developer.wordpress.org/reference/functions/wp_logout/) `wp-includes/pluggable.php` | Logs the current user out. |
| [wp\_validate\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_validate_auth_cookie/) `wp-includes/pluggable.php` | Validates authentication cookie. |
| [wp\_set\_current\_user()](https://developer.wordpress.org/reference/functions/wp_set_current_user/) `wp-includes/pluggable.php` | Changes the current user by ID or name. |
| [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) `wp-includes/pluggable.php` | Sends an email, similar to PHP’s mail function. |
| [wp\_head()](https://developer.wordpress.org/reference/functions/wp_head/) `wp-includes/general-template.php` | Fires the wp\_head action. |
| [wp\_footer()](https://developer.wordpress.org/reference/functions/wp_footer/) `wp-includes/general-template.php` | Fires the wp\_footer action. |
| [wp\_meta()](https://developer.wordpress.org/reference/functions/wp_meta/) `wp-includes/general-template.php` | Theme container function for the ‘wp\_meta’ action. |
| [get\_header()](https://developer.wordpress.org/reference/functions/get_header/) `wp-includes/general-template.php` | Loads header template. |
| [get\_footer()](https://developer.wordpress.org/reference/functions/get_footer/) `wp-includes/general-template.php` | Loads footer template. |
| [get\_sidebar()](https://developer.wordpress.org/reference/functions/get_sidebar/) `wp-includes/general-template.php` | Loads sidebar template. |
| [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) `wp-includes/general-template.php` | Loads a template part into a template. |
| [get\_search\_form()](https://developer.wordpress.org/reference/functions/get_search_form/) `wp-includes/general-template.php` | Displays search form. |
| [delete\_usermeta()](https://developer.wordpress.org/reference/functions/delete_usermeta/) `wp-includes/deprecated.php` | Remove user meta data. |
| [update\_usermeta()](https://developer.wordpress.org/reference/functions/update_usermeta/) `wp-includes/deprecated.php` | Update metadata of user. |
| [WP\_Query::have\_posts()](https://developer.wordpress.org/reference/classes/wp_query/have_posts/) `wp-includes/class-wp-query.php` | Determines whether there are more posts available in the loop. |
| [WP\_Query::the\_comment()](https://developer.wordpress.org/reference/classes/wp_query/the_comment/) `wp-includes/class-wp-query.php` | Sets up the current comment. |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |
| [WP\_Query::parse\_tax\_query()](https://developer.wordpress.org/reference/classes/wp_query/parse_tax_query/) `wp-includes/class-wp-query.php` | Parses various taxonomy related query vars. |
| [shutdown\_action\_hook()](https://developer.wordpress.org/reference/functions/shutdown_action_hook/) `wp-includes/load.php` | Runs just before PHP shuts down execution. |
| [WP\_Http::\_dispatch\_request()](https://developer.wordpress.org/reference/classes/wp_http/_dispatch_request/) `wp-includes/class-wp-http.php` | Dispatches a HTTP request to a supporting transport. |
| [WP\_Http::request()](https://developer.wordpress.org/reference/classes/wp_http/request/) `wp-includes/class-wp-http.php` | Send an HTTP request to a URI. |
| [wp\_print\_scripts()](https://developer.wordpress.org/reference/functions/wp_print_scripts/) `wp-includes/functions.wp-scripts.php` | Prints scripts in document head that are in the $handles queue. |
| [\_deprecated\_function()](https://developer.wordpress.org/reference/functions/_deprecated_function/) `wp-includes/functions.php` | Marks a function as deprecated and inform when it has been used. |
| [\_deprecated\_file()](https://developer.wordpress.org/reference/functions/_deprecated_file/) `wp-includes/functions.php` | Marks a file as deprecated and inform when it has been used. |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |
| [do\_robots()](https://developer.wordpress.org/reference/functions/do_robots/) `wp-includes/functions.php` | Displays the default robots.txt file content. |
| [do\_feed()](https://developer.wordpress.org/reference/functions/do_feed/) `wp-includes/functions.php` | Loads the feed template from the use of an action hook. |
| [wp\_widgets\_init()](https://developer.wordpress.org/reference/functions/wp_widgets_init/) `wp-includes/widgets.php` | Registers all of the default WordPress widgets on startup. |
| [WP\_Customize\_Section::maybe\_render()](https://developer.wordpress.org/reference/classes/wp_customize_section/maybe_render/) `wp-includes/class-wp-customize-section.php` | Check capabilities and render the section. |
| [\_update\_post\_term\_count()](https://developer.wordpress.org/reference/functions/_update_post_term_count/) `wp-includes/taxonomy.php` | Updates term count based on object types of the current taxonomy. |
| [\_update\_generic\_term\_count()](https://developer.wordpress.org/reference/functions/_update_generic_term_count/) `wp-includes/taxonomy.php` | Updates term count based on number of objects. |
| [clean\_object\_term\_cache()](https://developer.wordpress.org/reference/functions/clean_object_term_cache/) `wp-includes/taxonomy.php` | Removes the taxonomy relationship to terms from the cache. |
| [wp\_update\_term()](https://developer.wordpress.org/reference/functions/wp_update_term/) `wp-includes/taxonomy.php` | Updates term based on arguments provided. |
| [clean\_term\_cache()](https://developer.wordpress.org/reference/functions/clean_term_cache/) `wp-includes/taxonomy.php` | Removes all of the term IDs from the cache. |
| [wp\_set\_object\_terms()](https://developer.wordpress.org/reference/functions/wp_set_object_terms/) `wp-includes/taxonomy.php` | Creates term and taxonomy relationships. |
| [wp\_remove\_object\_terms()](https://developer.wordpress.org/reference/functions/wp_remove_object_terms/) `wp-includes/taxonomy.php` | Removes term(s) associated with a given object. |
| [wp\_insert\_term()](https://developer.wordpress.org/reference/functions/wp_insert_term/) `wp-includes/taxonomy.php` | Adds a new term to the database. |
| [wp\_delete\_term()](https://developer.wordpress.org/reference/functions/wp_delete_term/) `wp-includes/taxonomy.php` | Removes a term from the database. |
| [register\_taxonomy()](https://developer.wordpress.org/reference/functions/register_taxonomy/) `wp-includes/taxonomy.php` | Creates or modifies a taxonomy object. |
| [register\_taxonomy\_for\_object\_type()](https://developer.wordpress.org/reference/functions/register_taxonomy_for_object_type/) `wp-includes/taxonomy.php` | Adds an already registered taxonomy to an object type. |
| [unregister\_taxonomy\_for\_object\_type()](https://developer.wordpress.org/reference/functions/unregister_taxonomy_for_object_type/) `wp-includes/taxonomy.php` | Removes an already registered taxonomy from an object type. |
| [WP\_Admin\_Bar::add\_menus()](https://developer.wordpress.org/reference/classes/wp_admin_bar/add_menus/) `wp-includes/class-wp-admin-bar.php` | Adds menus to the admin bar. |
| [WP\_Admin\_Bar::initialize()](https://developer.wordpress.org/reference/classes/wp_admin_bar/initialize/) `wp-includes/class-wp-admin-bar.php` | Initializes the admin bar. |
| [wp\_version\_check()](https://developer.wordpress.org/reference/functions/wp_version_check/) `wp-includes/update.php` | Checks WordPress version against the newest version. |
| [wp\_print\_styles()](https://developer.wordpress.org/reference/functions/wp_print_styles/) `wp-includes/functions.wp-styles.php` | Displays styles that are in the $handles queue. |
| [wp\_admin\_bar\_render()](https://developer.wordpress.org/reference/functions/wp_admin_bar_render/) `wp-includes/admin-bar.php` | Renders the admin bar to the page based on the $wp\_admin\_bar->menu member var. |
| [WP\_Customize\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_setting/preview/) `wp-includes/class-wp-customize-setting.php` | Add filters to supply the setting’s value when accessed. |
| [WP\_Customize\_Setting::save()](https://developer.wordpress.org/reference/classes/wp_customize_setting/save/) `wp-includes/class-wp-customize-setting.php` | Checks user capabilities and theme supports, and then saves the value of the setting. |
| [WP\_Customize\_Setting::update()](https://developer.wordpress.org/reference/classes/wp_customize_setting/update/) `wp-includes/class-wp-customize-setting.php` | Save the value of the setting, using the related API. |
| [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/) `wp-includes/option.php` | Sets/updates the value of a site transient. |
| [delete\_site\_transient()](https://developer.wordpress.org/reference/functions/delete_site_transient/) `wp-includes/option.php` | Deletes a site transient. |
| [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/) `wp-includes/option.php` | Sets/updates the value of a transient. |
| [update\_option()](https://developer.wordpress.org/reference/functions/update_option/) `wp-includes/option.php` | Updates the value of an option that was already added. |
| [add\_option()](https://developer.wordpress.org/reference/functions/add_option/) `wp-includes/option.php` | Adds a new option. |
| [delete\_option()](https://developer.wordpress.org/reference/functions/delete_option/) `wp-includes/option.php` | Removes an option by name. Prevents removal of protected WordPress options. |
| [delete\_transient()](https://developer.wordpress.org/reference/functions/delete_transient/) `wp-includes/option.php` | Deletes a transient. |
| [wp\_update\_user()](https://developer.wordpress.org/reference/functions/wp_update_user/) `wp-includes/user.php` | Updates a user in the database. |
| [reset\_password()](https://developer.wordpress.org/reference/functions/reset_password/) `wp-includes/user.php` | Handles resetting the user’s password. |
| [register\_new\_user()](https://developer.wordpress.org/reference/functions/register_new_user/) `wp-includes/user.php` | Handles registering a new user. |
| [clean\_user\_cache()](https://developer.wordpress.org/reference/functions/clean_user_cache/) `wp-includes/user.php` | Cleans all user caches. |
| [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) `wp-includes/user.php` | Inserts a user into the database. |
| [wp\_signon()](https://developer.wordpress.org/reference/functions/wp_signon/) `wp-includes/user.php` | Authenticates and logs a user in with ‘remember’ capability. |
| [load\_template()](https://developer.wordpress.org/reference/functions/load_template/) `wp-includes/template.php` | Requires the template file with WordPress environment. |
| [get\_the\_post\_thumbnail()](https://developer.wordpress.org/reference/functions/get_the_post_thumbnail/) `wp-includes/post-thumbnail-template.php` | Retrieves the post thumbnail. |
| [clean\_post\_cache()](https://developer.wordpress.org/reference/functions/clean_post_cache/) `wp-includes/post.php` | Will clean the post in the cache. |
| [clean\_attachment\_cache()](https://developer.wordpress.org/reference/functions/clean_attachment_cache/) `wp-includes/post.php` | Will clean the attachment in the cache. |
| [\_publish\_post\_hook()](https://developer.wordpress.org/reference/functions/_publish_post_hook/) `wp-includes/post.php` | Hook to schedule pings and enclosures when a post is published. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [wp\_publish\_post()](https://developer.wordpress.org/reference/functions/wp_publish_post/) `wp-includes/post.php` | Publishes a post by transitioning the post status. |
| [wp\_transition\_post\_status()](https://developer.wordpress.org/reference/functions/wp_transition_post_status/) `wp-includes/post.php` | Fires actions related to the transitioning of a post’s status. |
| [wp\_untrash\_post\_comments()](https://developer.wordpress.org/reference/functions/wp_untrash_post_comments/) `wp-includes/post.php` | Restores comments for a post from the Trash. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wp\_delete\_post()](https://developer.wordpress.org/reference/functions/wp_delete_post/) `wp-includes/post.php` | Trashes or deletes a post or page. |
| [wp\_trash\_post()](https://developer.wordpress.org/reference/functions/wp_trash_post/) `wp-includes/post.php` | Moves a post or page to the Trash |
| [wp\_untrash\_post()](https://developer.wordpress.org/reference/functions/wp_untrash_post/) `wp-includes/post.php` | Restores a post from the Trash. |
| [wp\_trash\_post\_comments()](https://developer.wordpress.org/reference/functions/wp_trash_post_comments/) `wp-includes/post.php` | Moves comments for a post to the Trash. |
| [stick\_post()](https://developer.wordpress.org/reference/functions/stick_post/) `wp-includes/post.php` | Makes a post sticky. |
| [unstick\_post()](https://developer.wordpress.org/reference/functions/unstick_post/) `wp-includes/post.php` | Un-sticks a post. |
| [register\_post\_type()](https://developer.wordpress.org/reference/functions/register_post_type/) `wp-includes/post.php` | Registers a post type. |
| [WP\_Rewrite::set\_permalink\_structure()](https://developer.wordpress.org/reference/classes/wp_rewrite/set_permalink_structure/) `wp-includes/class-wp-rewrite.php` | Sets the main permalink structure for the site. |
| [\_wp\_put\_post\_revision()](https://developer.wordpress.org/reference/functions/_wp_put_post_revision/) `wp-includes/revision.php` | Inserts post data into the posts table as a post revision. |
| [wp\_restore\_post\_revision()](https://developer.wordpress.org/reference/functions/wp_restore_post_revision/) `wp-includes/revision.php` | Restores a post to the specified revision. |
| [wp\_delete\_post\_revision()](https://developer.wordpress.org/reference/functions/wp_delete_post_revision/) `wp-includes/revision.php` | Deletes a revision. |
| [add\_existing\_user\_to\_blog()](https://developer.wordpress.org/reference/functions/add_existing_user_to_blog/) `wp-includes/ms-functions.php` | Adds a user to a blog based on details from [maybe\_add\_existing\_user\_to\_blog()](https://developer.wordpress.org/reference/functions/maybe_add_existing_user_to_blog/) . |
| [wpmu\_activate\_signup()](https://developer.wordpress.org/reference/functions/wpmu_activate_signup/) `wp-includes/ms-functions.php` | Activates a signup. |
| [wpmu\_create\_user()](https://developer.wordpress.org/reference/functions/wpmu_create_user/) `wp-includes/ms-functions.php` | Creates a user. |
| [wpmu\_signup\_blog()](https://developer.wordpress.org/reference/functions/wpmu_signup_blog/) `wp-includes/ms-functions.php` | Records site signup information for future activation. |
| [wpmu\_signup\_user()](https://developer.wordpress.org/reference/functions/wpmu_signup_user/) `wp-includes/ms-functions.php` | Records user signup information for future activation. |
| [add\_user\_to\_blog()](https://developer.wordpress.org/reference/functions/add_user_to_blog/) `wp-includes/ms-functions.php` | Adds a user to a blog, along with specifying the user’s role. |
| [remove\_user\_from\_blog()](https://developer.wordpress.org/reference/functions/remove_user_from_blog/) `wp-includes/ms-functions.php` | Removes a user from a blog. |
| [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) `wp-includes/ms-blogs.php` | Switches the current blog. |
| [restore\_current\_blog()](https://developer.wordpress.org/reference/functions/restore_current_blog/) `wp-includes/ms-blogs.php` | Restores the current blog, after calling [switch\_to\_blog()](https://developer.wordpress.org/reference/functions/switch_to_blog/) . |
| [clean\_blog\_cache()](https://developer.wordpress.org/reference/functions/clean_blog_cache/) `wp-includes/ms-site.php` | Clean the blog cache |
| [wpmu\_update\_blogs\_date()](https://developer.wordpress.org/reference/functions/wpmu_update_blogs_date/) `wp-includes/ms-blogs.php` | Updates the last\_updated field for the current site. |
| [wp\_delete\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_delete_nav_menu/) `wp-includes/nav-menu.php` | Deletes a navigation menu. |
| [wp\_update\_nav\_menu\_object()](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_object/) `wp-includes/nav-menu.php` | Saves the properties of a menu or create a new menu with those properties. |
| [wp\_update\_nav\_menu\_item()](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/) `wp-includes/nav-menu.php` | Saves the properties of a menu item or create a new one. |
| [wp\_xmlrpc\_server::mt\_getPostCategories()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_getpostcategories/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves post categories. |
| [wp\_xmlrpc\_server::mt\_setPostCategories()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_setpostcategories/) `wp-includes/class-wp-xmlrpc-server.php` | Sets categories for a post. |
| [wp\_xmlrpc\_server::mt\_supportedMethods()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_supportedmethods/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves an array of methods supported by this server. |
| [wp\_xmlrpc\_server::mt\_supportedTextFilters()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_supportedtextfilters/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves an empty array because we don’t support per-post text filters. |
| [wp\_xmlrpc\_server::mt\_getTrackbackPings()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_gettrackbackpings/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves trackbacks sent to a given post. |
| [wp\_xmlrpc\_server::mt\_publishPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_publishpost/) `wp-includes/class-wp-xmlrpc-server.php` | Sets a post’s publish status to ‘publish’. |
| [wp\_xmlrpc\_server::pingback\_ping()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_ping/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a pingback and registers it. |
| [wp\_xmlrpc\_server::pingback\_extensions\_getPingbacks()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_extensions_getpingbacks/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves an array of URLs that pingbacked the given URL. |
| [wp\_xmlrpc\_server::mw\_editPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_editpost/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a post. |
| [wp\_xmlrpc\_server::mw\_getPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_getpost/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post. |
| [wp\_xmlrpc\_server::mw\_getRecentPosts()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_getrecentposts/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves list of recent posts. |
| [wp\_xmlrpc\_server::mw\_getCategories()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_getcategories/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the list of categories on a given blog. |
| [wp\_xmlrpc\_server::mw\_newMediaObject()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_newmediaobject/) `wp-includes/class-wp-xmlrpc-server.php` | Uploads a file, following your settings. |
| [wp\_xmlrpc\_server::mt\_getRecentPostTitles()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_getrecentposttitles/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the post titles of recent posts. |
| [wp\_xmlrpc\_server::mt\_getCategoryList()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_getcategorylist/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the list of all categories on a blog. |
| [wp\_xmlrpc\_server::blogger\_getUserInfo()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getuserinfo/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves user’s data. |
| [wp\_xmlrpc\_server::blogger\_getPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getpost/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post. |
| [wp\_xmlrpc\_server::blogger\_getRecentPosts()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getrecentposts/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the list of recent posts. |
| [wp\_xmlrpc\_server::blogger\_newPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_newpost/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new post. |
| [wp\_xmlrpc\_server::blogger\_editPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_editpost/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a post. |
| [wp\_xmlrpc\_server::blogger\_deletePost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_deletepost/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a post. |
| [wp\_xmlrpc\_server::mw\_newPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_newpost/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new post. |
| [wp\_xmlrpc\_server::wp\_getMediaItem()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getmediaitem/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a media item by ID. |
| [wp\_xmlrpc\_server::wp\_getMediaLibrary()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getmedialibrary/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a collection of media library items (or attachments). |
| [wp\_xmlrpc\_server::wp\_getPostFormats()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpostformats/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a list of post formats used by the site. |
| [wp\_xmlrpc\_server::wp\_getPostType()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposttype/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post type. |
| [wp\_xmlrpc\_server::wp\_getPostTypes()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposttypes/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves post types. |
| [wp\_xmlrpc\_server::wp\_getRevisions()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getrevisions/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves revisions for a specific post. |
| [wp\_xmlrpc\_server::wp\_restoreRevision()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_restorerevision/) `wp-includes/class-wp-xmlrpc-server.php` | Restores a post revision. |
| [wp\_xmlrpc\_server::blogger\_getUsersBlogs()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/blogger_getusersblogs/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves blogs that user owns. |
| [wp\_xmlrpc\_server::wp\_getComments()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getcomments/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves comments. |
| [wp\_xmlrpc\_server::wp\_deleteComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deletecomment/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a comment. |
| [wp\_xmlrpc\_server::wp\_editComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a comment. |
| [wp\_xmlrpc\_server::wp\_newComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new comment. |
| [wp\_xmlrpc\_server::wp\_getCommentStatusList()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getcommentstatuslist/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves all of the comment status. |
| [wp\_xmlrpc\_server::wp\_getCommentCount()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getcommentcount/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves comment counts. |
| [wp\_xmlrpc\_server::wp\_getPostStatusList()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpoststatuslist/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves post statuses. |
| [wp\_xmlrpc\_server::wp\_getPageStatusList()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpagestatuslist/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves page statuses. |
| [wp\_xmlrpc\_server::wp\_getPages()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpages/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves Pages. |
| [wp\_xmlrpc\_server::wp\_newPage()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newpage/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new page. |
| [wp\_xmlrpc\_server::wp\_deletePage()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deletepage/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a page. |
| [wp\_xmlrpc\_server::wp\_editPage()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editpage/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a page. |
| [wp\_xmlrpc\_server::wp\_getPageList()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpagelist/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves page list. |
| [wp\_xmlrpc\_server::wp\_getAuthors()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getauthors/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves authors list. |
| [wp\_xmlrpc\_server::wp\_getTags()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_gettags/) `wp-includes/class-wp-xmlrpc-server.php` | Gets the list of all tags. |
| [wp\_xmlrpc\_server::wp\_newCategory()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newcategory/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new category. |
| [wp\_xmlrpc\_server::wp\_deleteCategory()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deletecategory/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a category. |
| [wp\_xmlrpc\_server::wp\_suggestCategories()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_suggestcategories/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves category list. |
| [wp\_xmlrpc\_server::wp\_getComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a comment. |
| [wp\_xmlrpc\_server::wp\_getPosts()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposts/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves posts. |
| [wp\_xmlrpc\_server::wp\_newTerm()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newterm/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new term. |
| [wp\_xmlrpc\_server::wp\_editTerm()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editterm/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a term. |
| [wp\_xmlrpc\_server::wp\_deleteTerm()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deleteterm/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a term. |
| [wp\_xmlrpc\_server::wp\_getTerm()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getterm/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a term. |
| [wp\_xmlrpc\_server::wp\_getTerms()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getterms/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves all terms for a taxonomy. |
| [wp\_xmlrpc\_server::wp\_getTaxonomy()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_gettaxonomy/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a taxonomy. |
| [wp\_xmlrpc\_server::wp\_getTaxonomies()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_gettaxonomies/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves all taxonomies. |
| [wp\_xmlrpc\_server::wp\_getUser()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getuser/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a user. |
| [wp\_xmlrpc\_server::wp\_getUsers()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getusers/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves users. |
| [wp\_xmlrpc\_server::wp\_getProfile()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getprofile/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves information about the requesting user. |
| [wp\_xmlrpc\_server::wp\_editProfile()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editprofile/) `wp-includes/class-wp-xmlrpc-server.php` | Edits user’s profile. |
| [wp\_xmlrpc\_server::wp\_getPage()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpage/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a page. |
| [wp\_xmlrpc\_server::wp\_newPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newpost/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new post for any registered post type. |
| [wp\_xmlrpc\_server::wp\_editPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_editpost/) `wp-includes/class-wp-xmlrpc-server.php` | Edits a post for any registered post type. |
| [wp\_xmlrpc\_server::wp\_deletePost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deletepost/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a post for any registered post type. |
| [wp\_xmlrpc\_server::wp\_getPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpost/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post. |
| [wp\_xmlrpc\_server::wp\_getUsersBlogs()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getusersblogs/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves the blogs of the user. |
| [WP\_Customize\_Control::maybe\_render()](https://developer.wordpress.org/reference/classes/wp_customize_control/maybe_render/) `wp-includes/class-wp-customize-control.php` | Checks capabilities and render the control. |
| [dynamic\_sidebar()](https://developer.wordpress.org/reference/functions/dynamic_sidebar/) `wp-includes/widgets.php` | Displays dynamic sidebar. |
| [the\_widget()](https://developer.wordpress.org/reference/functions/the_widget/) `wp-includes/widgets.php` | Outputs an arbitrary widget as a template tag. |
| [wp\_register\_sidebar\_widget()](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/) `wp-includes/widgets.php` | Registers an instance of a widget. |
| [wp\_unregister\_sidebar\_widget()](https://developer.wordpress.org/reference/functions/wp_unregister_sidebar_widget/) `wp-includes/widgets.php` | Remove widget from sidebar. |
| [register\_sidebar()](https://developer.wordpress.org/reference/functions/register_sidebar/) `wp-includes/widgets.php` | Builds the definition for a single sidebar and returns the ID. |
| [comment\_form()](https://developer.wordpress.org/reference/functions/comment_form/) `wp-includes/comment-template.php` | Outputs a complete commenting form for use within a template. |
| [WP\_Customize\_Widgets::wp\_ajax\_update\_widget()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/wp_ajax_update_widget/) `wp-includes/class-wp-customize-widgets.php` | Updates widget settings asynchronously. |
| [WP\_Customize\_Widgets::print\_styles()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/print_styles/) `wp-includes/class-wp-customize-widgets.php` | Calls admin\_print\_styles-widgets.php and admin\_print\_styles hooks to allow custom styles from plugins. |
| [WP\_Customize\_Widgets::print\_scripts()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/print_scripts/) `wp-includes/class-wp-customize-widgets.php` | Calls admin\_print\_scripts-widgets.php and admin\_print\_scripts hooks to allow custom scripts from plugins. |
| [WP\_Customize\_Widgets::enqueue\_scripts()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/enqueue_scripts/) `wp-includes/class-wp-customize-widgets.php` | Enqueues scripts and styles for Customizer panel and export data to JavaScript. |
| [WP\_Customize\_Widgets::print\_footer\_scripts()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/print_footer_scripts/) `wp-includes/class-wp-customize-widgets.php` | Calls admin\_print\_footer\_scripts and admin\_print\_scripts hooks to allow custom scripts from plugins. |
| [WP\_Customize\_Widgets::customize\_controls\_init()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/customize_controls_init/) `wp-includes/class-wp-customize-widgets.php` | Ensures all widgets get loaded into the Customizer. |
| [print\_head\_scripts()](https://developer.wordpress.org/reference/functions/print_head_scripts/) `wp-includes/script-loader.php` | Prints the script queue in the HTML head on admin pages. |
| [wp\_print\_head\_scripts()](https://developer.wordpress.org/reference/functions/wp_print_head_scripts/) `wp-includes/script-loader.php` | Prints the script queue in the HTML head on the front end. |
| [wp\_print\_footer\_scripts()](https://developer.wordpress.org/reference/functions/wp_print_footer_scripts/) `wp-includes/script-loader.php` | Hooks to print the scripts and styles in the footer. |
| [wp\_enqueue\_scripts()](https://developer.wordpress.org/reference/functions/wp_enqueue_scripts/) `wp-includes/script-loader.php` | Wrapper for do\_action( ‘wp\_enqueue\_scripts’ ). |
| [clean\_comment\_cache()](https://developer.wordpress.org/reference/functions/clean_comment_cache/) `wp-includes/comment.php` | Removes a comment from the object cache. |
| [wp\_new\_comment()](https://developer.wordpress.org/reference/functions/wp_new_comment/) `wp-includes/comment.php` | Adds a new comment to the database. |
| [wp\_set\_comment\_status()](https://developer.wordpress.org/reference/functions/wp_set_comment_status/) `wp-includes/comment.php` | Sets the status of a comment. |
| [wp\_update\_comment()](https://developer.wordpress.org/reference/functions/wp_update_comment/) `wp-includes/comment.php` | Updates an existing comment in the database. |
| [wp\_update\_comment\_count\_now()](https://developer.wordpress.org/reference/functions/wp_update_comment_count_now/) `wp-includes/comment.php` | Updates the comment count for the post. |
| [do\_all\_pings()](https://developer.wordpress.org/reference/functions/do_all_pings/) `wp-includes/comment.php` | Performs all pingbacks, enclosures, trackbacks, and sends to pingback services. |
| [wp\_spam\_comment()](https://developer.wordpress.org/reference/functions/wp_spam_comment/) `wp-includes/comment.php` | Marks a comment as Spam. |
| [wp\_unspam\_comment()](https://developer.wordpress.org/reference/functions/wp_unspam_comment/) `wp-includes/comment.php` | Removes a comment from the Spam. |
| [wp\_transition\_comment\_status()](https://developer.wordpress.org/reference/functions/wp_transition_comment_status/) `wp-includes/comment.php` | Calls hooks for when a comment status transition occurs. |
| [wp\_insert\_comment()](https://developer.wordpress.org/reference/functions/wp_insert_comment/) `wp-includes/comment.php` | Inserts a comment into the database. |
| [wp\_delete\_comment()](https://developer.wordpress.org/reference/functions/wp_delete_comment/) `wp-includes/comment.php` | Trashes or deletes a comment. |
| [wp\_trash\_comment()](https://developer.wordpress.org/reference/functions/wp_trash_comment/) `wp-includes/comment.php` | Moves a comment to the Trash |
| [wp\_untrash\_comment()](https://developer.wordpress.org/reference/functions/wp_untrash_comment/) `wp-includes/comment.php` | Removes a comment from the Trash |
| [wp\_allow\_comment()](https://developer.wordpress.org/reference/functions/wp_allow_comment/) `wp-includes/comment.php` | Validates whether this comment is allowed to be made. |
| [delete\_metadata()](https://developer.wordpress.org/reference/functions/delete_metadata/) `wp-includes/meta.php` | Deletes metadata for the specified object. |
| [update\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/update_metadata_by_mid/) `wp-includes/meta.php` | Updates metadata by meta ID. |
| [delete\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/delete_metadata_by_mid/) `wp-includes/meta.php` | Deletes metadata by meta ID. |
| [add\_metadata()](https://developer.wordpress.org/reference/functions/add_metadata/) `wp-includes/meta.php` | Adds metadata for the specified object. |
| [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/) `wp-includes/meta.php` | Updates metadata for the specified object. If no value already exists for the specified object ID and metadata key, the metadata will be added. |
| [\_WP\_Editors::enqueue\_scripts()](https://developer.wordpress.org/reference/classes/_wp_editors/enqueue_scripts/) `wp-includes/class-wp-editor.php` |  |
| [\_WP\_Editors::editor\_js()](https://developer.wordpress.org/reference/classes/_wp_editors/editor_js/) `wp-includes/class-wp-editor.php` | Print (output) the TinyMCE configuration and initialization scripts. |
| [\_WP\_Editors::editor()](https://developer.wordpress.org/reference/classes/_wp_editors/editor/) `wp-includes/class-wp-editor.php` | Outputs the HTML for a single instance of the editor. |
| [WP\_Error::add()](https://developer.wordpress.org/reference/classes/wp_error/add/) `wp-includes/class-wp-error.php` | Adds an error or appends an additional message to an existing error. |
| [wp\_print\_media\_templates()](https://developer.wordpress.org/reference/functions/wp_print_media_templates/) `wp-includes/media-template.php` | Prints the templates used in the media manager. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 405 more](https://developer.wordpress.org/reference/functions/do_action/#) [Show less](https://developer.wordpress.org/reference/functions/do_action/#)

## [Changelog](https://developer.wordpress.org/reference/functions/do_action/\#changelog)

| Version | Description |
| --- | --- |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Formalized the existing and already documented `...$arg` parameter by adding it to the function signature. |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/do_action/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/do_action/#comment-content-473)



**Example**





`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/do_action/#)

[Copy](https://developer.wordpress.org/reference/functions/do_action/#)




```php
# ======= Somewhere in a (mu-)plugin, theme or the core ======= #

/**
    * You can have as many arguments as you want,
    * but your callback function and the add_action call need to agree in number of arguments.
    * Note: `add_action` above has 2 and 'i_am_hook' accepts 2.
    * You will find action hooks like these in a lot of themes & plugins and in many place @core
    * @see: https://codex.wordpress.org/Plugin_API/Action_Reference
    */

# ======= e.g., inside your functions.php file ======= #

/**
    * Define callback function
    * Inside this function you can do whatever you can imagine
    * with the variables that are loaded in the do_action() call above.
    */
function wpdocs_who_is_hook( $a, $b ) {
   	echo '<code>';
   		print_r( $a ); // `print_r` the array data inside the 1st argument
   	echo '</code>';

   	echo '<br />'.$b; // echo linebreak and value of 2nd argument
}

// then add it to the action hook, matching the defined number (2) of arguments in do_action
// see [https://codex.wordpress.org/Function_Reference/add_action] in the Codex

// add_action( $tag, $function_to_add, $priority, $accepted_args );
add_action( 'wpdocs_i_am_hook', 'wpdocs_who_is_hook', 10, 2 );

// Define the arguments for the action hook
$a = array(
   	'eye patch'  => 'yes',
   	'parrot'     => true,
   	'wooden leg' => 1
);
$b = __( 'And Hook said: "I ate ice cream with Peter Pan."', 'textdomain' );

// Executes the action hook named 'i_am_hook'
do_action( 'wpdocs_i_am_hook', $a, $b );
```





Result:





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/do_action/#)




```php
Array (
   	['eye patch'] =&gt; 'yes'
   	['parrot'] =&gt; true
   	['wooden leg'] =&gt; 1
)
And hook said: "I ate ice cream with Peter Pan."
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_action%2F%3Freplytocom%3D473%23feedback-editor-473)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/do_action/#comment-content-2371)



BIG GOTCHA:



When calling `do_action`, if the `$arg` you pass in is an array with a single object, it will instead pass that obejct in and NOT an array. It doesn’t do the same switcheroo, however, if the array’s single item is anything other than an array



E.g.,





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/do_action/#)




```php
function my_callback( $should_be_an_array ){
      var_dump($should_be_an_array);
}
add_action( 'my_action', 'my_callback' );
do_action( 'my_action', array(new stdclass()) );
do_action( 'my_action', array( 'array_item_thats_not_an_object') );
```





echoes out





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/do_action/#)




```php
object(stdClass)[420]
array (size=1)
     0 => string 'array_item_thats_not_an_object' (length=30)
```





notice that the first time we passed in an array with an `stdclass` in it, but the callback function only received the `stdclass`, NOT an array





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_action%2F%3Freplytocom%3D2371%23feedback-editor-2371)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/do_action/#comment-content-2351)



Related:



[add\_action()](https://developer.wordpress.org/reference/functions/add_action/)

[remove\_action()](https://developer.wordpress.org/reference/functions/remove_action/)





[Show feedback (1)](https://developer.wordpress.org/reference/functions/do_action/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_action%2F%3Freplytocom%3D2351%23feedback-editor-2351)



- `do_action` allows you to create a custom action hook. Suppose I want to create custom hook called `my_custom_hook` and want to work with it. So the codes will be something like this-







`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/do_action/#)




```php
/* call the action where you want to put the hook */ do_action( 'my_custom_hook' ); /* Now work with this custom hook */ function wporg_my_custom_hook_function() { /* write what you want */ } add_action( 'my_custom_hook', 'wporg_my_custom_hook_function' );
```







[Binsaifullah](https://profiles.wordpress.org/binsaifullah/) [6 years ago](https://developer.wordpress.org/reference/functions/do_action/#comment-3444)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_action%2F) before being able to contribute a note or feedback.

Notifications