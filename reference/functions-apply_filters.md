---
url: https://developer.wordpress.org/reference/functions/apply_filters
scraped_at: 2025-10-20T03:44:34.202Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/apply_filters/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

apply\_filters()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)apply\_filters()

Search

# apply\_filters( string$hook\_name, mixed$value, mixed$args ): mixed

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/apply_filters/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/apply_filters/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/apply_filters/#return)
- [Source](https://developer.wordpress.org/reference/functions/apply_filters/#source)
- [Related](https://developer.wordpress.org/reference/functions/apply_filters/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/apply_filters/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/apply_filters/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/apply_filters/#wp--skip-link--target)

Calls the callback functions that have been added to a filter hook.

## [Description](https://developer.wordpress.org/reference/functions/apply_filters/\#description)

This function invokes all functions attached to filter hook `$hook_name`.

It is possible to create new filter hooks by simply calling this function, specifying the name of the new hook using the `$hook_name` parameter.

The function also allows for multiple additional arguments to be passed to hooks.

Example usage:

`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/apply_filters/#)

[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)

```php
// The filter callback function.
function example_callback( $string, $arg1, $arg2 ) {
    // (maybe) modify $string.
    return $string;
}
add_filter( 'example_filter', 'example_callback', 10, 3 );

/*
 * Apply the filters by calling the 'example_callback()' function
 * that's hooked onto `example_filter` above.
 *
 * - 'example_filter' is the filter hook.
 * - 'filter me' is the value being filtered.
 * - $arg1 and $arg2 are the additional arguments passed to the callback.
$value = apply_filters( 'example_filter', 'filter me', $arg1, $arg2 );
```

## [Parameters](https://developer.wordpress.org/reference/functions/apply_filters/\#parameters)

`$hook_name` stringrequired

The name of the filter hook.

`$value` mixedrequired

The value to filter.

`$args` mixedoptional

Additional parameters to pass to the callback functions.

## [Return](https://developer.wordpress.org/reference/functions/apply_filters/\#return)

mixed The filtered value after all hooked functions are applied to it.

## [Source](https://developer.wordpress.org/reference/functions/apply_filters/\#source)

`wp-includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/apply_filters/#)

[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)

```php
function apply_filters( $hook_name, $value, ...$args ) {
	global $wp_filter, $wp_filters, $wp_current_filter;

	if ( ! isset( $wp_filters[ $hook_name ] ) ) {
		$wp_filters[ $hook_name ] = 1;
	} else {
		++$wp_filters[ $hook_name ];
	}

	// Do 'all' actions first.
	if ( isset( $wp_filter['all'] ) ) {
		$wp_current_filter[] = $hook_name;

		$all_args = func_get_args(); // phpcs:ignore PHPCompatibility.FunctionUse.ArgumentFunctionsReportCurrentValue.NeedsInspection
		_wp_call_all_hook( $all_args );
	}

	if ( ! isset( $wp_filter[ $hook_name ] ) ) {
		if ( isset( $wp_filter['all'] ) ) {
			array_pop( $wp_current_filter );
		}

		return $value;
	}

	if ( ! isset( $wp_filter['all'] ) ) {
		$wp_current_filter[] = $hook_name;
	}

	// Pass the value to WP_Hook.
	array_unshift( $args, $value );

	$filtered = $wp_filter[ $hook_name ]->apply_filters( $value, $args );

	array_pop( $wp_current_filter );

	return $filtered;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L173) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L173-L210)

## [Related](https://developer.wordpress.org/reference/functions/apply_filters/\#related)

| Uses | Description |
| --- | --- |
| [\_wp\_call\_all\_hook()](https://developer.wordpress.org/reference/functions/_wp_call_all_hook/) `wp-includes/plugin.php` | Calls the ‘all’ hook, which will process the functions hooked into it. |

| Used by | Description |
| --- | --- |
| [wp\_password\_needs\_rehash()](https://developer.wordpress.org/reference/functions/wp_password_needs_rehash/) `wp-includes/pluggable.php` | Checks whether a password hash needs to be rehashed. |
| [is\_post\_embeddable()](https://developer.wordpress.org/reference/functions/is_post_embeddable/) `wp-includes/post.php` | Determines whether a post is embeddable. |
| [wp\_should\_load\_block\_assets\_on\_demand()](https://developer.wordpress.org/reference/functions/wp_should_load_block_assets_on_demand/) `wp-includes/script-loader.php` | Checks whether block styles should be loaded only on-render. |
| [WP\_REST\_Menu\_Locations\_Controller::check\_has\_read\_only\_access()](https://developer.wordpress.org/reference/classes/wp_rest_menu_locations_controller/check_has_read_only_access/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-locations-controller.php` | Checks whether the current user has read permission for the endpoint. |
| [wp\_check\_comment\_data()](https://developer.wordpress.org/reference/functions/wp_check_comment_data/) `wp-includes/comment.php` | Checks whether comment data passes internal checks or has disallowed content. |
| [WP\_Script\_Modules::print\_script\_module\_data()](https://developer.wordpress.org/reference/classes/wp_script_modules/print_script_module_data/) `wp-includes/class-wp-script-modules.php` | Print data associated with Script Modules. |
| [WP\_Block\_Metadata\_Registry::register\_collection()](https://developer.wordpress.org/reference/classes/wp_block_metadata_registry/register_collection/) `wp-includes/class-wp-block-metadata-registry.php` | Registers a block metadata collection. |
| [wp\_autoload\_values\_to\_autoload()](https://developer.wordpress.org/reference/functions/wp_autoload_values_to_autoload/) `wp-includes/option.php` | Returns the values that trigger autoloading from the options table. |
| [wp\_determine\_option\_autoload\_value()](https://developer.wordpress.org/reference/functions/wp_determine_option_autoload_value/) `wp-includes/option.php` | Determines the appropriate autoload value for an option based on input. |
| [wp\_filter\_default\_autoload\_value\_via\_option\_size()](https://developer.wordpress.org/reference/functions/wp_filter_default_autoload_value_via_option_size/) `wp-includes/option.php` | Filters the default autoload value to disable autoloading if the option value is too large. |
| [insert\_hooked\_blocks\_into\_rest\_response()](https://developer.wordpress.org/reference/functions/insert_hooked_blocks_into_rest_response/) `wp-includes/blocks.php` | Hooks into the REST API response for the Posts endpoint and adds the first and last inner blocks. |
| [WP\_Site\_Health::get\_test\_autoloaded\_options()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_autoloaded_options/) `wp-admin/includes/class-wp-site-health.php` | Tests the number of autoloaded options. |
| [WP\_Automatic\_Updater::has\_fatal\_error()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/has_fatal_error/) `wp-admin/includes/class-wp-automatic-updater.php` | Performs a loopback request to check for potential fatal errors. |
| [\_wp\_filter\_font\_directory()](https://developer.wordpress.org/reference/functions/_wp_filter_font_directory/) `wp-includes/fonts.php` | A callback function for use in the [‘upload\_dir’](https://developer.wordpress.org/reference/hooks/upload_dir/) filter. |
| [WP\_Block\_Type::get\_variations()](https://developer.wordpress.org/reference/classes/wp_block_type/get_variations/) `wp-includes/class-wp-block-type.php` | Get block variations. |
| [WP\_Block\_Type::get\_uses\_context()](https://developer.wordpress.org/reference/classes/wp_block_type/get_uses_context/) `wp-includes/class-wp-block-type.php` | Get block uses context. |
| [WP\_Plugin\_Dependencies::sanitize\_dependency\_slugs()](https://developer.wordpress.org/reference/classes/wp_plugin_dependencies/sanitize_dependency_slugs/) `wp-includes/class-wp-plugin-dependencies.php` | Sanitizes slugs. |
| [wp\_is\_rest\_endpoint()](https://developer.wordpress.org/reference/functions/wp_is_rest_endpoint/) `wp-includes/rest-api.php` | Checks whether a REST API endpoint request is currently being handled. |
| [WP\_Block\_Bindings\_Source::get\_value()](https://developer.wordpress.org/reference/classes/wp_block_bindings_source/get_value/) `wp-includes/class-wp-block-bindings-source.php` | Calls the callback function specified in the `$get_value_callback` property with the given arguments and returns the result. It can be modified with `block_bindings_source_value` filter. |
| [WP\_Script\_Modules::get\_src()](https://developer.wordpress.org/reference/classes/wp_script_modules/get_src/) `wp-includes/class-wp-script-modules.php` | Gets the versioned URL for a script module src. |
| [WP\_Textdomain\_Registry::get\_language\_files\_from\_path()](https://developer.wordpress.org/reference/classes/wp_textdomain_registry/get_language_files_from_path/) `wp-includes/class-wp-textdomain-registry.php` | Retrieves translation files from the specified path. |
| [WP\_REST\_Font\_Faces\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_font_faces_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-font-faces-controller.php` | Retrieves the query params for the font face collection. |
| [WP\_REST\_Font\_Faces\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_font_faces_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-font-faces-controller.php` | Prepares a single font face output for response. |
| [WP\_REST\_Font\_Families\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_font_families_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-font-families-controller.php` | Retrieves the query params for the font family collection. |
| [WP\_REST\_Font\_Families\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_font_families_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-font-families-controller.php` | Prepares a single font family output for response. |
| [WP\_REST\_Font\_Collections\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_font_collections_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-font-collections-controller.php` | Retrieves the search params for the font collections. |
| [WP\_REST\_Font\_Collections\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_font_collections_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-font-collections-controller.php` | Prepare a single collection output for response. |
| [set\_ignored\_hooked\_blocks\_metadata()](https://developer.wordpress.org/reference/functions/set_ignored_hooked_blocks_metadata/) `wp-includes/blocks.php` | Adds a list of hooked block types to an anchor block’s ignored hooked block types. |
| [insert\_hooked\_blocks()](https://developer.wordpress.org/reference/functions/insert_hooked_blocks/) `wp-includes/blocks.php` | Returns the markup for blocks hooked to the given anchor block in a specific relative position. |
| [wp\_zip\_file\_is\_valid()](https://developer.wordpress.org/reference/functions/wp_zip_file_is_valid/) `wp-admin/includes/file.php` | Determines whether the given file is a valid ZIP file. |
| [wp\_get\_admin\_notice()](https://developer.wordpress.org/reference/functions/wp_get_admin_notice/) `wp-includes/functions.php` | Creates and returns the markup for an admin notice. |
| [\_deprecated\_class()](https://developer.wordpress.org/reference/functions/_deprecated_class/) `wp-includes/functions.php` | Marks a class as deprecated and informs when it has been used. |
| [wp\_get\_https\_detection\_errors()](https://developer.wordpress.org/reference/functions/wp_get_https_detection_errors/) `wp-includes/https-detection.php` | Runs a remote HTTPS request to detect whether HTTPS supported, and stores potential errors. |
| [WP\_Theme::get\_block\_patterns()](https://developer.wordpress.org/reference/classes/wp_theme/get_block_patterns/) `wp-includes/class-wp-theme.php` | Gets block pattern data for a specified theme. |
| [WP\_Theme::set\_pattern\_cache()](https://developer.wordpress.org/reference/classes/wp_theme/set_pattern_cache/) `wp-includes/class-wp-theme.php` | Sets block pattern cache. |
| [wp\_post\_revision\_meta\_keys()](https://developer.wordpress.org/reference/functions/wp_post_revision_meta_keys/) `wp-includes/revision.php` | Determine which post meta fields should be revisioned. |
| [wp\_is\_authorize\_application\_redirect\_url\_valid()](https://developer.wordpress.org/reference/functions/wp_is_authorize_application_redirect_url_valid/) `wp-admin/includes/user.php` | Validates the redirect URL protocol scheme. The protocol can be anything except `http` and `javascript`. |
| [wp\_is\_password\_reset\_allowed\_for\_user()](https://developer.wordpress.org/reference/functions/wp_is_password_reset_allowed_for_user/) `wp-includes/user.php` | Checks if password reset is allowed for a specific user. |
| [WP\_Navigation\_Fallback::get\_fallback()](https://developer.wordpress.org/reference/classes/wp_navigation_fallback/get_fallback/) `wp-includes/class-wp-navigation-fallback.php` | Gets (and/or creates) an appropriate fallback Navigation Menu. |
| [sanitize\_locale\_name()](https://developer.wordpress.org/reference/functions/sanitize_locale_name/) `wp-includes/formatting.php` | Strips out all characters not allowed in a locale name. |
| [\_make\_clickable\_rel\_attr()](https://developer.wordpress.org/reference/functions/_make_clickable_rel_attr/) `wp-includes/formatting.php` | Helper function used to build the “rel” attribute for a URL when creating an anchor using [make\_clickable()](https://developer.wordpress.org/reference/functions/make_clickable/) . |
| [wp\_internal\_hosts()](https://developer.wordpress.org/reference/functions/wp_internal_hosts/) `wp-includes/link-template.php` | Returns an array of URL hosts which are considered to be internal hosts. |
| [wp\_theme\_has\_theme\_json()](https://developer.wordpress.org/reference/functions/wp_theme_has_theme_json/) `wp-includes/global-styles-and-settings.php` | Checks whether a theme or its parent has a theme.json file. |
| [wp\_img\_tag\_add\_decoding\_attr()](https://developer.wordpress.org/reference/functions/wp_img_tag_add_decoding_attr/) `wp-includes/deprecated.php` | Adds `decoding` attribute to an `img` HTML tag. |
| [get\_template\_hierarchy()](https://developer.wordpress.org/reference/functions/get_template_hierarchy/) `wp-includes/block-template-utils.php` | Gets the template hierarchy for the given template slug to be created. |
| [wp\_required\_field\_message()](https://developer.wordpress.org/reference/functions/wp_required_field_message/) `wp-includes/general-template.php` | Creates a message to explain required form fields. |
| [wp\_required\_field\_indicator()](https://developer.wordpress.org/reference/functions/wp_required_field_indicator/) `wp-includes/general-template.php` | Assigns a visual indicator for required form fields. |
| [wp\_preload\_resources()](https://developer.wordpress.org/reference/functions/wp_preload_resources/) `wp-includes/general-template.php` | Prints resource preloads directives to browsers. |
| [WP\_Textdomain\_Registry::get()](https://developer.wordpress.org/reference/classes/wp_textdomain_registry/get/) `wp-includes/class-wp-textdomain-registry.php` | Returns the languages directory path for a specific domain and locale. |
| [WP\_REST\_Server::get\_json\_encode\_options()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_json_encode_options/) `wp-includes/rest-api/class-wp-rest-server.php` | Gets the encoding options passed to [wp\_json\_encode](https://developer.wordpress.org/reference/functions/wp_json_encode). |
| [WP\_Theme\_JSON\_Resolver::get\_block\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_block_data/) `wp-includes/class-wp-theme-json-resolver.php` | Gets the styles for blocks from the block.json file. |
| [WP\_Site\_Health::available\_object\_cache\_services()](https://developer.wordpress.org/reference/classes/wp_site_health/available_object_cache_services/) `wp-admin/includes/class-wp-site-health.php` | Returns a list of available persistent object cache services. |
| [WP\_Site\_Health::get\_page\_cache\_headers()](https://developer.wordpress.org/reference/classes/wp_site_health/get_page_cache_headers/) `wp-admin/includes/class-wp-site-health.php` | Returns a list of headers and its verification callback to verify if page cache is enabled or not. |
| [WP\_Site\_Health::check\_for\_page\_caching()](https://developer.wordpress.org/reference/classes/wp_site_health/check_for_page_caching/) `wp-admin/includes/class-wp-site-health.php` | Checks if site has page cache enabled or not. |
| [WP\_Site\_Health::get\_good\_response\_time\_threshold()](https://developer.wordpress.org/reference/classes/wp_site_health/get_good_response_time_threshold/) `wp-admin/includes/class-wp-site-health.php` | Gets the threshold below which a response time is considered good. |
| [WP\_Site\_Health::should\_suggest\_persistent\_object\_cache()](https://developer.wordpress.org/reference/classes/wp_site_health/should_suggest_persistent_object_cache/) `wp-admin/includes/class-wp-site-health.php` | Determines whether to suggest using a persistent object cache. |
| [WP\_Site\_Health::get\_test\_persistent\_object\_cache()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_persistent_object_cache/) `wp-admin/includes/class-wp-site-health.php` | Tests if the site uses persistent object cache and recommends to use it if not. |
| [IXR\_Message::parse()](https://developer.wordpress.org/reference/classes/ixr_message/parse/) `wp-includes/IXR/class-IXR-message.php` |  |
| [\_register\_remote\_theme\_patterns()](https://developer.wordpress.org/reference/functions/_register_remote_theme_patterns/) `wp-includes/block-patterns.php` | Registers patterns from Pattern Directory provided by a theme’s `theme.json` file. |
| [wp\_filesize()](https://developer.wordpress.org/reference/functions/wp_filesize/) `wp-includes/functions.php` | Wrapper for PHP filesize with filters and casting the result as an integer. |
| [wp\_maybe\_update\_user\_counts()](https://developer.wordpress.org/reference/functions/wp_maybe_update_user_counts/) `wp-includes/user.php` | Updates the total count of users on the site if live user counting is enabled. |
| [wp\_is\_large\_user\_count()](https://developer.wordpress.org/reference/functions/wp_is_large_user_count/) `wp-includes/user.php` | Determines whether the site has a large number of users. |
| [\_load\_remote\_featured\_patterns()](https://developer.wordpress.org/reference/functions/_load_remote_featured_patterns/) `wp-includes/block-patterns.php` | Register `Featured` (category) patterns from wordpress.org/patterns. |
| [WP\_Theme\_JSON\_Resolver::get\_user\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_user_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns the user’s origin config. |
| [WP\_REST\_Menu\_Items\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Prepares a single nav menu item output for response. |
| [WP\_REST\_Menu\_Items\_Controller::check\_has\_read\_only\_access()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/check_has_read_only_access/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Checks whether the current user has read permission for the endpoint. |
| [WP\_REST\_Menu\_Items\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Prepares a single nav menu item for create or update. |
| [WP\_REST\_URL\_Details\_Controller::set\_cache()](https://developer.wordpress.org/reference/classes/wp_rest_url_details_controller/set_cache/) `wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php` | Utility function to cache a given data set at a given cache key. |
| [WP\_REST\_URL\_Details\_Controller::parse\_url\_details()](https://developer.wordpress.org/reference/classes/wp_rest_url_details_controller/parse_url_details/) `wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php` | Retrieves the contents of the title tag from the HTML response. |
| [WP\_REST\_URL\_Details\_Controller::get\_remote\_url()](https://developer.wordpress.org/reference/classes/wp_rest_url_details_controller/get_remote_url/) `wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php` | Retrieves the document title from a remote URL. |
| [WP\_REST\_Menus\_Controller::check\_has\_read\_only\_access()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/check_has_read_only_access/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Checks whether the current user has read permission for the endpoint. |
| [WP\_REST\_Menus\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_menus_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php` | Prepares a single term output for response. |
| [WP\_REST\_Menu\_Locations\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_menu_locations_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-locations-controller.php` | Prepares a menu location object for serialization. |
| [WP\_Theme::get\_file\_path()](https://developer.wordpress.org/reference/classes/wp_theme/get_file_path/) `wp-includes/class-wp-theme.php` | Retrieves the path of a file in the theme. |
| [wp\_list\_users()](https://developer.wordpress.org/reference/functions/wp_list_users/) `wp-includes/user.php` | Lists all the users of the site, with several options available. |
| [get\_block\_file\_template()](https://developer.wordpress.org/reference/functions/get_block_file_template/) `wp-includes/block-template-utils.php` | Retrieves a unified template object based on a theme file. |
| [get\_allowed\_block\_template\_part\_areas()](https://developer.wordpress.org/reference/functions/get_allowed_block_template_part_areas/) `wp-includes/block-template-utils.php` | Returns a filtered list of allowed area values for template parts. |
| [get\_default\_block\_template\_types()](https://developer.wordpress.org/reference/functions/get_default_block_template_types/) `wp-includes/block-template-utils.php` | Returns a filtered list of default template types, containing their localized titles and descriptions. |
| [rest\_get\_route\_for\_post\_type\_items()](https://developer.wordpress.org/reference/functions/rest_get_route_for_post_type_items/) `wp-includes/rest-api.php` | Gets the REST API route for a post type. |
| [rest\_get\_route\_for\_taxonomy\_items()](https://developer.wordpress.org/reference/functions/rest_get_route_for_taxonomy_items/) `wp-includes/rest-api.php` | Gets the REST API route for a taxonomy. |
| [WP\_Widget\_Block::widget()](https://developer.wordpress.org/reference/classes/wp_widget_block/widget/) `wp-includes/widgets/class-wp-widget-block.php` | Outputs the content for the current Block widget instance. |
| [WP\_Widget\_Block::get\_dynamic\_classname()](https://developer.wordpress.org/reference/classes/wp_widget_block/get_dynamic_classname/) `wp-includes/widgets/class-wp-widget-block.php` | Calculates the classname to use in the block widget’s container HTML. |
| [\_load\_remote\_block\_patterns()](https://developer.wordpress.org/reference/functions/_load_remote_block_patterns/) `wp-includes/block-patterns.php` | Register Core’s official patterns from wordpress.org/patterns. |
| [WP\_Theme\_JSON\_Resolver::get\_theme\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_theme_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns the theme’s data. |
| [WP\_Theme\_JSON\_Resolver::get\_core\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_core_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns core’s origin config. |
| [WP\_REST\_Widgets\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_widgets_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-widgets-controller.php` | Prepares the widget for the REST response. |
| [WP\_REST\_Sidebars\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_sidebars_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-sidebars-controller.php` | Prepares a single sidebar output for response. |
| [WP\_REST\_Templates\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_templates_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php` | Prepare a single template output for response |
| [WP\_REST\_Templates\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_templates_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php` | Prepares a single template for create or update. |
| [WP\_REST\_Pattern\_Directory\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_pattern_directory_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-pattern-directory-controller.php` | Prepare a raw block pattern before it gets output in a REST API response. |
| [WP\_REST\_Pattern\_Directory\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_pattern_directory_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-pattern-directory-controller.php` | Retrieves the search parameters for the block pattern’s collection. |
| [WP\_REST\_Widget\_Types\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_widget_types_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php` | Prepares a widget type object for serialization. |
| [WP\_REST\_Widget\_Types\_Controller::encode\_form\_data()](https://developer.wordpress.org/reference/classes/wp_rest_widget_types_controller/encode_form_data/) `wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php` | An RPC-style endpoint which can be used by clients to turn user input in a widget admin form into an encoded instance object. |
| [WP\_REST\_Widget\_Types\_Controller::get\_widget\_form()](https://developer.wordpress.org/reference/classes/wp_rest_widget_types_controller/get_widget_form/) `wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php` | Returns the output of [WP\_Widget::form()](https://developer.wordpress.org/reference/classes/wp_widget/form/) when called with the provided instance. Used by encode\_form\_data() to preview a widget’s form. |
| [get\_legacy\_widget\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_legacy_widget_block_editor_settings/) `wp-includes/block-editor.php` | Returns the block editor settings needed to use the Legacy Widget block which is not registered by default. |
| [get\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_block_editor_settings/) `wp-includes/block-editor.php` | Returns the contextualized block editor settings for a selected editor context. |
| [block\_editor\_rest\_api\_preload()](https://developer.wordpress.org/reference/functions/block_editor_rest_api_preload/) `wp-includes/block-editor.php` | Preloads common data used with the block editor by specifying an array of REST API paths that will be preloaded for a given block editor context. |
| [get\_allowed\_block\_types()](https://developer.wordpress.org/reference/functions/get_allowed_block_types/) `wp-includes/block-editor.php` | Gets the list of allowed block types to use in the block editor. |
| [get\_default\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_default_block_editor_settings/) `wp-includes/block-editor.php` | Returns the default block editor settings. |
| [wp\_render\_widget()](https://developer.wordpress.org/reference/functions/wp_render_widget/) `wp-includes/widgets.php` | Calls the render callback of a widget and returns the output. |
| [wp\_use\_widgets\_block\_editor()](https://developer.wordpress.org/reference/functions/wp_use_widgets_block_editor/) `wp-includes/widgets.php` | Determines whether or not to use the block editor to manage widgets. |
| [wp\_xmlrpc\_server::set\_is\_enabled()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/set_is_enabled/) `wp-includes/class-wp-xmlrpc-server.php` | Sets wp\_xmlrpc\_server::$is\_enabled property. |
| [wp\_maybe\_inline\_styles()](https://developer.wordpress.org/reference/functions/wp_maybe_inline_styles/) `wp-includes/script-loader.php` | Allows small styles to be inlined. |
| [wp\_should\_load\_separate\_core\_block\_assets()](https://developer.wordpress.org/reference/functions/wp_should_load_separate_core_block_assets/) `wp-includes/script-loader.php` | Checks whether separate styles should be loaded for core blocks. |
| [get\_block\_templates()](https://developer.wordpress.org/reference/functions/get_block_templates/) `wp-includes/block-template-utils.php` | Retrieves a list of unified template objects based on a query. |
| [get\_block\_template()](https://developer.wordpress.org/reference/functions/get_block_template/) `wp-includes/block-template-utils.php` | Retrieves a single unified template object using its id. |
| [build\_query\_vars\_from\_query\_block()](https://developer.wordpress.org/reference/functions/build_query_vars_from_query_block/) `wp-includes/blocks.php` | Helper function that constructs a [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) args array from a `Query` block properties. |
| [wp\_robots()](https://developer.wordpress.org/reference/functions/wp_robots/) `wp-includes/robots-template.php` | Displays the robots meta tag as necessary. |
| [wp\_get\_inline\_script\_tag()](https://developer.wordpress.org/reference/functions/wp_get_inline_script_tag/) `wp-includes/script-loader.php` | Constructs an inline script tag. |
| [wp\_get\_script\_tag()](https://developer.wordpress.org/reference/functions/wp_get_script_tag/) `wp-includes/script-loader.php` | Formats `` loader tags. |
| [wp\_get\_update\_https\_url()](https://developer.wordpress.org/reference/functions/wp_get_update_https_url/) `wp-includes/functions.php` | Gets the URL to learn more about updating the site to use HTTPS. |
| [wp\_get\_direct\_update\_https\_url()](https://developer.wordpress.org/reference/functions/wp_get_direct_update_https_url/) `wp-includes/functions.php` | Gets the URL for directly updating the site to use HTTPS. |
| [is\_post\_status\_viewable()](https://developer.wordpress.org/reference/functions/is_post_status_viewable/) `wp-includes/post.php` | Determines whether a post status is considered “viewable”. |
| [wp\_update\_https\_detection\_errors()](https://developer.wordpress.org/reference/functions/wp_update_https_detection_errors/) `wp-includes/deprecated.php` | Runs a remote HTTPS request to detect whether HTTPS supported, and stores potential errors. |
| [wp\_is\_site\_url\_using\_https()](https://developer.wordpress.org/reference/functions/wp_is_site_url_using_https/) `wp-includes/https-detection.php` | Checks whether the current site’s URL where WordPress is stored is using HTTPS. |
| [wp\_should\_replace\_insecure\_home\_url()](https://developer.wordpress.org/reference/functions/wp_should_replace_insecure_home_url/) `wp-includes/https-migration.php` | Checks whether WordPress should replace old HTTP URLs to the site with their HTTPS counterpart. |
| [wp\_is\_site\_protected\_by\_basic\_auth()](https://developer.wordpress.org/reference/functions/wp_is_site_protected_by_basic_auth/) `wp-includes/load.php` | Checks if this site is protected by HTTP Basic Auth. |
| [wpmu\_new\_site\_admin\_notification()](https://developer.wordpress.org/reference/functions/wpmu_new_site_admin_notification/) `wp-includes/ms-functions.php` | Notifies the Multisite network administrator that a new site was created. |
| [WP\_REST\_Server::get\_max\_batch\_size()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_max_batch_size/) `wp-includes/rest-api/class-wp-rest-server.php` | Gets the maximum number of requests that can be included in a batch. |
| [WP\_REST\_Server::serve\_batch\_request\_v1()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_batch_request_v1/) `wp-includes/rest-api/class-wp-rest-server.php` | Serves the batch/v1 request. |
| [WP\_REST\_Server::respond\_to\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/respond_to_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Dispatches the request to the callback handler. |
| [WP\_REST\_Site\_Health\_Controller::validate\_request\_permission()](https://developer.wordpress.org/reference/classes/wp_rest_site_health_controller/validate_request_permission/) `wp-includes/rest-api/endpoints/class-wp-rest-site-health-controller.php` | Validates if the current user can request this REST endpoint. |
| [WP\_REST\_Application\_Passwords\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_application_passwords_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-application-passwords-controller.php` | Prepares an application password for a create or update operation. |
| [WP\_REST\_Application\_Passwords\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_application_passwords_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-application-passwords-controller.php` | Prepares the application password for the REST response. |
| [WP\_REST\_Comments\_Controller::check\_is\_comment\_content\_allowed()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/check_is_comment_content_allowed/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | If empty comments are not allowed, checks if the provided comment content is not empty. |
| [WP\_REST\_Term\_Search\_Handler::search\_items()](https://developer.wordpress.org/reference/classes/wp_rest_term_search_handler/search_items/) `wp-includes/rest-api/search/class-wp-rest-term-search-handler.php` | Searches terms for a given search request. |
| [WP\_REST\_Post\_Format\_Search\_Handler::search\_items()](https://developer.wordpress.org/reference/classes/wp_rest_post_format_search_handler/search_items/) `wp-includes/rest-api/search/class-wp-rest-post-format-search-handler.php` | Searches the post formats for a given search request. |
| [wp\_should\_load\_block\_editor\_scripts\_and\_styles()](https://developer.wordpress.org/reference/functions/wp_should_load_block_editor_scripts_and_styles/) `wp-includes/script-loader.php` | Checks if the editor scripts and styles for all registered block types should be enqueued on the current screen. |
| [wp\_is\_application\_passwords\_available()](https://developer.wordpress.org/reference/functions/wp_is_application_passwords_available/) `wp-includes/user.php` | Checks if Application Passwords is globally available. |
| [wp\_is\_application\_passwords\_available\_for\_user()](https://developer.wordpress.org/reference/functions/wp_is_application_passwords_available_for_user/) `wp-includes/user.php` | Checks if Application Passwords is available for a specific user. |
| [wp\_authenticate\_application\_password()](https://developer.wordpress.org/reference/functions/wp_authenticate_application_password/) `wp-includes/user.php` | Authenticates the user using an application password. |
| [get\_media\_states()](https://developer.wordpress.org/reference/functions/get_media_states/) `wp-admin/includes/template.php` | Retrieves an array of media states from an attachment. |
| [wp\_is\_auto\_update\_forced\_for\_item()](https://developer.wordpress.org/reference/functions/wp_is_auto_update_forced_for_item/) `wp-admin/includes/update.php` | Checks whether auto-updates are forced for an item. |
| [WP\_Comments\_List\_Table::comment\_type\_dropdown()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/comment_type_dropdown/) `wp-admin/includes/class-wp-comments-list-table.php` | Displays a comment type drop-down for filtering on the Comments list table. |
| [core\_auto\_updates\_settings()](https://developer.wordpress.org/reference/functions/core_auto_updates_settings/) `wp-admin/update-core.php` | Display WordPress auto-updates settings. |
| [esc\_xml()](https://developer.wordpress.org/reference/functions/esc_xml/) `wp-includes/formatting.php` | Escaping for XML blocks. |
| [get\_metadata\_default()](https://developer.wordpress.org/reference/functions/get_metadata_default/) `wp-includes/meta.php` | Retrieves default metadata value for the specified meta key and object. |
| [get\_metadata\_raw()](https://developer.wordpress.org/reference/functions/get_metadata_raw/) `wp-includes/meta.php` | Retrieves raw metadata value for the specified object. |
| [WP\_Block::render()](https://developer.wordpress.org/reference/classes/wp_block/render/) `wp-includes/class-wp-block.php` | Generates the render output for the block. |
| [wp\_is\_maintenance\_mode()](https://developer.wordpress.org/reference/functions/wp_is_maintenance_mode/) `wp-includes/load.php` | Checks if maintenance mode is enabled. |
| [WP\_REST\_Block\_Directory\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_block_directory_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-block-directory-controller.php` | Retrieves the search params for the blocks collection. |
| [WP\_REST\_Plugins\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_plugins_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-plugins-controller.php` | Uploads a plugin and optionally activates it. |
| [WP\_REST\_Plugins\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_plugins_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-plugins-controller.php` | Prepares the plugin for the REST response. |
| [WP\_REST\_Block\_Types\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_block_types_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-block-types-controller.php` | Prepares a block type object for serialization. |
| [WP\_REST\_Attachments\_Controller::edit\_media\_item()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/edit_media_item/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Applies edits to a media item and creates a new attachment record. |
| [\_wp\_batch\_update\_comment\_type()](https://developer.wordpress.org/reference/functions/_wp_batch_update_comment_type/) `wp-includes/comment.php` | Updates the comment type for a batch of comments. |
| [wp\_img\_tag\_add\_loading\_attr()](https://developer.wordpress.org/reference/functions/wp_img_tag_add_loading_attr/) `wp-includes/deprecated.php` | Adds `loading` attribute to an `img` HTML tag. |
| [rest\_get\_route\_for\_post()](https://developer.wordpress.org/reference/functions/rest_get_route_for_post/) `wp-includes/rest-api.php` | Gets the REST API route for a post. |
| [rest\_get\_route\_for\_term()](https://developer.wordpress.org/reference/functions/rest_get_route_for_term/) `wp-includes/rest-api.php` | Gets the REST API route for a term. |
| [rest\_get\_queried\_resource\_route()](https://developer.wordpress.org/reference/functions/rest_get_queried_resource_route/) `wp-includes/rest-api.php` | Gets the REST route for the currently queried object. |
| [WP\_Embed::get\_embed\_handler\_html()](https://developer.wordpress.org/reference/classes/wp_embed/get_embed_handler_html/) `wp-includes/class-wp-embed.php` | Returns embed HTML for a given URL from embed handlers. |
| [register\_block\_type\_from\_metadata()](https://developer.wordpress.org/reference/functions/register_block_type_from_metadata/) `wp-includes/blocks.php` | Registers a block type from the metadata stored in the `block.json` file. |
| [wp\_sitemaps\_get\_max\_urls()](https://developer.wordpress.org/reference/functions/wp_sitemaps_get_max_urls/) `wp-includes/sitemaps.php` | Gets the maximum number of URLs for a sitemap. |
| [WP\_Sitemaps\_Provider::get\_sitemap\_entries()](https://developer.wordpress.org/reference/classes/wp_sitemaps_provider/get_sitemap_entries/) `wp-includes/sitemaps/class-wp-sitemaps-provider.php` | Lists sitemap pages exposed by this provider. |
| [WP\_Sitemaps::sitemaps\_enabled()](https://developer.wordpress.org/reference/classes/wp_sitemaps/sitemaps_enabled/) `wp-includes/sitemaps/class-wp-sitemaps.php` | Determines whether sitemaps are enabled or not. |
| [WP\_Sitemaps\_Renderer::get\_sitemap\_index\_stylesheet\_url()](https://developer.wordpress.org/reference/classes/wp_sitemaps_renderer/get_sitemap_index_stylesheet_url/) `wp-includes/sitemaps/class-wp-sitemaps-renderer.php` | Gets the URL for the sitemap index stylesheet. |
| [WP\_Sitemaps\_Users::get\_url\_list()](https://developer.wordpress.org/reference/classes/wp_sitemaps_users/get_url_list/) `wp-includes/sitemaps/providers/class-wp-sitemaps-users.php` | Gets a URL list for a user sitemap. |
| [WP\_Sitemaps\_Users::get\_max\_num\_pages()](https://developer.wordpress.org/reference/classes/wp_sitemaps_users/get_max_num_pages/) `wp-includes/sitemaps/providers/class-wp-sitemaps-users.php` | Gets the max number of pages available for the object type. |
| [WP\_Sitemaps\_Users::get\_users\_query\_args()](https://developer.wordpress.org/reference/classes/wp_sitemaps_users/get_users_query_args/) `wp-includes/sitemaps/providers/class-wp-sitemaps-users.php` | Returns the query args for retrieving users to list in the sitemap. |
| [WP\_Sitemaps\_Renderer::get\_sitemap\_stylesheet\_url()](https://developer.wordpress.org/reference/classes/wp_sitemaps_renderer/get_sitemap_stylesheet_url/) `wp-includes/sitemaps/class-wp-sitemaps-renderer.php` | Gets the URL for the sitemap stylesheet. |
| [WP\_Sitemaps\_Posts::get\_posts\_query\_args()](https://developer.wordpress.org/reference/classes/wp_sitemaps_posts/get_posts_query_args/) `wp-includes/sitemaps/providers/class-wp-sitemaps-posts.php` | Returns the query args for retrieving posts to list in the sitemap. |
| [WP\_Sitemaps\_Taxonomies::get\_object\_subtypes()](https://developer.wordpress.org/reference/classes/wp_sitemaps_taxonomies/get_object_subtypes/) `wp-includes/sitemaps/providers/class-wp-sitemaps-taxonomies.php` | Returns all public, registered taxonomies. |
| [WP\_Sitemaps\_Taxonomies::get\_url\_list()](https://developer.wordpress.org/reference/classes/wp_sitemaps_taxonomies/get_url_list/) `wp-includes/sitemaps/providers/class-wp-sitemaps-taxonomies.php` | Gets a URL list for a taxonomy sitemap. |
| [WP\_Sitemaps\_Taxonomies::get\_max\_num\_pages()](https://developer.wordpress.org/reference/classes/wp_sitemaps_taxonomies/get_max_num_pages/) `wp-includes/sitemaps/providers/class-wp-sitemaps-taxonomies.php` | Gets the max number of pages available for the object type. |
| [WP\_Sitemaps\_Taxonomies::get\_taxonomies\_query\_args()](https://developer.wordpress.org/reference/classes/wp_sitemaps_taxonomies/get_taxonomies_query_args/) `wp-includes/sitemaps/providers/class-wp-sitemaps-taxonomies.php` | Returns the query args for retrieving taxonomy terms to list in the sitemap. |
| [WP\_Sitemaps\_Posts::get\_object\_subtypes()](https://developer.wordpress.org/reference/classes/wp_sitemaps_posts/get_object_subtypes/) `wp-includes/sitemaps/providers/class-wp-sitemaps-posts.php` | Returns the public post types, which excludes nav\_items and similar types. |
| [WP\_Sitemaps\_Posts::get\_url\_list()](https://developer.wordpress.org/reference/classes/wp_sitemaps_posts/get_url_list/) `wp-includes/sitemaps/providers/class-wp-sitemaps-posts.php` | Gets a URL list for a post type sitemap. |
| [WP\_Sitemaps\_Posts::get\_max\_num\_pages()](https://developer.wordpress.org/reference/classes/wp_sitemaps_posts/get_max_num_pages/) `wp-includes/sitemaps/providers/class-wp-sitemaps-posts.php` | Gets the max number of pages available for the object type. |
| [WP\_Sitemaps\_Stylesheet::get\_stylesheet\_css()](https://developer.wordpress.org/reference/classes/wp_sitemaps_stylesheet/get_stylesheet_css/) `wp-includes/sitemaps/class-wp-sitemaps-stylesheet.php` | Gets the CSS to be included in sitemap XSL stylesheets. |
| [WP\_Sitemaps\_Stylesheet::get\_sitemap\_stylesheet()](https://developer.wordpress.org/reference/classes/wp_sitemaps_stylesheet/get_sitemap_stylesheet/) `wp-includes/sitemaps/class-wp-sitemaps-stylesheet.php` | Returns the escaped XSL for all sitemaps, except index. |
| [WP\_Sitemaps\_Stylesheet::get\_sitemap\_index\_stylesheet()](https://developer.wordpress.org/reference/classes/wp_sitemaps_stylesheet/get_sitemap_index_stylesheet/) `wp-includes/sitemaps/class-wp-sitemaps-stylesheet.php` | Returns the escaped XSL for the index sitemaps. |
| [WP\_Sitemaps\_Registry::add\_provider()](https://developer.wordpress.org/reference/classes/wp_sitemaps_registry/add_provider/) `wp-includes/sitemaps/class-wp-sitemaps-registry.php` | Adds a new sitemap provider. |
| [wp\_admin\_viewport\_meta()](https://developer.wordpress.org/reference/functions/wp_admin_viewport_meta/) `wp-admin/includes/misc.php` | Displays the viewport meta in the admin. |
| [wp\_opcache\_invalidate()](https://developer.wordpress.org/reference/functions/wp_opcache_invalidate/) `wp-admin/includes/file.php` | Attempts to clear the opcode cache for an individual PHP file. |
| [WP\_Automatic\_Updater::send\_plugin\_theme\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_plugin_theme_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Sends an email upon the completion or failure of a plugin or theme background update. |
| [WP\_Automatic\_Updater::after\_plugin\_theme\_update()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/after_plugin_theme_update/) `wp-admin/includes/class-wp-automatic-updater.php` | Checks whether an email should be sent after attempting plugin or theme updates. |
| [wp\_is\_auto\_update\_enabled\_for\_type()](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/) `wp-admin/includes/update.php` | Checks whether auto-updates are enabled. |
| [Plugin\_Installer\_Skin::do\_overwrite()](https://developer.wordpress.org/reference/classes/plugin_installer_skin/do_overwrite/) `wp-admin/includes/class-plugin-installer-skin.php` | Checks if the plugin can be overwritten and outputs the HTML for overwriting a plugin on upload. |
| [Theme\_Installer\_Skin::do\_overwrite()](https://developer.wordpress.org/reference/classes/theme_installer_skin/do_overwrite/) `wp-admin/includes/class-theme-installer-skin.php` | Checks if the theme can be overwritten and outputs the HTML for overwriting a theme on upload. |
| [WP\_MS\_Themes\_List\_Table::column\_autoupdates()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/column_autoupdates/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Handles the auto-updates column output. |
| [wp\_ajax\_toggle\_auto\_updates()](https://developer.wordpress.org/reference/functions/wp_ajax_toggle_auto_updates/) `wp-admin/includes/ajax-actions.php` | Handles enabling or disable plugin and theme auto-updates via AJAX. |
| [wp\_theme\_auto\_update\_setting\_template()](https://developer.wordpress.org/reference/functions/wp_theme_auto_update_setting_template/) `wp-admin/themes.php` | Returns the JavaScript template used to display the auto-update setting for a theme. |
| [WP\_Site\_Health::perform\_test()](https://developer.wordpress.org/reference/classes/wp_site_health/perform_test/) `wp-admin/includes/class-wp-site-health.php` | Runs a Site Health test directly. |
| [wpdb::log\_query()](https://developer.wordpress.org/reference/classes/wpdb/log_query/) `wp-includes/class-wpdb.php` | Logs query data. |
| [WP\_Image\_Editor::maybe\_exif\_rotate()](https://developer.wordpress.org/reference/classes/wp_image_editor/maybe_exif_rotate/) `wp-includes/class-wp-image-editor.php` | Check if a JPEG image has EXIF Orientation tag and rotate it if needed. |
| [wp\_date()](https://developer.wordpress.org/reference/functions/wp_date/) `wp-includes/functions.php` | Retrieves the date, in localized format. |
| [wp\_get\_original\_image\_path()](https://developer.wordpress.org/reference/functions/wp_get_original_image_path/) `wp-includes/post.php` | Retrieves the path to an uploaded image file. |
| [wp\_get\_original\_image\_url()](https://developer.wordpress.org/reference/functions/wp_get_original_image_url/) `wp-includes/post.php` | Retrieves the URL to an original attachment image. |
| [get\_post\_states()](https://developer.wordpress.org/reference/functions/get_post_states/) `wp-admin/includes/template.php` | Retrieves an array of post states from a post. |
| [wp\_get\_missing\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_get_missing_image_subsizes/) `wp-admin/includes/image.php` | Compare the existing image sub-sizes (as saved in the attachment meta) to the currently registered image sub-sizes, and return the difference. |
| [wp\_update\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_update_image_subsizes/) `wp-admin/includes/image.php` | If any of the currently registered image sub-sizes are missing, create them and update the image meta data. |
| [wp\_create\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_create_image_subsizes/) `wp-admin/includes/image.php` | Creates image sub-sizes, adds the new data to the image meta `sizes` array, and updates the image metadata. |
| [WP\_Privacy\_Data\_Removal\_Requests\_List\_Table::column\_email()](https://developer.wordpress.org/reference/classes/wp_privacy_data_removal_requests_list_table/column_email/) `wp-admin/includes/class-wp-privacy-data-removal-requests-list-table.php` | Outputs the Actions column. |
| [WP\_Privacy\_Data\_Removal\_Requests\_List\_Table::column\_next\_steps()](https://developer.wordpress.org/reference/classes/wp_privacy_data_removal_requests_list_table/column_next_steps/) `wp-admin/includes/class-wp-privacy-data-removal-requests-list-table.php` | Outputs the Next steps column. |
| [WP\_MS\_Sites\_List\_Table::site\_states()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/site_states/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Determines whether to output comma-separated site states. |
| [WP\_Privacy\_Data\_Export\_Requests\_List\_Table::column\_email()](https://developer.wordpress.org/reference/classes/wp_privacy_data_export_requests_list_table/column_email/) `wp-admin/includes/class-wp-privacy-data-export-requests-list-table.php` | Actions column. |
| [WP\_Privacy\_Data\_Export\_Requests\_List\_Table::column\_next\_steps()](https://developer.wordpress.org/reference/classes/wp_privacy_data_export_requests_list_table/column_next_steps/) `wp-admin/includes/class-wp-privacy-data-export-requests-list-table.php` | Displays the next steps column. |
| [WP\_Recovery\_Mode::get\_email\_rate\_limit()](https://developer.wordpress.org/reference/classes/wp_recovery_mode/get_email_rate_limit/) `wp-includes/class-wp-recovery-mode.php` | Gets the rate limit between sending new recovery mode email links. |
| [WP\_Recovery\_Mode::get\_link\_ttl()](https://developer.wordpress.org/reference/classes/wp_recovery_mode/get_link_ttl/) `wp-includes/class-wp-recovery-mode.php` | Gets the number of seconds the recovery mode link is valid for. |
| [wp\_is\_jsonp\_request()](https://developer.wordpress.org/reference/functions/wp_is_jsonp_request/) `wp-includes/load.php` | Checks whether current request is a JSONP request, or is expecting a JSONP response. |
| [is\_protected\_endpoint()](https://developer.wordpress.org/reference/functions/is_protected_endpoint/) `wp-includes/load.php` | Determines whether we are currently on an endpoint that should be protected against WSODs. |
| [is\_protected\_ajax\_action()](https://developer.wordpress.org/reference/functions/is_protected_ajax_action/) `wp-includes/load.php` | Determines whether we are currently handling an Ajax action that should be protected against WSODs. |
| [get\_feed\_build\_date()](https://developer.wordpress.org/reference/functions/get_feed_build_date/) `wp-includes/feed.php` | Gets the UTC time of the most recently modified post from [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). |
| [WP\_Recovery\_Mode\_Email\_Service::send\_recovery\_mode\_email()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_email_service/send_recovery_mode_email/) `wp-includes/class-wp-recovery-mode-email-service.php` | Sends the Recovery Mode email to the site admin email address. |
| [WP\_Recovery\_Mode\_Cookie\_Service::set\_cookie()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_cookie_service/set_cookie/) `wp-includes/class-wp-recovery-mode-cookie-service.php` | Sets the recovery mode cookie. |
| [WP\_Recovery\_Mode\_Cookie\_Service::validate\_cookie()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_cookie_service/validate_cookie/) `wp-includes/class-wp-recovery-mode-cookie-service.php` | Validates the recovery mode cookie. |
| [WP\_Recovery\_Mode\_Link\_Service::get\_recovery\_mode\_begin\_url()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_link_service/get_recovery_mode_begin_url/) `wp-includes/class-wp-recovery-mode-link-service.php` | Gets a URL to begin recovery mode. |
| [wp\_is\_fatal\_error\_handler\_enabled()](https://developer.wordpress.org/reference/functions/wp_is_fatal_error_handler_enabled/) `wp-includes/error-protection.php` | Checks whether the fatal error handler is enabled. |
| [WP\_Fatal\_Error\_Handler::display\_default\_error\_template()](https://developer.wordpress.org/reference/classes/wp_fatal_error_handler/display_default_error_template/) `wp-includes/class-wp-fatal-error-handler.php` | Displays the default PHP error template. |
| [WP\_Fatal\_Error\_Handler::should\_handle\_error()](https://developer.wordpress.org/reference/classes/wp_fatal_error_handler/should_handle_error/) `wp-includes/class-wp-fatal-error-handler.php` | Determines whether we are dealing with an error that WordPress should handle in order to protect the admin backend against WSODs. |
| [wp\_filter\_oembed\_iframe\_title\_attribute()](https://developer.wordpress.org/reference/functions/wp_filter_oembed_iframe_title_attribute/) `wp-includes/embed.php` | Filters the given oEmbed HTML to make sure iframes have a title attribute. |
| [WP\_Query::generate\_postdata()](https://developer.wordpress.org/reference/classes/wp_query/generate_postdata/) `wp-includes/class-wp-query.php` | Generates post data. |
| [wp\_trusted\_keys()](https://developer.wordpress.org/reference/functions/wp_trusted_keys/) `wp-admin/includes/file.php` | Retrieves the list of signing keys trusted by WordPress. |
| [WP\_Site\_Health::get\_test\_rest\_availability()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_rest_availability/) `wp-admin/includes/class-wp-site-health.php` | Tests if the REST API is accessible. |
| [WP\_Site\_Health::get\_tests()](https://developer.wordpress.org/reference/classes/wp_site_health/get_tests/) `wp-admin/includes/class-wp-site-health.php` | Returns a set of tests that belong to the site status page. |
| [WP\_Site\_Health::can\_perform\_loopback()](https://developer.wordpress.org/reference/classes/wp_site_health/can_perform_loopback/) `wp-admin/includes/class-wp-site-health.php` | Runs a loopback test on the site. |
| [WP\_Site\_Health::get\_test\_php\_extensions()](https://developer.wordpress.org/reference/classes/wp_site_health/get_test_php_extensions/) `wp-admin/includes/class-wp-site-health.php` | Tests if required PHP modules are installed on the host. |
| [WP\_Posts\_List\_Table::formats\_dropdown()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/formats_dropdown/) `wp-admin/includes/class-wp-posts-list-table.php` | Displays a formats drop-down for filtering items. |
| [WP\_Site\_Health\_Auto\_Updates::test\_accepts\_dev\_updates()](https://developer.wordpress.org/reference/classes/wp_site_health_auto_updates/test_accepts_dev_updates/) `wp-admin/includes/class-wp-site-health-auto-updates.php` | Checks if the install is using a development branch and can use nightly packages. |
| [WP\_Site\_Health\_Auto\_Updates::test\_accepts\_minor\_updates()](https://developer.wordpress.org/reference/classes/wp_site_health_auto_updates/test_accepts_minor_updates/) `wp-admin/includes/class-wp-site-health-auto-updates.php` | Checks if the site supports automatic minor updates. |
| [WP\_Site\_Health\_Auto\_Updates::test\_filters\_automatic\_updater\_disabled()](https://developer.wordpress.org/reference/classes/wp_site_health_auto_updates/test_filters_automatic_updater_disabled/) `wp-admin/includes/class-wp-site-health-auto-updates.php` | Checks if automatic updates are disabled by a filter. |
| [WP\_Site\_Health\_Auto\_Updates::test\_vcs\_abspath()](https://developer.wordpress.org/reference/classes/wp_site_health_auto_updates/test_vcs_abspath/) `wp-admin/includes/class-wp-site-health-auto-updates.php` | Checks if WordPress is controlled by a VCS (Git, Subversion etc). |
| [wp\_get\_direct\_php\_update\_url()](https://developer.wordpress.org/reference/functions/wp_get_direct_php_update_url/) `wp-includes/functions.php` | Gets the URL for directly updating the PHP version the site is running on. |
| [wp\_targeted\_link\_rel\_callback()](https://developer.wordpress.org/reference/functions/wp_targeted_link_rel_callback/) `wp-includes/formatting.php` | Callback to add `rel="noopener"` string to HTML A element. |
| [wp\_using\_themes()](https://developer.wordpress.org/reference/functions/wp_using_themes/) `wp-includes/load.php` | Determines whether the current request should use themes. |
| [wp\_get\_ready\_cron\_jobs()](https://developer.wordpress.org/reference/functions/wp_get_ready_cron_jobs/) `wp-includes/cron.php` | Retrieves cron jobs ready to be run. |
| [wp\_get\_scheduled\_event()](https://developer.wordpress.org/reference/functions/wp_get_scheduled_event/) `wp-includes/cron.php` | Retrieves a scheduled event. |
| [wp\_initialize\_site()](https://developer.wordpress.org/reference/functions/wp_initialize_site/) `wp-includes/ms-site.php` | Runs the initialization routine for a given site. |
| [wp\_uninitialize\_site()](https://developer.wordpress.org/reference/functions/wp_uninitialize_site/) `wp-includes/ms-site.php` | Runs the uninitialization routine for a given site. |
| [wp\_is\_site\_initialized()](https://developer.wordpress.org/reference/functions/wp_is_site_initialized/) `wp-includes/ms-site.php` | Checks whether a site is initialized. |
| [wp\_prepare\_site\_data()](https://developer.wordpress.org/reference/functions/wp_prepare_site_data/) `wp-includes/ms-site.php` | Prepares site data for insertion or update in the database. |
| [wp\_get\_update\_php\_url()](https://developer.wordpress.org/reference/functions/wp_get_update_php_url/) `wp-includes/functions.php` | Gets the URL to learn more about updating the PHP version the site is running on. |
| [is\_avatar\_comment\_type()](https://developer.wordpress.org/reference/functions/is_avatar_comment_type/) `wp-includes/link-template.php` | Check if this comment type allows avatars to be retrieved. |
| [wp\_check\_php\_version()](https://developer.wordpress.org/reference/functions/wp_check_php_version/) `wp-admin/includes/misc.php` | Checks if the user needs to update PHP. |
| [populate\_network\_meta()](https://developer.wordpress.org/reference/functions/populate_network_meta/) `wp-admin/includes/schema.php` | Creates WordPress network meta and sets the default values. |
| [populate\_site\_meta()](https://developer.wordpress.org/reference/functions/populate_site_meta/) `wp-admin/includes/schema.php` | Creates WordPress site meta and sets the default values. |
| [wp\_kses\_uri\_attributes()](https://developer.wordpress.org/reference/functions/wp_kses_uri_attributes/) `wp-includes/kses.php` | Returns an array of HTML attribute names whose value contains a URL. |
| [WP\_REST\_Themes\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_themes_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-themes-controller.php` | Prepares a single theme output for response. |
| [WP\_REST\_Themes\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_themes_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-themes-controller.php` | Retrieves the search params for the themes collection. |
| [WP\_REST\_Autosaves\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_autosaves_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-autosaves-controller.php` | Prepares the revision for the REST response. |
| [WP\_REST\_Revisions\_Controller::prepare\_items\_query()](https://developer.wordpress.org/reference/classes/wp_rest_revisions_controller/prepare_items_query/) `wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php` | Determines the allowed query\_vars for a get\_items() response and prepares them for [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). |
| [WP\_REST\_Post\_Search\_Handler::search\_items()](https://developer.wordpress.org/reference/classes/wp_rest_post_search_handler/search_items/) `wp-includes/rest-api/search/class-wp-rest-post-search-handler.php` | Searches posts for a given search request. |
| [wp\_get\_script\_polyfill()](https://developer.wordpress.org/reference/functions/wp_get_script_polyfill/) `wp-includes/script-loader.php` | Returns contents of an inline script used in appending polyfill scripts for browsers which fail the provided tests. The provided array is a mapping from a condition to verify feature support to its polyfill script handle. |
| [wp\_tinymce\_inline\_scripts()](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/) `wp-includes/script-loader.php` | Adds inline scripts required for the TinyMCE in the block editor. |
| [get\_oembed\_response\_data\_for\_url()](https://developer.wordpress.org/reference/functions/get_oembed_response_data_for_url/) `wp-includes/embed.php` | Retrieves the oEmbed response data for a given URL. |
| [wp\_get\_code\_editor\_settings()](https://developer.wordpress.org/reference/functions/wp_get_code_editor_settings/) `wp-includes/general-template.php` | Generates and returns code editor settings. |
| [rest\_preload\_api\_request()](https://developer.wordpress.org/reference/functions/rest_preload_api_request/) `wp-includes/rest-api.php` | Append result of internal request to REST API for purpose of preloading data to be attached to a page. |
| [WP\_Block\_Type::set\_props()](https://developer.wordpress.org/reference/classes/wp_block_type/set_props/) `wp-includes/class-wp-block-type.php` | Sets block type properties. |
| [parse\_blocks()](https://developer.wordpress.org/reference/functions/parse_blocks/) `wp-includes/blocks.php` | Parses blocks out of a content string. |
| [excerpt\_remove\_blocks()](https://developer.wordpress.org/reference/functions/excerpt_remove_blocks/) `wp-includes/blocks.php` | Parses blocks out of a content string, and renders those appropriate for the excerpt. |
| [render\_block()](https://developer.wordpress.org/reference/functions/render_block/) `wp-includes/blocks.php` | Renders a single block into a HTML string. |
| [the\_block\_editor\_meta\_boxes()](https://developer.wordpress.org/reference/functions/the_block_editor_meta_boxes/) `wp-admin/includes/post.php` | Renders the meta boxes forms. |
| [use\_block\_editor\_for\_post\_type()](https://developer.wordpress.org/reference/functions/use_block_editor_for_post_type/) `wp-includes/post.php` | Returns whether a post type is compatible with the block editor. |
| [get\_block\_categories()](https://developer.wordpress.org/reference/functions/get_block_categories/) `wp-includes/block-editor.php` | Returns all the categories for block types that will be shown in the block editor. |
| [use\_block\_editor\_for\_post()](https://developer.wordpress.org/reference/functions/use_block_editor_for_post/) `wp-includes/post.php` | Returns whether the post can be edited in the block editor. |
| [get\_object\_subtype()](https://developer.wordpress.org/reference/functions/get_object_subtype/) `wp-includes/meta.php` | Returns the object subtype for a given object ID of a specific type. |
| [wp\_comments\_personal\_data\_eraser()](https://developer.wordpress.org/reference/functions/wp_comments_personal_data_eraser/) `wp-includes/comment.php` | Erases personal data associated with an email address from the comments table. |
| [wp\_privacy\_delete\_old\_export\_files()](https://developer.wordpress.org/reference/functions/wp_privacy_delete_old_export_files/) `wp-includes/functions.php` | Cleans up export files older than three days old. |
| [wp\_privacy\_exports\_dir()](https://developer.wordpress.org/reference/functions/wp_privacy_exports_dir/) `wp-includes/functions.php` | Returns the directory used to store personal data export files. |
| [wp\_privacy\_exports\_url()](https://developer.wordpress.org/reference/functions/wp_privacy_exports_url/) `wp-includes/functions.php` | Returns the URL of the directory used to store personal data export files. |
| [wp\_privacy\_anonymize\_data()](https://developer.wordpress.org/reference/functions/wp_privacy_anonymize_data/) `wp-includes/functions.php` | Returns uniform “anonymous” data by type. |
| [wp\_validate\_user\_request\_key()](https://developer.wordpress.org/reference/functions/wp_validate_user_request_key/) `wp-includes/user.php` | Validates a user request by comparing the key with the request’s key. |
| [\_wp\_privacy\_send\_request\_confirmation\_notification()](https://developer.wordpress.org/reference/functions/_wp_privacy_send_request_confirmation_notification/) `wp-includes/user.php` | Notifies the site administrator via email when a request is confirmed. |
| [\_wp\_privacy\_send\_erasure\_fulfillment\_notification()](https://developer.wordpress.org/reference/functions/_wp_privacy_send_erasure_fulfillment_notification/) `wp-includes/user.php` | Notifies the user when their erasure request is fulfilled. |
| [\_wp\_privacy\_account\_request\_confirmed\_message()](https://developer.wordpress.org/reference/functions/_wp_privacy_account_request_confirmed_message/) `wp-includes/user.php` | Returns request confirmation message HTML. |
| [wp\_user\_request\_action\_description()](https://developer.wordpress.org/reference/functions/wp_user_request_action_description/) `wp-includes/user.php` | Gets action description from the name and return a string. |
| [wp\_send\_user\_request()](https://developer.wordpress.org/reference/functions/wp_send_user_request/) `wp-includes/user.php` | Send a confirmation request email to confirm an action. |
| [wp\_user\_personal\_data\_exporter()](https://developer.wordpress.org/reference/functions/wp_user_personal_data_exporter/) `wp-includes/user.php` | Finds and exports personal data associated with an email address from the user and user\_meta table. |
| [get\_the\_privacy\_policy\_link()](https://developer.wordpress.org/reference/functions/get_the_privacy_policy_link/) `wp-includes/link-template.php` | Returns the privacy policy link with formatting, when applicable. |
| [get\_privacy\_policy\_url()](https://developer.wordpress.org/reference/functions/get_privacy_policy_url/) `wp-includes/link-template.php` | Retrieves the URL to the privacy policy page. |
| [wp\_privacy\_process\_personal\_data\_export\_page()](https://developer.wordpress.org/reference/functions/wp_privacy_process_personal_data_export_page/) `wp-admin/includes/privacy-tools.php` | Intercept personal data exporter page Ajax responses in order to assemble the personal data export file. |
| [wp\_privacy\_send\_personal\_data\_export\_email()](https://developer.wordpress.org/reference/functions/wp_privacy_send_personal_data_export_email/) `wp-admin/includes/privacy-tools.php` | Send an email to the user with a link to the personal data export file |
| [wp\_privacy\_process\_personal\_data\_erasure\_page()](https://developer.wordpress.org/reference/functions/wp_privacy_process_personal_data_erasure_page/) `wp-admin/includes/privacy-tools.php` | Mark erasure requests as completed after processing is finished. |
| [\_wp\_personal\_data\_cleanup\_requests()](https://developer.wordpress.org/reference/functions/_wp_personal_data_cleanup_requests/) `wp-admin/includes/privacy-tools.php` | Cleans up failed and expired requests before displaying the list table. |
| [wp\_ajax\_wp\_privacy\_export\_personal\_data()](https://developer.wordpress.org/reference/functions/wp_ajax_wp_privacy_export_personal_data/) `wp-admin/includes/ajax-actions.php` | Handles exporting a user’s personal data via AJAX. |
| [wp\_ajax\_wp\_privacy\_erase\_personal\_data()](https://developer.wordpress.org/reference/functions/wp_ajax_wp_privacy_erase_personal_data/) `wp-admin/includes/ajax-actions.php` | Handles erasing personal data via AJAX. |
| [WP\_Network::get\_main\_site\_id()](https://developer.wordpress.org/reference/classes/wp_network/get_main_site_id/) `wp-includes/class-wp-network.php` | Returns the main site ID for the network. |
| [wp\_unschedule\_hook()](https://developer.wordpress.org/reference/functions/wp_unschedule_hook/) `wp-includes/cron.php` | Unschedules all events attached to the hook. |
| [WP\_Customize\_Manager::handle\_load\_themes\_request()](https://developer.wordpress.org/reference/classes/wp_customize_manager/handle_load_themes_request/) `wp-includes/class-wp-customize-manager.php` | Loads themes into the theme browsing/installation UI. |
| [WP\_Customize\_Manager::trash\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/trash_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Trashes or deletes a changeset post. |
| [WP\_Customize\_Manager::branching()](https://developer.wordpress.org/reference/classes/wp_customize_manager/branching/) `wp-includes/class-wp-customize-manager.php` | Whether the changeset branching is allowed. |
| [get\_the\_post\_type\_description()](https://developer.wordpress.org/reference/functions/get_the_post_type_description/) `wp-includes/general-template.php` | Retrieves the description for a post type archive. |
| [wp\_get\_nav\_menu\_name()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_name/) `wp-includes/nav-menu.php` | Returns the name of a navigation menu. |
| [wp\_site\_admin\_email\_change\_notification()](https://developer.wordpress.org/reference/functions/wp_site_admin_email_change_notification/) `wp-includes/functions.php` | Sends an email to the old site admin email address when the site admin email address changes. |
| [WP\_Widget\_Media\_Gallery::get\_instance\_schema()](https://developer.wordpress.org/reference/classes/wp_widget_media_gallery/get_instance_schema/) `wp-includes/widgets/class-wp-widget-media-gallery.php` | Get schema for properties of a widget instance (item). |
| [WP\_Widget\_Custom\_HTML::widget()](https://developer.wordpress.org/reference/classes/wp_widget_custom_html/widget/) `wp-includes/widgets/class-wp-widget-custom-html.php` | Outputs the content for the current Custom HTML widget instance. |
| [update\_network\_option\_new\_admin\_email()](https://developer.wordpress.org/reference/functions/update_network_option_new_admin_email/) `wp-includes/ms-functions.php` | Sends a confirmation request email when a change of network admin email address is attempted. |
| [wp\_network\_admin\_email\_change\_notification()](https://developer.wordpress.org/reference/functions/wp_network_admin_email_change_notification/) `wp-includes/ms-functions.php` | Sends an email to the old network admin email address when the network admin email address changes. |
| [wp\_admin\_headers()](https://developer.wordpress.org/reference/functions/wp_admin_headers/) `wp-includes/functions.php` | Sends a referrer policy header so referrers are not sent externally from administration screens. |
| [wp\_get\_plugin\_file\_editable\_extensions()](https://developer.wordpress.org/reference/functions/wp_get_plugin_file_editable_extensions/) `wp-admin/includes/file.php` | Gets the list of file extensions that are editable in plugins. |
| [wp\_get\_theme\_file\_editable\_extensions()](https://developer.wordpress.org/reference/functions/wp_get_theme_file_editable_extensions/) `wp-admin/includes/file.php` | Gets the list of file extensions that are editable for a given theme. |
| [wp\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_edit_theme_plugin_file/) `wp-admin/includes/file.php` | Attempts to edit a file for a theme or plugin. |
| [wp\_doing\_cron()](https://developer.wordpress.org/reference/functions/wp_doing_cron/) `wp-includes/load.php` | Determines whether the current request is a WordPress cron request. |
| [wp\_is\_file\_mod\_allowed()](https://developer.wordpress.org/reference/functions/wp_is_file_mod_allowed/) `wp-includes/load.php` | Determines whether file modifications are allowed. |
| [WP\_oEmbed\_Controller::get\_proxy\_item()](https://developer.wordpress.org/reference/classes/wp_oembed_controller/get_proxy_item/) `wp-includes/class-wp-oembed-controller.php` | Callback for the proxy API endpoint. |
| [WP\_Widget\_Media\_Video::enqueue\_preview\_scripts()](https://developer.wordpress.org/reference/classes/wp_widget_media_video/enqueue_preview_scripts/) `wp-includes/widgets/class-wp-widget-media-video.php` | Enqueue preview scripts. |
| [WP\_Widget\_Media\_Audio::enqueue\_preview\_scripts()](https://developer.wordpress.org/reference/classes/wp_widget_media_audio/enqueue_preview_scripts/) `wp-includes/widgets/class-wp-widget-media-audio.php` | Enqueue preview scripts. |
| [WP\_Widget\_Media::get\_instance\_schema()](https://developer.wordpress.org/reference/classes/wp_widget_media/get_instance_schema/) `wp-includes/widgets/class-wp-widget-media.php` | Get schema for properties of a widget instance (item). |
| [WP\_Widget\_Media::widget()](https://developer.wordpress.org/reference/classes/wp_widget_media/widget/) `wp-includes/widgets/class-wp-widget-media.php` | Displays the widget on the front-end. |
| [rest\_get\_avatar\_sizes()](https://developer.wordpress.org/reference/functions/rest_get_avatar_sizes/) `wp-includes/rest-api.php` | Retrieves the pixel sizes for avatars. |
| [create\_initial\_rest\_routes()](https://developer.wordpress.org/reference/functions/create_initial_rest_routes/) `wp-includes/rest-api.php` | Registers default REST API routes. |
| [wp\_doing\_ajax()](https://developer.wordpress.org/reference/functions/wp_doing_ajax/) `wp-includes/load.php` | Determines whether the current request is a WordPress Ajax request. |
| [WP\_Customize\_Manager::get\_allowed\_urls()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_allowed_urls/) `wp-includes/class-wp-customize-manager.php` | Gets URLs allowed to be previewed. |
| [WP\_Customize\_Manager::save\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Saves the post for the loaded changeset. |
| [get\_theme\_starter\_content()](https://developer.wordpress.org/reference/functions/get_theme_starter_content/) `wp-includes/theme.php` | Expands a theme’s starter content configuration using core-provided data. |
| [wp\_update\_custom\_css\_post()](https://developer.wordpress.org/reference/functions/wp_update_custom_css_post/) `wp-includes/theme.php` | Updates the `custom_css` post for a given theme. |
| [wp\_get\_custom\_css()](https://developer.wordpress.org/reference/functions/wp_get_custom_css/) `wp-includes/theme.php` | Fetches the saved Custom CSS content for rendering. |
| [get\_header\_video\_url()](https://developer.wordpress.org/reference/functions/get_header_video_url/) `wp-includes/theme.php` | Retrieves header video URL for custom header. |
| [get\_header\_video\_settings()](https://developer.wordpress.org/reference/functions/get_header_video_settings/) `wp-includes/theme.php` | Retrieves header video settings. |
| [is\_header\_video\_active()](https://developer.wordpress.org/reference/functions/is_header_video_active/) `wp-includes/theme.php` | Checks whether the custom header video is eligible to show on the current page. |
| [WP\_REST\_Users\_Controller::check\_username()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/check_username/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Check a username for the REST API. |
| [WP\_REST\_Users\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Retrieves the query params for collections. |
| [WP\_REST\_Users\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Prepares a single user output for response. |
| [WP\_REST\_Users\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Prepares a single user for creation or update. |
| [WP\_REST\_Users\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_users_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php` | Retrieves all users. |
| [WP\_REST\_Revisions\_Controller::prepare\_excerpt\_response()](https://developer.wordpress.org/reference/classes/wp_rest_revisions_controller/prepare_excerpt_response/) `wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php` | Checks the post excerpt and prepare it for single post output. |
| [WP\_REST\_Revisions\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_revisions_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php` | Prepares the revision for the REST response. |
| [WP\_REST\_Revisions\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_revisions_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php` | Gets a collection of revisions. |
| [WP\_REST\_Attachments\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Prepares a single attachment output for response. |
| [WP\_REST\_Attachments\_Controller::create\_item\_permissions\_check()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/create_item_permissions_check/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Checks if a given request has access to create an attachment. |
| [WP\_REST\_Post\_Statuses\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_post_statuses_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-post-statuses-controller.php` | Prepares a post status object for serialization. |
| [WP\_REST\_Settings\_Controller::get\_item()](https://developer.wordpress.org/reference/classes/wp_rest_settings_controller/get_item/) `wp-includes/rest-api/endpoints/class-wp-rest-settings-controller.php` | Retrieves the settings. |
| [WP\_REST\_Settings\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_settings_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-settings-controller.php` | Updates settings for the settings object. |
| [WP\_REST\_Terms\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Prepares a single term output for response. |
| [WP\_REST\_Terms\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Retrieves the query params for collections. |
| [WP\_REST\_Terms\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Prepares a single term for create or update. |
| [WP\_REST\_Terms\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_terms_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php` | Retrieves terms associated with a taxonomy. |
| [WP\_REST\_Posts\_Controller::get\_item\_schema()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_item_schema/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves the post’s schema, conforming to JSON Schema. |
| [WP\_REST\_Posts\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves the query params for the posts collection. |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post output for response. |
| [WP\_REST\_Posts\_Controller::prepare\_items\_query()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_items_query/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Determines the allowed query\_vars for a get\_items() response and prepares them for [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post for create or update. |
| [WP\_REST\_Posts\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Deletes a single post. |
| [WP\_REST\_Posts\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves a collection of posts. |
| [WP\_REST\_Taxonomies\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_taxonomies_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-taxonomies-controller.php` | Prepares a taxonomy object for serialization. |
| [WP\_REST\_Post\_Types\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_post_types_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-post-types-controller.php` | Prepares a post type object for serialization. |
| [WP\_REST\_Comments\_Controller::get\_collection\_params()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/get_collection_params/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Retrieves the query params for collections. |
| [WP\_REST\_Comments\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Prepares a single comment output for response. |
| [WP\_REST\_Comments\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Prepares a single comment to be inserted into the database. |
| [WP\_REST\_Comments\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Deletes a comment. |
| [WP\_REST\_Comments\_Controller::create\_item\_permissions\_check()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/create_item_permissions_check/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Checks if a given request has access to create a comment. |
| [WP\_REST\_Comments\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Creates a comment. |
| [WP\_REST\_Comments\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Retrieves a list of comment items. |
| [WP\_Taxonomy::set\_props()](https://developer.wordpress.org/reference/classes/wp_taxonomy/set_props/) `wp-includes/class-wp-taxonomy.php` | Sets taxonomy properties. |
| [sanitize\_textarea\_field()](https://developer.wordpress.org/reference/functions/sanitize_textarea_field/) `wp-includes/formatting.php` | Sanitizes a multiline string from user input or from the database. |
| [wp\_check\_comment\_flood()](https://developer.wordpress.org/reference/functions/wp_check_comment_flood/) `wp-includes/comment.php` | Checks whether comment flooding is occurring. |
| [get\_parent\_theme\_file\_path()](https://developer.wordpress.org/reference/functions/get_parent_theme_file_path/) `wp-includes/link-template.php` | Retrieves the path of a file in the parent theme. |
| [get\_parent\_theme\_file\_uri()](https://developer.wordpress.org/reference/functions/get_parent_theme_file_uri/) `wp-includes/link-template.php` | Retrieves the URL of a file in the parent theme. |
| [get\_theme\_file\_path()](https://developer.wordpress.org/reference/functions/get_theme_file_path/) `wp-includes/link-template.php` | Retrieves the path of a file in the theme. |
| [get\_theme\_file\_uri()](https://developer.wordpress.org/reference/functions/get_theme_file_uri/) `wp-includes/link-template.php` | Retrieves the URL of a file in the theme. |
| [WP\_Customize\_Custom\_CSS\_Setting::value()](https://developer.wordpress.org/reference/classes/wp_customize_custom_css_setting/value/) `wp-includes/customize/class-wp-customize-custom-css-setting.php` | Fetch the value of the setting. Will return the previewed value when `preview()` is called. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::get\_original\_title()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/get_original_title/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Get original title. |
| [WP\_Term\_Query::get\_terms()](https://developer.wordpress.org/reference/classes/wp_term_query/get_terms/) `wp-includes/class-wp-term-query.php` | Retrieves the query results. |
| [WP\_Term\_Query::parse\_orderby()](https://developer.wordpress.org/reference/classes/wp_term_query/parse_orderby/) `wp-includes/class-wp-term-query.php` | Parse and sanitize ‘orderby’ keys passed to the term query. |
| [WP\_Term\_Query::parse\_query()](https://developer.wordpress.org/reference/classes/wp_term_query/parse_query/) `wp-includes/class-wp-term-query.php` | Parse arguments passed to the term query with default query parameters. |
| [WP\_Customize\_Manager::validate\_setting\_values()](https://developer.wordpress.org/reference/classes/wp_customize_manager/validate_setting_values/) `wp-includes/class-wp-customize-manager.php` | Validates setting values. |
| [WP\_Customize\_Setting::validate()](https://developer.wordpress.org/reference/classes/wp_customize_setting/validate/) `wp-includes/class-wp-customize-setting.php` | Validates an input. |
| [WP\_Network\_Query::set\_found\_networks()](https://developer.wordpress.org/reference/classes/wp_network_query/set_found_networks/) `wp-includes/class-wp-network-query.php` | Populates found\_networks and max\_num\_pages properties for the current query if the limit clause was used. |
| [wp\_resource\_hints()](https://developer.wordpress.org/reference/functions/wp_resource_hints/) `wp-includes/general-template.php` | Prints resource hints to browsers for pre-fetching, pre-rendering and pre-connecting to websites. |
| [get\_network()](https://developer.wordpress.org/reference/functions/get_network/) `wp-includes/ms-network.php` | Retrieves network data given a network ID or network object. |
| [get\_site()](https://developer.wordpress.org/reference/functions/get_site/) `wp-includes/ms-site.php` | Retrieves site data given a site ID or site object. |
| [WP\_Post\_Type::set\_props()](https://developer.wordpress.org/reference/classes/wp_post_type/set_props/) `wp-includes/class-wp-post-type.php` | Sets post type properties. |
| [WP\_Site::get\_details()](https://developer.wordpress.org/reference/classes/wp_site/get_details/) `wp-includes/class-wp-site.php` | Retrieves the details for this site. |
| [WP\_Comment\_Query::set\_found\_comments()](https://developer.wordpress.org/reference/classes/wp_comment_query/set_found_comments/) `wp-includes/class-wp-comment-query.php` | Populates found\_comments and max\_num\_pages properties for the current query if the limit clause was used. |
| [the\_post\_thumbnail\_caption()](https://developer.wordpress.org/reference/functions/the_post_thumbnail_caption/) `wp-includes/post-thumbnail-template.php` | Displays the post thumbnail caption. |
| [wp\_raise\_memory\_limit()](https://developer.wordpress.org/reference/functions/wp_raise_memory_limit/) `wp-includes/functions.php` | Attempts to raise the PHP memory limit for memory intensive processes. |
| [\_deprecated\_hook()](https://developer.wordpress.org/reference/functions/_deprecated_hook/) `wp-includes/functions.php` | Marks a deprecated action or filter hook as deprecated and throws a notice. |
| [wp\_get\_ext\_types()](https://developer.wordpress.org/reference/functions/wp_get_ext_types/) `wp-includes/functions.php` | Retrieves the list of common file extensions and their types. |
| [wp\_get\_canonical\_url()](https://developer.wordpress.org/reference/functions/wp_get_canonical_url/) `wp-includes/link-template.php` | Returns the canonical URL for a post. |
| [wp\_get\_attachment\_caption()](https://developer.wordpress.org/reference/functions/wp_get_attachment_caption/) `wp-includes/post.php` | Retrieves the caption for an attachment. |
| [WP\_Site\_Query::get\_site\_ids()](https://developer.wordpress.org/reference/classes/wp_site_query/get_site_ids/) `wp-includes/class-wp-site-query.php` | Used internally to get a list of site IDs matching the query vars. |
| [WP\_Site\_Query::set\_found\_sites()](https://developer.wordpress.org/reference/classes/wp_site_query/set_found_sites/) `wp-includes/class-wp-site-query.php` | Populates found\_sites and max\_num\_pages properties for the current query if the limit clause was used. |
| [WP\_Posts\_List\_Table::categories\_dropdown()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/categories_dropdown/) `wp-admin/includes/class-wp-posts-list-table.php` | Displays a categories drop-down for filtering on the Posts list table. |
| [network\_edit\_site\_nav()](https://developer.wordpress.org/reference/functions/network_edit_site_nav/) `wp-admin/includes/ms.php` | Outputs the HTML for a network’s “Edit Site” tabular interface. |
| [rest\_get\_server()](https://developer.wordpress.org/reference/functions/rest_get_server/) `wp-includes/rest-api.php` | Retrieves the current REST server instance. |
| [the\_embed\_site\_title()](https://developer.wordpress.org/reference/functions/the_embed_site_title/) `wp-includes/embed.php` | Prints the necessary markup for the site title in an embed template. |
| [WP\_Customize\_Manager::get\_nonces()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_nonces/) `wp-includes/class-wp-customize-manager.php` | Gets nonces for the Customizer. |
| [WP\_Customize\_Manager::get\_previewable\_devices()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_previewable_devices/) `wp-includes/class-wp-customize-manager.php` | Returns a list of devices to allow previewing. |
| [WP\_Image\_Editor\_Imagick::thumbnail\_image()](https://developer.wordpress.org/reference/classes/wp_image_editor_imagick/thumbnail_image/) `wp-includes/class-wp-image-editor-imagick.php` | Efficiently resize the current image |
| [get\_custom\_logo()](https://developer.wordpress.org/reference/functions/get_custom_logo/) `wp-includes/general-template.php` | Returns a custom logo, linked to home unless the theme supports removing the link on the home page. |
| [WP\_REST\_Request::from\_url()](https://developer.wordpress.org/reference/classes/wp_rest_request/from_url/) `wp-includes/rest-api/class-wp-rest-request.php` | Retrieves a [WP\_REST\_Request](https://developer.wordpress.org/reference/classes/wp_rest_request/) object from a full URL. |
| [WP\_REST\_Response::get\_curies()](https://developer.wordpress.org/reference/classes/wp_rest_response/get_curies/) `wp-includes/rest-api/class-wp-rest-response.php` | Retrieves the CURIEs (compact URIs) used for relations. |
| [\_wp\_get\_current\_user()](https://developer.wordpress.org/reference/functions/_wp_get_current_user/) `wp-includes/user.php` | Retrieves the current user object. |
| [wp\_authenticate\_email\_password()](https://developer.wordpress.org/reference/functions/wp_authenticate_email_password/) `wp-includes/user.php` | Authenticates a user using the email and password. |
| [wp\_get\_comment\_fields\_max\_lengths()](https://developer.wordpress.org/reference/functions/wp_get_comment_fields_max_lengths/) `wp-includes/comment.php` | Retrieves the maximum character lengths for the comment form fields. |
| [WP\_Customize\_Partial::render()](https://developer.wordpress.org/reference/classes/wp_customize_partial/render/) `wp-includes/customize/class-wp-customize-partial.php` | Renders the template partial involving the associated settings. |
| [WP\_Customize\_Selective\_Refresh::add\_dynamic\_partials()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/add_dynamic_partials/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Registers dynamically-created partials. |
| [WP\_Customize\_Selective\_Refresh::handle\_render\_partials\_request()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/handle_render_partials_request/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Handles the Ajax request to return the rendered partials for the requested placements. |
| [WP\_Customize\_Selective\_Refresh::add\_partial()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/add_partial/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Adds a partial. |
| [WP\_Network::get\_by\_path()](https://developer.wordpress.org/reference/classes/wp_network/get_by_path/) `wp-includes/class-wp-network.php` | Retrieves the closest matching network for a domain and path. |
| [get\_rest\_url()](https://developer.wordpress.org/reference/functions/get_rest_url/) `wp-includes/rest-api.php` | Retrieves the URL to a REST endpoint on a site. |
| [rest\_get\_url\_prefix()](https://developer.wordpress.org/reference/functions/rest_get_url_prefix/) `wp-includes/rest-api.php` | Retrieves the URL prefix for any API resource. |
| [the\_excerpt\_embed()](https://developer.wordpress.org/reference/functions/the_excerpt_embed/) `wp-includes/embed.php` | Displays the post excerpt for the embed template. |
| [wp\_oembed\_add\_discovery\_links()](https://developer.wordpress.org/reference/functions/wp_oembed_add_discovery_links/) `wp-includes/embed.php` | Adds oEmbed discovery links in the head element of the website. |
| [get\_post\_embed\_url()](https://developer.wordpress.org/reference/functions/get_post_embed_url/) `wp-includes/embed.php` | Retrieves the URL to embed a specific post in an iframe. |
| [get\_oembed\_endpoint\_url()](https://developer.wordpress.org/reference/functions/get_oembed_endpoint_url/) `wp-includes/embed.php` | Retrieves the oEmbed endpoint URL for a given permalink. |
| [get\_post\_embed\_html()](https://developer.wordpress.org/reference/functions/get_post_embed_html/) `wp-includes/embed.php` | Retrieves the embed code for a specific post. |
| [get\_oembed\_response\_data()](https://developer.wordpress.org/reference/functions/get_oembed_response_data/) `wp-includes/embed.php` | Retrieves the oEmbed response data for a given post. |
| [get\_header\_image\_tag()](https://developer.wordpress.org/reference/functions/get_header_image_tag/) `wp-includes/theme.php` | Creates image tag markup for a custom header image. |
| [get\_the\_author\_posts\_link()](https://developer.wordpress.org/reference/functions/get_the_author_posts_link/) `wp-includes/author-template.php` | Retrieves an HTML link to the author page of the current post’s author. |
| [wp\_get\_document\_title()](https://developer.wordpress.org/reference/functions/wp_get_document_title/) `wp-includes/general-template.php` | Returns document title for the current page. |
| [WP\_REST\_Request::get\_parameter\_order()](https://developer.wordpress.org/reference/classes/wp_rest_request/get_parameter_order/) `wp-includes/rest-api/class-wp-rest-request.php` | Retrieves the parameter priority order. |
| [WP\_REST\_Server::get\_data\_for\_routes()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_data_for_routes/) `wp-includes/rest-api/class-wp-rest-server.php` | Retrieves the publicly-visible data for routes. |
| [WP\_REST\_Server::dispatch()](https://developer.wordpress.org/reference/classes/wp_rest_server/dispatch/) `wp-includes/rest-api/class-wp-rest-server.php` | Matches the request to a callback and call it. |
| [WP\_REST\_Server::get\_index()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_index/) `wp-includes/rest-api/class-wp-rest-server.php` | Retrieves the site index. |
| [WP\_REST\_Server::get\_namespace\_index()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_namespace_index/) `wp-includes/rest-api/class-wp-rest-server.php` | Retrieves the index for a namespace. |
| [WP\_REST\_Server::envelope\_response()](https://developer.wordpress.org/reference/classes/wp_rest_server/envelope_response/) `wp-includes/rest-api/class-wp-rest-server.php` | Wraps the response in an envelope. |
| [WP\_REST\_Server::get\_routes()](https://developer.wordpress.org/reference/classes/wp_rest_server/get_routes/) `wp-includes/rest-api/class-wp-rest-server.php` | Retrieves the route map. |
| [WP\_REST\_Server::serve\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Handles serving a REST API request. |
| [WP\_REST\_Server::embed\_links()](https://developer.wordpress.org/reference/classes/wp_rest_server/embed_links/) `wp-includes/rest-api/class-wp-rest-server.php` | Embeds the links from the data into the request. |
| [WP\_REST\_Server::check\_authentication()](https://developer.wordpress.org/reference/classes/wp_rest_server/check_authentication/) `wp-includes/rest-api/class-wp-rest-server.php` | Checks the authentication headers if supplied. |
| [WP\_oEmbed\_Controller::get\_item()](https://developer.wordpress.org/reference/classes/wp_oembed_controller/get_item/) `wp-includes/class-wp-oembed-controller.php` | Callback for the embed API endpoint. |
| [WP\_oEmbed\_Controller::register\_routes()](https://developer.wordpress.org/reference/classes/wp_oembed_controller/register_routes/) `wp-includes/class-wp-oembed-controller.php` | Register the oEmbed REST API route. |
| [get\_the\_post\_thumbnail\_url()](https://developer.wordpress.org/reference/functions/get_the_post_thumbnail_url/) `wp-includes/post-thumbnail-template.php` | Returns the post thumbnail URL. |
| [wp\_removable\_query\_args()](https://developer.wordpress.org/reference/functions/wp_removable_query_args/) `wp-includes/functions.php` | Returns an array of single-use query variable names that can be removed from a URL. |
| [wp\_handle\_comment\_submission()](https://developer.wordpress.org/reference/functions/wp_handle_comment_submission/) `wp-includes/comment.php` | Handles the submission of a comment, usually posted to wp-comments-post.php via a comment form. |
| [wp\_new\_comment\_notify\_moderator()](https://developer.wordpress.org/reference/functions/wp_new_comment_notify_moderator/) `wp-includes/comment.php` | Sends a comment moderation notification to the comment moderator. |
| [wp\_new\_comment\_notify\_postauthor()](https://developer.wordpress.org/reference/functions/wp_new_comment_notify_postauthor/) `wp-includes/comment.php` | Sends a notification of a new comment to the post author. |
| [get\_preview\_post\_link()](https://developer.wordpress.org/reference/functions/get_preview_post_link/) `wp-includes/link-template.php` | Retrieves the URL used for the post preview. |
| [is\_post\_type\_viewable()](https://developer.wordpress.org/reference/functions/is_post_type_viewable/) `wp-includes/post.php` | Determines whether a post type is considered “viewable”. |
| [update\_network\_option()](https://developer.wordpress.org/reference/functions/update_network_option/) `wp-includes/option.php` | Updates the value of a network option that was already added. |
| [add\_network\_option()](https://developer.wordpress.org/reference/functions/add_network_option/) `wp-includes/option.php` | Adds a new network option. |
| [get\_network\_option()](https://developer.wordpress.org/reference/functions/get_network_option/) `wp-includes/option.php` | Retrieves a network’s option value based on the option name. |
| [get\_subdirectory\_reserved\_names()](https://developer.wordpress.org/reference/functions/get_subdirectory_reserved_names/) `wp-includes/ms-functions.php` | Retrieves a list of reserved site on a sub-directory Multisite installation. |
| [WP\_Screen::render\_view\_mode()](https://developer.wordpress.org/reference/classes/wp_screen/render_view_mode/) `wp-admin/includes/class-wp-screen.php` | Renders the list table view mode preferences. |
| [WP\_Users\_List\_Table::get\_role\_list()](https://developer.wordpress.org/reference/classes/wp_users_list_table/get_role_list/) `wp-admin/includes/class-wp-users-list-table.php` | Returns an array of translated user role names for a given user object. |
| [signup\_get\_available\_languages()](https://developer.wordpress.org/reference/functions/signup_get_available_languages/) `wp-signup.php` | Retrieves languages available during the site/user sign-up process. |
| [WP\_Customize\_Nav\_Menu\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_setting/sanitize/) `wp-includes/customize/class-wp-customize-nav-menu-setting.php` | Sanitize an input. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::value\_as\_wp\_post\_nav\_menu\_item()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/value_as_wp_post_nav_menu_item/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Get the value emulated into a [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) and set up as a nav\_menu\_item. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/sanitize/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Sanitize an input. |
| [get\_language\_attributes()](https://developer.wordpress.org/reference/functions/get_language_attributes/) `wp-includes/general-template.php` | Gets the language attributes for the ‘html’ tag. |
| [wp\_site\_icon()](https://developer.wordpress.org/reference/functions/wp_site_icon/) `wp-includes/general-template.php` | Displays site icon meta tags. |
| [get\_site\_icon\_url()](https://developer.wordpress.org/reference/functions/get_site_icon_url/) `wp-includes/general-template.php` | Returns the Site Icon URL. |
| [get\_main\_network\_id()](https://developer.wordpress.org/reference/functions/get_main_network_id/) `wp-includes/functions.php` | Gets the main network ID. |
| [\_deprecated\_constructor()](https://developer.wordpress.org/reference/functions/_deprecated_constructor/) `wp-includes/functions.php` | Marks a constructor as deprecated and informs when it has been used. |
| [format\_for\_editor()](https://developer.wordpress.org/reference/functions/format_for_editor/) `wp-includes/formatting.php` | Formats text for the editor. |
| [get\_default\_comment\_status()](https://developer.wordpress.org/reference/functions/get_default_comment_status/) `wp-includes/comment.php` | Gets the default comment status for a post type. |
| [WP\_Customize\_Nav\_Menus::search\_available\_items\_query()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/search_available_items_query/) `wp-includes/class-wp-customize-nav-menus.php` | Performs post queries for available-item searching. |
| [WP\_Customize\_Nav\_Menus::available\_item\_types()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/available_item_types/) `wp-includes/class-wp-customize-nav-menus.php` | Returns an array of all the available item types. |
| [WP\_Customize\_Nav\_Menus::load\_available\_items\_query()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/load_available_items_query/) `wp-includes/class-wp-customize-nav-menus.php` | Performs the post\_type and taxonomy queries for loading available menu items. |
| [WP\_Posts\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/handle_row_actions/) `wp-admin/includes/class-wp-posts-list-table.php` | Generates and displays row action links. |
| [WP\_Posts\_List\_Table::column\_cb()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_cb/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the checkbox column output. |
| [WP\_Posts\_List\_Table::column\_title()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_title/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the title column output. |
| [WP\_Posts\_List\_Table::column\_date()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_date/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the post date column output. |
| [WP\_Posts\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_default/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the default column output. |
| [WP\_MS\_Themes\_List\_Table::column\_name()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/column_name/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Handles the name column output. |
| [WP\_MS\_Themes\_List\_Table::column\_description()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/column_description/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Handles the description column output. |
| [WP\_Site\_Icon::insert\_attachment()](https://developer.wordpress.org/reference/classes/wp_site_icon/insert_attachment/) `wp-admin/includes/class-wp-site-icon.php` | Inserts an attachment. |
| [WP\_Site\_Icon::additional\_sizes()](https://developer.wordpress.org/reference/classes/wp_site_icon/additional_sizes/) `wp-admin/includes/class-wp-site-icon.php` | Adds additional sizes to be made when creating the site icon images. |
| [WP\_Site\_Icon::intermediate\_image\_sizes()](https://developer.wordpress.org/reference/classes/wp_site_icon/intermediate_image_sizes/) `wp-admin/includes/class-wp-site-icon.php` | Adds Site Icon sizes to the array of image sizes on demand. |
| [WP\_Comments\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/handle_row_actions/) `wp-admin/includes/class-wp-comments-list-table.php` | Generates and displays row actions links. |
| [wp\_ajax\_crop\_image()](https://developer.wordpress.org/reference/functions/wp_ajax_crop_image/) `wp-admin/includes/ajax-actions.php` | Handles cropping an image via AJAX. |
| [WP\_List\_Table::get\_primary\_column\_name()](https://developer.wordpress.org/reference/classes/wp_list_table/get_primary_column_name/) `wp-admin/includes/class-wp-list-table.php` | Gets the name of the primary column. |
| [WP\_MS\_Sites\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/handle_row_actions/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Generates and displays row action links. |
| [WP\_Terms\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/handle_row_actions/) `wp-admin/includes/class-wp-terms-list-table.php` | Generates and displays row action links. |
| [WP\_MS\_Users\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/handle_row_actions/) `wp-admin/includes/class-wp-ms-users-list-table.php` | Generates and displays row action links. |
| [WP\_MS\_Users\_List\_Table::column\_blogs()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/column_blogs/) `wp-admin/includes/class-wp-ms-users-list-table.php` | Handles the sites column output. |
| [WP\_MS\_Users\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/column_default/) `wp-admin/includes/class-wp-ms-users-list-table.php` | Handles the default column output. |
| [WP\_Media\_List\_Table::column\_date()](https://developer.wordpress.org/reference/classes/wp_media_list_table/column_date/) `wp-admin/includes/class-wp-media-list-table.php` | Handles the date column output. |
| [wp\_should\_upgrade\_global\_tables()](https://developer.wordpress.org/reference/functions/wp_should_upgrade_global_tables/) `wp-admin/includes/upgrade.php` | Determine if global tables should be upgraded. |
| [WP\_Customize\_Manager::add\_dynamic\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_manager/add_dynamic_settings/) `wp-includes/class-wp-customize-manager.php` | Registers any dynamically-created settings, such as those from $\_POST\[‘customized’\] that have no corresponding setting created. |
| [wpdb::get\_table\_charset()](https://developer.wordpress.org/reference/classes/wpdb/get_table_charset/) `wp-includes/class-wpdb.php` | Retrieves the character set for the given table. |
| [wpdb::get\_col\_charset()](https://developer.wordpress.org/reference/classes/wpdb/get_col_charset/) `wp-includes/class-wpdb.php` | Retrieves the character set for the given column. |
| [wp\_delete\_file()](https://developer.wordpress.org/reference/functions/wp_delete_file/) `wp-includes/functions.php` | Deletes a file. |
| [wp\_staticize\_emoji()](https://developer.wordpress.org/reference/functions/wp_staticize_emoji/) `wp-includes/formatting.php` | Converts emoji to a static img element. |
| [wp\_staticize\_emoji\_for\_email()](https://developer.wordpress.org/reference/functions/wp_staticize_emoji_for_email/) `wp-includes/formatting.php` | Converts emoji in emails into static images. |
| [get\_avatar\_data()](https://developer.wordpress.org/reference/functions/get_avatar_data/) `wp-includes/link-template.php` | Retrieves default data about the avatar. |
| [the\_meta()](https://developer.wordpress.org/reference/functions/the_meta/) `wp-includes/post-template.php` | Displays a list of post custom fields. |
| [wp\_admin\_canonical\_url()](https://developer.wordpress.org/reference/functions/wp_admin_canonical_url/) `wp-admin/includes/misc.php` | Removes single-use URL parameters and create canonical link based on new URL. |
| [wp\_edit\_attachments\_query\_vars()](https://developer.wordpress.org/reference/functions/wp_edit_attachments_query_vars/) `wp-admin/includes/post.php` | Returns the query variables for the current attachments request. |
| [WP\_Meta\_Query::find\_compatible\_table\_alias()](https://developer.wordpress.org/reference/classes/wp_meta_query/find_compatible_table_alias/) `wp-includes/class-wp-meta-query.php` | Identifies an existing table alias that is compatible with the current query clause. |
| [WP\_Customize\_Panel::active()](https://developer.wordpress.org/reference/classes/wp_customize_panel/active/) `wp-includes/class-wp-customize-panel.php` | Check whether panel is active to current Customizer preview. |
| [get\_the\_archive\_description()](https://developer.wordpress.org/reference/functions/get_the_archive_description/) `wp-includes/general-template.php` | Retrieves the description for an author, post type, or term archive. |
| [get\_the\_archive\_title()](https://developer.wordpress.org/reference/functions/get_the_archive_title/) `wp-includes/general-template.php` | Retrieves the archive title based on the queried object. |
| [wp\_get\_password\_hint()](https://developer.wordpress.org/reference/functions/wp_get_password_hint/) `wp-includes/user.php` | Gets the text suggesting how to create strong passwords. |
| [\_navigation\_markup()](https://developer.wordpress.org/reference/functions/_navigation_markup/) `wp-includes/link-template.php` | Wraps passed links in navigational markup. |
| [get\_the\_posts\_pagination()](https://developer.wordpress.org/reference/functions/get_the_posts_pagination/) `wp-includes/link-template.php` | Retrieves a paginated navigation to next/previous set of posts, when applicable. |
| [WP\_Customize\_Section::active()](https://developer.wordpress.org/reference/classes/wp_customize_section/active/) `wp-includes/class-wp-customize-section.php` | Check whether section is active to current Customizer preview. |
| [WP\_Session\_Tokens::create()](https://developer.wordpress.org/reference/classes/wp_session_tokens/create/) `wp-includes/class-wp-session-tokens.php` | Generates a session token and attaches session information to it. |
| [WP\_Session\_Tokens::destroy\_all\_for\_all\_users()](https://developer.wordpress.org/reference/classes/wp_session_tokens/destroy_all_for_all_users/) `wp-includes/class-wp-session-tokens.php` | Destroys all sessions for all users. |
| [WP\_Session\_Tokens::get\_instance()](https://developer.wordpress.org/reference/classes/wp_session_tokens/get_instance/) `wp-includes/class-wp-session-tokens.php` | Retrieves a session manager instance for a user. |
| [WP\_Customize\_Control::active()](https://developer.wordpress.org/reference/classes/wp_customize_control/active/) `wp-includes/class-wp-customize-control.php` | Checks whether control is active to current Customizer preview. |
| [get\_editor\_stylesheets()](https://developer.wordpress.org/reference/functions/get_editor_stylesheets/) `wp-includes/theme.php` | Retrieves any registered editor stylesheet URLs. |
| [get\_comments\_number\_text()](https://developer.wordpress.org/reference/functions/get_comments_number_text/) `wp-includes/comment-template.php` | Displays the language string for the number of comments the current post has. |
| [wp\_embed\_handler\_youtube()](https://developer.wordpress.org/reference/functions/wp_embed_handler_youtube/) `wp-includes/embed.php` | YouTube iframe embed handler callback. |
| [wp\_spaces\_regexp()](https://developer.wordpress.org/reference/functions/wp_spaces_regexp/) `wp-includes/formatting.php` | Returns the regexp for common whitespace characters. |
| [WP\_Media\_List\_Table::views()](https://developer.wordpress.org/reference/classes/wp_media_list_table/views/) `wp-admin/includes/class-wp-media-list-table.php` | Overrides parent views to use the filter bar display. |
| [\_wp\_handle\_upload()](https://developer.wordpress.org/reference/functions/_wp_handle_upload/) `wp-admin/includes/file.php` | Handles PHP uploads in WordPress. |
| [WP\_Plugin\_Install\_List\_Table::views()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/views/) `wp-admin/includes/class-wp-plugin-install-list-table.php` | Overrides parent views so we can use the filter bar display. |
| [translations\_api()](https://developer.wordpress.org/reference/functions/translations_api/) `wp-admin/includes/translation-install.php` | Retrieve translations from WordPress Translation API. |
| [retrieve\_password()](https://developer.wordpress.org/reference/functions/retrieve_password/) `wp-includes/user.php` | Handles sending a password retrieval email to a user. |
| [login\_footer()](https://developer.wordpress.org/reference/functions/login_footer/) `wp-login.php` | Outputs the footer for the login page. |
| [login\_header()](https://developer.wordpress.org/reference/functions/login_header/) `wp-login.php` | Outputs the login page header. |
| [signup\_another\_blog()](https://developer.wordpress.org/reference/functions/signup_another_blog/) `wp-signup.php` | Shows a form for returning users to sign up for another site. |
| [validate\_another\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_another_blog_signup/) `wp-signup.php` | Validates a new site sign-up for an existing user. |
| [signup\_user()](https://developer.wordpress.org/reference/functions/signup_user/) `wp-signup.php` | Shows a form for a visitor to sign up for a new user account. |
| [validate\_user\_signup()](https://developer.wordpress.org/reference/functions/validate_user_signup/) `wp-signup.php` | Validates the new user sign-up. |
| [signup\_blog()](https://developer.wordpress.org/reference/functions/signup_blog/) `wp-signup.php` | Shows a form for a user or visitor to sign up for a new site. |
| [validate\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_blog_signup/) `wp-signup.php` | Validates new site signup. |
| [allow\_subdirectory\_install()](https://developer.wordpress.org/reference/functions/allow_subdirectory_install/) `wp-admin/includes/network.php` | Allow subdirectory installation. |
| [WP\_Automatic\_Updater::run()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/run/) `wp-admin/includes/class-wp-automatic-updater.php` | Kicks off the background update process, looping through all pending updates. |
| [WP\_Automatic\_Updater::send\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Sends an email upon the completion or failure of a background core update. |
| [WP\_Automatic\_Updater::send\_debug\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_debug_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Prepares and sends an email of a full log of background update results, useful for debugging and geekery. |
| [WP\_Automatic\_Updater::is\_disabled()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/is_disabled/) `wp-admin/includes/class-wp-automatic-updater.php` | Determines whether the entire automatic updater is disabled. |
| [WP\_Automatic\_Updater::is\_vcs\_checkout()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/is_vcs_checkout/) `wp-admin/includes/class-wp-automatic-updater.php` | Checks for version control checkouts. |
| [WP\_Automatic\_Updater::should\_update()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/should_update/) `wp-admin/includes/class-wp-automatic-updater.php` | Tests to see if we can and should update a specific item. |
| [WP\_Automatic\_Updater::send\_core\_update\_notification\_email()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/send_core_update_notification_email/) `wp-admin/includes/class-wp-automatic-updater.php` | Notifies an administrator of a core update. |
| [Language\_Pack\_Upgrader::async\_upgrade()](https://developer.wordpress.org/reference/classes/language_pack_upgrader/async_upgrade/) `wp-admin/includes/class-language-pack-upgrader.php` | Asynchronously upgrades language packs after other upgrades have been made. |
| [Core\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/core_upgrader/upgrade/) `wp-admin/includes/class-core-upgrader.php` | Upgrades WordPress core. |
| [Core\_Upgrader::should\_update\_to\_version()](https://developer.wordpress.org/reference/classes/core_upgrader/should_update_to_version/) `wp-admin/includes/class-core-upgrader.php` | Determines if this WordPress Core version should update to an offered version or not. |
| [WP\_Upgrader::download\_package()](https://developer.wordpress.org/reference/classes/wp_upgrader/download_package/) `wp-admin/includes/class-wp-upgrader.php` | Downloads a package. |
| [WP\_Upgrader::install\_package()](https://developer.wordpress.org/reference/classes/wp_upgrader/install_package/) `wp-admin/includes/class-wp-upgrader.php` | Install a package. |
| [WP\_Upgrader::run()](https://developer.wordpress.org/reference/classes/wp_upgrader/run/) `wp-admin/includes/class-wp-upgrader.php` | Runs an upgrade/installation. |
| [WP\_MS\_Users\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-users-list-table.php` |  |
| [WP\_MS\_Users\_List\_Table::get\_columns()](https://developer.wordpress.org/reference/classes/wp_ms_users_list_table/get_columns/) `wp-admin/includes/class-wp-ms-users-list-table.php` |  |
| [wp\_prepare\_themes\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_themes_for_js/) `wp-admin/includes/theme.php` | Prepares themes for JavaScript. |
| [WP\_Screen::show\_screen\_options()](https://developer.wordpress.org/reference/classes/wp_screen/show_screen_options/) `wp-admin/includes/class-wp-screen.php` |  |
| [WP\_Screen::render\_screen\_options()](https://developer.wordpress.org/reference/classes/wp_screen/render_screen_options/) `wp-admin/includes/class-wp-screen.php` | Renders the screen options tab. |
| [WP\_Screen::render\_per\_page\_options()](https://developer.wordpress.org/reference/classes/wp_screen/render_per_page_options/) `wp-admin/includes/class-wp-screen.php` | Renders the items per page option. |
| [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) `wp-admin/includes/theme.php` | Retrieves theme installer pages from the WordPress.org Themes API. |
| [WP\_Screen::render\_screen\_meta()](https://developer.wordpress.org/reference/classes/wp_screen/render_screen_meta/) `wp-admin/includes/class-wp-screen.php` | Renders the screen’s help section. |
| [WP\_Screen::get()](https://developer.wordpress.org/reference/classes/wp_screen/get/) `wp-admin/includes/class-wp-screen.php` | Fetches a screen object. |
| [WP\_Plugins\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/single_row/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [get\_column\_headers()](https://developer.wordpress.org/reference/functions/get_column_headers/) `wp-admin/includes/screen.php` | Get the column headers for a screen |
| [get\_hidden\_columns()](https://developer.wordpress.org/reference/functions/get_hidden_columns/) `wp-admin/includes/screen.php` | Get a list of hidden columns. |
| [get\_hidden\_meta\_boxes()](https://developer.wordpress.org/reference/functions/get_hidden_meta_boxes/) `wp-admin/includes/screen.php` | Gets an array of IDs of hidden meta boxes. |
| [WP\_Plugins\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/prepare_items/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [wp\_create\_thumbnail()](https://developer.wordpress.org/reference/functions/wp_create_thumbnail/) `wp-admin/includes/deprecated.php` | This was once used to create a thumbnail from an Image given a maximum side size. |
| [get\_editable\_authors()](https://developer.wordpress.org/reference/functions/get_editable_authors/) `wp-admin/includes/deprecated.php` | Gets author users who can edit posts. |
| [get\_others\_unpublished\_posts()](https://developer.wordpress.org/reference/functions/get_others_unpublished_posts/) `wp-admin/includes/deprecated.php` | Retrieves editable posts from other users. |
| [Language\_Pack\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/language_pack_upgrader_skin/bulk_footer/) `wp-admin/includes/class-language-pack-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Theme\_Upgrader\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_upgrader_skin/after/) `wp-admin/includes/class-theme-upgrader-skin.php` | Performs an action following a single theme update. |
| [Plugin\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_installer_skin/after/) `wp-admin/includes/class-plugin-installer-skin.php` | Performs an action following a plugin install. |
| [Bulk\_Theme\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/bulk_theme_upgrader_skin/bulk_footer/) `wp-admin/includes/class-bulk-theme-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Theme\_Installer\_Skin::after()](https://developer.wordpress.org/reference/classes/theme_installer_skin/after/) `wp-admin/includes/class-theme-installer-skin.php` | Performs an action following a single theme install. |
| [Bulk\_Plugin\_Upgrader\_Skin::bulk\_footer()](https://developer.wordpress.org/reference/classes/bulk_plugin_upgrader_skin/bulk_footer/) `wp-admin/includes/class-bulk-plugin-upgrader-skin.php` | Displays the footer following the bulk update process. |
| [Plugin\_Upgrader\_Skin::after()](https://developer.wordpress.org/reference/classes/plugin_upgrader_skin/after/) `wp-admin/includes/class-plugin-upgrader-skin.php` | Performs an action following a single plugin update. |
| [WP\_List\_Table::get\_items\_per\_page()](https://developer.wordpress.org/reference/classes/wp_list_table/get_items_per_page/) `wp-admin/includes/class-wp-list-table.php` | Gets the number of items to display on a single page. |
| [WP\_List\_Table::get\_column\_info()](https://developer.wordpress.org/reference/classes/wp_list_table/get_column_info/) `wp-admin/includes/class-wp-list-table.php` | Gets a list of all, hidden, and sortable columns, with filter applied. |
| [WP\_List\_Table::views()](https://developer.wordpress.org/reference/classes/wp_list_table/views/) `wp-admin/includes/class-wp-list-table.php` | Displays the list of views available on this table. |
| [WP\_List\_Table::bulk\_actions()](https://developer.wordpress.org/reference/classes/wp_list_table/bulk_actions/) `wp-admin/includes/class-wp-list-table.php` | Displays the bulk actions dropdown. |
| [WP\_List\_Table::months\_dropdown()](https://developer.wordpress.org/reference/classes/wp_list_table/months_dropdown/) `wp-admin/includes/class-wp-list-table.php` | Displays a dropdown for filtering items in the list table by month. |
| [mu\_dropdown\_languages()](https://developer.wordpress.org/reference/functions/mu_dropdown_languages/) `wp-admin/includes/ms.php` | Generates and displays a drop-down of available languages. |
| [can\_edit\_network()](https://developer.wordpress.org/reference/functions/can_edit_network/) `wp-admin/includes/ms.php` | Determines whether or not this network from this page can be edited. |
| [format\_code\_lang()](https://developer.wordpress.org/reference/functions/format_code_lang/) `wp-admin/includes/ms.php` | Returns the language for a language code. |
| [update\_option\_new\_admin\_email()](https://developer.wordpress.org/reference/functions/update_option_new_admin_email/) `wp-admin/includes/misc.php` | Sends a confirmation request email when a change of site admin email address is attempted. |
| [send\_confirmation\_on\_profile\_email()](https://developer.wordpress.org/reference/functions/send_confirmation_on_profile_email/) `wp-includes/user.php` | Sends a confirmation request email when a change of user email address is attempted. |
| [wp\_save\_image\_file()](https://developer.wordpress.org/reference/functions/wp_save_image_file/) `wp-admin/includes/image-edit.php` | Saves image to file. |
| [image\_edit\_apply\_changes()](https://developer.wordpress.org/reference/functions/image_edit_apply_changes/) `wp-admin/includes/image-edit.php` | Performs group of changes on Editor specified. |
| [wp\_save\_image()](https://developer.wordpress.org/reference/functions/wp_save_image/) `wp-admin/includes/image-edit.php` | Saves image to post, along with enqueued changes in `$_REQUEST['history']`. |
| [wp\_image\_editor()](https://developer.wordpress.org/reference/functions/wp_image_editor/) `wp-admin/includes/image-edit.php` | Loads the WP image-editing interface. |
| [wp\_stream\_image()](https://developer.wordpress.org/reference/functions/wp_stream_image/) `wp-admin/includes/image-edit.php` | Streams image in [WP\_Image\_Editor](https://developer.wordpress.org/reference/classes/wp_image_editor/) to browser. |
| [WP\_MS\_Themes\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-themes-list-table.php` |  |
| [insert\_with\_markers()](https://developer.wordpress.org/reference/functions/insert_with_markers/) `wp-admin/includes/misc.php` | Inserts an array of strings into a file (.htaccess), placing it between BEGIN and END markers. |
| [wp\_doc\_link\_parse()](https://developer.wordpress.org/reference/functions/wp_doc_link_parse/) `wp-admin/includes/misc.php` |  |
| [set\_screen\_options()](https://developer.wordpress.org/reference/functions/set_screen_options/) `wp-admin/includes/misc.php` | Saves option for number of rows when listing posts, pages, comments, etc. |
| [got\_mod\_rewrite()](https://developer.wordpress.org/reference/functions/got_mod_rewrite/) `wp-admin/includes/misc.php` | Returns whether the server is running Apache with the mod\_rewrite module loaded. |
| [got\_url\_rewrite()](https://developer.wordpress.org/reference/functions/got_url_rewrite/) `wp-admin/includes/misc.php` | Returns whether the server supports URL rewriting. |
| [get\_terms\_to\_edit()](https://developer.wordpress.org/reference/functions/get_terms_to_edit/) `wp-admin/includes/taxonomy.php` | Gets comma-separated list of terms available to edit for the given post ID. |
| [WP\_Theme\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/prepare_items/) `wp-admin/includes/class-wp-theme-install-list-table.php` |  |
| [WP\_Theme\_Install\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/single_row/) `wp-admin/includes/class-wp-theme-install-list-table.php` | Prints a theme from the WordPress.org API. |
| [update\_right\_now\_message()](https://developer.wordpress.org/reference/functions/update_right_now_message/) `wp-admin/includes/update.php` | Displays WordPress version and active theme in the ‘At a Glance’ dashboard widget. |
| [wp\_generate\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_generate_attachment_metadata/) `wp-admin/includes/image.php` | Generates attachment meta data and create image sub-sizes for images. |
| [wp\_read\_image\_metadata()](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/) `wp-admin/includes/image.php` | Gets extended image metadata, exif or iptc as available. |
| [file\_is\_displayable\_image()](https://developer.wordpress.org/reference/functions/file_is_displayable_image/) `wp-admin/includes/image.php` | Validates that file is suitable for displaying within a web page. |
| [load\_image\_to\_edit()](https://developer.wordpress.org/reference/functions/load_image_to_edit/) `wp-admin/includes/image.php` | Loads an image resource for editing. |
| [\_load\_image\_to\_edit\_path()](https://developer.wordpress.org/reference/functions/_load_image_to_edit_path/) `wp-admin/includes/image.php` | Retrieves the path or URL of an attachment’s attached file. |
| [plugins\_api()](https://developer.wordpress.org/reference/functions/plugins_api/) `wp-admin/includes/plugin-install.php` | Retrieves plugin installer pages from the WordPress.org Plugins API. |
| [wp\_dashboard\_recent\_posts()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_posts/) `wp-admin/includes/dashboard.php` | Generates Publishing Soon and Recently Published sections. |
| [wp\_dashboard\_primary()](https://developer.wordpress.org/reference/functions/wp_dashboard_primary/) `wp-admin/includes/dashboard.php` | ‘WordPress Events and News’ dashboard widget. |
| [wp\_dashboard\_browser\_nag()](https://developer.wordpress.org/reference/functions/wp_dashboard_browser_nag/) `wp-admin/includes/dashboard.php` | Displays the browser update nag. |
| [wp\_dashboard\_right\_now()](https://developer.wordpress.org/reference/functions/wp_dashboard_right_now/) `wp-admin/includes/dashboard.php` | Dashboard widget that displays some basic stats about the site. |
| [wp\_dashboard\_quick\_press()](https://developer.wordpress.org/reference/functions/wp_dashboard_quick_press/) `wp-admin/includes/dashboard.php` | Displays the Quick Draft widget. |
| [wp\_dashboard\_recent\_drafts()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_drafts/) `wp-admin/includes/dashboard.php` | Show recent drafts of the user on the dashboard. |
| [\_wp\_dashboard\_recent\_comments\_row()](https://developer.wordpress.org/reference/functions/_wp_dashboard_recent_comments_row/) `wp-admin/includes/dashboard.php` | Outputs a row for the Recent Comments widget. |
| [wp\_dashboard\_setup()](https://developer.wordpress.org/reference/functions/wp_dashboard_setup/) `wp-admin/includes/dashboard.php` | Registers dashboard widgets. |
| [dbDelta()](https://developer.wordpress.org/reference/functions/dbdelta/) `wp-admin/includes/upgrade.php` | Modifies the database based on specified SQL statements. |
| [wp\_new\_blog\_notification()](https://developer.wordpress.org/reference/functions/wp_new_blog_notification/) `wp-admin/includes/upgrade.php` | Notifies the site admin that the installation of WordPress is complete. |
| [register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) `wp-includes/option.php` | Registers a setting and its data. |
| [get\_plugin\_files()](https://developer.wordpress.org/reference/functions/get_plugin_files/) `wp-admin/includes/plugin.php` | Gets a list of a plugin’s files. |
| [\_get\_list\_table()](https://developer.wordpress.org/reference/functions/_get_list_table/) `wp-admin/includes/list-table.php` | Fetches an instance of a [WP\_List\_Table](https://developer.wordpress.org/reference/classes/wp_list_table/) class. |
| [WP\_Plugin\_Install\_List\_Table::display\_rows()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/display_rows/) `wp-admin/includes/class-wp-plugin-install-list-table.php` | Generates the list table rows. |
| [edit\_user()](https://developer.wordpress.org/reference/functions/edit_user/) `wp-admin/includes/user.php` | Edit user settings based on contents of $\_POST |
| [get\_editable\_roles()](https://developer.wordpress.org/reference/functions/get_editable_roles/) `wp-admin/includes/user.php` | Fetch a filtered list of user roles that the current user is allowed to edit. |
| [get\_users\_drafts()](https://developer.wordpress.org/reference/functions/get_users_drafts/) `wp-admin/includes/user.php` | Retrieve the user’s drafts. |
| [wp\_delete\_user()](https://developer.wordpress.org/reference/functions/wp_delete_user/) `wp-admin/includes/user.php` | Delete user and optionally reassign posts and links to another user. |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [Walker\_Category\_Checklist::start\_el()](https://developer.wordpress.org/reference/classes/walker_category_checklist/start_el/) `wp-admin/includes/class-walker-category-checklist.php` | Start the element output. |
| [iframe\_header()](https://developer.wordpress.org/reference/functions/iframe_header/) `wp-admin/includes/template.php` | Generic Iframe header for use with Thickbox. |
| [get\_inline\_data()](https://developer.wordpress.org/reference/functions/get_inline_data/) `wp-admin/includes/template.php` | Adds hidden fields with the data for use in the inline editor for posts and pages. |
| [wp\_comment\_reply()](https://developer.wordpress.org/reference/functions/wp_comment_reply/) `wp-admin/includes/template.php` | Outputs the in-line comment reply-to form in the Comments list table. |
| [meta\_form()](https://developer.wordpress.org/reference/functions/meta_form/) `wp-admin/includes/template.php` | Prints the form in the Custom Fields meta box. |
| [wp\_import\_upload\_form()](https://developer.wordpress.org/reference/functions/wp_import_upload_form/) `wp-admin/includes/template.php` | Outputs the form used by the importers to accept the data to be imported. |
| [WP\_Themes\_List\_Table::display\_rows()](https://developer.wordpress.org/reference/classes/wp_themes_list_table/display_rows/) `wp-admin/includes/class-wp-themes-list-table.php` | Generates the list table rows. |
| [wp\_terms\_checklist()](https://developer.wordpress.org/reference/functions/wp_terms_checklist/) `wp-admin/includes/template.php` | Outputs an unordered list of checkbox input elements labelled with term names. |
| [wp\_popular\_terms\_checklist()](https://developer.wordpress.org/reference/functions/wp_popular_terms_checklist/) `wp-admin/includes/template.php` | Retrieves a list of the most popular terms from the specified taxonomy. |
| [wp\_link\_category\_checklist()](https://developer.wordpress.org/reference/functions/wp_link_category_checklist/) `wp-admin/includes/template.php` | Outputs a link category checklist element. |
| [WP\_Users\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_users_list_table/single_row/) `wp-admin/includes/class-wp-users-list-table.php` | Generates HTML for a single row on the users.php admin panel. |
| [WP\_MS\_Sites\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Prepares the list of sites for display. |
| [WP\_MS\_Sites\_List\_Table::get\_columns()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/get_columns/) `wp-admin/includes/class-wp-ms-sites-list-table.php` |  |
| [WP\_Users\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_users_list_table/prepare_items/) `wp-admin/includes/class-wp-users-list-table.php` | Prepares the users list for display. |
| [wp\_read\_video\_metadata()](https://developer.wordpress.org/reference/functions/wp_read_video_metadata/) `wp-admin/includes/media.php` | Retrieves metadata from a video file’s ID3 tags. |
| [wp\_read\_audio\_metadata()](https://developer.wordpress.org/reference/functions/wp_read_audio_metadata/) `wp-admin/includes/media.php` | Retrieves metadata from an audio file’s ID3 tags. |
| [media\_upload\_type\_form()](https://developer.wordpress.org/reference/functions/media_upload_type_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for a given media type. |
| [media\_upload\_type\_url\_form()](https://developer.wordpress.org/reference/functions/media_upload_type_url_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for external media. |
| [media\_upload\_gallery\_form()](https://developer.wordpress.org/reference/functions/media_upload_gallery_form/) `wp-admin/includes/media.php` | Adds gallery form to upload iframe. |
| [media\_upload\_library\_form()](https://developer.wordpress.org/reference/functions/media_upload_library_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form for the media library. |
| [wp\_media\_insert\_url\_form()](https://developer.wordpress.org/reference/functions/wp_media_insert_url_form/) `wp-admin/includes/media.php` | Creates the form for external url. |
| [edit\_form\_image\_editor()](https://developer.wordpress.org/reference/functions/edit_form_image_editor/) `wp-admin/includes/media.php` | Displays the image and editor in the post editor |
| [attachment\_submitbox\_metadata()](https://developer.wordpress.org/reference/functions/attachment_submitbox_metadata/) `wp-admin/includes/media.php` | Displays non-editable attachment metadata in the publish meta box. |
| [get\_attachment\_fields\_to\_edit()](https://developer.wordpress.org/reference/functions/get_attachment_fields_to_edit/) `wp-admin/includes/media.php` | Retrieves the attachment fields to edit form fields. |
| [get\_media\_item()](https://developer.wordpress.org/reference/functions/get_media_item/) `wp-admin/includes/media.php` | Retrieves HTML form for modifying the image attachment. |
| [get\_compat\_media\_markup()](https://developer.wordpress.org/reference/functions/get_compat_media_markup/) `wp-admin/includes/media.php` |  |
| [media\_upload\_form()](https://developer.wordpress.org/reference/functions/media_upload_form/) `wp-admin/includes/media.php` | Outputs the legacy media upload form. |
| [media\_upload\_form\_handler()](https://developer.wordpress.org/reference/functions/media_upload_form_handler/) `wp-admin/includes/media.php` | Handles form submissions for the legacy media uploader. |
| [wp\_media\_upload\_handler()](https://developer.wordpress.org/reference/functions/wp_media_upload_handler/) `wp-admin/includes/media.php` | Handles the process of uploading media. |
| [media\_sideload\_image()](https://developer.wordpress.org/reference/functions/media_sideload_image/) `wp-admin/includes/media.php` | Downloads an image from the specified URL, saves it as an attachment, and optionally attaches it to a post. |
| [image\_size\_input\_fields()](https://developer.wordpress.org/reference/functions/image_size_input_fields/) `wp-admin/includes/media.php` | Retrieves HTML for the size radio buttons with the specified one checked. |
| [the\_media\_upload\_tabs()](https://developer.wordpress.org/reference/functions/the_media_upload_tabs/) `wp-admin/includes/media.php` | Outputs the legacy media upload tabs UI. |
| [get\_image\_send\_to\_editor()](https://developer.wordpress.org/reference/functions/get_image_send_to_editor/) `wp-admin/includes/media.php` | Retrieves the image HTML to send to the editor. |
| [image\_add\_caption()](https://developer.wordpress.org/reference/functions/image_add_caption/) `wp-admin/includes/media.php` | Adds image shortcode with caption to editor. |
| [get\_upload\_iframe\_src()](https://developer.wordpress.org/reference/functions/get_upload_iframe_src/) `wp-admin/includes/media.php` | Retrieves the upload iframe source URL. |
| [get\_sample\_permalink\_html()](https://developer.wordpress.org/reference/functions/get_sample_permalink_html/) `wp-admin/includes/post.php` | Returns the HTML of the sample permalink slug editor. |
| [\_wp\_post\_thumbnail\_html()](https://developer.wordpress.org/reference/functions/_wp_post_thumbnail_html/) `wp-admin/includes/post.php` | Returns HTML for the post thumbnail meta box. |
| [wp\_check\_post\_lock()](https://developer.wordpress.org/reference/functions/wp_check_post_lock/) `wp-admin/includes/post.php` | Determines whether the post is currently being edited by another user. |
| [\_admin\_notice\_post\_locked()](https://developer.wordpress.org/reference/functions/_admin_notice_post_locked/) `wp-admin/includes/post.php` | Outputs the HTML for the notice to say that someone else is editing or has taken over editing of this post. |
| [media\_upload\_tabs()](https://developer.wordpress.org/reference/functions/media_upload_tabs/) `wp-admin/includes/media.php` | Defines the default media upload tabs. |
| [wp\_edit\_posts\_query()](https://developer.wordpress.org/reference/functions/wp_edit_posts_query/) `wp-admin/includes/post.php` | Runs the query to fetch the posts for listing on the edit posts page. |
| [postbox\_classes()](https://developer.wordpress.org/reference/functions/postbox_classes/) `wp-admin/includes/post.php` | Returns the list of classes to be used by a meta box. |
| [get\_sample\_permalink()](https://developer.wordpress.org/reference/functions/get_sample_permalink/) `wp-admin/includes/post.php` | Returns a sample permalink based on the post name. |
| [get\_available\_post\_mime\_types()](https://developer.wordpress.org/reference/functions/get_available_post_mime_types/) `wp-includes/post.php` | Gets all available post MIME types for a given post type. |
| [edit\_post()](https://developer.wordpress.org/reference/functions/edit_post/) `wp-admin/includes/post.php` | Updates an existing post with values provided in `$_POST`. |
| [get\_default\_post\_to\_edit()](https://developer.wordpress.org/reference/functions/get_default_post_to_edit/) `wp-admin/includes/post.php` | Returns default post information to use when populating the “Write Post” form. |
| [wp\_ajax\_send\_attachment\_to\_editor()](https://developer.wordpress.org/reference/functions/wp_ajax_send_attachment_to_editor/) `wp-admin/includes/ajax-actions.php` | Handles sending an attachment to the editor via AJAX. |
| [wp\_ajax\_send\_link\_to\_editor()](https://developer.wordpress.org/reference/functions/wp_ajax_send_link_to_editor/) `wp-admin/includes/ajax-actions.php` | Handles sending a link to the editor via AJAX. |
| [wp\_ajax\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API via AJAX. |
| [wp\_ajax\_query\_themes()](https://developer.wordpress.org/reference/functions/wp_ajax_query_themes/) `wp-admin/includes/ajax-actions.php` | Handles getting themes from [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) via AJAX. |
| [wp\_ajax\_wp\_remove\_post\_lock()](https://developer.wordpress.org/reference/functions/wp_ajax_wp_remove_post_lock/) `wp-admin/includes/ajax-actions.php` | Handles removing a post lock via AJAX. |
| [wp\_ajax\_query\_attachments()](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/) `wp-admin/includes/ajax-actions.php` | Handles querying attachments via AJAX. |
| [wp\_ajax\_save\_attachment\_compat()](https://developer.wordpress.org/reference/functions/wp_ajax_save_attachment_compat/) `wp-admin/includes/ajax-actions.php` | Handles saving backward compatible attachment attributes via AJAX. |
| [wp\_ajax\_add\_menu\_item()](https://developer.wordpress.org/reference/functions/wp_ajax_add_menu_item/) `wp-admin/includes/ajax-actions.php` | Handles adding a menu item via AJAX. |
| [wp\_ajax\_menu\_get\_metabox()](https://developer.wordpress.org/reference/functions/wp_ajax_menu_get_metabox/) `wp-admin/includes/ajax-actions.php` | Handles for retrieving menu meta boxes via AJAX. |
| [wp\_ajax\_inline\_save()](https://developer.wordpress.org/reference/functions/wp_ajax_inline_save/) `wp-admin/includes/ajax-actions.php` | Handles Quick Edit saving a post from a list table via AJAX. |
| [wp\_get\_revision\_ui\_diff()](https://developer.wordpress.org/reference/functions/wp_get_revision_ui_diff/) `wp-admin/includes/revision.php` | Get the revision UI diff. |
| [wp\_prepare\_revisions\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_revisions_for_js/) `wp-admin/includes/revision.php` | Prepare revisions for JavaScript. |
| [update\_core()](https://developer.wordpress.org/reference/functions/update_core/) `wp-admin/includes/update-core.php` | Upgrades the core of WordPress. |
| [wp\_ajax\_nopriv\_heartbeat()](https://developer.wordpress.org/reference/functions/wp_ajax_nopriv_heartbeat/) `wp-admin/includes/ajax-actions.php` | Handles the Heartbeat API in the no-privilege context via AJAX . |
| [wp\_ajax\_ajax\_tag\_search()](https://developer.wordpress.org/reference/functions/wp_ajax_ajax_tag_search/) `wp-admin/includes/ajax-actions.php` | Handles tag search via AJAX. |
| [wp\_ajax\_autocomplete\_user()](https://developer.wordpress.org/reference/functions/wp_ajax_autocomplete_user/) `wp-admin/includes/ajax-actions.php` | Handles user autocomplete via AJAX. |
| [post\_slug\_meta\_box()](https://developer.wordpress.org/reference/functions/post_slug_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays slug form fields. |
| [page\_attributes\_meta\_box()](https://developer.wordpress.org/reference/functions/page_attributes_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays page attributes form fields. |
| [post\_categories\_meta\_box()](https://developer.wordpress.org/reference/functions/post_categories_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post categories form fields. |
| [add\_menu\_classes()](https://developer.wordpress.org/reference/functions/add_menu_classes/) `wp-admin/includes/menu.php` | Adds CSS classes for top-level administration menu items. |
| [WP\_Media\_List\_Table::get\_columns()](https://developer.wordpress.org/reference/classes/wp_media_list_table/get_columns/) `wp-admin/includes/class-wp-media-list-table.php` |  |
| [WP\_Media\_List\_Table::\_get\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_media_list_table/_get_row_actions/) `wp-admin/includes/class-wp-media-list-table.php` |  |
| [WP\_Comments\_List\_Table::column\_author()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/column_author/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/get_views/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::column\_comment()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/column_comment/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Terms\_List\_Table::column\_name()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/column_name/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [WP\_Terms\_List\_Table::column\_slug()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/column_slug/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [WP\_Terms\_List\_Table::column\_default()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/column_default/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [WP\_Comments\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/prepare_items/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::get\_per\_page()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/get_per_page/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Terms\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/prepare_items/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [Walker\_Nav\_Menu\_Checklist::start\_el()](https://developer.wordpress.org/reference/classes/walker_nav_menu_checklist/start_el/) `wp-admin/includes/class-walker-nav-menu-checklist.php` | Start the element output. |
| [wp\_nav\_menu\_post\_type\_meta\_boxes()](https://developer.wordpress.org/reference/functions/wp_nav_menu_post_type_meta_boxes/) `wp-admin/includes/nav-menu.php` | Creates meta boxes for any post type menu item. |
| [wp\_nav\_menu\_taxonomy\_meta\_boxes()](https://developer.wordpress.org/reference/functions/wp_nav_menu_taxonomy_meta_boxes/) `wp-admin/includes/nav-menu.php` | Creates meta boxes for any taxonomy menu item. |
| [wp\_nav\_menu\_item\_post\_type\_meta\_box()](https://developer.wordpress.org/reference/functions/wp_nav_menu_item_post_type_meta_box/) `wp-admin/includes/nav-menu.php` | Displays a meta box for a post type menu item. |
| [wp\_get\_nav\_menu\_to\_edit()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_to_edit/) `wp-admin/includes/nav-menu.php` | Returns the menu formatted to edit. |
| [get\_filesystem\_method()](https://developer.wordpress.org/reference/functions/get_filesystem_method/) `wp-admin/includes/file.php` | Determines which method to use for reading, writing, modifying, or deleting files on the filesystem. |
| [request\_filesystem\_credentials()](https://developer.wordpress.org/reference/functions/request_filesystem_credentials/) `wp-admin/includes/file.php` | Displays a form to the user to request for their FTP/SSH details in order to connect to the filesystem. |
| [download\_url()](https://developer.wordpress.org/reference/functions/download_url/) `wp-admin/includes/file.php` | Downloads a URL to a local temporary file using the WordPress HTTP API. |
| [unzip\_file()](https://developer.wordpress.org/reference/functions/unzip_file/) `wp-admin/includes/file.php` | Unzips a specified ZIP file to a location on the filesystem via the WordPress Filesystem Abstraction. |
| [\_unzip\_file\_ziparchive()](https://developer.wordpress.org/reference/functions/_unzip_file_ziparchive/) `wp-admin/includes/file.php` | Attempts to unzip an archive using the ZipArchive class. |
| [\_unzip\_file\_pclzip()](https://developer.wordpress.org/reference/functions/_unzip_file_pclzip/) `wp-admin/includes/file.php` | Attempts to unzip an archive using the PclZip library. |
| [WP\_Filesystem()](https://developer.wordpress.org/reference/functions/wp_filesystem/) `wp-admin/includes/file.php` | Initializes and connects the WordPress Filesystem Abstraction classes. |
| [WP\_Posts\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/inline_edit/) `wp-admin/includes/class-wp-posts-list-table.php` | Outputs the hidden row displayed when inline editing |
| [WP\_Posts\_List\_Table::get\_columns()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/get_columns/) `wp-admin/includes/class-wp-posts-list-table.php` |  |
| [WP\_Posts\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/prepare_items/) `wp-admin/includes/class-wp-posts-list-table.php` |  |
| [get\_comment\_to\_edit()](https://developer.wordpress.org/reference/functions/get_comment_to_edit/) `wp-admin/includes/comment.php` | Returns a [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object based on comment ID. |
| [Custom\_Image\_Header::insert\_attachment()](https://developer.wordpress.org/reference/classes/custom_image_header/insert_attachment/) `wp-admin/includes/class-custom-image-header.php` | Inserts an attachment and its metadata. |
| [Custom\_Image\_Header::ajax\_header\_crop()](https://developer.wordpress.org/reference/classes/custom_image_header/ajax_header_crop/) `wp-admin/includes/class-custom-image-header.php` | Gets attachment uploaded by Media Manager, crops it, then saves it as a new object. Returns JSON-encoded object details. |
| [Custom\_Image\_Header::step\_2()](https://developer.wordpress.org/reference/classes/custom_image_header/step_2/) `wp-admin/includes/class-custom-image-header.php` | Displays second step of custom header image page. |
| [Custom\_Image\_Header::step\_3()](https://developer.wordpress.org/reference/classes/custom_image_header/step_3/) `wp-admin/includes/class-custom-image-header.php` | Displays third step of custom header image page. |
| [redirect\_post()](https://developer.wordpress.org/reference/functions/redirect_post/) `wp-admin/includes/post.php` | Redirects to previous page. |
| [Custom\_Background::wp\_set\_background\_image()](https://developer.wordpress.org/reference/classes/custom_background/wp_set_background_image/) `wp-admin/includes/class-custom-background.php` |  |
| [Custom\_Background::handle\_upload()](https://developer.wordpress.org/reference/classes/custom_background/handle_upload/) `wp-admin/includes/class-custom-background.php` | Handles an Image upload for the background image. |
| [WP\_User::has\_cap()](https://developer.wordpress.org/reference/classes/wp_user/has_cap/) `wp-includes/class-wp-user.php` | Returns whether the user has the specified capability. |
| [WP\_Role::has\_cap()](https://developer.wordpress.org/reference/classes/wp_role/has_cap/) `wp-includes/class-wp-role.php` | Determines whether the role has the given capability. |
| [WP\_Customize\_Manager::add\_setting()](https://developer.wordpress.org/reference/classes/wp_customize_manager/add_setting/) `wp-includes/class-wp-customize-manager.php` | Adds a customize setting. |
| [map\_meta\_cap()](https://developer.wordpress.org/reference/functions/map_meta_cap/) `wp-includes/capabilities.php` | Maps a capability to the primitive capabilities required of the given user to satisfy the capability being checked. |
| [WP\_Customize\_Manager::save()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save/) `wp-includes/class-wp-customize-manager.php` | Handles customize\_save WP Ajax request to save/update a changeset. |
| [WP\_Styles::all\_deps()](https://developer.wordpress.org/reference/classes/wp_styles/all_deps/) `wp-includes/class-wp-styles.php` | Determines style dependencies. |
| [WP\_Styles::\_css\_href()](https://developer.wordpress.org/reference/classes/wp_styles/_css_href/) `wp-includes/class-wp-styles.php` | Generates an enqueued style’s fully-qualified URL. |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [WP\_Styles::do\_item()](https://developer.wordpress.org/reference/classes/wp_styles/do_item/) `wp-includes/class-wp-styles.php` | Processes a style dependency. |
| [wp\_schedule\_event()](https://developer.wordpress.org/reference/functions/wp_schedule_event/) `wp-includes/cron.php` | Schedules a recurring event. |
| [wp\_reschedule\_event()](https://developer.wordpress.org/reference/functions/wp_reschedule_event/) `wp-includes/cron.php` | Reschedules a recurring event. |
| [wp\_unschedule\_event()](https://developer.wordpress.org/reference/functions/wp_unschedule_event/) `wp-includes/cron.php` | Unschedules a previously scheduled event. |
| [wp\_clear\_scheduled\_hook()](https://developer.wordpress.org/reference/functions/wp_clear_scheduled_hook/) `wp-includes/cron.php` | Unschedules all events attached to the hook with the specified arguments. |
| [wp\_next\_scheduled()](https://developer.wordpress.org/reference/functions/wp_next_scheduled/) `wp-includes/cron.php` | Retrieves the timestamp of the next scheduled event for the given hook. |
| [spawn\_cron()](https://developer.wordpress.org/reference/functions/spawn_cron/) `wp-includes/cron.php` | Sends a request to run cron through HTTP request that doesn’t halt page loading. |
| [wp\_get\_schedules()](https://developer.wordpress.org/reference/functions/wp_get_schedules/) `wp-includes/cron.php` | Retrieves supported event recurrence schedules. |
| [wp\_get\_schedule()](https://developer.wordpress.org/reference/functions/wp_get_schedule/) `wp-includes/cron.php` | Retrieves the name of the recurrence schedule for an event. |
| [wp\_schedule\_single\_event()](https://developer.wordpress.org/reference/functions/wp_schedule_single_event/) `wp-includes/cron.php` | Schedules an event to run only once. |
| [Walker\_Category::start\_el()](https://developer.wordpress.org/reference/classes/walker_category/start_el/) `wp-includes/class-walker-category.php` | Starts the element output. |
| [Walker\_CategoryDropdown::start\_el()](https://developer.wordpress.org/reference/classes/walker_categorydropdown/start_el/) `wp-includes/class-walker-category-dropdown.php` | Starts the element output. |
| [get\_the\_term\_list()](https://developer.wordpress.org/reference/functions/get_the_term_list/) `wp-includes/category-template.php` | Retrieves a post’s terms as a list with specified format. |
| [the\_terms()](https://developer.wordpress.org/reference/functions/the_terms/) `wp-includes/category-template.php` | Displays the terms for a post in a list. |
| [wp\_tag\_cloud()](https://developer.wordpress.org/reference/functions/wp_tag_cloud/) `wp-includes/category-template.php` | Displays a tag cloud. |
| [wp\_generate\_tag\_cloud()](https://developer.wordpress.org/reference/functions/wp_generate_tag_cloud/) `wp-includes/category-template.php` | Generates a tag cloud (heatmap) from provided data. |
| [get\_the\_tags()](https://developer.wordpress.org/reference/functions/get_the_tags/) `wp-includes/category-template.php` | Retrieves the tags for a post. |
| [get\_the\_tag\_list()](https://developer.wordpress.org/reference/functions/get_the_tag_list/) `wp-includes/category-template.php` | Retrieves the tags for a post formatted as a string. |
| [get\_the\_terms()](https://developer.wordpress.org/reference/functions/get_the_terms/) `wp-includes/category-template.php` | Retrieves the terms of the taxonomy that are attached to the post. |
| [get\_the\_category()](https://developer.wordpress.org/reference/functions/get_the_category/) `wp-includes/category-template.php` | Retrieves post categories. |
| [get\_the\_category\_list()](https://developer.wordpress.org/reference/functions/get_the_category_list/) `wp-includes/category-template.php` | Retrieves category list for a post in either HTML list or custom format. |
| [wp\_dropdown\_categories()](https://developer.wordpress.org/reference/functions/wp_dropdown_categories/) `wp-includes/category-template.php` | Displays or retrieves the HTML dropdown list of categories. |
| [wp\_list\_categories()](https://developer.wordpress.org/reference/functions/wp_list_categories/) `wp-includes/category-template.php` | Displays or retrieves the HTML list of categories. |
| [current\_theme\_supports()](https://developer.wordpress.org/reference/functions/current_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature. |
| [set\_theme\_mod()](https://developer.wordpress.org/reference/functions/set_theme_mod/) `wp-includes/theme.php` | Updates theme modification value for the active theme. |
| [get\_header\_image()](https://developer.wordpress.org/reference/functions/get_header_image/) `wp-includes/theme.php` | Retrieves header image for custom header. |
| [get\_theme\_root()](https://developer.wordpress.org/reference/functions/get_theme_root/) `wp-includes/theme.php` | Retrieves path to themes directory. |
| [get\_theme\_root\_uri()](https://developer.wordpress.org/reference/functions/get_theme_root_uri/) `wp-includes/theme.php` | Retrieves URI for themes directory. |
| [validate\_current\_theme()](https://developer.wordpress.org/reference/functions/validate_current_theme/) `wp-includes/theme.php` | Checks that the active theme has the required files. |
| [get\_theme\_mod()](https://developer.wordpress.org/reference/functions/get_theme_mod/) `wp-includes/theme.php` | Retrieves theme modification value for the active theme. |
| [get\_stylesheet\_directory()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory/) `wp-includes/theme.php` | Retrieves stylesheet directory path for the active theme. |
| [get\_stylesheet\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory_uri/) `wp-includes/theme.php` | Retrieves stylesheet directory URI for the active theme. |
| [get\_stylesheet\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_uri/) `wp-includes/theme.php` | Retrieves stylesheet URI for the active theme. |
| [get\_locale\_stylesheet\_uri()](https://developer.wordpress.org/reference/functions/get_locale_stylesheet_uri/) `wp-includes/theme.php` | Retrieves the localized stylesheet URI. |
| [get\_template()](https://developer.wordpress.org/reference/functions/get_template/) `wp-includes/theme.php` | Retrieves name of the active theme. |
| [get\_template\_directory()](https://developer.wordpress.org/reference/functions/get_template_directory/) `wp-includes/theme.php` | Retrieves template directory path for the active theme. |
| [get\_template\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_template_directory_uri/) `wp-includes/theme.php` | Retrieves template directory URI for the active theme. |
| [search\_theme\_directories()](https://developer.wordpress.org/reference/functions/search_theme_directories/) `wp-includes/theme.php` | Searches all registered theme directories for complete and valid themes. |
| [get\_stylesheet()](https://developer.wordpress.org/reference/functions/get_stylesheet/) `wp-includes/theme.php` | Retrieves name of the current stylesheet. |
| [sanitize\_text\_field()](https://developer.wordpress.org/reference/functions/sanitize_text_field/) `wp-includes/formatting.php` | Sanitizes a string from user input or from the database. |
| [sanitize\_mime\_type()](https://developer.wordpress.org/reference/functions/sanitize_mime_type/) `wp-includes/formatting.php` | Sanitizes a mime type |
| [sanitize\_trackback\_urls()](https://developer.wordpress.org/reference/functions/sanitize_trackback_urls/) `wp-includes/formatting.php` | Sanitizes space or carriage return separated URLs that are used to send trackbacks. |
| [esc\_textarea()](https://developer.wordpress.org/reference/functions/esc_textarea/) `wp-includes/formatting.php` | Escaping for textarea values. |
| [tag\_escape()](https://developer.wordpress.org/reference/functions/tag_escape/) `wp-includes/formatting.php` | Escapes an HTML tag name. |
| [sanitize\_option()](https://developer.wordpress.org/reference/functions/sanitize_option/) `wp-includes/formatting.php` | Sanitizes various option values based on the nature of the option. |
| [wp\_parse\_str()](https://developer.wordpress.org/reference/functions/wp_parse_str/) `wp-includes/formatting.php` | Parses a string into variables to be stored in an array. |
| [wp\_sprintf()](https://developer.wordpress.org/reference/functions/wp_sprintf/) `wp-includes/formatting.php` | WordPress’ implementation of PHP sprintf() with filters. |
| [wp\_sprintf\_l()](https://developer.wordpress.org/reference/functions/wp_sprintf_l/) `wp-includes/formatting.php` | Localizes list items before the rest of the content. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [esc\_js()](https://developer.wordpress.org/reference/functions/esc_js/) `wp-includes/formatting.php` | Escapes single quotes, `"`, ``, `&amp;`, and fixes line endings. |
| [esc\_html()](https://developer.wordpress.org/reference/functions/esc_html/) `wp-includes/formatting.php` | Escaping for HTML blocks. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [wp\_htmledit\_pre()](https://developer.wordpress.org/reference/functions/wp_htmledit_pre/) `wp-includes/deprecated.php` | Formats text for the HTML editor. |
| [sanitize\_email()](https://developer.wordpress.org/reference/functions/sanitize_email/) `wp-includes/formatting.php` | Strips out all characters that are not allowable in an email. |
| [human\_time\_diff()](https://developer.wordpress.org/reference/functions/human_time_diff/) `wp-includes/formatting.php` | Determines the difference between two timestamps. |
| [wp\_trim\_excerpt()](https://developer.wordpress.org/reference/functions/wp_trim_excerpt/) `wp-includes/formatting.php` | Generates an excerpt from the content, if needed. |
| [wp\_trim\_words()](https://developer.wordpress.org/reference/functions/wp_trim_words/) `wp-includes/formatting.php` | Trims text to a certain number of words. |
| [ent2ncr()](https://developer.wordpress.org/reference/functions/ent2ncr/) `wp-includes/formatting.php` | Converts named entities into numbered entities. |
| [wp\_richedit\_pre()](https://developer.wordpress.org/reference/functions/wp_richedit_pre/) `wp-includes/deprecated.php` | Formats text for the rich text editor. |
| [translate\_smiley()](https://developer.wordpress.org/reference/functions/translate_smiley/) `wp-includes/formatting.php` | Converts one smiley code to the icon graphic file equivalent. |
| [is\_email()](https://developer.wordpress.org/reference/functions/is_email/) `wp-includes/formatting.php` | Verifies that an email is valid. |
| [sanitize\_file\_name()](https://developer.wordpress.org/reference/functions/sanitize_file_name/) `wp-includes/formatting.php` | Sanitizes a filename, replacing whitespace with dashes. |
| [sanitize\_user()](https://developer.wordpress.org/reference/functions/sanitize_user/) `wp-includes/formatting.php` | Sanitizes a username, stripping out unsafe characters. |
| [sanitize\_key()](https://developer.wordpress.org/reference/functions/sanitize_key/) `wp-includes/formatting.php` | Sanitizes a string key. |
| [sanitize\_title()](https://developer.wordpress.org/reference/functions/sanitize_title/) `wp-includes/formatting.php` | Sanitizes a string into a slug, which can be used in URLs or HTML attributes. |
| [sanitize\_html\_class()](https://developer.wordpress.org/reference/functions/sanitize_html_class/) `wp-includes/formatting.php` | Sanitizes an HTML classname to ensure it only contains valid characters. |
| [format\_to\_edit()](https://developer.wordpress.org/reference/functions/format_to_edit/) `wp-includes/formatting.php` | Acts on text which is about to be edited. |
| [wptexturize()](https://developer.wordpress.org/reference/functions/wptexturize/) `wp-includes/formatting.php` | Replaces common plain text characters with formatted entities. |
| [get\_avatar()](https://developer.wordpress.org/reference/functions/get_avatar/) `wp-includes/pluggable.php` | Retrieves the avatar `<img>` tag for a user, email address, MD5 hash, comment, or post. |
| [wp\_password\_change\_notification()](https://developer.wordpress.org/reference/functions/wp_password_change_notification/) `wp-includes/pluggable.php` | Notifies the blog admin of a user changing password, normally via email. |
| [wp\_new\_user\_notification()](https://developer.wordpress.org/reference/functions/wp_new_user_notification/) `wp-includes/pluggable.php` | Emails login credentials to a newly-registered user. |
| [wp\_nonce\_tick()](https://developer.wordpress.org/reference/functions/wp_nonce_tick/) `wp-includes/pluggable.php` | Returns the time-dependent variable for nonce creation. |
| [wp\_verify\_nonce()](https://developer.wordpress.org/reference/functions/wp_verify_nonce/) `wp-includes/pluggable.php` | Verifies that a correct security nonce was used with time limit. |
| [wp\_create\_nonce()](https://developer.wordpress.org/reference/functions/wp_create_nonce/) `wp-includes/pluggable.php` | Creates a cryptographic token tied to a specific action, user, user session, and window of time. |
| [wp\_salt()](https://developer.wordpress.org/reference/functions/wp_salt/) `wp-includes/pluggable.php` | Returns a salt to add to hashes. |
| [wp\_hash\_password()](https://developer.wordpress.org/reference/functions/wp_hash_password/) `wp-includes/pluggable.php` | Creates a hash of a plain text password. |
| [wp\_check\_password()](https://developer.wordpress.org/reference/functions/wp_check_password/) `wp-includes/pluggable.php` | Checks a plaintext password against a hashed password. |
| [wp\_generate\_password()](https://developer.wordpress.org/reference/functions/wp_generate_password/) `wp-includes/pluggable.php` | Generates a random password drawn from the defined set of characters. |
| [wp\_redirect()](https://developer.wordpress.org/reference/functions/wp_redirect/) `wp-includes/pluggable.php` | Redirects to another page. |
| [wp\_safe\_redirect()](https://developer.wordpress.org/reference/functions/wp_safe_redirect/) `wp-includes/pluggable.php` | Performs a safe (local) redirect, using [wp\_redirect()](https://developer.wordpress.org/reference/functions/wp_redirect/) . |
| [wp\_validate\_redirect()](https://developer.wordpress.org/reference/functions/wp_validate_redirect/) `wp-includes/pluggable.php` | Validates a URL for use in a redirect. |
| [wp\_notify\_postauthor()](https://developer.wordpress.org/reference/functions/wp_notify_postauthor/) `wp-includes/pluggable.php` | Notifies an author (and/or others) of a comment/trackback/pingback on a post. |
| [wp\_notify\_moderator()](https://developer.wordpress.org/reference/functions/wp_notify_moderator/) `wp-includes/pluggable.php` | Notifies the moderator of the site about a new comment that is awaiting approval. |
| [wp\_set\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_set_auth_cookie/) `wp-includes/pluggable.php` | Sets the authentication cookies based on user ID. |
| [wp\_clear\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_clear_auth_cookie/) `wp-includes/pluggable.php` | Removes all of the cookies associated with authentication. |
| [auth\_redirect()](https://developer.wordpress.org/reference/functions/auth_redirect/) `wp-includes/pluggable.php` | Checks if a user is logged in, if not it redirects them to the login page. |
| [wp\_authenticate()](https://developer.wordpress.org/reference/functions/wp_authenticate/) `wp-includes/pluggable.php` | Authenticates a user, confirming the login credentials are valid. |
| [wp\_generate\_auth\_cookie()](https://developer.wordpress.org/reference/functions/wp_generate_auth_cookie/) `wp-includes/pluggable.php` | Generates authentication cookie contents. |
| [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) `wp-includes/pluggable.php` | Sends an email, similar to PHP’s mail function. |
| [the\_search\_query()](https://developer.wordpress.org/reference/functions/the_search_query/) `wp-includes/general-template.php` | Displays the contents of the search query variable. |
| [wp\_admin\_css\_uri()](https://developer.wordpress.org/reference/functions/wp_admin_css_uri/) `wp-includes/general-template.php` | Displays the URL of a WordPress admin CSS file. |
| [wp\_generator()](https://developer.wordpress.org/reference/functions/wp_generator/) `wp-includes/general-template.php` | Displays the XHTML generator that is generated on the wp\_head hook. |
| [paginate\_links()](https://developer.wordpress.org/reference/functions/paginate_links/) `wp-includes/general-template.php` | Retrieves paginated links for archive post pages. |
| [wp\_admin\_css()](https://developer.wordpress.org/reference/functions/wp_admin_css/) `wp-includes/general-template.php` | Enqueues or directly prints a stylesheet link to the specified CSS file. |
| [the\_generator()](https://developer.wordpress.org/reference/functions/the_generator/) `wp-includes/general-template.php` | Displays the generator XML or Comment for RSS, ATOM, etc. |
| [get\_the\_generator()](https://developer.wordpress.org/reference/functions/get_the_generator/) `wp-includes/general-template.php` | Creates the generator XML or Comment for RSS, ATOM, etc. |
| [feed\_links()](https://developer.wordpress.org/reference/functions/feed_links/) `wp-includes/general-template.php` | Displays the links to the general feeds. |
| [feed\_links\_extra()](https://developer.wordpress.org/reference/functions/feed_links_extra/) `wp-includes/general-template.php` | Displays the links to the extra feeds such as category feeds. |
| [user\_can\_richedit()](https://developer.wordpress.org/reference/functions/user_can_richedit/) `wp-includes/general-template.php` | Determines whether the user can access the visual editor. |
| [wp\_default\_editor()](https://developer.wordpress.org/reference/functions/wp_default_editor/) `wp-includes/general-template.php` | Finds out which editor should be displayed by default. |
| [get\_search\_query()](https://developer.wordpress.org/reference/functions/get_search_query/) `wp-includes/general-template.php` | Retrieves the contents of the search WordPress query variable. |
| [get\_the\_modified\_date()](https://developer.wordpress.org/reference/functions/get_the_modified_date/) `wp-includes/general-template.php` | Retrieves the date on which the post was last modified. |
| [the\_time()](https://developer.wordpress.org/reference/functions/the_time/) `wp-includes/general-template.php` | Displays the time of the post. |
| [get\_the\_time()](https://developer.wordpress.org/reference/functions/get_the_time/) `wp-includes/general-template.php` | Retrieves the time of the post. |
| [get\_post\_time()](https://developer.wordpress.org/reference/functions/get_post_time/) `wp-includes/general-template.php` | Retrieves the localized time of the post. |
| [the\_modified\_time()](https://developer.wordpress.org/reference/functions/the_modified_time/) `wp-includes/general-template.php` | Displays the time at which the post was last modified. |
| [get\_the\_modified\_time()](https://developer.wordpress.org/reference/functions/get_the_modified_time/) `wp-includes/general-template.php` | Retrieves the time at which the post was last modified. |
| [get\_post\_modified\_time()](https://developer.wordpress.org/reference/functions/get_post_modified_time/) `wp-includes/general-template.php` | Retrieves the time at which the post was last modified. |
| [the\_weekday()](https://developer.wordpress.org/reference/functions/the_weekday/) `wp-includes/general-template.php` | Displays the localized weekday for the post. |
| [the\_weekday\_date()](https://developer.wordpress.org/reference/functions/the_weekday_date/) `wp-includes/general-template.php` | Displays the localized weekday for the post. |
| [get\_archives\_link()](https://developer.wordpress.org/reference/functions/get_archives_link/) `wp-includes/general-template.php` | Retrieves archive link content based on predefined or custom code. |
| [wp\_get\_archives()](https://developer.wordpress.org/reference/functions/wp_get_archives/) `wp-includes/general-template.php` | Displays archive links based on type and format. |
| [get\_calendar()](https://developer.wordpress.org/reference/functions/get_calendar/) `wp-includes/general-template.php` | Displays calendar with days that have posts as links. |
| [the\_date()](https://developer.wordpress.org/reference/functions/the_date/) `wp-includes/general-template.php` | Displays or retrieves the date of the post (once per date). |
| [get\_the\_date()](https://developer.wordpress.org/reference/functions/get_the_date/) `wp-includes/general-template.php` | Retrieves the date of the post. |
| [the\_modified\_date()](https://developer.wordpress.org/reference/functions/the_modified_date/) `wp-includes/general-template.php` | Displays the date on which the post was last modified. |
| [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/) `wp-includes/general-template.php` | Retrieves information about the current site. |
| [single\_post\_title()](https://developer.wordpress.org/reference/functions/single_post_title/) `wp-includes/general-template.php` | Displays or retrieves page title for post. |
| [wp\_title()](https://developer.wordpress.org/reference/functions/wp_title/) `wp-includes/general-template.php` | Displays or retrieves page title for all areas of blog. |
| [post\_type\_archive\_title()](https://developer.wordpress.org/reference/functions/post_type_archive_title/) `wp-includes/general-template.php` | Displays or retrieves title for a post type archive. |
| [single\_term\_title()](https://developer.wordpress.org/reference/functions/single_term_title/) `wp-includes/general-template.php` | Displays or retrieves page title for taxonomy term archive. |
| [wp\_loginout()](https://developer.wordpress.org/reference/functions/wp_loginout/) `wp-includes/general-template.php` | Displays the Log In/Out link. |
| [wp\_logout\_url()](https://developer.wordpress.org/reference/functions/wp_logout_url/) `wp-includes/general-template.php` | Retrieves the logout URL. |
| [wp\_login\_url()](https://developer.wordpress.org/reference/functions/wp_login_url/) `wp-includes/general-template.php` | Retrieves the login URL. |
| [wp\_registration\_url()](https://developer.wordpress.org/reference/functions/wp_registration_url/) `wp-includes/general-template.php` | Returns the URL that allows the user to register on the site. |
| [wp\_login\_form()](https://developer.wordpress.org/reference/functions/wp_login_form/) `wp-includes/general-template.php` | Provides a simple login form for use anywhere within WordPress. |
| [wp\_lostpassword\_url()](https://developer.wordpress.org/reference/functions/wp_lostpassword_url/) `wp-includes/general-template.php` | Returns the URL that allows the user to reset the lost password. |
| [wp\_register()](https://developer.wordpress.org/reference/functions/wp_register/) `wp-includes/general-template.php` | Displays the Registration or Admin link. |
| [get\_search\_form()](https://developer.wordpress.org/reference/functions/get_search_form/) `wp-includes/general-template.php` | Displays search form. |
| [get\_theme\_data()](https://developer.wordpress.org/reference/functions/get_theme_data/) `wp-includes/deprecated.php` | Retrieve theme data from parsed theme file. |
| [get\_boundary\_post\_rel\_link()](https://developer.wordpress.org/reference/functions/get_boundary_post_rel_link/) `wp-includes/deprecated.php` | Get boundary post relational link. |
| [get\_index\_rel\_link()](https://developer.wordpress.org/reference/functions/get_index_rel_link/) `wp-includes/deprecated.php` | Get site index relational link. |
| [get\_parent\_post\_rel\_link()](https://developer.wordpress.org/reference/functions/get_parent_post_rel_link/) `wp-includes/deprecated.php` | Get parent post relational link. |
| [get\_attachment\_icon\_src()](https://developer.wordpress.org/reference/functions/get_attachment_icon_src/) `wp-includes/deprecated.php` | Retrieve icon URL and Path. |
| [get\_attachment\_icon()](https://developer.wordpress.org/reference/functions/get_attachment_icon/) `wp-includes/deprecated.php` | Retrieve HTML content of icon attachment image element. |
| [get\_attachment\_innerHTML()](https://developer.wordpress.org/reference/functions/get_attachment_innerhtml/) `wp-includes/deprecated.php` | Retrieve HTML content of image element. |
| [the\_content\_rss()](https://developer.wordpress.org/reference/functions/the_content_rss/) `wp-includes/deprecated.php` | Display the post content for the feed. |
| [get\_links\_list()](https://developer.wordpress.org/reference/functions/get_links_list/) `wp-includes/deprecated.php` | Output entire list of links by category. |
| [safecss\_filter\_attr()](https://developer.wordpress.org/reference/functions/safecss_filter_attr/) `wp-includes/kses.php` | Filters an inline style attribute and removes disallowed rules. |
| [previous\_post()](https://developer.wordpress.org/reference/functions/previous_post/) `wp-includes/deprecated.php` | Prints a link to the previous post. |
| [next\_post()](https://developer.wordpress.org/reference/functions/next_post/) `wp-includes/deprecated.php` | Prints link to the next post. |
| [WP\_Theme::get\_allowed()](https://developer.wordpress.org/reference/classes/wp_theme/get_allowed/) `wp-includes/class-wp-theme.php` | Returns array of stylesheet names of themes allowed on the site or network. |
| [WP\_Theme::get\_allowed\_on\_network()](https://developer.wordpress.org/reference/classes/wp_theme/get_allowed_on_network/) `wp-includes/class-wp-theme.php` | Returns array of stylesheet names of themes allowed on the network. |
| [WP\_Theme::get\_allowed\_on\_site()](https://developer.wordpress.org/reference/classes/wp_theme/get_allowed_on_site/) `wp-includes/class-wp-theme.php` | Returns array of stylesheet names of themes allowed on the site. |
| [wp\_kses\_allowed\_html()](https://developer.wordpress.org/reference/functions/wp_kses_allowed_html/) `wp-includes/kses.php` | Returns an array of allowed HTML tags and attributes for a given context. |
| [wp\_kses\_hook()](https://developer.wordpress.org/reference/functions/wp_kses_hook/) `wp-includes/kses.php` | You add any KSES hooks here. |
| [WP\_Theme::get\_page\_templates()](https://developer.wordpress.org/reference/classes/wp_theme/get_page_templates/) `wp-includes/class-wp-theme.php` | Returns the theme’s post templates for a given post type. |
| [WP\_Theme::scandir()](https://developer.wordpress.org/reference/classes/wp_theme/scandir/) `wp-includes/class-wp-theme.php` | Scans a directory for files of a certain extension. |
| [WP::handle\_404()](https://developer.wordpress.org/reference/classes/wp/handle_404/) `wp-includes/class-wp.php` | Set the Headers for 404, if nothing is found for requested URL. |
| [WP\_Theme::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_theme/__construct/) `wp-includes/class-wp-theme.php` | Constructor for [WP\_Theme](https://developer.wordpress.org/reference/classes/wp_theme/). |
| [wp\_is\_mobile()](https://developer.wordpress.org/reference/functions/wp_is_mobile/) `wp-includes/vars.php` | Test if the current browser runs on a mobile device (smart phone, tablet, etc.). |
| [WP::parse\_request()](https://developer.wordpress.org/reference/classes/wp/parse_request/) `wp-includes/class-wp.php` | Parses the request to find the correct WordPress query. |
| [WP::send\_headers()](https://developer.wordpress.org/reference/classes/wp/send_headers/) `wp-includes/class-wp.php` | Sends additional HTTP headers for caching, content type, etc. |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |
| [WP\_Query::parse\_search()](https://developer.wordpress.org/reference/classes/wp_query/parse_search/) `wp-includes/class-wp-query.php` | Generates SQL for the WHERE clause based on passed search terms. |
| [WP\_Query::get\_search\_stopwords()](https://developer.wordpress.org/reference/classes/wp_query/get_search_stopwords/) `wp-includes/class-wp-query.php` | Retrieves stopwords used when parsing search terms. |
| [wp\_old\_slug\_redirect()](https://developer.wordpress.org/reference/functions/wp_old_slug_redirect/) `wp-includes/query.php` | Redirect old slugs to the correct permalink. |
| [get\_tags()](https://developer.wordpress.org/reference/functions/get_tags/) `wp-includes/category.php` | Retrieves all post tags. |
| [WP\_Image\_Editor\_Imagick::\_save()](https://developer.wordpress.org/reference/classes/wp_image_editor_imagick/_save/) `wp-includes/class-wp-image-editor-imagick.php` |  |
| [get\_categories()](https://developer.wordpress.org/reference/functions/get_categories/) `wp-includes/category.php` | Retrieves a list of category objects. |
| [wp\_debug\_mode()](https://developer.wordpress.org/reference/functions/wp_debug_mode/) `wp-includes/load.php` | Sets PHP error reporting based on WordPress debug settings. |
| [wp\_start\_object\_cache()](https://developer.wordpress.org/reference/functions/wp_start_object_cache/) `wp-includes/load.php` | Starts the WordPress object cache. |
| [WP\_Http\_Cookie::getHeaderValue()](https://developer.wordpress.org/reference/classes/wp_http_cookie/getheadervalue/) `wp-includes/class-wp-http-cookie.php` | Convert cookie name and value back to header string. |
| [WP\_Http\_Encoding::accept\_encoding()](https://developer.wordpress.org/reference/classes/wp_http_encoding/accept_encoding/) `wp-includes/class-wp-http-encoding.php` | What encoding types to accept and their priority values. |
| [WP\_HTTP\_Proxy::send\_through\_proxy()](https://developer.wordpress.org/reference/classes/wp_http_proxy/send_through_proxy/) `wp-includes/class-wp-http-proxy.php` | Determines whether the request should be sent through a proxy. |
| [WP\_Http\_Curl::test()](https://developer.wordpress.org/reference/classes/wp_http_curl/test/) `wp-includes/class-wp-http-curl.php` | Determines whether this class can be used for retrieving a URL. |
| [WP\_Http\_Curl::request()](https://developer.wordpress.org/reference/classes/wp_http_curl/request/) `wp-includes/class-wp-http-curl.php` | Send a HTTP request to a URI using cURL extension. |
| [WP\_Http\_Streams::request()](https://developer.wordpress.org/reference/classes/wp_http_streams/request/) `wp-includes/class-wp-http-streams.php` | Send a HTTP request to a URI using PHP Streams. |
| [WP\_Http\_Streams::test()](https://developer.wordpress.org/reference/classes/wp_http_streams/test/) `wp-includes/class-wp-http-streams.php` | Determines whether this class can be used for retrieving a URL. |
| [WP\_Http::block\_request()](https://developer.wordpress.org/reference/classes/wp_http/block_request/) `wp-includes/class-wp-http.php` | Determines whether an HTTP API request to the given URL should be blocked. |
| [WP\_Http::\_dispatch\_request()](https://developer.wordpress.org/reference/classes/wp_http/_dispatch_request/) `wp-includes/class-wp-http.php` | Dispatches a HTTP request to a supporting transport. |
| [WP\_Http::request()](https://developer.wordpress.org/reference/classes/wp_http/request/) `wp-includes/class-wp-http.php` | Send an HTTP request to a URI. |
| [wp\_allowed\_protocols()](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/) `wp-includes/functions.php` | Retrieves a list of protocols to allow in HTML attributes. |
| [wp\_checkdate()](https://developer.wordpress.org/reference/functions/wp_checkdate/) `wp-includes/functions.php` | Tests if the supplied date is valid for the Gregorian calendar. |
| [wp\_auth\_check\_load()](https://developer.wordpress.org/reference/functions/wp_auth_check_load/) `wp-includes/functions.php` | Loads the auth check for monitoring whether the user is still logged in. |
| [wp\_auth\_check\_html()](https://developer.wordpress.org/reference/functions/wp_auth_check_html/) `wp-includes/functions.php` | Outputs the HTML that shows the wp-login dialog when the user is no longer logged in. |
| [get\_file\_data()](https://developer.wordpress.org/reference/functions/get_file_data/) `wp-includes/functions.php` | Retrieves metadata from a file. |
| [\_deprecated\_function()](https://developer.wordpress.org/reference/functions/_deprecated_function/) `wp-includes/functions.php` | Marks a function as deprecated and inform when it has been used. |
| [\_deprecated\_file()](https://developer.wordpress.org/reference/functions/_deprecated_file/) `wp-includes/functions.php` | Marks a file as deprecated and inform when it has been used. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |
| [iis7\_supports\_permalinks()](https://developer.wordpress.org/reference/functions/iis7_supports_permalinks/) `wp-includes/functions.php` | Checks if IIS 7+ supports pretty permalinks. |
| [smilies\_init()](https://developer.wordpress.org/reference/functions/smilies_init/) `wp-includes/functions.php` | Converts smiley code to the icon graphic file equivalent. |
| [wp\_maybe\_load\_widgets()](https://developer.wordpress.org/reference/functions/wp_maybe_load_widgets/) `wp-includes/functions.php` | Determines if Widgets library should be loaded. |
| [wp\_check\_filetype\_and\_ext()](https://developer.wordpress.org/reference/functions/wp_check_filetype_and_ext/) `wp-includes/functions.php` | Attempts to determine the real file type of a file. |
| [wp\_get\_mime\_types()](https://developer.wordpress.org/reference/functions/wp_get_mime_types/) `wp-includes/functions.php` | Retrieves the list of mime types and file extensions. |
| [wp\_upload\_bits()](https://developer.wordpress.org/reference/functions/wp_upload_bits/) `wp-includes/functions.php` | Creates a file in the upload folder with given content. |
| [get\_allowed\_mime\_types()](https://developer.wordpress.org/reference/functions/get_allowed_mime_types/) `wp-includes/functions.php` | Retrieves the list of allowed mime types and file extensions. |
| [wp\_die()](https://developer.wordpress.org/reference/functions/wp_die/) `wp-includes/functions.php` | Kills WordPress execution and displays HTML page with an error message. |
| [do\_robots()](https://developer.wordpress.org/reference/functions/do_robots/) `wp-includes/functions.php` | Displays the default robots.txt file content. |
| [wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) `wp-includes/functions.php` | Returns an array containing the current upload directory’s path and URL. |
| [wp\_unique\_filename()](https://developer.wordpress.org/reference/functions/wp_unique_filename/) `wp-includes/functions.php` | Gets a filename that is sanitized and unique for the given directory. |
| [status\_header()](https://developer.wordpress.org/reference/functions/status_header/) `wp-includes/functions.php` | Sets HTTP status header. |
| [wp\_get\_nocache\_headers()](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/) `wp-includes/functions.php` | Gets the HTTP header information to prevent caching. |
| [date\_i18n()](https://developer.wordpress.org/reference/functions/date_i18n/) `wp-includes/functions.php` | Retrieves the date in localized format, based on a sum of Unix timestamp and timezone offset in seconds. |
| [number\_format\_i18n()](https://developer.wordpress.org/reference/functions/number_format_i18n/) `wp-includes/functions.php` | Converts float number to format based on the locale. |
| [do\_enclose()](https://developer.wordpress.org/reference/functions/do_enclose/) `wp-includes/functions.php` | Checks content for video and audio links to add as enclosures. |
| [WP\_Nav\_Menu\_Widget::widget()](https://developer.wordpress.org/reference/classes/wp_nav_menu_widget/widget/) `wp-includes/widgets/class-wp-nav-menu-widget.php` | Outputs the content for the current Navigation Menu widget instance. |
| [WP\_Widget\_Tag\_Cloud::widget()](https://developer.wordpress.org/reference/classes/wp_widget_tag_cloud/widget/) `wp-includes/widgets/class-wp-widget-tag-cloud.php` | Outputs the content for the current Tag Cloud widget instance. |
| [WP\_Widget\_RSS::widget()](https://developer.wordpress.org/reference/classes/wp_widget_rss/widget/) `wp-includes/widgets/class-wp-widget-rss.php` | Outputs the content for the current RSS widget instance. |
| [WP\_Widget\_Recent\_Posts::widget()](https://developer.wordpress.org/reference/classes/wp_widget_recent_posts/widget/) `wp-includes/widgets/class-wp-widget-recent-posts.php` | Outputs the content for the current Recent Posts widget instance. |
| [WP\_Widget\_Recent\_Comments::recent\_comments\_style()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/recent_comments_style/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Outputs the default styles for the Recent Comments widget. |
| [WP\_Widget\_Recent\_Comments::widget()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/widget/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Outputs the content for the current Recent Comments widget instance. |
| [WP\_Widget\_Categories::widget()](https://developer.wordpress.org/reference/classes/wp_widget_categories/widget/) `wp-includes/widgets/class-wp-widget-categories.php` | Outputs the content for the current Categories widget instance. |
| [WP\_Widget\_Calendar::widget()](https://developer.wordpress.org/reference/classes/wp_widget_calendar/widget/) `wp-includes/widgets/class-wp-widget-calendar.php` | Outputs the content for the current Calendar widget instance. |
| [WP\_Widget\_Text::widget()](https://developer.wordpress.org/reference/classes/wp_widget_text/widget/) `wp-includes/widgets/class-wp-widget-text.php` | Outputs the content for the current Text widget instance. |
| [WP\_Widget\_Text::form()](https://developer.wordpress.org/reference/classes/wp_widget_text/form/) `wp-includes/widgets/class-wp-widget-text.php` | Outputs the Text widget settings form. |
| [WP\_Widget\_Archives::widget()](https://developer.wordpress.org/reference/classes/wp_widget_archives/widget/) `wp-includes/widgets/class-wp-widget-archives.php` | Outputs the content for the current Archives widget instance. |
| [WP\_Widget\_Meta::widget()](https://developer.wordpress.org/reference/classes/wp_widget_meta/widget/) `wp-includes/widgets/class-wp-widget-meta.php` | Outputs the content for the current Meta widget instance. |
| [WP\_Widget\_Search::widget()](https://developer.wordpress.org/reference/classes/wp_widget_search/widget/) `wp-includes/widgets/class-wp-widget-search.php` | Outputs the content for the current Search widget instance. |
| [WP\_Widget\_Links::widget()](https://developer.wordpress.org/reference/classes/wp_widget_links/widget/) `wp-includes/widgets/class-wp-widget-links.php` | Outputs the content for the current Links widget instance. |
| [WP\_Widget\_Pages::widget()](https://developer.wordpress.org/reference/classes/wp_widget_pages/widget/) `wp-includes/widgets/class-wp-widget-pages.php` | Outputs the content for the current Pages widget instance. |
| [WP\_Embed::cache\_oembed()](https://developer.wordpress.org/reference/classes/wp_embed/cache_oembed/) `wp-includes/class-wp-embed.php` | Triggers a caching of all oEmbed results. |
| [WP\_Embed::maybe\_make\_link()](https://developer.wordpress.org/reference/classes/wp_embed/maybe_make_link/) `wp-includes/class-wp-embed.php` | Conditionally makes a hyperlink based on an internal class variable. |
| [WP\_Embed::shortcode()](https://developer.wordpress.org/reference/classes/wp_embed/shortcode/) `wp-includes/class-wp-embed.php` | The [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) callback function. |
| [WP\_Feed\_Cache\_Transient::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_feed_cache_transient/__construct/) `wp-includes/class-wp-feed-cache-transient.php` | Creates a new (transient) cache object. |
| [\_update\_post\_term\_count()](https://developer.wordpress.org/reference/functions/_update_post_term_count/) `wp-includes/taxonomy.php` | Updates term count based on object types of the current taxonomy. |
| [get\_term\_link()](https://developer.wordpress.org/reference/functions/get_term_link/) `wp-includes/taxonomy.php` | Generates a permalink for a taxonomy term archive. |
| [get\_ancestors()](https://developer.wordpress.org/reference/functions/get_ancestors/) `wp-includes/taxonomy.php` | Gets an array of ancestor IDs for a given object. |
| [wp\_unique\_term\_slug()](https://developer.wordpress.org/reference/functions/wp_unique_term_slug/) `wp-includes/taxonomy.php` | Makes term slug unique, if it isn’t already. |
| [wp\_update\_term()](https://developer.wordpress.org/reference/functions/wp_update_term/) `wp-includes/taxonomy.php` | Updates term based on arguments provided. |
| [wp\_get\_object\_terms()](https://developer.wordpress.org/reference/functions/wp_get_object_terms/) `wp-includes/taxonomy.php` | Retrieves the terms associated with the given object(s), in the supplied taxonomies. |
| [wp\_insert\_term()](https://developer.wordpress.org/reference/functions/wp_insert_term/) `wp-includes/taxonomy.php` | Adds a new term to the database. |
| [term\_exists()](https://developer.wordpress.org/reference/functions/term_exists/) `wp-includes/taxonomy.php` | Determines whether a taxonomy term exists. |
| [sanitize\_term\_field()](https://developer.wordpress.org/reference/functions/sanitize_term_field/) `wp-includes/taxonomy.php` | Sanitizes the field value in the term based on the context. |
| [get\_terms()](https://developer.wordpress.org/reference/functions/get_terms/) `wp-includes/taxonomy.php` | Retrieves the terms in a given taxonomy or list of taxonomies. |
| [create\_initial\_taxonomies()](https://developer.wordpress.org/reference/functions/create_initial_taxonomies/) `wp-includes/taxonomy.php` | Creates the initial taxonomies. |
| [get\_taxonomy\_labels()](https://developer.wordpress.org/reference/functions/get_taxonomy_labels/) `wp-includes/taxonomy.php` | Builds an object with all taxonomy labels out of a taxonomy object. |
| [get\_term()](https://developer.wordpress.org/reference/functions/get_term/) `wp-includes/taxonomy.php` | Gets all term data from database by term ID. |
| [self\_admin\_url()](https://developer.wordpress.org/reference/functions/self_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for either the current site or the network depending on context. |
| [set\_url\_scheme()](https://developer.wordpress.org/reference/functions/set_url_scheme/) `wp-includes/link-template.php` | Sets the scheme for a URL. |
| [get\_dashboard\_url()](https://developer.wordpress.org/reference/functions/get_dashboard_url/) `wp-includes/link-template.php` | Retrieves the URL to the user’s dashboard. |
| [get\_edit\_profile\_url()](https://developer.wordpress.org/reference/functions/get_edit_profile_url/) `wp-includes/link-template.php` | Retrieves the URL to the user’s profile editor. |
| [wp\_get\_shortlink()](https://developer.wordpress.org/reference/functions/wp_get_shortlink/) `wp-includes/link-template.php` | Returns a shortlink for a post, page, attachment, or site. |
| [the\_shortlink()](https://developer.wordpress.org/reference/functions/the_shortlink/) `wp-includes/link-template.php` | Displays the shortlink for a post. |
| [get\_admin\_url()](https://developer.wordpress.org/reference/functions/get_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for a given site. |
| [includes\_url()](https://developer.wordpress.org/reference/functions/includes_url/) `wp-includes/link-template.php` | Retrieves the URL to the includes directory. |
| [content\_url()](https://developer.wordpress.org/reference/functions/content_url/) `wp-includes/link-template.php` | Retrieves the URL to the content directory. |
| [plugins\_url()](https://developer.wordpress.org/reference/functions/plugins_url/) `wp-includes/link-template.php` | Retrieves a URL within the plugins or mu-plugins directory. |
| [network\_site\_url()](https://developer.wordpress.org/reference/functions/network_site_url/) `wp-includes/link-template.php` | Retrieves the site URL for the current network. |
| [network\_home\_url()](https://developer.wordpress.org/reference/functions/network_home_url/) `wp-includes/link-template.php` | Retrieves the home URL for the current network. |
| [network\_admin\_url()](https://developer.wordpress.org/reference/functions/network_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the network. |
| [user\_admin\_url()](https://developer.wordpress.org/reference/functions/user_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current user. |
| [get\_comments\_pagenum\_link()](https://developer.wordpress.org/reference/functions/get_comments_pagenum_link/) `wp-includes/link-template.php` | Retrieves the comments page number link. |
| [get\_next\_comments\_link()](https://developer.wordpress.org/reference/functions/get_next_comments_link/) `wp-includes/link-template.php` | Retrieves the link to the next comments page. |
| [get\_previous\_comments\_link()](https://developer.wordpress.org/reference/functions/get_previous_comments_link/) `wp-includes/link-template.php` | Retrieves the link to the previous comments page. |
| [get\_home\_url()](https://developer.wordpress.org/reference/functions/get_home_url/) `wp-includes/link-template.php` | Retrieves the URL for a given site where the front end is accessible. |
| [get\_site\_url()](https://developer.wordpress.org/reference/functions/get_site_url/) `wp-includes/link-template.php` | Retrieves the URL for a given site where WordPress application files (e.g. wp-blog-header.php or the wp-admin/ folder) are accessible. |
| [get\_shortcut\_link()](https://developer.wordpress.org/reference/functions/get_shortcut_link/) `wp-includes/deprecated.php` | Retrieves the Press This bookmarklet link. |
| [get\_adjacent\_post\_link()](https://developer.wordpress.org/reference/functions/get_adjacent_post_link/) `wp-includes/link-template.php` | Retrieves the adjacent post link. |
| [get\_pagenum\_link()](https://developer.wordpress.org/reference/functions/get_pagenum_link/) `wp-includes/link-template.php` | Retrieves the link for a page number. |
| [get\_next\_posts\_link()](https://developer.wordpress.org/reference/functions/get_next_posts_link/) `wp-includes/link-template.php` | Retrieves the next posts page link. |
| [get\_previous\_posts\_link()](https://developer.wordpress.org/reference/functions/get_previous_posts_link/) `wp-includes/link-template.php` | Retrieves the previous posts page link. |
| [get\_edit\_user\_link()](https://developer.wordpress.org/reference/functions/get_edit_user_link/) `wp-includes/link-template.php` | Retrieves the edit user link. |
| [get\_adjacent\_post()](https://developer.wordpress.org/reference/functions/get_adjacent_post/) `wp-includes/link-template.php` | Retrieves the adjacent post. |
| [get\_adjacent\_post\_rel\_link()](https://developer.wordpress.org/reference/functions/get_adjacent_post_rel_link/) `wp-includes/link-template.php` | Retrieves the adjacent post relational link. |
| [get\_search\_comments\_feed\_link()](https://developer.wordpress.org/reference/functions/get_search_comments_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the search results comments feed. |
| [get\_post\_type\_archive\_link()](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/) `wp-includes/link-template.php` | Retrieves the permalink for a post type archive. |
| [get\_post\_type\_archive\_feed\_link()](https://developer.wordpress.org/reference/functions/get_post_type_archive_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for a post type archive feed. |
| [get\_edit\_post\_link()](https://developer.wordpress.org/reference/functions/get_edit_post_link/) `wp-includes/link-template.php` | Retrieves the edit post link for post. |
| [edit\_post\_link()](https://developer.wordpress.org/reference/functions/edit_post_link/) `wp-includes/link-template.php` | Displays the edit post link for post. |
| [get\_delete\_post\_link()](https://developer.wordpress.org/reference/functions/get_delete_post_link/) `wp-includes/link-template.php` | Retrieves the delete posts link for post. |
| [get\_edit\_comment\_link()](https://developer.wordpress.org/reference/functions/get_edit_comment_link/) `wp-includes/link-template.php` | Retrieves the edit comment link. |
| [edit\_comment\_link()](https://developer.wordpress.org/reference/functions/edit_comment_link/) `wp-includes/link-template.php` | Displays the edit comment link with formatting. |
| [get\_edit\_bookmark\_link()](https://developer.wordpress.org/reference/functions/get_edit_bookmark_link/) `wp-includes/link-template.php` | Displays the edit bookmark link. |
| [edit\_bookmark\_link()](https://developer.wordpress.org/reference/functions/edit_bookmark_link/) `wp-includes/link-template.php` | Displays the edit bookmark link anchor content. |
| [get\_term\_feed\_link()](https://developer.wordpress.org/reference/functions/get_term_feed_link/) `wp-includes/link-template.php` | Retrieves the feed link for a term. |
| [get\_edit\_tag\_link()](https://developer.wordpress.org/reference/functions/get_edit_tag_link/) `wp-includes/link-template.php` | Retrieves the edit link for a tag. |
| [edit\_tag\_link()](https://developer.wordpress.org/reference/functions/edit_tag_link/) `wp-includes/link-template.php` | Displays or retrieves the edit link for a tag with formatting. |
| [get\_edit\_term\_link()](https://developer.wordpress.org/reference/functions/get_edit_term_link/) `wp-includes/link-template.php` | Retrieves the URL for editing a given term. |
| [edit\_term\_link()](https://developer.wordpress.org/reference/functions/edit_term_link/) `wp-includes/link-template.php` | Displays or retrieves the edit term link with formatting. |
| [get\_search\_link()](https://developer.wordpress.org/reference/functions/get_search_link/) `wp-includes/link-template.php` | Retrieves the permalink for a search. |
| [get\_search\_feed\_link()](https://developer.wordpress.org/reference/functions/get_search_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the search results feed. |
| [get\_month\_link()](https://developer.wordpress.org/reference/functions/get_month_link/) `wp-includes/link-template.php` | Retrieves the permalink for the month archives with year. |
| [get\_day\_link()](https://developer.wordpress.org/reference/functions/get_day_link/) `wp-includes/link-template.php` | Retrieves the permalink for the day archives with year and month. |
| [the\_feed\_link()](https://developer.wordpress.org/reference/functions/the_feed_link/) `wp-includes/link-template.php` | Displays the permalink for the feed type. |
| [get\_feed\_link()](https://developer.wordpress.org/reference/functions/get_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the feed type. |
| [get\_post\_comments\_feed\_link()](https://developer.wordpress.org/reference/functions/get_post_comments_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the post comments feed. |
| [post\_comments\_feed\_link()](https://developer.wordpress.org/reference/functions/post_comments_feed_link/) `wp-includes/link-template.php` | Displays the comment feed link for a post. |
| [get\_author\_feed\_link()](https://developer.wordpress.org/reference/functions/get_author_feed_link/) `wp-includes/link-template.php` | Retrieves the feed link for a given author. |
| [get\_permalink()](https://developer.wordpress.org/reference/functions/get_permalink/) `wp-includes/link-template.php` | Retrieves the full permalink for the current post or post ID. |
| [get\_post\_permalink()](https://developer.wordpress.org/reference/functions/get_post_permalink/) `wp-includes/link-template.php` | Retrieves the permalink for a post of a custom post type. |
| [get\_page\_link()](https://developer.wordpress.org/reference/functions/get_page_link/) `wp-includes/link-template.php` | Retrieves the permalink for the current page or page ID. |
| [\_get\_page\_link()](https://developer.wordpress.org/reference/functions/_get_page_link/) `wp-includes/link-template.php` | Retrieves the page permalink. |
| [get\_attachment\_link()](https://developer.wordpress.org/reference/functions/get_attachment_link/) `wp-includes/link-template.php` | Retrieves the permalink for an attachment. |
| [get\_year\_link()](https://developer.wordpress.org/reference/functions/get_year_link/) `wp-includes/link-template.php` | Retrieves the permalink for the year archives. |
| [the\_permalink()](https://developer.wordpress.org/reference/functions/the_permalink/) `wp-includes/link-template.php` | Displays the permalink for the current post. |
| [user\_trailingslashit()](https://developer.wordpress.org/reference/functions/user_trailingslashit/) `wp-includes/link-template.php` | Retrieves a trailing-slashed string if the site is set for adding trailing slashes. |
| [wp\_version\_check()](https://developer.wordpress.org/reference/functions/wp_version_check/) `wp-includes/update.php` | Checks WordPress version against the newest version. |
| [wp\_update\_plugins()](https://developer.wordpress.org/reference/functions/wp_update_plugins/) `wp-includes/update.php` | Checks for available updates to plugins based on the latest versions hosted on WordPress.org. |
| [wp\_update\_themes()](https://developer.wordpress.org/reference/functions/wp_update_themes/) `wp-includes/update.php` | Checks for available updates to themes based on the latest versions hosted on WordPress.org. |
| [wp\_get\_update\_data()](https://developer.wordpress.org/reference/functions/wp_get_update_data/) `wp-includes/update.php` | Collects counts and UI strings for available updates. |
| [is\_allowed\_http\_origin()](https://developer.wordpress.org/reference/functions/is_allowed_http_origin/) `wp-includes/http.php` | Determines if the HTTP origin is an authorized one. |
| [wp\_http\_validate\_url()](https://developer.wordpress.org/reference/functions/wp_http_validate_url/) `wp-includes/http.php` | Validates a URL for safe use in the HTTP API. |
| [get\_http\_origin()](https://developer.wordpress.org/reference/functions/get_http_origin/) `wp-includes/http.php` | Gets the HTTP Origin of the current request. |
| [get\_allowed\_http\_origins()](https://developer.wordpress.org/reference/functions/get_allowed_http_origins/) `wp-includes/http.php` | Retrieves list of allowed HTTP origins. |
| [WP\_Date\_Query::validate\_column()](https://developer.wordpress.org/reference/classes/wp_date_query/validate_column/) `wp-includes/class-wp-date-query.php` | Validates a column name parameter. |
| [WP\_Date\_Query::get\_sql()](https://developer.wordpress.org/reference/classes/wp_date_query/get_sql/) `wp-includes/class-wp-date-query.php` | Generates WHERE clause to be appended to a main query. |
| [do\_shortcode\_tag()](https://developer.wordpress.org/reference/functions/do_shortcode_tag/) `wp-includes/shortcodes.php` | Regular Expression callable for [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) for calling shortcode hook. |
| [shortcode\_atts()](https://developer.wordpress.org/reference/functions/shortcode_atts/) `wp-includes/shortcodes.php` | Combines user attributes with known attributes and fill in defaults when needed. |
| [strip\_shortcodes()](https://developer.wordpress.org/reference/functions/strip_shortcodes/) `wp-includes/shortcodes.php` | Removes all shortcode tags from the given content. |
| [WP\_Image\_Editor::set\_quality()](https://developer.wordpress.org/reference/classes/wp_image_editor/set_quality/) `wp-includes/class-wp-image-editor.php` | Sets Image Compression quality on a 1-100% scale. |
| [WP\_Image\_Editor::get\_output\_format()](https://developer.wordpress.org/reference/classes/wp_image_editor/get_output_format/) `wp-includes/class-wp-image-editor.php` | Returns preferred mime-type and extension based on provided file’s extension and mime, or current file’s extension and mime. |
| [WP\_oEmbed::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_oembed/__construct/) `wp-includes/class-wp-oembed.php` | Constructor. |
| [WP\_oEmbed::get\_html()](https://developer.wordpress.org/reference/classes/wp_oembed/get_html/) `wp-includes/class-wp-oembed.php` | The do-it-all function that takes a URL and attempts to return the HTML. |
| [WP\_oEmbed::discover()](https://developer.wordpress.org/reference/classes/wp_oembed/discover/) `wp-includes/class-wp-oembed.php` | Attempts to discover link tags at the given URL for an oEmbed provider. |
| [WP\_oEmbed::fetch()](https://developer.wordpress.org/reference/classes/wp_oembed/fetch/) `wp-includes/class-wp-oembed.php` | Connects to an oEmbed provider and returns the result. |
| [WP\_oEmbed::\_fetch\_with\_format()](https://developer.wordpress.org/reference/classes/wp_oembed/_fetch_with_format/) `wp-includes/class-wp-oembed.php` | Fetches result from an oEmbed provider for a specific format and complete provider URL |
| [WP\_oEmbed::data2html()](https://developer.wordpress.org/reference/classes/wp_oembed/data2html/) `wp-includes/class-wp-oembed.php` | Converts a data object from [WP\_oEmbed::fetch()](https://developer.wordpress.org/reference/classes/wp_oembed/fetch/) and returns the HTML. |
| [wp\_admin\_bar\_my\_sites\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_my_sites_menu/) `wp-includes/admin-bar.php` | Adds the “My Sites/\[Site Name\]” menu and all submenus. |
| [is\_admin\_bar\_showing()](https://developer.wordpress.org/reference/functions/is_admin_bar_showing/) `wp-includes/admin-bar.php` | Determines whether the admin bar should be showing. |
| [\_wp\_admin\_bar\_init()](https://developer.wordpress.org/reference/functions/_wp_admin_bar_init/) `wp-includes/admin-bar.php` | Instantiates the admin bar object and set it up as a global for access elsewhere. |
| [get\_the\_category\_rss()](https://developer.wordpress.org/reference/functions/get_the_category_rss/) `wp-includes/feed.php` | Retrieves all of the post categories, formatted for use in feeds. |
| [rss\_enclosure()](https://developer.wordpress.org/reference/functions/rss_enclosure/) `wp-includes/feed.php` | Displays the rss enclosure for the current post. |
| [atom\_enclosure()](https://developer.wordpress.org/reference/functions/atom_enclosure/) `wp-includes/feed.php` | Displays the atom enclosure for the current post. |
| [self\_link()](https://developer.wordpress.org/reference/functions/self_link/) `wp-includes/feed.php` | Displays the link for the currently displayed feed in a XSS safe way. |
| [feed\_content\_type()](https://developer.wordpress.org/reference/functions/feed_content_type/) `wp-includes/feed.php` | Returns the content type for specified feed type. |
| [fetch\_feed()](https://developer.wordpress.org/reference/functions/fetch_feed/) `wp-includes/feed.php` | Builds SimplePie object based on RSS or Atom feed from URL. |
| [get\_the\_content\_feed()](https://developer.wordpress.org/reference/functions/get_the_content_feed/) `wp-includes/feed.php` | Retrieves the post content for feeds. |
| [the\_excerpt\_rss()](https://developer.wordpress.org/reference/functions/the_excerpt_rss/) `wp-includes/feed.php` | Displays the post excerpt for the feed. |
| [the\_permalink\_rss()](https://developer.wordpress.org/reference/functions/the_permalink_rss/) `wp-includes/feed.php` | Displays the permalink to the post for use in feeds. |
| [comments\_link\_feed()](https://developer.wordpress.org/reference/functions/comments_link_feed/) `wp-includes/feed.php` | Outputs the link to the comments for the current post in an XML safe way. |
| [comment\_link()](https://developer.wordpress.org/reference/functions/comment_link/) `wp-includes/feed.php` | Displays the link to the comments. |
| [get\_comment\_author\_rss()](https://developer.wordpress.org/reference/functions/get_comment_author_rss/) `wp-includes/feed.php` | Retrieves the current comment author for use in the feeds. |
| [comment\_text\_rss()](https://developer.wordpress.org/reference/functions/comment_text_rss/) `wp-includes/feed.php` | Displays the current comment content for use in the feeds. |
| [get\_bloginfo\_rss()](https://developer.wordpress.org/reference/functions/get_bloginfo_rss/) `wp-includes/feed.php` | Retrieves RSS container for the bloginfo function. |
| [bloginfo\_rss()](https://developer.wordpress.org/reference/functions/bloginfo_rss/) `wp-includes/feed.php` | Displays RSS container for the bloginfo function. |
| [get\_default\_feed()](https://developer.wordpress.org/reference/functions/get_default_feed/) `wp-includes/feed.php` | Retrieves the default feed. |
| [get\_wp\_title\_rss()](https://developer.wordpress.org/reference/functions/get_wp_title_rss/) `wp-includes/feed.php` | Retrieves the blog title for the feed title. |
| [wp\_title\_rss()](https://developer.wordpress.org/reference/functions/wp_title_rss/) `wp-includes/feed.php` | Displays the blog title for display of the feed title. |
| [get\_the\_title\_rss()](https://developer.wordpress.org/reference/functions/get_the_title_rss/) `wp-includes/feed.php` | Retrieves the current post title for the feed. |
| [WP\_Customize\_Setting::value()](https://developer.wordpress.org/reference/classes/wp_customize_setting/value/) `wp-includes/class-wp-customize-setting.php` | Fetch the value of the setting. |
| [WP\_Customize\_Setting::js\_value()](https://developer.wordpress.org/reference/classes/wp_customize_setting/js_value/) `wp-includes/class-wp-customize-setting.php` | Sanitize the setting’s value for use in JavaScript. |
| [WP\_Customize\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_setting/sanitize/) `wp-includes/class-wp-customize-setting.php` | Sanitize an input. |
| [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/) `wp-includes/option.php` | Sets/updates the value of a site transient. |
| [get\_site\_transient()](https://developer.wordpress.org/reference/functions/get_site_transient/) `wp-includes/option.php` | Retrieves the value of a site transient. |
| [get\_transient()](https://developer.wordpress.org/reference/functions/get_transient/) `wp-includes/option.php` | Retrieves the value of a transient. |
| [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/) `wp-includes/option.php` | Sets/updates the value of a transient. |
| [wp\_load\_alloptions()](https://developer.wordpress.org/reference/functions/wp_load_alloptions/) `wp-includes/option.php` | Loads and caches all autoloaded options, if available or all options. |
| [update\_option()](https://developer.wordpress.org/reference/functions/update_option/) `wp-includes/option.php` | Updates the value of an option that was already added. |
| [add\_option()](https://developer.wordpress.org/reference/functions/add_option/) `wp-includes/option.php` | Adds a new option. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [WP\_User\_Query::prepare\_query()](https://developer.wordpress.org/reference/classes/wp_user_query/prepare_query/) `wp-includes/class-wp-user-query.php` | Prepares the query variables. |
| [WP\_User\_Query::query()](https://developer.wordpress.org/reference/classes/wp_user_query/query/) `wp-includes/class-wp-user-query.php` | Executes the query, with the current variables. |
| [wp\_update\_user()](https://developer.wordpress.org/reference/functions/wp_update_user/) `wp-includes/user.php` | Updates a user in the database. |
| [wp\_get\_user\_contact\_methods()](https://developer.wordpress.org/reference/functions/wp_get_user_contact_methods/) `wp-includes/user.php` | Sets up the user contact methods. |
| [check\_password\_reset\_key()](https://developer.wordpress.org/reference/functions/check_password_reset_key/) `wp-includes/user.php` | Retrieves a user row based on password reset key and login. |
| [register\_new\_user()](https://developer.wordpress.org/reference/functions/register_new_user/) `wp-includes/user.php` | Handles registering a new user. |
| [username\_exists()](https://developer.wordpress.org/reference/functions/username_exists/) `wp-includes/user.php` | Determines whether the given username exists. |
| [email\_exists()](https://developer.wordpress.org/reference/functions/email_exists/) `wp-includes/user.php` | Determines whether the given email exists. |
| [validate\_username()](https://developer.wordpress.org/reference/functions/validate_username/) `wp-includes/user.php` | Checks whether a username is valid. |
| [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) `wp-includes/user.php` | Inserts a user into the database. |
| [get\_blogs\_of\_user()](https://developer.wordpress.org/reference/functions/get_blogs_of_user/) `wp-includes/user.php` | Gets the sites a user belongs to. |
| [count\_users()](https://developer.wordpress.org/reference/functions/count_users/) `wp-includes/user.php` | Counts number of users who have each of the user roles. |
| [wp\_dropdown\_users()](https://developer.wordpress.org/reference/functions/wp_dropdown_users/) `wp-includes/user.php` | Creates dropdown HTML content of users. |
| [sanitize\_user\_field()](https://developer.wordpress.org/reference/functions/sanitize_user_field/) `wp-includes/user.php` | Sanitizes user field based on context. |
| [wp\_signon()](https://developer.wordpress.org/reference/functions/wp_signon/) `wp-includes/user.php` | Authenticates and logs a user in with ‘remember’ capability. |
| [wp\_authenticate\_username\_password()](https://developer.wordpress.org/reference/functions/wp_authenticate_username_password/) `wp-includes/user.php` | Authenticates a user, confirming the username and password are valid. |
| [wp\_authenticate\_spam\_check()](https://developer.wordpress.org/reference/functions/wp_authenticate_spam_check/) `wp-includes/user.php` | For Multisite blogs, checks if the authenticated user has been marked as a spammer, or if the user’s primary blog has been marked as spam. |
| [count\_user\_posts()](https://developer.wordpress.org/reference/functions/count_user_posts/) `wp-includes/user.php` | Gets the number of posts a user has written. |
| [count\_many\_users\_posts()](https://developer.wordpress.org/reference/functions/count_many_users_posts/) `wp-includes/user.php` | Gets the number of posts written by a list of users. |
| [get\_user\_option()](https://developer.wordpress.org/reference/functions/get_user_option/) `wp-includes/user.php` | Retrieves user option that can be either per Site or per Network. |
| [wp\_list\_bookmarks()](https://developer.wordpress.org/reference/functions/wp_list_bookmarks/) `wp-includes/bookmark-template.php` | Retrieves or echoes all of the bookmarks. |
| [get\_query\_template()](https://developer.wordpress.org/reference/functions/get_query_template/) `wp-includes/template.php` | Retrieves path to a template. |
| [WP\_Image\_Editor\_GD::\_save()](https://developer.wordpress.org/reference/classes/wp_image_editor_gd/_save/) `wp-includes/class-wp-image-editor-gd.php` |  |
| [Walker\_Nav\_Menu::start\_el()](https://developer.wordpress.org/reference/classes/walker_nav_menu/start_el/) `wp-includes/class-walker-nav-menu.php` | Starts the element output. |
| [has\_post\_thumbnail()](https://developer.wordpress.org/reference/functions/has_post_thumbnail/) `wp-includes/post-thumbnail-template.php` | Determines whether a post has an image attached. |
| [get\_post\_thumbnail\_id()](https://developer.wordpress.org/reference/functions/get_post_thumbnail_id/) `wp-includes/post-thumbnail-template.php` | Retrieves the post thumbnail ID. |
| [get\_the\_post\_thumbnail()](https://developer.wordpress.org/reference/functions/get_the_post_thumbnail/) `wp-includes/post-thumbnail-template.php` | Retrieves the post thumbnail. |
| [Walker\_Nav\_Menu::start\_lvl()](https://developer.wordpress.org/reference/classes/walker_nav_menu/start_lvl/) `wp-includes/class-walker-nav-menu.php` | Starts the list before the elements are added. |
| [Walker\_PageDropdown::start\_el()](https://developer.wordpress.org/reference/classes/walker_pagedropdown/start_el/) `wp-includes/class-walker-page-dropdown.php` | Starts the element output. |
| [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) `wp-includes/nav-menu-template.php` | Displays a navigation menu. |
| [Walker\_Page::start\_el()](https://developer.wordpress.org/reference/classes/walker_page/start_el/) `wp-includes/class-walker-page.php` | Outputs the beginning of the current element in the tree. |
| [wp\_get\_attachment\_link()](https://developer.wordpress.org/reference/functions/wp_get_attachment_link/) `wp-includes/post-template.php` | Retrieves an attachment page link using an image or icon, if possible. |
| [prepend\_attachment()](https://developer.wordpress.org/reference/functions/prepend_attachment/) `wp-includes/post-template.php` | Wraps attachment in paragraph tag before content. |
| [get\_the\_password\_form()](https://developer.wordpress.org/reference/functions/get_the_password_form/) `wp-includes/post-template.php` | Retrieves protected post password form content. |
| [wp\_post\_revision\_title\_expanded()](https://developer.wordpress.org/reference/functions/wp_post_revision_title_expanded/) `wp-includes/post-template.php` | Retrieves formatted date timestamp of a revision (linked to that revisions’s page). |
| [post\_password\_required()](https://developer.wordpress.org/reference/functions/post_password_required/) `wp-includes/post-template.php` | Determines whether the post requires password and whether a correct password has been provided. |
| [wp\_link\_pages()](https://developer.wordpress.org/reference/functions/wp_link_pages/) `wp-includes/post-template.php` | The formatted output of a list of pages. |
| [wp\_dropdown\_pages()](https://developer.wordpress.org/reference/functions/wp_dropdown_pages/) `wp-includes/post-template.php` | Retrieves or displays a list of pages as a dropdown (select list). |
| [wp\_list\_pages()](https://developer.wordpress.org/reference/functions/wp_list_pages/) `wp-includes/post-template.php` | Retrieves or displays a list of pages (or hierarchical post type items) in list (li) format. |
| [wp\_page\_menu()](https://developer.wordpress.org/reference/functions/wp_page_menu/) `wp-includes/post-template.php` | Displays or retrieves a list of pages with an optional home link. |
| [get\_the\_guid()](https://developer.wordpress.org/reference/functions/get_the_guid/) `wp-includes/post-template.php` | Retrieves the Post Global Unique Identifier (guid). |
| [the\_content()](https://developer.wordpress.org/reference/functions/the_content/) `wp-includes/post-template.php` | Displays the post content. |
| [get\_the\_content()](https://developer.wordpress.org/reference/functions/get_the_content/) `wp-includes/post-template.php` | Retrieves the post content. |
| [the\_excerpt()](https://developer.wordpress.org/reference/functions/the_excerpt/) `wp-includes/post-template.php` | Displays the post excerpt. |
| [get\_the\_excerpt()](https://developer.wordpress.org/reference/functions/get_the_excerpt/) `wp-includes/post-template.php` | Retrieves the post excerpt. |
| [get\_post\_class()](https://developer.wordpress.org/reference/functions/get_post_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the post container element. |
| [get\_body\_class()](https://developer.wordpress.org/reference/functions/get_body_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the body element. |
| [get\_the\_title()](https://developer.wordpress.org/reference/functions/get_the_title/) `wp-includes/post-template.php` | Retrieves the post title. |
| [the\_guid()](https://developer.wordpress.org/reference/functions/the_guid/) `wp-includes/post-template.php` | Displays the Post Global Unique Identifier (guid). |
| [wp\_embed\_defaults()](https://developer.wordpress.org/reference/functions/wp_embed_defaults/) `wp-includes/embed.php` | Creates default array of embed parameters. |
| [wp\_maybe\_load\_embeds()](https://developer.wordpress.org/reference/functions/wp_maybe_load_embeds/) `wp-includes/embed.php` | Determines if default embed handlers should be loaded. |
| [wp\_embed\_handler\_audio()](https://developer.wordpress.org/reference/functions/wp_embed_handler_audio/) `wp-includes/embed.php` | Audio embed handler callback. |
| [wp\_embed\_handler\_video()](https://developer.wordpress.org/reference/functions/wp_embed_handler_video/) `wp-includes/embed.php` | Video embed handler callback. |
| [wp\_mime\_type\_icon()](https://developer.wordpress.org/reference/functions/wp_mime_type_icon/) `wp-includes/post.php` | Retrieves the icon for a MIME type or attachment. |
| [get\_lastpostdate()](https://developer.wordpress.org/reference/functions/get_lastpostdate/) `wp-includes/post.php` | Retrieves the most recent time that a post on the site was published. |
| [get\_lastpostmodified()](https://developer.wordpress.org/reference/functions/get_lastpostmodified/) `wp-includes/post.php` | Gets the most recent time that a post on the site was modified. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [wp\_get\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/) `wp-includes/post.php` | Retrieves attachment metadata for attachment ID. |
| [wp\_update\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_update_attachment_metadata/) `wp-includes/post.php` | Updates metadata for an attachment. |
| [wp\_get\_attachment\_url()](https://developer.wordpress.org/reference/functions/wp_get_attachment_url/) `wp-includes/post.php` | Retrieves the URL for an attachment. |
| [wp\_get\_attachment\_thumb\_url()](https://developer.wordpress.org/reference/functions/wp_get_attachment_thumb_url/) `wp-includes/post.php` | Retrieves URL for an attachment thumbnail. |
| [wp\_get\_attachment\_thumb\_file()](https://developer.wordpress.org/reference/functions/wp_get_attachment_thumb_file/) `wp-includes/deprecated.php` | Retrieves thumbnail for an attachment. |
| [get\_enclosed()](https://developer.wordpress.org/reference/functions/get_enclosed/) `wp-includes/post.php` | Retrieves enclosures already enclosed for a post. |
| [get\_pung()](https://developer.wordpress.org/reference/functions/get_pung/) `wp-includes/post.php` | Retrieves URLs already pinged for a post. |
| [get\_to\_ping()](https://developer.wordpress.org/reference/functions/get_to_ping/) `wp-includes/post.php` | Retrieves URLs that need to be pinged. |
| [get\_page\_uri()](https://developer.wordpress.org/reference/functions/get_page_uri/) `wp-includes/post.php` | Builds the URI path for a page. |
| [get\_pages()](https://developer.wordpress.org/reference/functions/get_pages/) `wp-includes/post.php` | Retrieves an array of pages (or hierarchical post type items). |
| [wp\_unique\_post\_slug()](https://developer.wordpress.org/reference/functions/wp_unique_post_slug/) `wp-includes/post.php` | Computes a unique slug for the post, when given the desired slug and some post details. |
| [wp\_set\_post\_categories()](https://developer.wordpress.org/reference/functions/wp_set_post_categories/) `wp-includes/post.php` | Sets categories for a post. |
| [add\_ping()](https://developer.wordpress.org/reference/functions/add_ping/) `wp-includes/post.php` | Adds a URL to those already pinged. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [get\_post\_mime\_types()](https://developer.wordpress.org/reference/functions/get_post_mime_types/) `wp-includes/post.php` | Gets default post mime types. |
| [wp\_delete\_post()](https://developer.wordpress.org/reference/functions/wp_delete_post/) `wp-includes/post.php` | Trashes or deletes a post or page. |
| [wp\_trash\_post()](https://developer.wordpress.org/reference/functions/wp_trash_post/) `wp-includes/post.php` | Moves a post or page to the Trash |
| [wp\_untrash\_post()](https://developer.wordpress.org/reference/functions/wp_untrash_post/) `wp-includes/post.php` | Restores a post from the Trash. |
| [wp\_count\_posts()](https://developer.wordpress.org/reference/functions/wp_count_posts/) `wp-includes/post.php` | Counts number of posts of a post type and if user has permissions to view. |
| [wp\_count\_attachments()](https://developer.wordpress.org/reference/functions/wp_count_attachments/) `wp-includes/post.php` | Counts number of attachments for the mime type(s). |
| [is\_sticky()](https://developer.wordpress.org/reference/functions/is_sticky/) `wp-includes/post.php` | Determines whether a post is sticky. |
| [sanitize\_post\_field()](https://developer.wordpress.org/reference/functions/sanitize_post_field/) `wp-includes/post.php` | Sanitizes a post field based on context. |
| [get\_post\_type\_labels()](https://developer.wordpress.org/reference/functions/get_post_type_labels/) `wp-includes/post.php` | Builds an object with all post type labels out of a post type object. |
| [get\_post\_status()](https://developer.wordpress.org/reference/functions/get_post_status/) `wp-includes/post.php` | Retrieves the post status based on the post ID. |
| [get\_attached\_file()](https://developer.wordpress.org/reference/functions/get_attached_file/) `wp-includes/post.php` | Retrieves attached file path based on attachment ID. |
| [update\_attached\_file()](https://developer.wordpress.org/reference/functions/update_attached_file/) `wp-includes/post.php` | Updates attachment file path based on attachment ID. |
| [\_wp\_relative\_upload\_path()](https://developer.wordpress.org/reference/functions/_wp_relative_upload_path/) `wp-includes/post.php` | Returns relative path to an uploaded file. |
| [WP\_Rewrite::mod\_rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/mod_rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Retrieves mod\_rewrite-formatted rewrite rules to write to .htaccess. |
| [WP\_Rewrite::iis7\_url\_rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/iis7_url_rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Retrieves IIS7 URL Rewrite formatted rewrite rules to write to web.config file. |
| [WP\_Rewrite::flush\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/flush_rules/) `wp-includes/class-wp-rewrite.php` | Removes rewrite rules and then recreate rewrite rules. |
| [WP\_Rewrite::rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Constructs rewrite matches and queries from permalink structure. |
| [redirect\_canonical()](https://developer.wordpress.org/reference/functions/redirect_canonical/) `wp-includes/canonical.php` | Redirects incoming links to the proper URL based on the site url. |
| [redirect\_guess\_404\_permalink()](https://developer.wordpress.org/reference/functions/redirect_guess_404_permalink/) `wp-includes/canonical.php` | Attempts to guess the correct URL for a 404 request based on query vars. |
| [url\_to\_postid()](https://developer.wordpress.org/reference/functions/url_to_postid/) `wp-includes/rewrite.php` | Examines a URL and try to determine the post ID it represents. |
| [wp\_revisions\_to\_keep()](https://developer.wordpress.org/reference/functions/wp_revisions_to_keep/) `wp-includes/revision.php` | Determines how many revisions to retain for a given post. |
| [\_wp\_post\_revision\_fields()](https://developer.wordpress.org/reference/functions/_wp_post_revision_fields/) `wp-includes/revision.php` | Determines which fields of posts are to be saved in revisions. |
| [wp\_save\_post\_revision()](https://developer.wordpress.org/reference/functions/wp_save_post_revision/) `wp-includes/revision.php` | Creates a revision for the current version of a post. |
| [get\_space\_used()](https://developer.wordpress.org/reference/functions/get_space_used/) `wp-includes/ms-functions.php` | Returns the space used by the current site. |
| [get\_space\_allowed()](https://developer.wordpress.org/reference/functions/get_space_allowed/) `wp-includes/ms-functions.php` | Returns the upload quota for the current blog. |
| [wp\_is\_large\_network()](https://developer.wordpress.org/reference/functions/wp_is_large_network/) `wp-includes/ms-functions.php` | Determines whether or not we have a large network. |
| [wp\_maybe\_update\_network\_site\_counts()](https://developer.wordpress.org/reference/functions/wp_maybe_update_network_site_counts/) `wp-includes/ms-functions.php` | Updates the count of sites for the current network. |
| [wp\_maybe\_update\_network\_user\_counts()](https://developer.wordpress.org/reference/functions/wp_maybe_update_network_user_counts/) `wp-includes/ms-functions.php` | Updates the network-wide users count. |
| [recurse\_dirsize()](https://developer.wordpress.org/reference/functions/recurse_dirsize/) `wp-includes/functions.php` | Gets the size of a directory recursively. |
| [wpmu\_welcome\_user\_notification()](https://developer.wordpress.org/reference/functions/wpmu_welcome_user_notification/) `wp-includes/ms-functions.php` | Notifies a user that their account activation has been successful. |
| [maybe\_redirect\_404()](https://developer.wordpress.org/reference/functions/maybe_redirect_404/) `wp-includes/ms-functions.php` | Corrects 404 redirects when NOBLOGREDIRECT is defined. |
| [newblog\_notify\_siteadmin()](https://developer.wordpress.org/reference/functions/newblog_notify_siteadmin/) `wp-includes/ms-functions.php` | Notifies the network admin that a new site has been activated. |
| [newuser\_notify\_siteadmin()](https://developer.wordpress.org/reference/functions/newuser_notify_siteadmin/) `wp-includes/ms-functions.php` | Notifies the network admin that a new user has been activated. |
| [domain\_exists()](https://developer.wordpress.org/reference/functions/domain_exists/) `wp-includes/ms-functions.php` | Checks whether a site name is already taken. |
| [wpmu\_welcome\_notification()](https://developer.wordpress.org/reference/functions/wpmu_welcome_notification/) `wp-includes/ms-functions.php` | Notifies the site administrator that their site activation was successful. |
| [is\_email\_address\_unsafe()](https://developer.wordpress.org/reference/functions/is_email_address_unsafe/) `wp-includes/ms-functions.php` | Checks an email address against a list of banned domains. |
| [wpmu\_validate\_user\_signup()](https://developer.wordpress.org/reference/functions/wpmu_validate_user_signup/) `wp-includes/ms-functions.php` | Sanitizes and validates data required for a user sign-up. |
| [wpmu\_validate\_blog\_signup()](https://developer.wordpress.org/reference/functions/wpmu_validate_blog_signup/) `wp-includes/ms-functions.php` | Processes new site registrations. |
| [wpmu\_signup\_blog()](https://developer.wordpress.org/reference/functions/wpmu_signup_blog/) `wp-includes/ms-functions.php` | Records site signup information for future activation. |
| [wpmu\_signup\_user()](https://developer.wordpress.org/reference/functions/wpmu_signup_user/) `wp-includes/ms-functions.php` | Records user signup information for future activation. |
| [wpmu\_signup\_blog\_notification()](https://developer.wordpress.org/reference/functions/wpmu_signup_blog_notification/) `wp-includes/ms-functions.php` | Sends a confirmation request email to a user when they sign up for a new site. The new site will not become active until the confirmation link is clicked. |
| [wpmu\_signup\_user\_notification()](https://developer.wordpress.org/reference/functions/wpmu_signup_user_notification/) `wp-includes/ms-functions.php` | Sends a confirmation request email to a user when they sign up for a new user account (without signing up for a site at the same time). The user account will not become active until the confirmation link is clicked. |
| [add\_user\_to\_blog()](https://developer.wordpress.org/reference/functions/add_user_to_blog/) `wp-includes/ms-functions.php` | Adds a user to a blog, along with specifying the user’s role. |
| [sanitize\_bookmark\_field()](https://developer.wordpress.org/reference/functions/sanitize_bookmark_field/) `wp-includes/bookmark.php` | Sanitizes a bookmark field. |
| [WP\_HTTP\_IXR\_Client::query()](https://developer.wordpress.org/reference/classes/wp_http_ixr_client/query/) `wp-includes/class-wp-http-ixr-client.php` |  |
| [get\_site\_by\_path()](https://developer.wordpress.org/reference/functions/get_site_by_path/) `wp-includes/ms-load.php` | Retrieves the closest matching site object by its domain and path. |
| [get\_bookmarks()](https://developer.wordpress.org/reference/functions/get_bookmarks/) `wp-includes/bookmark.php` | Retrieves the list of bookmarks. |
| [graceful\_fail()](https://developer.wordpress.org/reference/functions/graceful_fail/) `wp-includes/ms-deprecated.php` | Deprecated functionality to gracefully fail. |
| [ms\_site\_check()](https://developer.wordpress.org/reference/functions/ms_site_check/) `wp-includes/ms-load.php` | Checks status of current blog. |
| [WP\_Scripts::do\_item()](https://developer.wordpress.org/reference/classes/wp_scripts/do_item/) `wp-includes/class-wp-scripts.php` | Processes a script dependency. |
| [WP\_Scripts::all\_deps()](https://developer.wordpress.org/reference/classes/wp_scripts/all_deps/) `wp-includes/class-wp-scripts.php` | Determines script dependencies. |
| [the\_author\_meta()](https://developer.wordpress.org/reference/functions/the_author_meta/) `wp-includes/author-template.php` | Outputs the field from the user’s DB object. Defaults to current post’s author. |
| [get\_the\_author\_link()](https://developer.wordpress.org/reference/functions/get_the_author_link/) `wp-includes/author-template.php` | Retrieves either author’s link or author’s name. |
| [get\_author\_posts\_url()](https://developer.wordpress.org/reference/functions/get_author_posts_url/) `wp-includes/author-template.php` | Retrieves the URL to the author page for the user with the ID provided. |
| [wp\_list\_authors()](https://developer.wordpress.org/reference/functions/wp_list_authors/) `wp-includes/author-template.php` | Lists all the authors of the site, with several options available. |
| [get\_the\_author\_meta()](https://developer.wordpress.org/reference/functions/get_the_author_meta/) `wp-includes/author-template.php` | Retrieves the requested data of the author of the current post. |
| [is\_multi\_author()](https://developer.wordpress.org/reference/functions/is_multi_author/) `wp-includes/author-template.php` | Determines whether this site has more than one author. |
| [get\_the\_author()](https://developer.wordpress.org/reference/functions/get_the_author/) `wp-includes/author-template.php` | Retrieves the author of the current post. |
| [get\_the\_modified\_author()](https://developer.wordpress.org/reference/functions/get_the_modified_author/) `wp-includes/author-template.php` | Retrieves the author who last edited the current post. |
| [get\_blog\_option()](https://developer.wordpress.org/reference/functions/get_blog_option/) `wp-includes/ms-blogs.php` | Retrieves option value for a given blog id based on name of option. |
| [wp\_setup\_nav\_menu\_item()](https://developer.wordpress.org/reference/functions/wp_setup_nav_menu_item/) `wp-includes/nav-menu.php` | Decorates a menu item object with the shared navigation menu item properties. |
| [has\_nav\_menu()](https://developer.wordpress.org/reference/functions/has_nav_menu/) `wp-includes/nav-menu.php` | Determines whether a registered nav menu location has a menu assigned to it. |
| [wp\_get\_nav\_menus()](https://developer.wordpress.org/reference/functions/wp_get_nav_menus/) `wp-includes/nav-menu.php` | Returns all navigation menu objects. |
| [wp\_get\_nav\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_items/) `wp-includes/nav-menu.php` | Retrieves all menu items of a navigation menu. |
| [wp\_get\_nav\_menu\_object()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_object/) `wp-includes/nav-menu.php` | Returns a navigation menu object. |
| [wp\_xmlrpc\_server::mt\_supportedTextFilters()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mt_supportedtextfilters/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves an empty array because we don’t support per-post text filters. |
| [wp\_xmlrpc\_server::pingback\_ping()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_ping/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a pingback and registers it. |
| [wp\_xmlrpc\_server::pingback\_error()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_error/) `wp-includes/class-wp-xmlrpc-server.php` | Sends a pingback error based on the given error code and message. |
| [wp\_xmlrpc\_server::mw\_newMediaObject()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/mw_newmediaobject/) `wp-includes/class-wp-xmlrpc-server.php` | Uploads a file, following your settings. |
| [wp\_xmlrpc\_server::wp\_getPostType()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposttype/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post type. |
| [wp\_xmlrpc\_server::wp\_getPostTypes()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposttypes/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves post types. |
| [wp\_xmlrpc\_server::wp\_getRevisions()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getrevisions/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves revisions for a specific post. |
| [wp\_xmlrpc\_server::wp\_newComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new comment. |
| [wp\_xmlrpc\_server::wp\_getPosts()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getposts/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves posts. |
| [wp\_xmlrpc\_server::wp\_getTaxonomy()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_gettaxonomy/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a taxonomy. |
| [wp\_xmlrpc\_server::wp\_getTaxonomies()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_gettaxonomies/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves all taxonomies. |
| [wp\_xmlrpc\_server::wp\_getUser()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getuser/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a user. |
| [wp\_xmlrpc\_server::wp\_getUsers()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getusers/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves users. |
| [wp\_xmlrpc\_server::wp\_getProfile()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getprofile/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves information about the requesting user. |
| [wp\_xmlrpc\_server::\_prepare\_page()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_page/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares page data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_comment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_comment/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares comment data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_user()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_user/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares user data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_insert\_post()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_insert_post/) `wp-includes/class-wp-xmlrpc-server.php` | Helper method for wp\_newPost() and wp\_editPost(), containing shared logic. |
| [wp\_xmlrpc\_server::wp\_getPost()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpost/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a post. |
| [wp\_xmlrpc\_server::\_prepare\_taxonomy()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_taxonomy/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares taxonomy data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_term()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_term/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares term data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_post()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_post/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares post data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_post\_type()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_post_type/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares post data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_media\_item()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_media_item/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares media item data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/__construct/) `wp-includes/class-wp-xmlrpc-server.php` | Registers all of the XMLRPC methods that XMLRPC server understands. |
| [wp\_xmlrpc\_server::login()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/login/) `wp-includes/class-wp-xmlrpc-server.php` | Logs user in. |
| [wp\_xmlrpc\_server::initialise\_blog\_option\_info()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/initialise_blog_option_info/) `wp-includes/class-wp-xmlrpc-server.php` | Sets up blog options property. |
| [wpdb::query()](https://developer.wordpress.org/reference/classes/wpdb/query/) `wp-includes/class-wpdb.php` | Performs a database query, using current database connection. |
| [wpdb::set\_sql\_mode()](https://developer.wordpress.org/reference/classes/wpdb/set_sql_mode/) `wp-includes/class-wpdb.php` | Changes the current SQL mode, and ensures its WordPress compatibility. |
| [WP\_Widget::display\_callback()](https://developer.wordpress.org/reference/classes/wp_widget/display_callback/) `wp-includes/class-wp-widget.php` | Generates the actual widget content (Do NOT override). |
| [WP\_Widget::update\_callback()](https://developer.wordpress.org/reference/classes/wp_widget/update_callback/) `wp-includes/class-wp-widget.php` | Handles changed settings (Do NOT override). |
| [WP\_Widget::form\_callback()](https://developer.wordpress.org/reference/classes/wp_widget/form_callback/) `wp-includes/class-wp-widget.php` | Generates the widget control form (Do NOT override). |
| [dynamic\_sidebar()](https://developer.wordpress.org/reference/functions/dynamic_sidebar/) `wp-includes/widgets.php` | Displays dynamic sidebar. |
| [is\_active\_sidebar()](https://developer.wordpress.org/reference/functions/is_active_sidebar/) `wp-includes/widgets.php` | Determines whether a sidebar contains widgets. |
| [wp\_get\_sidebars\_widgets()](https://developer.wordpress.org/reference/functions/wp_get_sidebars_widgets/) `wp-includes/widgets.php` | Retrieves the full list of sidebars and their widget instance IDs. |
| [the\_widget()](https://developer.wordpress.org/reference/functions/the_widget/) `wp-includes/widgets.php` | Outputs an arbitrary widget as a template tag. |
| [register\_sidebar()](https://developer.wordpress.org/reference/functions/register_sidebar/) `wp-includes/widgets.php` | Builds the definition for a single sidebar and returns the ID. |
| [get\_post\_reply\_link()](https://developer.wordpress.org/reference/functions/get_post_reply_link/) `wp-includes/comment-template.php` | Retrieves HTML content for reply to post link. |
| [get\_cancel\_comment\_reply\_link()](https://developer.wordpress.org/reference/functions/get_cancel_comment_reply_link/) `wp-includes/comment-template.php` | Retrieves HTML content for cancel comment reply link. |
| [get\_comment\_id\_fields()](https://developer.wordpress.org/reference/functions/get_comment_id_fields/) `wp-includes/comment-template.php` | Retrieves hidden input HTML for replying to comments. |
| [wp\_list\_comments()](https://developer.wordpress.org/reference/functions/wp_list_comments/) `wp-includes/comment-template.php` | Displays a list of comments. |
| [comment\_form()](https://developer.wordpress.org/reference/functions/comment_form/) `wp-includes/comment-template.php` | Outputs a complete commenting form for use within a template. |
| [get\_trackback\_url()](https://developer.wordpress.org/reference/functions/get_trackback_url/) `wp-includes/comment-template.php` | Retrieves the current post’s trackback URL. |
| [comments\_open()](https://developer.wordpress.org/reference/functions/comments_open/) `wp-includes/comment-template.php` | Determines whether the current post is open for comments. |
| [pings\_open()](https://developer.wordpress.org/reference/functions/pings_open/) `wp-includes/comment-template.php` | Determines whether the current post is open for pings. |
| [comments\_popup\_link()](https://developer.wordpress.org/reference/functions/comments_popup_link/) `wp-includes/comment-template.php` | Displays the link to the comments for the current post ID. |
| [get\_comment\_reply\_link()](https://developer.wordpress.org/reference/functions/get_comment_reply_link/) `wp-includes/comment-template.php` | Retrieves HTML content for reply to comment link. |
| [comments\_template()](https://developer.wordpress.org/reference/functions/comments_template/) `wp-includes/comment-template.php` | Loads the comment template specified in $file. |
| [get\_comment\_link()](https://developer.wordpress.org/reference/functions/get_comment_link/) `wp-includes/comment-template.php` | Retrieves the link to a given comment. |
| [get\_comments\_link()](https://developer.wordpress.org/reference/functions/get_comments_link/) `wp-includes/comment-template.php` | Retrieves the link to the current post comments. |
| [get\_comments\_number()](https://developer.wordpress.org/reference/functions/get_comments_number/) `wp-includes/comment-template.php` | Retrieves the amount of comments a post has. |
| [get\_comment\_text()](https://developer.wordpress.org/reference/functions/get_comment_text/) `wp-includes/comment-template.php` | Retrieves the text of the current comment. |
| [comment\_text()](https://developer.wordpress.org/reference/functions/comment_text/) `wp-includes/comment-template.php` | Displays the text of the current comment. |
| [get\_comment\_time()](https://developer.wordpress.org/reference/functions/get_comment_time/) `wp-includes/comment-template.php` | Retrieves the comment time of the current comment. |
| [get\_comment\_type()](https://developer.wordpress.org/reference/functions/get_comment_type/) `wp-includes/comment-template.php` | Retrieves the comment type of the current comment. |
| [comment\_author\_url()](https://developer.wordpress.org/reference/functions/comment_author_url/) `wp-includes/comment-template.php` | Displays the URL of the author of the current comment, not linked. |
| [get\_comment\_author\_url\_link()](https://developer.wordpress.org/reference/functions/get_comment_author_url_link/) `wp-includes/comment-template.php` | Retrieves the HTML link of the URL of the author of the current comment. |
| [get\_comment\_class()](https://developer.wordpress.org/reference/functions/get_comment_class/) `wp-includes/comment-template.php` | Returns the classes for the comment div as an array. |
| [get\_comment\_date()](https://developer.wordpress.org/reference/functions/get_comment_date/) `wp-includes/comment-template.php` | Retrieves the comment date of the current comment. |
| [get\_comment\_excerpt()](https://developer.wordpress.org/reference/functions/get_comment_excerpt/) `wp-includes/comment-template.php` | Retrieves the excerpt of the given comment. |
| [comment\_excerpt()](https://developer.wordpress.org/reference/functions/comment_excerpt/) `wp-includes/comment-template.php` | Displays the excerpt of the current comment. |
| [get\_comment\_ID()](https://developer.wordpress.org/reference/functions/get_comment_id/) `wp-includes/comment-template.php` | Retrieves the comment ID of the current comment. |
| [get\_comment\_author()](https://developer.wordpress.org/reference/functions/get_comment_author/) `wp-includes/comment-template.php` | Retrieves the author of the current comment. |
| [comment\_author()](https://developer.wordpress.org/reference/functions/comment_author/) `wp-includes/comment-template.php` | Displays the author of the current comment. |
| [get\_comment\_author\_email()](https://developer.wordpress.org/reference/functions/get_comment_author_email/) `wp-includes/comment-template.php` | Retrieves the email of the author of the current comment. |
| [comment\_author\_email()](https://developer.wordpress.org/reference/functions/comment_author_email/) `wp-includes/comment-template.php` | Displays the email of the author of the current global $comment. |
| [get\_comment\_author\_email\_link()](https://developer.wordpress.org/reference/functions/get_comment_author_email_link/) `wp-includes/comment-template.php` | Returns the HTML email link to the author of the current comment. |
| [get\_comment\_author\_link()](https://developer.wordpress.org/reference/functions/get_comment_author_link/) `wp-includes/comment-template.php` | Retrieves the HTML link to the URL of the author of the current comment. |
| [get\_comment\_author\_IP()](https://developer.wordpress.org/reference/functions/get_comment_author_ip/) `wp-includes/comment-template.php` | Retrieves the IP address of the author of the current comment. |
| [get\_comment\_author\_url()](https://developer.wordpress.org/reference/functions/get_comment_author_url/) `wp-includes/comment-template.php` | Retrieves the URL of the author of the current comment, not linked. |
| [WP\_Customize\_Widgets::capture\_filter\_pre\_get\_option()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/capture_filter_pre_get_option/) `wp-includes/class-wp-customize-widgets.php` | Pre-filters captured option values before retrieving. |
| [WP\_Customize\_Widgets::get\_setting\_args()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/get_setting_args/) `wp-includes/class-wp-customize-widgets.php` | Retrieves common arguments to supply when constructing a Customizer setting. |
| [WP\_Customize\_Widgets::customize\_register()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/customize_register/) `wp-includes/class-wp-customize-widgets.php` | Registers Customizer settings and controls for all sidebars and widgets. |
| [WP\_Customize\_Widgets::is\_wide\_widget()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/is_wide_widget/) `wp-includes/class-wp-customize-widgets.php` | Determines whether the widget is considered “wide”. |
| [print\_head\_scripts()](https://developer.wordpress.org/reference/functions/print_head_scripts/) `wp-includes/script-loader.php` | Prints the script queue in the HTML head on admin pages. |
| [print\_footer\_scripts()](https://developer.wordpress.org/reference/functions/print_footer_scripts/) `wp-includes/script-loader.php` | Prints the scripts that were queued for the footer or too late for the HTML head. |
| [print\_admin\_styles()](https://developer.wordpress.org/reference/functions/print_admin_styles/) `wp-includes/script-loader.php` | Prints the styles queue in the HTML head on admin pages. |
| [print\_late\_styles()](https://developer.wordpress.org/reference/functions/print_late_styles/) `wp-includes/script-loader.php` | Prints the styles that were queued too late for the HTML head. |
| [\_close\_comments\_for\_old\_posts()](https://developer.wordpress.org/reference/functions/_close_comments_for_old_posts/) `wp-includes/comment.php` | Closes comments on old posts on the fly, without any extra DB queries. Hooked to the\_posts. |
| [\_close\_comments\_for\_old\_post()](https://developer.wordpress.org/reference/functions/_close_comments_for_old_post/) `wp-includes/comment.php` | Closes comments on an old post. Hooked to comments\_open and pings\_open. |
| [wp\_default\_scripts()](https://developer.wordpress.org/reference/functions/wp_default_scripts/) `wp-includes/script-loader.php` | Registers all WordPress scripts. |
| [wp\_new\_comment()](https://developer.wordpress.org/reference/functions/wp_new_comment/) `wp-includes/comment.php` | Adds a new comment to the database. |
| [wp\_update\_comment()](https://developer.wordpress.org/reference/functions/wp_update_comment/) `wp-includes/comment.php` | Updates an existing comment in the database. |
| [wp\_update\_comment\_count\_now()](https://developer.wordpress.org/reference/functions/wp_update_comment_count_now/) `wp-includes/comment.php` | Updates the comment count for the post. |
| [do\_trackbacks()](https://developer.wordpress.org/reference/functions/do_trackbacks/) `wp-includes/comment.php` | Performs trackbacks. |
| [pingback()](https://developer.wordpress.org/reference/functions/pingback/) `wp-includes/comment.php` | Pings back the links found in a post. |
| [wp\_get\_current\_commenter()](https://developer.wordpress.org/reference/functions/wp_get_current_commenter/) `wp-includes/comment.php` | Gets current commenter’s name, email, and URL. |
| [wp\_filter\_comment()](https://developer.wordpress.org/reference/functions/wp_filter_comment/) `wp-includes/comment.php` | Filters and sanitizes comment data. |
| [get\_page\_of\_comment()](https://developer.wordpress.org/reference/functions/get_page_of_comment/) `wp-includes/comment.php` | Calculates what page number a comment will appear on for comment paging. |
| [wp\_count\_comments()](https://developer.wordpress.org/reference/functions/wp_count_comments/) `wp-includes/comment.php` | Retrieves the total comment counts for the whole site or a single post. |
| [wp\_set\_comment\_cookies()](https://developer.wordpress.org/reference/functions/wp_set_comment_cookies/) `wp-includes/comment.php` | Sets the cookies used to store an unauthenticated commentator’s identity. Typically used to recall previous comments by this commentator that are still held in moderation. |
| [sanitize\_comment\_cookies()](https://developer.wordpress.org/reference/functions/sanitize_comment_cookies/) `wp-includes/comment.php` | Sanitizes the cookies sent to the user already. |
| [wp\_allow\_comment()](https://developer.wordpress.org/reference/functions/wp_allow_comment/) `wp-includes/comment.php` | Validates whether this comment is allowed to be made. |
| [is\_protected\_meta()](https://developer.wordpress.org/reference/functions/is_protected_meta/) `wp-includes/meta.php` | Determines whether a meta key is considered protected. |
| [sanitize\_meta()](https://developer.wordpress.org/reference/functions/sanitize_meta/) `wp-includes/meta.php` | Sanitizes meta value. |
| [register\_meta()](https://developer.wordpress.org/reference/functions/register_meta/) `wp-includes/meta.php` | Registers a meta key. |
| [get\_comment()](https://developer.wordpress.org/reference/functions/get_comment/) `wp-includes/comment.php` | Retrieves comment data given a comment ID or comment object. |
| [check\_comment()](https://developer.wordpress.org/reference/functions/check_comment/) `wp-includes/comment.php` | Checks whether a comment passes internal checks to be allowed to add. |
| [delete\_metadata()](https://developer.wordpress.org/reference/functions/delete_metadata/) `wp-includes/meta.php` | Deletes metadata for the specified object. |
| [metadata\_exists()](https://developer.wordpress.org/reference/functions/metadata_exists/) `wp-includes/meta.php` | Determines if a meta field with the given key exists for the given object ID. |
| [get\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/get_metadata_by_mid/) `wp-includes/meta.php` | Retrieves metadata by meta ID. |
| [update\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/update_metadata_by_mid/) `wp-includes/meta.php` | Updates metadata by meta ID. |
| [delete\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/delete_metadata_by_mid/) `wp-includes/meta.php` | Deletes metadata by meta ID. |
| [update\_meta\_cache()](https://developer.wordpress.org/reference/functions/update_meta_cache/) `wp-includes/meta.php` | Updates the metadata cache for the specified objects. |
| [\_WP\_Editors::wp\_link\_query()](https://developer.wordpress.org/reference/classes/_wp_editors/wp_link_query/) `wp-includes/class-wp-editor.php` | Performs post queries for internal linking. |
| [add\_metadata()](https://developer.wordpress.org/reference/functions/add_metadata/) `wp-includes/meta.php` | Adds metadata for the specified object. |
| [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/) `wp-includes/meta.php` | Updates metadata for the specified object. If no value already exists for the specified object ID and metadata key, the metadata will be added. |
| [\_WP\_Editors::editor\_settings()](https://developer.wordpress.org/reference/classes/_wp_editors/editor_settings/) `wp-includes/class-wp-editor.php` |  |
| [\_WP\_Editors::wp\_mce\_translation()](https://developer.wordpress.org/reference/classes/_wp_editors/wp_mce_translation/) `wp-includes/class-wp-editor.php` | Translates the default TinyMCE strings and returns them as JSON encoded object ready to be loaded with tinymce.addI18n(), or as JS snippet that should run after tinymce.js is loaded. |
| [\_WP\_Editors::parse\_settings()](https://developer.wordpress.org/reference/classes/_wp_editors/parse_settings/) `wp-includes/class-wp-editor.php` | Parse default arguments for the editor instance. |
| [\_WP\_Editors::editor()](https://developer.wordpress.org/reference/classes/_wp_editors/editor/) `wp-includes/class-wp-editor.php` | Outputs the HTML for a single instance of the editor. |
| [wp\_print\_media\_templates()](https://developer.wordpress.org/reference/functions/wp_print_media_templates/) `wp-includes/media-template.php` | Prints the templates used in the media manager. |

[Show 1,280 more](https://developer.wordpress.org/reference/functions/apply_filters/#) [Show less](https://developer.wordpress.org/reference/functions/apply_filters/#)

## [Changelog](https://developer.wordpress.org/reference/functions/apply_filters/\#changelog)

| Version | Description |
| --- | --- |
| [6.0.0](https://developer.wordpress.org/reference/since/6.0.0/) | Formalized the existing and already documented `...$args` parameter by adding it to the function signature. |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/apply_filters/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/apply_filters/#comment-content-443)



**Echo after Filtering**





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
echo apply_filters( $tag, $value );
```





**Get Filtered**





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
$myvar = apply_filters( $tag, $value );
```





**Additional Filter Arguments**





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
$myvar = apply_filters( $tag, $value, $param, $otherparam );
```





For example:





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
$myvar = apply_filters( 'example_filter', 'filter me', 'arg1', 'arg2 ');
```





**With the\_title filter**





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
$my_custom_title = apply_filters('the_title', '  My Custom Title (tm)  ');
$my_custom_title will now contain 'My Custom Title ™', since the_title filter applies wptexturize() and trim(), among others.
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F%3Freplytocom%3D443%23feedback-editor-443)

2. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/apply_filters/#comment-content-2122)



One fundamental argument that is easy to miss is specifying the number of arguments. Most filters have only one argument and so people drop the argument from `add_filter`.



The `3`, below is very important.





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
add_filter( 'example_filter', 'example_callback', 10, 3 );
```





Otherwise you get the following error, such as this StackOverflow question( [http://stackoverflow.com/questions/24198086/missing-argument-2-for-the-function-in-wordpress](http://stackoverflow.com/questions/24198086/missing-argument-2-for-the-function-in-wordpress)):



`Missing argument 2 for example_callback()`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F%3Freplytocom%3D2122%23feedback-editor-2122)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/apply_filters/#comment-content-3362)



Something that is not obvious from reading this function’s definition and description is that if `add_filter( 'filter_name', 'filter_function' )` is never called/executed in code, the use of `apply_filters( 'filter_name', $value )` will return the value of `$value` by default.



I noticed a call to `apply_filters( 'my_filter', ... )` in my theme’s `functions.php` file and couldn’t find a similar `add_filter( 'my_filter', ... )` call anywhere else and was confused about this (I’m still wrapping my head around filters/hooks).



More detail on this can be seen in the example found on this page: [https://docs.presscustomizr.com/article/26-wordpress-actions-filters-and-hooks-a-guide-for-non-developers](https://docs.presscustomizr.com/article/26-wordpress-actions-filters-and-hooks-a-guide-for-non-developers) at the section about Filters.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F%3Freplytocom%3D3362%23feedback-editor-3362)

4. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/apply_filters/#comment-content-6671)



If someone would like to give permission to other developers to change their plugin or theme function value without touching the core code then should use **apply\_filters**



For example –





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
$value = 'Hello world!';
echo apply_filters( 'wpdocs_hook_name', $value, $arg1, $arg2 ); // You can pass arguments also
```





Now how 3rd party developer will work using this hook name? Using the **add\_filter** developer can change the **$value** variable.


Please follow below –





`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/apply_filters/#)




```php
function wpdocs_func_name( $value, $arg1, $arg2 ) {
   	return 'Hi Jack!';
}
add_filter( 'wpdocs_hook_name', 'wpdocs_func_name', 10, 3 ); // Must specify the arguments number if you use multiple arguments
```





Now the result will show “ **Hi Jack!**” instead of “ **Hello world!**” and it has changed the **$value** variable dynamically without touching the core file.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F%3Freplytocom%3D6671%23feedback-editor-6671)

5. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/apply_filters/#comment-content-5825)



The second line in the description is technically incorrect:



**“It is possible to create new filter hooks by simply calling this function…”**



`apply_filters` doesn’t create filter hooks. Read for [https://stackoverflow.com/q/72161547/3429430](https://stackoverflow.com/q/72161547/3429430) details





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F%3Freplytocom%3D5825%23feedback-editor-5825)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fapply_filters%2F) before being able to contribute a note or feedback.

Notifications