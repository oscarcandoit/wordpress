---
url: https://developer.wordpress.org/reference/functions/add_action
scraped_at: 2025-10-20T03:44:06.571Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/add_action/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

add\_action()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)add\_action()

Search

# add\_action( string$hook\_name, callable$callback, int$priority = 10, int$accepted\_args = 1 ): true

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/add_action/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/add_action/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/add_action/#return)
- [More Information](https://developer.wordpress.org/reference/functions/add_action/#more-information)
  - [Usage](https://developer.wordpress.org/reference/functions/add_action/#usage)
- [Source](https://developer.wordpress.org/reference/functions/add_action/#source)
- [Related](https://developer.wordpress.org/reference/functions/add_action/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/add_action/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_action/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/add_action/#wp--skip-link--target)

Adds a callback function to an action hook.

## [Description](https://developer.wordpress.org/reference/functions/add_action/\#description)

Actions are the hooks that the WordPress core launches at specific points during execution, or when specific events occur. Plugins can specify that one or more of its PHP functions are executed at these points, using the Action API.

## [Parameters](https://developer.wordpress.org/reference/functions/add_action/\#parameters)

`$hook_name` stringrequired

The name of the action to add the callback to.

`$callback` callablerequired

The callback to be run when the action is called.

`$priority` intoptional

Used to specify the order in which the functions associated with a particular action are executed.

Lower numbers correspond with earlier execution, and functions with the same priority are executed in the order in which they were added to the action.

Default: `10`

`$accepted_args` intoptional

The number of arguments the function accepts.

Default: `1`

## [Return](https://developer.wordpress.org/reference/functions/add_action/\#return)

true Always returns true.

## [More Information](https://developer.wordpress.org/reference/functions/add_action/\#more-information)

### [Usage](https://developer.wordpress.org/reference/functions/add_action/\#usage)

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_action/#)

```php
add_action( $hook, $function_to_add, $priority, $accepted_args );
```

To find out the number and name of arguments for an action, simply search the code base for the matching [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) call. For example, if you are hooking into ‘save\_post’, you would find it in post.php:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_action/#)

```php
do_action( 'save_post', $post_ID, $post, $update );
```

Your add\_action call would look like:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_action/#)

```php
add_action( 'save_post', 'wpdocs_my_save_post', 10, 3 );
```

And your function would be:

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_action/#)

```php
function wpdocs_my_save_post( $post_ID, $post, $update ) {
// do stuff here
}
```

## [Source](https://developer.wordpress.org/reference/functions/add_action/\#source)

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_action/#)

```php
function add_action( $hook_name, $callback, $priority = 10, $accepted_args = 1 ) {
	return add_filter( $hook_name, $callback, $priority, $accepted_args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L441) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L441-L443)

## [Related](https://developer.wordpress.org/reference/functions/add_action/\#related)

| Uses | Description |
| --- | --- |
| [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) `wp-includes/plugin.php` | Adds a callback function to a filter hook. |

| Used by | Description |
| --- | --- |
| [WP\_Script\_Modules::add\_hooks()](https://developer.wordpress.org/reference/classes/wp_script_modules/add_hooks/) `wp-includes/class-wp-script-modules.php` | Adds the hooks to print the import map, enqueued script modules and script module preloads. |
| [WP\_Textdomain\_Registry::init()](https://developer.wordpress.org/reference/classes/wp_textdomain_registry/init/) `wp-includes/class-wp-textdomain-registry.php` | Initializes the registry. |
| [wp\_initialize\_theme\_preview\_hooks()](https://developer.wordpress.org/reference/functions/wp_initialize_theme_preview_hooks/) `wp-includes/theme-previews.php` | Add filters and actions to enable Block Theme Previews in the Site Editor. |
| [WP\_Rewrite::refresh\_rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/refresh_rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Refreshes the rewrite rules, saving the fresh value to the database. |
| [wp\_delete\_all\_temp\_backups()](https://developer.wordpress.org/reference/functions/wp_delete_all_temp_backups/) `wp-includes/update.php` | Schedules the removal of all contents in the temporary backup directory. |
| [\_wp\_get\_iframed\_editor\_assets()](https://developer.wordpress.org/reference/functions/_wp_get_iframed_editor_assets/) `wp-includes/block-editor.php` | Collect the block editor assets that need to be loaded into the editor’s iframe. |
| [wp\_enqueue\_block\_support\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_support_styles/) `wp-includes/script-loader.php` | Hooks inline styles in the proper place, depending on the active theme. |
| [\_wp\_theme\_json\_webfonts\_handler()](https://developer.wordpress.org/reference/functions/_wp_theme_json_webfonts_handler/) `wp-includes/deprecated.php` | Runs the theme.json webfonts handler. |
| [\_add\_template\_loader\_filters()](https://developer.wordpress.org/reference/functions/_add_template_loader_filters/) `wp-includes/block-template.php` | Adds necessary hooks to resolve ‘\_wp-find-template’ requests. |
| [wp\_enqueue\_block\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_style/) `wp-includes/script-loader.php` | Enqueues a stylesheet for a specific block. |
| [locate\_block\_template()](https://developer.wordpress.org/reference/functions/locate_block_template/) `wp-includes/block-template.php` | Finds a block template with equal or higher specificity than a given PHP template file. |
| [WP\_Sitemaps::init()](https://developer.wordpress.org/reference/classes/wp_sitemaps/init/) `wp-includes/sitemaps/class-wp-sitemaps.php` | Initiates all sitemap functionality. |
| [WP\_Recovery\_Mode::initialize()](https://developer.wordpress.org/reference/classes/wp_recovery_mode/initialize/) `wp-includes/class-wp-recovery-mode.php` | Initialize recovery mode for the current request. |
| [WP\_Site\_Health::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_site_health/__construct/) `wp-admin/includes/class-wp-site-health.php` | [WP\_Site\_Health](https://developer.wordpress.org/reference/classes/wp_site_health/) constructor. |
| [wp\_is\_site\_initialized()](https://developer.wordpress.org/reference/functions/wp_is_site_initialized/) `wp-includes/ms-site.php` | Checks whether a site is initialized. |
| [register\_and\_do\_post\_meta\_boxes()](https://developer.wordpress.org/reference/functions/register_and_do_post_meta_boxes/) `wp-admin/includes/meta-boxes.php` | Registers the default post meta boxes, and runs the `do_meta_boxes` actions. |
| [WP\_Privacy\_Policy\_Content::text\_change\_check()](https://developer.wordpress.org/reference/classes/wp_privacy_policy_content/text_change_check/) `wp-admin/includes/class-wp-privacy-policy-content.php` | Performs a quick check to determine whether any privacy info has changed. |
| [WP\_Roles::get\_roles\_data()](https://developer.wordpress.org/reference/classes/wp_roles/get_roles_data/) `wp-includes/class-wp-roles.php` | Gets the available roles data. |
| [WP\_Widget\_Text::\_register\_one()](https://developer.wordpress.org/reference/classes/wp_widget_text/_register_one/) `wp-includes/widgets/class-wp-widget-text.php` | Adds hooks for enqueueing assets when registering all widget instances of this widget class. |
| [WP\_Widget\_Custom\_HTML::\_register\_one()](https://developer.wordpress.org/reference/classes/wp_widget_custom_html/_register_one/) `wp-includes/widgets/class-wp-widget-custom-html.php` | Add hooks for enqueueing assets when registering all widget instances of this widget class. |
| [WP\_Widget\_Media::\_register\_one()](https://developer.wordpress.org/reference/classes/wp_widget_media/_register_one/) `wp-includes/widgets/class-wp-widget-media.php` | Add hooks while registering all widget instances of this widget class. |
| [\_WP\_Editors::enqueue\_default\_editor()](https://developer.wordpress.org/reference/classes/_wp_editors/enqueue_default_editor/) `wp-includes/class-wp-editor.php` | Enqueue all editor scripts. |
| [\_wp\_delete\_customize\_changeset\_dependent\_auto\_drafts()](https://developer.wordpress.org/reference/functions/_wp_delete_customize_changeset_dependent_auto_drafts/) `wp-includes/nav-menu.php` | Deletes auto-draft posts associated with the supplied changeset. |
| [WP\_Customize\_Manager::import\_theme\_starter\_content()](https://developer.wordpress.org/reference/classes/wp_customize_manager/import_theme_starter_content/) `wp-includes/class-wp-customize-manager.php` | Imports theme starter content into the customized state. |
| [WP\_Post\_Type::register\_meta\_boxes()](https://developer.wordpress.org/reference/classes/wp_post_type/register_meta_boxes/) `wp-includes/class-wp-post-type.php` | Registers the post type meta box if a custom callback was specified. |
| [WP\_Post\_Type::add\_hooks()](https://developer.wordpress.org/reference/classes/wp_post_type/add_hooks/) `wp-includes/class-wp-post-type.php` | Adds the future post hook action for the post type. |
| [WP\_Customize\_Widgets::selective\_refresh\_init()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/selective_refresh_init/) `wp-includes/class-wp-customize-widgets.php` | Adds hooks for selective refresh. |
| [WP\_Customize\_Selective\_Refresh::init\_preview()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/init_preview/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Initializes the Customizer preview. |
| [WP\_Customize\_Selective\_Refresh::enqueue\_preview\_scripts()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/enqueue_preview_scripts/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Enqueues preview scripts. |
| [WP\_Customize\_Selective\_Refresh::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_selective_refresh/__construct/) `wp-includes/customize/class-wp-customize-selective-refresh.php` | Plugin bootstrap for Partial Refresh functionality. |
| [rest\_api\_default\_filters()](https://developer.wordpress.org/reference/functions/rest_api_default_filters/) `wp-includes/rest-api.php` | Registers the default REST API filters. |
| [WP\_Customize\_Setting::aggregate\_multidimensional()](https://developer.wordpress.org/reference/classes/wp_customize_setting/aggregate_multidimensional/) `wp-includes/class-wp-customize-setting.php` | Set up the setting for aggregated multidimensional values. |
| [wp\_admin\_bar\_customize\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_customize_menu/) `wp-includes/admin-bar.php` | Adds the “Customize” link to the Toolbar. |
| [WP\_Widget\_Factory::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_factory/__construct/) `wp-includes/class-wp-widget-factory.php` | PHP5 constructor. |
| [WP\_Customize\_Site\_Icon\_Control::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_site_icon_control/__construct/) `wp-includes/customize/class-wp-customize-site-icon-control.php` | Constructor. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/__construct/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Constructor. |
| [WP\_Customize\_Nav\_Menus::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/customize_preview_init/) `wp-includes/class-wp-customize-nav-menus.php` | Adds hooks for the Customizer preview. |
| [WP\_Customize\_Nav\_Menus::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/__construct/) `wp-includes/class-wp-customize-nav-menus.php` | Constructor. |
| [WP\_Site\_Icon::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_site_icon/__construct/) `wp-admin/includes/class-wp-site-icon.php` | Registers actions and filters. |
| [login\_header()](https://developer.wordpress.org/reference/functions/login_header/) `wp-login.php` | Outputs the login page header. |
| [Language\_Pack\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/language_pack_upgrader/bulk_upgrade/) `wp-admin/includes/class-language-pack-upgrader.php` | Upgrades several language packs at once. |
| [Theme\_Upgrader::install()](https://developer.wordpress.org/reference/classes/theme_upgrader/install/) `wp-admin/includes/class-theme-upgrader.php` | Install a theme package. |
| [Theme\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades a theme. |
| [Plugin\_Upgrader::install()](https://developer.wordpress.org/reference/classes/plugin_upgrader/install/) `wp-admin/includes/class-plugin-upgrader.php` | Install a plugin package. |
| [Plugin\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades a plugin. |
| [WP\_Upgrader::run()](https://developer.wordpress.org/reference/classes/wp_upgrader/run/) `wp-admin/includes/class-wp-upgrader.php` | Runs an upgrade/installation. |
| [WP\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_list_table/__construct/) `wp-admin/includes/class-wp-list-table.php` | Constructor. |
| [WP\_Theme\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/prepare_items/) `wp-admin/includes/class-wp-theme-install-list-table.php` |  |
| [wp\_plugin\_update\_rows()](https://developer.wordpress.org/reference/functions/wp_plugin_update_rows/) `wp-admin/includes/update.php` | Adds a callback to display update information for plugins with updates available. |
| [wp\_theme\_update\_rows()](https://developer.wordpress.org/reference/functions/wp_theme_update_rows/) `wp-admin/includes/update.php` | Adds a callback to display update information for themes with updates available. |
| [uninstall\_plugin()](https://developer.wordpress.org/reference/functions/uninstall_plugin/) `wp-admin/includes/plugin.php` | Uninstalls a single plugin. |
| [add\_menu\_page()](https://developer.wordpress.org/reference/functions/add_menu_page/) `wp-admin/includes/plugin.php` | Adds a top-level menu page. |
| [add\_submenu\_page()](https://developer.wordpress.org/reference/functions/add_submenu_page/) `wp-admin/includes/plugin.php` | Adds a submenu page. |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [WP\_Internal\_Pointers::enqueue\_scripts()](https://developer.wordpress.org/reference/classes/wp_internal_pointers/enqueue_scripts/) `wp-admin/includes/class-wp-internal-pointers.php` | Initializes the new feature pointers. |
| [Custom\_Image\_Header::\_\_construct()](https://developer.wordpress.org/reference/classes/custom_image_header/__construct/) `wp-admin/includes/class-custom-image-header.php` | Constructor – Registers administration header callback. |
| [Custom\_Image\_Header::init()](https://developer.wordpress.org/reference/classes/custom_image_header/init/) `wp-admin/includes/class-custom-image-header.php` | Sets up the hooks for the Custom Header admin page. |
| [Custom\_Background::\_\_construct()](https://developer.wordpress.org/reference/classes/custom_background/__construct/) `wp-admin/includes/class-custom-background.php` | Constructor – Registers administration header callback. |
| [Custom\_Background::init()](https://developer.wordpress.org/reference/classes/custom_background/init/) `wp-admin/includes/class-custom-background.php` | Sets up the hooks for the Custom Background admin page. |
| [WP\_Customize\_Manager::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_preview_init/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings. |
| [WP\_Customize\_Manager::setup\_theme()](https://developer.wordpress.org/reference/classes/wp_customize_manager/setup_theme/) `wp-includes/class-wp-customize-manager.php` | Starts preview and customize theme. |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [wp\_cron()](https://developer.wordpress.org/reference/functions/wp_cron/) `wp-includes/cron.php` | Registers [\_wp\_cron()](https://developer.wordpress.org/reference/functions/_wp_cron/) to run on the [‘wp\_loaded’](https://developer.wordpress.org/reference/hooks/wp_loaded/) action. |
| [\_custom\_header\_background\_just\_in\_time()](https://developer.wordpress.org/reference/functions/_custom_header_background_just_in_time/) `wp-includes/theme.php` | Registers the internal custom header and background routines. |
| [add\_thickbox()](https://developer.wordpress.org/reference/functions/add_thickbox/) `wp-includes/general-template.php` | Enqueues the default ThickBox js and css. |
| [wp\_auth\_check\_load()](https://developer.wordpress.org/reference/functions/wp_auth_check_load/) `wp-includes/functions.php` | Loads the auth check for monitoring whether the user is still logged in. |
| [wp\_maybe\_load\_widgets()](https://developer.wordpress.org/reference/functions/wp_maybe_load_widgets/) `wp-includes/functions.php` | Determines if Widgets library should be loaded. |
| [WP\_Widget\_Recent\_Comments::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/__construct/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Sets up a new Recent Comments widget instance. |
| [WP\_Embed::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_embed/__construct/) `wp-includes/class-wp-embed.php` | Constructor |
| [WP\_Admin\_Bar::add\_menus()](https://developer.wordpress.org/reference/classes/wp_admin_bar/add_menus/) `wp-includes/class-wp-admin-bar.php` | Adds menus to the admin bar. |
| [WP\_Admin\_Bar::initialize()](https://developer.wordpress.org/reference/classes/wp_admin_bar/initialize/) `wp-includes/class-wp-admin-bar.php` | Initializes the admin bar. |
| [register\_activation\_hook()](https://developer.wordpress.org/reference/functions/register_activation_hook/) `wp-includes/plugin.php` | Set the activation hook for a plugin. |
| [register\_deactivation\_hook()](https://developer.wordpress.org/reference/functions/register_deactivation_hook/) `wp-includes/plugin.php` | Sets the deactivation hook for a plugin. |
| [WP\_Customize\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_setting/preview/) `wp-includes/class-wp-customize-setting.php` | Add filters to supply the setting’s value when accessed. |
| [WP\_Rewrite::flush\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/flush_rules/) `wp-includes/class-wp-rewrite.php` | Removes rewrite rules and then recreate rewrite rules. |
| [add\_feed()](https://developer.wordpress.org/reference/functions/add_feed/) `wp-includes/rewrite.php` | Adds a new feed type like /atom1/. |
| [WP\_Scripts::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_scripts/__construct/) `wp-includes/class-wp-scripts.php` | Constructor. |
| [WP\_Customize\_Header\_Image\_Control::prepare\_control()](https://developer.wordpress.org/reference/classes/wp_customize_header_image_control/prepare_control/) `wp-includes/customize/class-wp-customize-header-image-control.php` |  |
| [WP\_Customize\_Widgets::customize\_preview\_init()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/customize_preview_init/) `wp-includes/class-wp-customize-widgets.php` | Adds hooks for the Customizer preview. |
| [WP\_Customize\_Widgets::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/__construct/) `wp-includes/class-wp-customize-widgets.php` | Initial loader. |
| [WP\_Customize\_Widgets::schedule\_customize\_register()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/schedule_customize_register/) `wp-includes/class-wp-customize-widgets.php` | Ensures widgets are available for all types of previews. |
| [wp\_set\_comment\_status()](https://developer.wordpress.org/reference/functions/wp_set_comment_status/) `wp-includes/comment.php` | Sets the status of a comment. |
| [\_WP\_Editors::editor\_settings()](https://developer.wordpress.org/reference/classes/_wp_editors/editor_settings/) `wp-includes/class-wp-editor.php` |  |
| [wp\_print\_media\_templates()](https://developer.wordpress.org/reference/functions/wp_print_media_templates/) `wp-includes/media-template.php` | Prints the templates used in the media manager. |

[Show 79 more](https://developer.wordpress.org/reference/functions/add_action/#) [Show less](https://developer.wordpress.org/reference/functions/add_action/#)

## [Changelog](https://developer.wordpress.org/reference/functions/add_action/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_action/\#user-contributed-notes)

01. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-355)



    **Using with a Class**


    To use `add_action()` when your plugin or theme is built using classes, you need to use the array callable syntax. You would pass the function to `add_action()` as an array, with `$this` as the first element, then the name of the class method, like so:





    `wp-includes/plugin.php`
    [Expand code](https://developer.wordpress.org/reference/functions/add_action/#)

    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * Class WP_Docs_Class.
     */
    class WP_Docs_Class {

    	/**
    	 * Constructor
    	 */
    	public function __construct() {
    		add_action( 'save_post', array( $this, 'wpdocs_save_posts' ) );
    	}

    	/**
    	 * Handle saving post data.
    	 */
    	public function wpdocs_save_posts() {
    		// do stuff here...
    	}
    }

    $wpdocsclass = new WP_Docs_Class();
    ```







    [Show feedback (1)](https://developer.wordpress.org/reference/functions/add_action/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D355%23feedback-editor-355)



- Don’t use this in themes you want to distribute. It won’t be possible to remove the action as $this would be a different value;



[theking2](https://profiles.wordpress.org/theking2/) [3 years ago](https://developer.wordpress.org/reference/functions/add_action/#comment-6274)


02. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-356)



    **Using with static functions in a class**


    If the class is called staticly the approach has to be like below as `$this` is not available. This also works if class is extended. Use the following:





    `wp-includes/plugin.php`
    [Expand code](https://developer.wordpress.org/reference/functions/add_action/#)

    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * Class WP_Docs_Static_Class.
     */
    class WP_Docs_Static_Class {

    	/**
    	 * Initializer for setting up action handler
    	 */
    	public static function init() {
    		add_action( 'save_post', array( get_called_class(), 'wpdocs_save_posts' ) );
    	}

    	/**
    	 * Handler for saving post data.
    	 */
    	public static function wpdocs_save_posts() {
    		// do stuff here...
    	}
    }

    WP_Docs_Static_Class::init();
    ```







    [Show feedback (1)](https://developer.wordpress.org/reference/functions/add_action/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D356%23feedback-editor-356)



- If we have callback function which is static in another class, we can use the following: `add_action( 'save_post', array( Classname::class, 'wpdocs_save_posts' ) );`



[sumeetboga95](https://profiles.wordpress.org/sumeetboga95/) [3 years ago](https://developer.wordpress.org/reference/functions/add_action/#comment-6256)


03. [Skip to note 13 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-3546)



    To pass a variable to the called function of the action, you can use closures (since PHP 5.3+) when the argument is not available in the original coded do\_action. For example:





    `wp-includes/plugin.php`
    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    add_action('wp_footer', function($arguments) use ($myvar) {
        echo $myvar;
    }, $priority_integer, $accepted_arguments_integer);
    ```







    [Show feedback (1)](https://developer.wordpress.org/reference/functions/add_action/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D3546%23feedback-editor-3546)



- Don’t use anonymous closures on themes you want to distribute. It would be impossible to remove the action. Instead use closure variables: ` $myvar = 'Hello World'; $action_wp_footer = function($arguments) use ($myvar) {      echo $myvar; }; add_action('wp_footer', $action_wp_footer, 100, 1); ` which can be removed with: ` remove_action('wp_footer', $action_wp_footer, 100); ` with the advantage that typos in the closure name will yeild a helpfull Undfined variable error on typos.



[theking2](https://profiles.wordpress.org/theking2/) [3 years ago](https://developer.wordpress.org/reference/functions/add_action/#comment-6275)


04. [Skip to note 14 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-353)



    **Simple Hook**


    To email some friends whenever an entry is posted on your blog:





    `wp-includes/plugin.php`
    [Expand code](https://developer.wordpress.org/reference/functions/add_action/#)

    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * Send email to my friends.
     *
     * @param int $post_id Post ID.
     * @return int Post ID.
     */
    function wpdocs_email_friends( $post_id ) {
    	$friends = 'bob@example.org, susie@example.org';
    	wp_mail( $friends, "sally's blog updated", 'I just put something on my blog: http://blog.example.com' );

    	return $post_id;
    }
    add_action( 'publish_post', 'wpdocs_email_friends' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D353%23feedback-editor-353)

05. [Skip to note 15 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-6440)



    I urge you, don’t attach your hook callbacks inside class’ constructor.



    Instead of implementing _official_ example most upvoted in this thread, opt for decoupled solution. You have one more line of code to write, but objects become more reusable and less error-prone (consider, what would happen if you call `new WP_Docs_Class()` twice in your code, following Codex example).





    `wp-includes/plugin.php`
    [Expand code](https://developer.wordpress.org/reference/functions/add_action/#)

    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * Class WP_Docs_Class.
     */
    class WP_Docs_Class {

    	/**
    	 * Initiate all hooks' callbacks in a separate method.
    	 */
    	public function hooks() {
    		add_action( 'save_post', array( $this, 'wpdocs_save_posts' ) );
    	}

    	/**
    	 * Handle saving post data.
    	 */
    	public function wpdocs_save_posts() {
    		// do stuff here...
    	}
    }

    $wpdocsclass = new WP_Docs_Class();
    $wpdocsclass->hooks();
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D6440%23feedback-editor-6440)

06. [Skip to note 16 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-2352)



    Related:



    [do\_action()](https://developer.wordpress.org/reference/functions/do_action/)

    [remove\_action()](https://developer.wordpress.org/reference/functions/remove_action/)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D2352%23feedback-editor-2352)

07. [Skip to note 17 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-2658)



    **Passing parameters while using in a Class**


    To pass parameters to your method in a Class while calling it with add\_action, you can do as following:





    `wp-includes/plugin.php`
    [Expand code](https://developer.wordpress.org/reference/functions/add_action/#)

    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    public function __construct() {
        // Actions
        add_action('init', array($this, 'call_somefunction'));
    }

    /**
     *    Intermediate function to call add_action with parameters
     */
    public function call_somefunction() {
        $this->somefunction('Hello World');
    }

    /**
     *    Actual function that does something
     */
    public function somefunction($text) {
        echo $text;
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D2658%23feedback-editor-2658)

08. [Skip to note 18 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-3937)



    How to add an action that calls a function (with parameters) from an instantiated class:





    `wp-includes/plugin.php`
    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    $admin_menu_hider = new AdminMenuHider( UserManagement::get_internal_users() );
    			add_action(
    				'wp_before_admin_bar_render',
    				function () use ( $admin_menu_hider ) {
    					$admin_menu_hider->change_greeting_message( 'Hello' );
    				}
    			);
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D3937%23feedback-editor-3937)

09. [Skip to note 19 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-354)



    **Accepted Arguments**


    A hooked function can optionally accept arguments from the action call, if any are set to be passed. In this simplistic example, the `echo_comment_id` function takes the `$comment_id` argument, which is automatically passed to when the `do_action()` call using the `comment_id_not_found` filter hook is run.





    `wp-includes/plugin.php`
    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * Warn about comment not found
     *
     * @param int $comment_id Comment ID.
     */
    function echo_comment_id( $comment_id ) {
    	printf( 'Comment ID %s could not be found', esc_html( $comment_id ) );
    }
    add_action( 'comment_id_not_found', 'echo_comment_id', 10, 1 );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D354%23feedback-editor-354)

10. [Skip to note 20 content](https://developer.wordpress.org/reference/functions/add_action/#comment-content-6158)



    To prevent runtime errors due to easy typo errors (defensive programming) and prevent pollution of the global namespace use closures instead of function names. The sample code adjusted:





    `wp-includes/plugin.php`
    [Copy](https://developer.wordpress.org/reference/functions/add_action/#)




    ```php
    /**
     * add a save post hook
     */
    add_action( 'save_post', function( $post_ID, $post, $update ) {
       // do stuff here
    }, 10, 3 );
    ```







    [Show feedback (2)](https://developer.wordpress.org/reference/functions/add_action/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F%3Freplytocom%3D6158%23feedback-editor-6158)



- Do not do this in themes or plugins you intend to distribute, as it will prevent others from removing your callables if desired.



[crstauf](https://profiles.wordpress.org/crstauf/) [3 years ago](https://developer.wordpress.org/reference/functions/add_action/#comment-6165)

- Not recommended, as you would be missing a valuable callback function name in any stack trace.



[Dave Green](https://profiles.wordpress.org/davegreenwp/) [3 years ago](https://developer.wordpress.org/reference/functions/add_action/#comment-6348)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_action%2F) before being able to contribute a note or feedback.

Notifications