---
url: https://developer.wordpress.org/reference/functions/add_filter
scraped_at: 2025-10-20T03:44:18.762Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/add_filter/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

add\_filter()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)add\_filter()

Search

# add\_filter( string$hook\_name, callable$callback, int$priority = 10, int$accepted\_args = 1 ): true

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/add_filter/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/add_filter/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/add_filter/#return)
- [More Information](https://developer.wordpress.org/reference/functions/add_filter/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/add_filter/#source)
- [Related](https://developer.wordpress.org/reference/functions/add_filter/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/add_filter/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_filter/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/add_filter/#wp--skip-link--target)

Adds a callback function to a filter hook.

## [Description](https://developer.wordpress.org/reference/functions/add_filter/\#description)

WordPress offers filter hooks to allow plugins to modify various types of internal data at runtime.

A plugin can modify data by binding a callback to a filter hook. When the filter is later applied, each bound callback is run in order of priority, and given the opportunity to modify a value by returning a new value.

The following example shows how a callback function is bound to a filter hook.

Note that `$example` is passed to the callback, (maybe) modified, then returned:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
function example_callback( $example ) {
    // Maybe modify $example in some way.
    return $example;
}
add_filter( 'example_filter', 'example_callback' );
```

Bound callbacks can accept from none to the total number of arguments passed as parameters in the corresponding [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) call.

In other words, if an [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) call passes four total arguments, callbacks bound to it can accept none (the same as 1) of the arguments or up to four. The important part is that the `$accepted_args` value must reflect the number of arguments the bound callback _actually_ opted to accept. If no arguments were accepted by the callback that is considered to be the same as accepting 1 argument. For example:

`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_filter/#)

[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
// Filter call.
$value = apply_filters( 'hook', $value, $arg2, $arg3 );

// Accepting zero/one arguments.
function example_callback() {
    ...
    return 'some value';
}
add_filter( 'hook', 'example_callback' ); // Where $priority is default 10, $accepted_args is default 1.

// Accepting two arguments (three possible).
function example_callback( $value, $arg2 ) {
    ...
    return $maybe_modified_value;
}
add_filter( 'hook', 'example_callback', 10, 2 ); // Where $priority is 10, $accepted_args is 2.
```

\_Note:\_ The function will return true whether or not the callback is valid.

It is up to you to take care. This is done for optimization purposes, so everything is as quick as possible.

## [Parameters](https://developer.wordpress.org/reference/functions/add_filter/\#parameters)

`$hook_name` stringrequired

The name of the filter to add the callback to.

`$callback` callablerequired

The callback to be run when the filter is applied.

`$priority` intoptional

Used to specify the order in which the functions associated with a particular filter are executed.

Lower numbers correspond with earlier execution, and functions with the same priority are executed in the order in which they were added to the filter.

Default: `10`

`$accepted_args` intoptional

The number of arguments the function accepts.

Default: `1`

## [Return](https://developer.wordpress.org/reference/functions/add_filter/\#return)

true Always returns true.

## [More Information](https://developer.wordpress.org/reference/functions/add_filter/\#more-information)

- Hooked functions can take extra arguments that are set when the matching `[do\_action()](https://developer.wordpress.org/reference/functions/do_action/ "Function Reference/do action")` or `[apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/ "Function Reference/apply filters")` call is run. For example, the `[comment\_id\_not\_found](https://developer.wordpress.org/reference/hooks/comment_id_not_found-3/ "Plugin API/Action Reference/comment id not found (page does not exist)")` action will pass the comment ID to each callback.
- Although you can pass the number of `$accepted_args`, you can only manipulate the `$value`. The other arguments are only to provide context, and their values cannot be changed by the filter function.
- You can also pass a class method as a callback.

Static class method:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
add_filter( 'media_upload_newtab', array( 'My_Class', 'media_upload_callback' ) );
```

Instance method:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
add_filter( 'media_upload_newtab', array( $this, 'media_upload_callback' ) );
```

- You can also pass an an anonymous function as a callback. For example:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
add_filter( 'the_title', function( $title ) { return '<strong>' . $title . '</strong>'; } );
```

## [Source](https://developer.wordpress.org/reference/functions/add_filter/\#source)

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)

```php
function add_filter( $hook_name, $callback, $priority = 10, $accepted_args = 1 ) {
	global $wp_filter;

	if ( ! isset( $wp_filter[ $hook_name ] ) ) {
		$wp_filter[ $hook_name ] = new WP_Hook();
	}

	$wp_filter[ $hook_name ]->add_filter( $hook_name, $callback, $priority, $accepted_args );

	return true;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L121) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L121-L131)

## [Related](https://developer.wordpress.org/reference/functions/add_filter/\#related)

| Used by | Description |
| --- | --- |
| [apply\_block\_hooks\_to\_content\_from\_post\_object()](https://developer.wordpress.org/reference/functions/apply_block_hooks_to_content_from_post_object/) `wp-includes/blocks.php` | Run the Block Hooks algorithm on a post object’s content. |
| [insert\_hooked\_blocks\_into\_rest\_response()](https://developer.wordpress.org/reference/functions/insert_hooked_blocks_into_rest_response/) `wp-includes/blocks.php` | Hooks into the REST API response for the Posts endpoint and adds the first and last inner blocks. |
| [apply\_block\_hooks\_to\_content()](https://developer.wordpress.org/reference/functions/apply_block_hooks_to_content/) `wp-includes/blocks.php` | Runs the hooked blocks algorithm on the given content. |
| [wp\_font\_dir()](https://developer.wordpress.org/reference/functions/wp_font_dir/) `wp-includes/fonts.php` | Returns an array containing the current fonts upload directory’s path and URL. |
| [WP\_REST\_Font\_Faces\_Controller::handle\_font\_file\_upload()](https://developer.wordpress.org/reference/classes/wp_rest_font_faces_controller/handle_font_file_upload/) `wp-includes/rest-api/endpoints/class-wp-rest-font-faces-controller.php` | Handles the upload of a font file using [wp\_handle\_upload()](https://developer.wordpress.org/reference/functions/wp_handle_upload/) . |
| [\_wp\_footnotes\_kses\_init\_filters()](https://developer.wordpress.org/reference/functions/_wp_footnotes_kses_init_filters/) `wp-includes/blocks.php` | Adds the filters for footnotes meta field. |
| [wp\_initialize\_theme\_preview\_hooks()](https://developer.wordpress.org/reference/functions/wp_initialize_theme_preview_hooks/) `wp-includes/theme-previews.php` | Add filters and actions to enable Block Theme Previews in the Site Editor. |
| [\_wp\_get\_iframed\_editor\_assets()](https://developer.wordpress.org/reference/functions/_wp_get_iframed_editor_assets/) `wp-includes/block-editor.php` | Collect the block editor assets that need to be loaded into the editor’s iframe. |
| [WP\_REST\_Menu\_Items\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Prepares a single nav menu item output for response. |
| [WP\_REST\_Global\_Styles\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_global_styles_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-global-styles-controller.php` | Prepare a global styles config output for response. |
| [\_add\_default\_theme\_supports()](https://developer.wordpress.org/reference/functions/_add_default_theme_supports/) `wp-includes/theme.php` | Adds default theme supports for block themes when the ‘after\_setup\_theme’ action fires. |
| [wp\_enqueue\_block\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_style/) `wp-includes/script-loader.php` | Enqueues a stylesheet for a specific block. |
| [WP\_Widget\_Block::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_block/__construct/) `wp-includes/widgets/class-wp-widget-block.php` | Sets up a new Block widget instance. |
| [wp\_enqueue\_global\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_global_styles/) `wp-includes/script-loader.php` | Enqueues the global styles defined via theme.json. |
| [WP\_Sitemaps::init()](https://developer.wordpress.org/reference/classes/wp_sitemaps/init/) `wp-includes/sitemaps/class-wp-sitemaps.php` | Initiates all sitemap functionality. |
| [WP\_Sitemaps\_Renderer::check\_for\_simple\_xml\_availability()](https://developer.wordpress.org/reference/classes/wp_sitemaps_renderer/check_for_simple_xml_availability/) `wp-includes/sitemaps/class-wp-sitemaps-renderer.php` | Checks for the availability of the SimpleXML extension and errors if missing. |
| [wp\_pre\_kses\_block\_attributes()](https://developer.wordpress.org/reference/functions/wp_pre_kses_block_attributes/) `wp-includes/formatting.php` | Removes non-allowable HTML from parsed block attribute values when filtering in the post context. |
| [enqueue\_block\_styles\_assets()](https://developer.wordpress.org/reference/functions/enqueue_block_styles_assets/) `wp-includes/script-loader.php` | Function responsible for enqueuing the styles required for block styles functionality on the editor and on the frontend. |
| [WP\_Site\_Health::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_site_health/__construct/) `wp-admin/includes/class-wp-site-health.php` | [WP\_Site\_Health](https://developer.wordpress.org/reference/classes/wp_site_health/) constructor. |
| [wp\_get\_active\_and\_valid\_themes()](https://developer.wordpress.org/reference/functions/wp_get_active_and_valid_themes/) `wp-includes/load.php` | Retrieves an array of active and valid themes. |
| [update\_sitemeta\_cache()](https://developer.wordpress.org/reference/functions/update_sitemeta_cache/) `wp-includes/ms-site.php` | Updates metadata cache for list of site IDs. |
| [WP\_REST\_Post\_Search\_Handler::prepare\_item()](https://developer.wordpress.org/reference/classes/wp_rest_post_search_handler/prepare_item/) `wp-includes/rest-api/search/class-wp-rest-post-search-handler.php` | Prepares the search result for a given post ID. |
| [do\_blocks()](https://developer.wordpress.org/reference/functions/do_blocks/) `wp-includes/blocks.php` | Parses dynamic blocks out of `post_content` and re-renders them. |
| [\_restore\_wpautop\_hook()](https://developer.wordpress.org/reference/functions/_restore_wpautop_hook/) `wp-includes/blocks.php` | If [do\_blocks()](https://developer.wordpress.org/reference/functions/do_blocks/) needs to remove [wpautop()](https://developer.wordpress.org/reference/functions/wpautop/) from the `the_content` filter, this re-adds it afterwards, for subsequent `the_content` usage. |
| [wpdb::placeholder\_escape()](https://developer.wordpress.org/reference/classes/wpdb/placeholder_escape/) `wp-includes/class-wpdb.php` | Generates and returns a placeholder escape string for use in queries returned by ::prepare(). |
| [WP\_Widget\_Custom\_HTML::widget()](https://developer.wordpress.org/reference/classes/wp_widget_custom_html/widget/) `wp-includes/widgets/class-wp-widget-custom-html.php` | Outputs the content for the current Custom HTML widget instance. |
| [WP\_Widget\_Media::\_register\_one()](https://developer.wordpress.org/reference/classes/wp_widget_media/_register_one/) `wp-includes/widgets/class-wp-widget-media.php` | Add hooks while registering all widget instances of this widget class. |
| [WP\_Widget\_Media\_Video::render\_media()](https://developer.wordpress.org/reference/classes/wp_widget_media_video/render_media/) `wp-includes/widgets/class-wp-widget-media-video.php` | Render the media on the frontend. |
| [WP\_Customize\_Manager::save\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Saves the post for the loaded changeset. |
| [WP\_REST\_Attachments\_Controller::prepare\_items\_query()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/prepare_items_query/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Determines the allowed query\_vars for a get\_items() response and prepares for [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post output for response. |
| [WP\_REST\_Posts\_Controller::get\_item\_permissions\_check()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_item_permissions_check/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Checks if a given request has access to read a post. |
| [WP\_REST\_Posts\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves a collection of posts. |
| [WP\_REST\_Comments\_Controller::check\_read\_post\_permission()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/check_read_post_permission/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Checks if the post can be read. |
| [WP\_Locale\_Switcher::init()](https://developer.wordpress.org/reference/classes/wp_locale_switcher/init/) `wp-includes/class-wp-locale-switcher.php` | Initializes the locale switcher. |
| [WP\_Taxonomy::add\_hooks()](https://developer.wordpress.org/reference/classes/wp_taxonomy/add_hooks/) `wp-includes/class-wp-taxonomy.php` | Registers the ajax callback for the meta box. |
| [WP\_Customize\_Nav\_Menus::insert\_auto\_draft\_post()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/insert_auto_draft_post/) `wp-includes/class-wp-customize-nav-menus.php` | Adds a new `auto-draft` post. |
| [WP\_Customize\_Custom\_CSS\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_custom_css_setting/preview/) `wp-includes/customize/class-wp-customize-custom-css-setting.php` | Add filter to preview post value. |
| [WP\_Metadata\_Lazyloader::queue\_objects()](https://developer.wordpress.org/reference/classes/wp_metadata_lazyloader/queue_objects/) `wp-includes/class-wp-metadata-lazyloader.php` | Adds objects to the metadata lazy-load queue. |
| [WP\_Customize\_Widgets::render\_widget\_partial()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/render_widget_partial/) `wp-includes/class-wp-customize-widgets.php` | Renders a specific widget using the supplied sidebar arguments. |
| [WP\_Customize\_Widgets::selective\_refresh\_init()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/selective_refresh_init/) `wp-includes/class-wp-customize-widgets.php` | Adds hooks for selective refresh. |
| [rest\_cookie\_check\_errors()](https://developer.wordpress.org/reference/functions/rest_cookie_check_errors/) `wp-includes/rest-api.php` | Checks for errors when using cookie-based authentication. |
| [rest\_api\_default\_filters()](https://developer.wordpress.org/reference/functions/rest_api_default_filters/) `wp-includes/rest-api.php` | Registers the default REST API filters. |
| [wp\_handle\_comment\_submission()](https://developer.wordpress.org/reference/functions/wp_handle_comment_submission/) `wp-includes/comment.php` | Handles the submission of a comment, usually posted to wp-comments-post.php via a comment form. |
| [WP\_Screen::render\_view\_mode()](https://developer.wordpress.org/reference/classes/wp_screen/render_view_mode/) `wp-admin/includes/class-wp-screen.php` | Renders the list table view mode preferences. |
| [WP\_Customize\_Nav\_Menu\_Setting::update()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_setting/update/) `wp-includes/customize/class-wp-customize-nav-menu-setting.php` | Create/update the nav\_menu term for this setting. |
| [WP\_Customize\_Nav\_Menu\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_setting/preview/) `wp-includes/customize/class-wp-customize-nav-menu-setting.php` | Handle previewing the setting. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::update()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/update/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Creates/updates the nav\_menu\_item post for this setting. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/preview/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Handle previewing the setting. |
| [WP\_Customize\_Nav\_Menus\_Panel::render\_screen\_options()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus_panel/render_screen_options/) `wp-includes/customize/class-wp-customize-nav-menus-panel.php` | Render screen options for Menus. |
| [WP\_Customize\_Nav\_Menus::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/customize_preview_init/) `wp-includes/class-wp-customize-nav-menus.php` | Adds hooks for the Customizer preview. |
| [WP\_Customize\_Nav\_Menus::customize\_register()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/customize_register/) `wp-includes/class-wp-customize-nav-menus.php` | Adds the customizer settings and controls. |
| [WP\_Customize\_Nav\_Menus::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/__construct/) `wp-includes/class-wp-customize-nav-menus.php` | Constructor. |
| [WP\_Site\_Icon::get\_post\_metadata()](https://developer.wordpress.org/reference/classes/wp_site_icon/get_post_metadata/) `wp-admin/includes/class-wp-site-icon.php` | Adds custom image sizes when meta data for an image is requested, that happens to be used as Site Icon. |
| [WP\_Site\_Icon::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_site_icon/__construct/) `wp-admin/includes/class-wp-site-icon.php` | Registers actions and filters. |
| [wp\_ajax\_crop\_image()](https://developer.wordpress.org/reference/functions/wp_ajax_crop_image/) `wp-admin/includes/ajax-actions.php` | Handles cropping an image via AJAX. |
| [wp\_edit\_attachments\_query\_vars()](https://developer.wordpress.org/reference/functions/wp_edit_attachments_query_vars/) `wp-admin/includes/post.php` | Returns the query variables for the current attachments request. |
| [\_WP\_List\_Table\_Compat::\_\_construct()](https://developer.wordpress.org/reference/classes/_wp_list_table_compat/__construct/) `wp-admin/includes/class-wp-list-table-compat.php` | Constructor. |
| [login\_header()](https://developer.wordpress.org/reference/functions/login_header/) `wp-login.php` | Outputs the login page header. |
| [WP\_Automatic\_Updater::update()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/update/) `wp-admin/includes/class-wp-automatic-updater.php` | Updates an item, if appropriate. |
| [Language\_Pack\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/language_pack_upgrader/bulk_upgrade/) `wp-admin/includes/class-language-pack-upgrader.php` | Upgrades several language packs at once. |
| [Plugin\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/bulk_upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades several plugins at once. |
| [Theme\_Upgrader::check\_parent\_theme\_filter()](https://developer.wordpress.org/reference/classes/theme_upgrader/check_parent_theme_filter/) `wp-admin/includes/class-theme-upgrader.php` | Checks if a child theme is being installed and its parent also needs to be installed. |
| [Theme\_Upgrader::install()](https://developer.wordpress.org/reference/classes/theme_upgrader/install/) `wp-admin/includes/class-theme-upgrader.php` | Install a theme package. |
| [Theme\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades a theme. |
| [Theme\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/bulk_upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades several themes at once. |
| [Plugin\_Upgrader::install()](https://developer.wordpress.org/reference/classes/plugin_upgrader/install/) `wp-admin/includes/class-plugin-upgrader.php` | Install a plugin package. |
| [Plugin\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades a plugin. |
| [WP\_Screen::render\_per\_page\_options()](https://developer.wordpress.org/reference/classes/wp_screen/render_per_page_options/) `wp-admin/includes/class-wp-screen.php` | Renders the items per page option. |
| [wp\_update\_core()](https://developer.wordpress.org/reference/functions/wp_update_core/) `wp-admin/includes/deprecated.php` | This was once used to kick-off the Core Updater. |
| [wp\_update\_plugin()](https://developer.wordpress.org/reference/functions/wp_update_plugin/) `wp-admin/includes/deprecated.php` | This was once used to kick-off the Plugin Updater. |
| [wp\_update\_theme()](https://developer.wordpress.org/reference/functions/wp_update_theme/) `wp-admin/includes/deprecated.php` | This was once used to kick-off the Theme Updater. |
| [WP\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_list_table/__construct/) `wp-admin/includes/class-wp-list-table.php` | Constructor. |
| [wp\_dashboard\_setup()](https://developer.wordpress.org/reference/functions/wp_dashboard_setup/) `wp-admin/includes/dashboard.php` | Registers dashboard widgets. |
| [register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) `wp-includes/option.php` | Registers a setting and its data. |
| [media\_upload\_type\_form()](https://developer.wordpress.org/reference/functions/media_upload_type_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for a given media type. |
| [media\_upload\_gallery\_form()](https://developer.wordpress.org/reference/functions/media_upload_gallery_form/) `wp-admin/includes/media.php` | Adds gallery form to upload iframe. |
| [media\_upload\_library\_form()](https://developer.wordpress.org/reference/functions/media_upload_library_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for the media library. |
| [wp\_ajax\_query\_attachments()](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/) `wp-admin/includes/ajax-actions.php` | Handles querying attachments via AJAX. |
| [wp\_ajax\_replyto\_comment()](https://developer.wordpress.org/reference/functions/wp_ajax_replyto_comment/) `wp-admin/includes/ajax-actions.php` | Handles replying to a comment via AJAX. |
| [wp\_link\_manager\_disabled\_message()](https://developer.wordpress.org/reference/functions/wp_link_manager_disabled_message/) `wp-admin/includes/bookmark.php` | Outputs the ‘disabled’ message for the WordPress Link Manager. |
| [WP\_Media\_List\_Table::display\_rows()](https://developer.wordpress.org/reference/classes/wp_media_list_table/display_rows/) `wp-admin/includes/class-wp-media-list-table.php` | Generates the list table rows. |
| [WP\_Importer::get\_page()](https://developer.wordpress.org/reference/classes/wp_importer/get_page/) `wp-admin/includes/class-wp-importer.php` | Gets URL. |
| [WP\_Comments\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/__construct/) `wp-admin/includes/class-wp-comments-list-table.php` | Constructor. |
| [wp\_nav\_menu\_setup()](https://developer.wordpress.org/reference/functions/wp_nav_menu_setup/) `wp-admin/includes/nav-menu.php` | Register nav menu meta boxes and advanced menu items. |
| [wp\_list\_widget\_controls()](https://developer.wordpress.org/reference/functions/wp_list_widget_controls/) `wp-admin/includes/widgets.php` | Show the widgets and their settings for a sidebar. |
| [WP\_Posts\_List\_Table::display\_rows()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/display_rows/) `wp-admin/includes/class-wp-posts-list-table.php` | Generates the list table rows. |
| [do\_core\_upgrade()](https://developer.wordpress.org/reference/functions/do_core_upgrade/) `wp-admin/update-core.php` | Upgrades WordPress core display. |
| [WP\_Customize\_Manager::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_preview_init/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings. |
| [WP\_Customize\_Manager::start\_previewing\_theme()](https://developer.wordpress.org/reference/classes/wp_customize_manager/start_previewing_theme/) `wp-includes/class-wp-customize-manager.php` | If the theme to be previewed isn’t the active theme, add filter callbacks to swap it out at runtime. |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [wp\_trim\_excerpt()](https://developer.wordpress.org/reference/functions/wp_trim_excerpt/) `wp-includes/formatting.php` | Generates an excerpt from the content, if needed. |
| [kses\_init\_filters()](https://developer.wordpress.org/reference/functions/kses_init_filters/) `wp-includes/kses.php` | Adds all KSES input form content filters. |
| [\_default\_wp\_die\_handler()](https://developer.wordpress.org/reference/functions/_default_wp_die_handler/) `wp-includes/functions.php` | Kills WordPress execution and displays HTML page with an error message. |
| [WP\_Widget\_Text::widget()](https://developer.wordpress.org/reference/classes/wp_widget_text/widget/) `wp-includes/widgets/class-wp-widget-text.php` | Outputs the content for the current Text widget instance. |
| [WP\_Widget\_Text::form()](https://developer.wordpress.org/reference/classes/wp_widget_text/form/) `wp-includes/widgets/class-wp-widget-text.php` | Outputs the Text widget settings form. |
| [WP\_Embed::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_embed/__construct/) `wp-includes/class-wp-embed.php` | Constructor |
| [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) `wp-includes/shortcodes.php` | Searches content for shortcodes and filter shortcodes through their hooks. |
| [WP\_oEmbed::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_oembed/__construct/) `wp-includes/class-wp-oembed.php` | Constructor. |
| [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) `wp-includes/plugin.php` | Adds a callback function to an action hook. |
| [WP\_Customize\_Setting::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_setting/__construct/) `wp-includes/class-wp-customize-setting.php` | Constructor. |
| [WP\_Customize\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_setting/preview/) `wp-includes/class-wp-customize-setting.php` | Add filters to supply the setting’s value when accessed. |
| [wp\_signon()](https://developer.wordpress.org/reference/functions/wp_signon/) `wp-includes/user.php` | Authenticates and logs a user in with ‘remember’ capability. |
| [\_set\_preview()](https://developer.wordpress.org/reference/functions/_set_preview/) `wp-includes/revision.php` | Sets up the post object for preview based on the post autosave. |
| [\_show\_post\_preview()](https://developer.wordpress.org/reference/functions/_show_post_preview/) `wp-includes/revision.php` | Filters the latest content for preview from the post autosave. |
| [ms\_upload\_constants()](https://developer.wordpress.org/reference/functions/ms_upload_constants/) `wp-includes/ms-default-constants.php` | Defines Multisite upload constants. |
| [Walker\_Comment::start\_el()](https://developer.wordpress.org/reference/classes/walker_comment/start_el/) `wp-includes/class-walker-comment.php` | Starts the element output. |
| [WP\_Customize\_Widgets::start\_capturing\_option\_updates()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/start_capturing_option_updates/) `wp-includes/class-wp-customize-widgets.php` | Begins keeping track of changes to widget options, caching new values. |
| [WP\_Customize\_Widgets::capture\_filter\_pre\_update\_option()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/capture_filter_pre_update_option/) `wp-includes/class-wp-customize-widgets.php` | Pre-filters captured option values before updating. |
| [WP\_Customize\_Widgets::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/__construct/) `wp-includes/class-wp-customize-widgets.php` | Initial loader. |
| [WP\_Customize\_Widgets::override\_sidebars\_widgets\_for\_theme\_switch()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/override_sidebars_widgets_for_theme_switch/) `wp-includes/class-wp-customize-widgets.php` | Override sidebars\_widgets for theme switch. |
| [WP\_Customize\_Widgets::customize\_register()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/customize_register/) `wp-includes/class-wp-customize-widgets.php` | Registers Customizer settings and controls for all sidebars and widgets. |
| [wp\_update\_comment()](https://developer.wordpress.org/reference/functions/wp_update_comment/) `wp-includes/comment.php` | Updates an existing comment in the database. |
| [check\_comment\_flood\_db()](https://developer.wordpress.org/reference/functions/check_comment_flood_db/) `wp-includes/comment.php` | Hooks WP’s native database-based comment-flood check. |
| [register\_meta()](https://developer.wordpress.org/reference/functions/register_meta/) `wp-includes/meta.php` | Registers a meta key. |
| [\_WP\_Editors::editor()](https://developer.wordpress.org/reference/classes/_wp_editors/editor/) `wp-includes/class-wp-editor.php` | Outputs the HTML for a single instance of the editor. |

[Show 111 more](https://developer.wordpress.org/reference/functions/add_filter/#) [Show less](https://developer.wordpress.org/reference/functions/add_filter/#)

## [Changelog](https://developer.wordpress.org/reference/functions/add_filter/\#changelog)

| Version | Description |
| --- | --- |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_filter/\#user-contributed-notes)

1. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-1934)



**Example:** Let’s add extra sections to TwentySeventeen Front page.

_By default, TwentySeventeen theme has 4 sections for the front page. **This example will make them 6**_





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
add_filter( 'twentyseventeen_front_page_sections', 'prefix_custom_front_page_sections' );

function prefix_custom_front_page_sections( $num_sections )
{
   		return 6;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D1934%23feedback-editor-1934)

2. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-3547)



To pass a variable to the called function of the filter, you can use closures (since PHP 5.3+) when the argument is not available in the original coded apply\_filters. For example:





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
add_filter('wp_footer', function($arguments) use ($myvar) {
       return $myvar;
}, $priority_integer, $accepted_arguments_integer);
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D3547%23feedback-editor-3547)

3. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-1778)



**Example:** Let display custom length of post excerpt.





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
if( ! function_exists( 'prefix_custom_excerpt_length' ) )
{
   	function prefix_custom_excerpt_length( $length )
   	{
   		return 40;
   	}
}
add_filter( 'excerpt_length', 'prefix_custom_excerpt_length', 999 );
```





By default, WordPress display 57 character. you can set custom length using above code. this time except length will be 40. it is a nice and easiest use of **add\_filter**.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D1778%23feedback-editor-1778)

4. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-3666)



**Example:** If you want to inject a CLASS/ID CSS in content. Let’s add extra CLASS/ID to post content.





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
//Add Class/ID to Post Content
add_filter('the_content', 'xai_my_class');
function xai_my_class($content)
{
       //Replace the instance with the Class/ID markup.
       $string = '<ul'; //your tag
       $replace = '<ul class="detail-list"'; //add your class/id and tag
       $content = str_replace( $string, $replace, $content );
       return $content;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D3666%23feedback-editor-3666)

5. [Skip to note 13 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-4863)



In the special case you have to add a filter before WordPress starts, you can create and pre-populate the global `$wp_filter` array instead of using the not-yet available `add_filter` (or `add_action`) function:





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
// Instead of add_filter( $tag, $function_to_add, $priority = 10, $accepted_args = 1 ):
$GLOBALS['wp_filter'][ $tag ][ $priority ][] = array(
     'function'      => $function_to_add,
     'accepted_args' => $accepted_args
);
```





`WP_Hook::build_preinitialized_hooks` will automatically take care of the rest.


Though to remove your filter, you can only use the [remove\_all\_filters()](https://developer.wordpress.org/reference/functions/remove_all_filters/) function.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D4863%23feedback-editor-4863)

6. [Skip to note 14 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-3722)



The Callback `$function_to_add` need not be defined until the Filter _hook fires_. This means that:



1. The `add_filter` function does not check that `$function_to_add` exists
2. The `function` statement for `$function_to_add` can be defined after the `add_filter` statement, even in a conditional (e.g. – `if` block) where the `$function_to_add` function does not actually _exist_ until after the `add_filter` function executes
3. If the Filter _hook_ never _fires_, an undefined _$function\_to\_add_ function will not be reported as an error

Point 3 needs to be considered during Testing or Quality Control

An undefined _$function\_to\_add_ function detected when a Filter _hook fires_ is reported as a Warning error:

`Warning: call_user_func_array() expects parameter 1 to be a valid callback, function 'reg_public1' not found or invalid function name in /var/www/example.com/public_html/wp-includes/class-wp-hook.php on line 288`

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D3722%23feedback-editor-3722)

7. [Skip to note 15 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-7156)



If you output something inside the callback, the output location is unpredictable.


Cause: the returned value is actually used somewhere else (more likely a bit far from where the function would be called). Therefore the output will go where the function was called while the return value is used somewhere else. I’m not sure when you would use this though :).





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
add_filter( 'the_content', 'wpdocs_append_to_content', 9 );

function wpdocs_append_to_content( $content ) {
           // output something
           echo 'I Don\'t Know Where I will end up being printed';

   	$additional_content = 'Appended to content';
   	$content = $content . $additional_content;

   	return $content;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D7156%23feedback-editor-7156)

8. [Skip to note 16 content](https://developer.wordpress.org/reference/functions/add_filter/#comment-content-407)



**Example**


The filter `img_caption_shortcode` is applied in `media.php` using the following call:





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
// Allow plugins/themes to override the default caption template.
$output = apply_filters( 'img_caption_shortcode', '', $attr, $content );
if ( $output != '' )
   	return $output;
```





The target filter function will be called with three arguments:



” <= This is normally the value the filter will be modifying


$attr


$content



In order for the filter function to actually receive the full argument list, the call to `add_filter()` must be modified to specify there are 3 arguments on the parameter list.





`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_filter/#)

[Copy](https://developer.wordpress.org/reference/functions/add_filter/#)




```php
add_filter('img_caption_shortcode', 'my_img_caption_shortcode_filter',10,3);

/**
    * Filter to replace the  shortcode text with HTML5 compliant code
    *
    * @return text HTML content describing embedded figure
    **/
function my_img_caption_shortcode_filter($val, $attr, $content = null)
{
   	extract( shortcode_atts( array(
   		'id'	=> '',
   		'align'	=> '',
   		'width'	=> '',
   		'caption' => ''
   	), $attr ) );

   	if ( 1 > (int) $width || empty($caption) )
   		return $val;

   	$capid = '';
   	if ( $id ) {
   		$id = esc_attr( $id );
   		$capid = 'id="figcaption_' . $id . '" ';
   		$id = 'id="' . $id . '" aria-labelledby="figcaption_' . $id . '" ';
   	}

   	return '<figure ' . $id . 'class="wp-caption ' . esc_attr($align) . '" style="width: '
   	. (10 + (int) $width) . 'px">' . do_shortcode( $content ) . '<figcaption ' . $capid
   	. 'class="wp-caption-text">' . $caption . '</figcaption></figure>';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F%3Freplytocom%3D407%23feedback-editor-407)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_filter%2F) before being able to contribute a note or feedback.

Notifications