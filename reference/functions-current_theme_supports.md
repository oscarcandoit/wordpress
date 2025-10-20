---
url: https://developer.wordpress.org/reference/functions/current_theme_supports
scraped_at: 2025-10-20T03:21:24.634Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/current_theme_supports/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

current\_theme\_supports()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)current\_theme\_supports()

Search

# current\_theme\_supports( string$feature, mixed$args ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/current_theme_supports/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/current_theme_supports/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/current_theme_supports/#return)
- [Source](https://developer.wordpress.org/reference/functions/current_theme_supports/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/current_theme_supports/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/current_theme_supports/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/current_theme_supports/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/current_theme_supports/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/current_theme_supports/#wp--skip-link--target)

Checks a theme’s support for a given feature.

## [Description](https://developer.wordpress.org/reference/functions/current_theme_supports/\#description)

Example usage:

`wp-includes/theme.php`
[Copy](https://developer.wordpress.org/reference/functions/current_theme_supports/#)

```php
current_theme_supports( 'custom-logo' );
current_theme_supports( 'html5', 'comment-form' );
```

## [Parameters](https://developer.wordpress.org/reference/functions/current_theme_supports/\#parameters)

`$feature` stringrequired

The feature being checked. See [add\_theme\_support()](https://developer.wordpress.org/reference/functions/add_theme_support/) for the list of possible values.More Arguments from add\_theme\_support( … $feature )The feature being added. Likely core values include:

- `'admin-bar'`
- `'align-wide'`
- `'appearance-tools'`
- `'automatic-feed-links'`
- `'block-templates'`
- `'block-template-parts'`
- `'border'`
- `'core-block-patterns'`
- `'custom-background'`
- `'custom-header'`
- `'custom-line-height'`
- `'custom-logo'`
- `'customize-selective-refresh-widgets'`
- `'custom-spacing'`
- `'custom-units'`
- `'dark-editor-style'`
- `'disable-custom-colors'`
- `'disable-custom-font-sizes'`
- `'disable-custom-gradients'`
- `'disable-layout-styles'`
- `'editor-color-palette'`
- `'editor-gradient-presets'`
- `'editor-font-sizes'`
- `'editor-spacing-sizes'`
- `'editor-styles'`
- `'featured-content'`
- `'html5'`
- `'link-color'`
- `'menus'`
- `'post-formats'`
- `'post-thumbnails'`
- `'responsive-embeds'`
- `'starter-content'`
- `'title-tag'`
- `'widgets'`
- `'widgets-block-editor'`
- `'wp-block-styles'`

`$args` mixedoptional

Optional extra arguments to be checked against certain features.

## [Return](https://developer.wordpress.org/reference/functions/current_theme_supports/\#return)

bool True if the active theme supports the feature, false otherwise.

## [Source](https://developer.wordpress.org/reference/functions/current_theme_supports/\#source)

`wp-includes/theme.php`
[Expand code](https://developer.wordpress.org/reference/functions/current_theme_supports/#)

[Copy](https://developer.wordpress.org/reference/functions/current_theme_supports/#)

```php
function current_theme_supports( $feature, ...$args ) {
	global $_wp_theme_features;

	if ( 'custom-header-uploads' === $feature ) {
		return current_theme_supports( 'custom-header', 'uploads' );
	}

	if ( ! isset( $_wp_theme_features[ $feature ] ) ) {
		return false;
	}

	// If no args passed then no extra checks need to be performed.
	if ( ! $args ) {
		/** This filter is documented in wp-includes/theme.php */
		return apply_filters( "current_theme_supports-{$feature}", true, $args, $_wp_theme_features[ $feature ] ); // phpcs:ignore WordPress.NamingConventions.ValidHookName.UseUnderscores
	}

	switch ( $feature ) {
		case 'post-thumbnails':
			/*
			 * post-thumbnails can be registered for only certain content/post types
			 * by passing an array of types to add_theme_support().
			 * If no array was passed, then any type is accepted.
			 */
			if ( true === $_wp_theme_features[ $feature ] ) {  // Registered for all types.
				return true;
			}
			$content_type = $args[0];
			return in_array( $content_type, $_wp_theme_features[ $feature ][0], true );

		case 'html5':
		case 'post-formats':
			/*
			 * Specific post formats can be registered by passing an array of types
			 * to add_theme_support().
			 *
			 * Specific areas of HTML5 support *must* be passed via an array to add_theme_support().
			 */
			$type = $args[0];
			return in_array( $type, $_wp_theme_features[ $feature ][0], true );

		case 'custom-logo':
		case 'custom-header':
		case 'custom-background':
			// Specific capabilities can be registered by passing an array to add_theme_support().
			return ( isset( $_wp_theme_features[ $feature ][0][ $args[0] ] ) && $_wp_theme_features[ $feature ][0][ $args[0] ] );
	}

	/**
	 * Filters whether the active theme supports a specific feature.
	 *
	 * The dynamic portion of the hook name, `$feature`, refers to the specific
	 * theme feature. See add_theme_support() for the list of possible values.
	 *
	 * @since 3.4.0
	 *
	 * @param bool   $supports Whether the active theme supports the given feature. Default true.
	 * @param array  $args     Array of arguments for the feature.
	 * @param string $feature  The theme feature.
	 */
	return apply_filters( "current_theme_supports-{$feature}", true, $args, $_wp_theme_features[ $feature ] ); // phpcs:ignore WordPress.NamingConventions.ValidHookName.UseUnderscores
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/theme.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/theme.php#L3160) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/theme.php#L3160-L3221)

## [Hooks](https://developer.wordpress.org/reference/functions/current_theme_supports/\#hooks)

[apply\_filters( “current\_theme\_supports-{$feature}”, bool$supports, array$args, string$feature )](https://developer.wordpress.org/reference/hooks/current_theme_supports-feature/)

Filters whether the active theme supports a specific feature.

## [Related](https://developer.wordpress.org/reference/functions/current_theme_supports/\#related)

| Uses | Description |
| --- | --- |
| [current\_theme\_supports()](https://developer.wordpress.org/reference/functions/current_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [\_wp\_render\_title\_tag()](https://developer.wordpress.org/reference/functions/_wp_render_title_tag/) `wp-includes/general-template.php` | Displays title tag with content. |
| [WP\_REST\_Attachments\_Controller::handle\_featured\_media()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/handle_featured_media/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Determines the featured media based on a request param. |
| [wp\_enqueue\_admin\_bar\_bump\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_admin_bar_bump_styles/) `wp-includes/admin-bar.php` | Enqueues inline bump styles to make room for the admin bar. |
| [WP\_Font\_Face::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_font_face/__construct/) `wp-includes/fonts/class-wp-font-face.php` | Creates and initializes an instance of [WP\_Font\_Face](https://developer.wordpress.org/reference/classes/wp_font_face/). |
| [wp\_enqueue\_block\_template\_skip\_link()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_template_skip_link/) `wp-includes/theme-templates.php` | Enqueues the skip-link script & styles. |
| [\_wp\_get\_iframed\_editor\_assets()](https://developer.wordpress.org/reference/functions/_wp_get_iframed_editor_assets/) `wp-includes/block-editor.php` | Collect the block editor assets that need to be loaded into the editor’s iframe. |
| [wp\_get\_global\_stylesheet()](https://developer.wordpress.org/reference/functions/wp_get_global_stylesheet/) `wp-includes/global-styles-and-settings.php` | Returns the stylesheet resulting of merging core, theme, and user data. |
| [\_add\_default\_theme\_supports()](https://developer.wordpress.org/reference/functions/_add_default_theme_supports/) `wp-includes/theme.php` | Adds default theme supports for block themes when the ‘after\_setup\_theme’ action fires. |
| [\_add\_template\_loader\_filters()](https://developer.wordpress.org/reference/functions/_add_template_loader_filters/) `wp-includes/block-template.php` | Adds necessary hooks to resolve ‘\_wp-find-template’ requests. |
| [WP\_Theme\_JSON\_Resolver::get\_theme\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_theme_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns the theme’s data. |
| [the\_block\_template\_skip\_link()](https://developer.wordpress.org/reference/functions/the_block_template_skip_link/) `wp-includes/deprecated.php` | Prints the skip-link script & styles. |
| [get\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_block_editor_settings/) `wp-includes/block-editor.php` | Returns the contextualized block editor settings for a selected editor context. |
| [get\_block\_editor\_theme\_styles()](https://developer.wordpress.org/reference/functions/get_block_editor_theme_styles/) `wp-includes/block-editor.php` | Creates an array of theme styles to load into the block editor. |
| [locate\_block\_template()](https://developer.wordpress.org/reference/functions/locate_block_template/) `wp-includes/block-template.php` | Finds a block template with equal or higher specificity than a given PHP template file. |
| [wp\_get\_inline\_script\_tag()](https://developer.wordpress.org/reference/functions/wp_get_inline_script_tag/) `wp-includes/script-loader.php` | Constructs an inline script tag. |
| [wp\_sanitize\_script\_attributes()](https://developer.wordpress.org/reference/functions/wp_sanitize_script_attributes/) `wp-includes/script-loader.php` | Sanitizes an attributes array into an attributes string to be placed inside a `` tag. |
| [wp\_get\_script\_tag()](https://developer.wordpress.org/reference/functions/wp_get_script_tag/) `wp-includes/script-loader.php` | Formats `` loader tags. |
| [get\_media\_states()](https://developer.wordpress.org/reference/functions/get_media_states/) `wp-admin/includes/template.php` | Retrieves an array of media states from an attachment. |
| [register\_block\_type\_from\_metadata()](https://developer.wordpress.org/reference/functions/register_block_type_from_metadata/) `wp-includes/blocks.php` | Registers a block type from the metadata stored in the `block.json` file. |
| [WP\_REST\_Themes\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_themes_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-themes-controller.php` | Prepares a single theme output for response. |
| [wp\_common\_block\_scripts\_and\_styles()](https://developer.wordpress.org/reference/functions/wp_common_block_scripts_and_styles/) `wp-includes/script-loader.php` | Handles the enqueueing of block scripts and styles that are common to both the editor and the front-end. |
| [register\_and\_do\_post\_meta\_boxes()](https://developer.wordpress.org/reference/functions/register_and_do_post_meta_boxes/) `wp-admin/includes/meta-boxes.php` | Registers the default post meta boxes, and runs the `do_meta_boxes` actions. |
| [WP\_Customize\_Nav\_Menu\_Locations\_Control::content\_template()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_locations_control/content_template/) `wp-includes/customize/class-wp-customize-nav-menu-locations-control.php` | JS/Underscore template for the control UI. |
| [WP\_Theme::get\_post\_templates()](https://developer.wordpress.org/reference/classes/wp_theme/get_post_templates/) `wp-includes/class-wp-theme.php` | Returns the theme’s post templates. |
| [wp\_custom\_css\_cb()](https://developer.wordpress.org/reference/functions/wp_custom_css_cb/) `wp-includes/theme.php` | Renders the Custom CSS style element. |
| [\_custom\_logo\_header\_styles()](https://developer.wordpress.org/reference/functions/_custom_logo_header_styles/) `wp-includes/theme.php` | Adds CSS to hide header text for custom logo, based on Customizer setting. |
| [WP\_Customize\_Widgets::customize\_dynamic\_partial\_args()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/customize_dynamic_partial_args/) `wp-includes/class-wp-customize-widgets.php` | Filters arguments for dynamic widget partials. |
| [WP\_Customize\_Widgets::selective\_refresh\_init()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/selective_refresh_init/) `wp-includes/class-wp-customize-widgets.php` | Adds hooks for selective refresh. |
| [WP\_Customize\_Widgets::get\_selective\_refreshable\_widgets()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/get_selective_refreshable_widgets/) `wp-includes/class-wp-customize-widgets.php` | List whether each registered widget can be use selective refresh. |
| [print\_embed\_styles()](https://developer.wordpress.org/reference/functions/print_embed_styles/) `wp-includes/deprecated.php` | Prints the CSS in the embed iframe header. |
| [WP\_Customize\_Nav\_Menus::customize\_register()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/customize_register/) `wp-includes/class-wp-customize-nav-menus.php` | Adds the customizer settings and controls. |
| [WP\_Customize\_Nav\_Menus::available\_item\_types()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/available_item_types/) `wp-includes/class-wp-customize-nav-menus.php` | Returns an array of all the available item types. |
| [print\_emoji\_styles()](https://developer.wordpress.org/reference/functions/print_emoji_styles/) `wp-includes/deprecated.php` | Prints the important emoji-related styles. |
| [WP\_Customize\_Panel::check\_capabilities()](https://developer.wordpress.org/reference/classes/wp_customize_panel/check_capabilities/) `wp-includes/class-wp-customize-panel.php` | Checks required user capabilities and whether the theme has the feature support required by the panel. |
| [wp\_generate\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_generate_attachment_metadata/) `wp-admin/includes/image.php` | Generates attachment meta data and create image sub-sizes for images. |
| [get\_media\_item()](https://developer.wordpress.org/reference/functions/get_media_item/) `wp-admin/includes/media.php` | Retrieves HTML form for modifying the image attachment. |
| [get\_default\_post\_to\_edit()](https://developer.wordpress.org/reference/functions/get_default_post_to_edit/) `wp-admin/includes/post.php` | Returns default post information to use when populating the “Write Post” form. |
| [post\_format\_meta\_box()](https://developer.wordpress.org/reference/functions/post_format_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post format form elements. |
| [WP\_Posts\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/inline_edit/) `wp-admin/includes/class-wp-posts-list-table.php` | Outputs the hidden row displayed when inline editing |
| [Custom\_Image\_Header::get\_header\_dimensions()](https://developer.wordpress.org/reference/classes/custom_image_header/get_header_dimensions/) `wp-admin/includes/class-custom-image-header.php` | Calculates width and height based on what the currently selected theme supports. |
| [Custom\_Image\_Header::ajax\_header\_crop()](https://developer.wordpress.org/reference/classes/custom_image_header/ajax_header_crop/) `wp-admin/includes/class-custom-image-header.php` | Gets attachment uploaded by Media Manager, crops it, then saves it as a new object. Returns JSON-encoded object details. |
| [Custom\_Image\_Header::step\_1()](https://developer.wordpress.org/reference/classes/custom_image_header/step_1/) `wp-admin/includes/class-custom-image-header.php` | Displays first step of custom header image page. |
| [Custom\_Image\_Header::step\_2()](https://developer.wordpress.org/reference/classes/custom_image_header/step_2/) `wp-admin/includes/class-custom-image-header.php` | Displays second step of custom header image page. |
| [Custom\_Image\_Header::step\_3()](https://developer.wordpress.org/reference/classes/custom_image_header/step_3/) `wp-admin/includes/class-custom-image-header.php` | Displays third step of custom header image page. |
| [Custom\_Image\_Header::js\_includes()](https://developer.wordpress.org/reference/classes/custom_image_header/js_includes/) `wp-admin/includes/class-custom-image-header.php` | Sets up the enqueue for the JavaScript files. |
| [Custom\_Image\_Header::css\_includes()](https://developer.wordpress.org/reference/classes/custom_image_header/css_includes/) `wp-admin/includes/class-custom-image-header.php` | Sets up the enqueue for the CSS files. |
| [Custom\_Image\_Header::js()](https://developer.wordpress.org/reference/classes/custom_image_header/js/) `wp-admin/includes/class-custom-image-header.php` | Executes JavaScript depending on step. |
| [Custom\_Image\_Header::js\_1()](https://developer.wordpress.org/reference/classes/custom_image_header/js_1/) `wp-admin/includes/class-custom-image-header.php` | Displays JavaScript based on Step 1 and 3. |
| [Custom\_Image\_Header::js\_2()](https://developer.wordpress.org/reference/classes/custom_image_header/js_2/) `wp-admin/includes/class-custom-image-header.php` | Displays JavaScript based on Step 2. |
| [Custom\_Background::admin\_page()](https://developer.wordpress.org/reference/classes/custom_background/admin_page/) `wp-admin/includes/class-custom-background.php` | Displays the custom background page. |
| [WP\_Customize\_Manager::register\_controls()](https://developer.wordpress.org/reference/classes/wp_customize_manager/register_controls/) `wp-includes/class-wp-customize-manager.php` | Registers some default controls. |
| [WP\_Styles::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_styles/__construct/) `wp-includes/class-wp-styles.php` | Constructor. |
| [\_custom\_background\_cb()](https://developer.wordpress.org/reference/functions/_custom_background_cb/) `wp-includes/theme.php` | Default custom background callback. |
| [remove\_editor\_styles()](https://developer.wordpress.org/reference/functions/remove_editor_styles/) `wp-includes/theme.php` | Removes all visual editor stylesheets. |
| [\_custom\_header\_background\_just\_in\_time()](https://developer.wordpress.org/reference/functions/_custom_header_background_just_in_time/) `wp-includes/theme.php` | Registers the internal custom header and background routines. |
| [current\_theme\_supports()](https://developer.wordpress.org/reference/functions/current_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature. |
| [require\_if\_theme\_supports()](https://developer.wordpress.org/reference/functions/require_if_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature before loading the functions which implement it. |
| [display\_header\_text()](https://developer.wordpress.org/reference/functions/display_header_text/) `wp-includes/theme.php` | Whether to display the header text. |
| [\_get\_random\_header\_data()](https://developer.wordpress.org/reference/functions/_get_random_header_data/) `wp-includes/theme.php` | Gets random header image data from registered images in theme. |
| [get\_custom\_header()](https://developer.wordpress.org/reference/functions/get_custom_header/) `wp-includes/theme.php` | Gets the header image data. |
| [locale\_stylesheet()](https://developer.wordpress.org/reference/functions/locale_stylesheet/) `wp-includes/theme.php` | Displays localized stylesheet link element. |
| [feed\_links()](https://developer.wordpress.org/reference/functions/feed_links/) `wp-includes/general-template.php` | Displays the links to the general feeds. |
| [get\_search\_form()](https://developer.wordpress.org/reference/functions/get_search_form/) `wp-includes/general-template.php` | Displays search form. |
| [wp\_widgets\_add\_menu()](https://developer.wordpress.org/reference/functions/wp_widgets_add_menu/) `wp-includes/functions.php` | Appends the Widgets menu to the themes main menu. |
| [WP\_Nav\_Menu\_Widget::widget()](https://developer.wordpress.org/reference/classes/wp_nav_menu_widget/widget/) `wp-includes/widgets/class-wp-nav-menu-widget.php` | Outputs the content for the current Navigation Menu widget instance. |
| [WP\_Widget\_Tag\_Cloud::widget()](https://developer.wordpress.org/reference/classes/wp_widget_tag_cloud/widget/) `wp-includes/widgets/class-wp-widget-tag-cloud.php` | Outputs the content for the current Tag Cloud widget instance. |
| [WP\_Widget\_RSS::widget()](https://developer.wordpress.org/reference/classes/wp_widget_rss/widget/) `wp-includes/widgets/class-wp-widget-rss.php` | Outputs the content for the current RSS widget instance. |
| [WP\_Widget\_Recent\_Posts::widget()](https://developer.wordpress.org/reference/classes/wp_widget_recent_posts/widget/) `wp-includes/widgets/class-wp-widget-recent-posts.php` | Outputs the content for the current Recent Posts widget instance. |
| [WP\_Widget\_Recent\_Comments::recent\_comments\_style()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/recent_comments_style/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Outputs the default styles for the Recent Comments widget. |
| [WP\_Widget\_Recent\_Comments::widget()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/widget/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Outputs the content for the current Recent Comments widget instance. |
| [WP\_Widget\_Categories::widget()](https://developer.wordpress.org/reference/classes/wp_widget_categories/widget/) `wp-includes/widgets/class-wp-widget-categories.php` | Outputs the content for the current Categories widget instance. |
| [WP\_Widget\_Archives::widget()](https://developer.wordpress.org/reference/classes/wp_widget_archives/widget/) `wp-includes/widgets/class-wp-widget-archives.php` | Outputs the content for the current Archives widget instance. |
| [WP\_Widget\_Meta::widget()](https://developer.wordpress.org/reference/classes/wp_widget_meta/widget/) `wp-includes/widgets/class-wp-widget-meta.php` | Outputs the content for the current Meta widget instance. |
| [WP\_Widget\_Pages::widget()](https://developer.wordpress.org/reference/classes/wp_widget_pages/widget/) `wp-includes/widgets/class-wp-widget-pages.php` | Outputs the content for the current Pages widget instance. |
| [WP\_Customize\_Section::check\_capabilities()](https://developer.wordpress.org/reference/classes/wp_customize_section/check_capabilities/) `wp-includes/class-wp-customize-section.php` | Checks required user capabilities and whether the theme has the feature support required by the section. |
| [create\_initial\_taxonomies()](https://developer.wordpress.org/reference/functions/create_initial_taxonomies/) `wp-includes/taxonomy.php` | Creates the initial taxonomies. |
| [WP\_Admin\_Bar::initialize()](https://developer.wordpress.org/reference/classes/wp_admin_bar/initialize/) `wp-includes/class-wp-admin-bar.php` | Initializes the admin bar. |
| [wp\_admin\_bar\_appearance\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_appearance_menu/) `wp-includes/admin-bar.php` | Adds appearance submenu items to the “Site Name” menu. |
| [wp\_admin\_bar\_header()](https://developer.wordpress.org/reference/functions/wp_admin_bar_header/) `wp-includes/deprecated.php` | Prints style and scripts for the admin bar. |
| [\_admin\_bar\_bump\_cb()](https://developer.wordpress.org/reference/functions/_admin_bar_bump_cb/) `wp-includes/deprecated.php` | Prints default admin bar callback. |
| [WP\_Customize\_Setting::check\_capabilities()](https://developer.wordpress.org/reference/classes/wp_customize_setting/check_capabilities/) `wp-includes/class-wp-customize-setting.php` | Validate user capabilities whether the theme supports the setting. |
| [get\_body\_class()](https://developer.wordpress.org/reference/functions/get_body_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the body element. |
| [get\_post\_class()](https://developer.wordpress.org/reference/functions/get_post_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the post container element. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wp\_xmlrpc\_server::wp\_getPostFormats()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpostformats/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a list of post formats used by the site. |
| [wp\_xmlrpc\_server::\_prepare\_post()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_post/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares post data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::initialise\_blog\_option\_info()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/initialise_blog_option_info/) `wp-includes/class-wp-xmlrpc-server.php` | Sets up blog options property. |
| [WP\_Customize\_Header\_Image\_Control::render\_content()](https://developer.wordpress.org/reference/classes/wp_customize_header_image_control/render_content/) `wp-includes/customize/class-wp-customize-header-image-control.php` |  |
| [wp\_list\_comments()](https://developer.wordpress.org/reference/functions/wp_list_comments/) `wp-includes/comment-template.php` | Displays a list of comments. |
| [comment\_form()](https://developer.wordpress.org/reference/functions/comment_form/) `wp-includes/comment-template.php` | Outputs a complete commenting form for use within a template. |
| [WP\_Customize\_Widgets::get\_setting\_args()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/get_setting_args/) `wp-includes/class-wp-customize-widgets.php` | Retrieves common arguments to supply when constructing a Customizer setting. |
| [wp\_default\_styles()](https://developer.wordpress.org/reference/functions/wp_default_styles/) `wp-includes/script-loader.php` | Assigns default styles to $styles object. |

[Show 87 more](https://developer.wordpress.org/reference/functions/current_theme_supports/#) [Show less](https://developer.wordpress.org/reference/functions/current_theme_supports/#)

## [Changelog](https://developer.wordpress.org/reference/functions/current_theme_supports/\#changelog)

| Version | Description |
| --- | --- |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Formalized the existing and already documented `...$args` parameter by adding it to the function signature. |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/current_theme_supports/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/current_theme_supports/#comment-content-1351)



**Basic Example**





`wp-includes/theme.php`
[Copy](https://developer.wordpress.org/reference/functions/current_theme_supports/#)




```php
<?php
if (current_theme_supports('custom-header')) {
     // do something special when custom-header is supported...
}
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcurrent_theme_supports%2F%3Freplytocom%3D1351%23feedback-editor-1351)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcurrent_theme_supports%2F) before being able to contribute a note or feedback.

Notifications