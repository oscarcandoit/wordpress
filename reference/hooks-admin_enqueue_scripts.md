---
url: https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts
scraped_at: 2025-10-20T03:42:04.291Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

admin\_enqueue\_scripts


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)admin\_enqueue\_scripts

Search

# do\_action( ‘admin\_enqueue\_scripts’, string$hook\_suffix )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#source)
- [Related](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#wp--skip-link--target)

Fires when enqueuing scripts for all admin pages.

## [Parameters](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#parameters)

`$hook_suffix` string

The current admin page.

## [More Information](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#more-information)

`admin_enqueue_scripts` is the proper hook to use when enqueuing scripts and styles that are meant to be used in the administration panel. Despite the name, it is **used for enqueuing both scripts and styles**.

It provides a single parameter, `$hook_suffix`, that informs the current admin page. This should be used to enqueue scripts and styles only in the pages they are going to be used, and avoid adding script and styles to all admin dashboard unnecessarily.

## [Source](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#source)

`wp-admin/admin-header.php`
[Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)

```php
do_action( 'admin_enqueue_scripts', $hook_suffix );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/admin-header.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/admin-header.php#L123) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/admin-header.php#L123-L123)

## [Related](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#related)

| Used by | Description |
| --- | --- |
| [iframe\_header()](https://developer.wordpress.org/reference/functions/iframe_header/) `wp-admin/includes/template.php` | Generic Iframe header for use with Thickbox. |
| [wp\_iframe()](https://developer.wordpress.org/reference/functions/wp_iframe/) `wp-admin/includes/media.php` | Outputs the iframe to display the media upload page. |
| [WP\_Customize\_Widgets::enqueue\_scripts()](https://developer.wordpress.org/reference/classes/wp_customize_widgets/enqueue_scripts/) `wp-includes/class-wp-customize-widgets.php` | Enqueues scripts and styles for Customizer panel and export data to JavaScript. |

## [Changelog](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/\#user-contributed-notes)

01. [Skip to note 11 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-70)



    **Selectively enqueue a script in the admin**



    The admin\_enqueue\_scripts action hook can also be used to target a specific admin page. In this example we are loading a javascript file in the head section of edit.php.





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    /**
     * Enqueue a script in the WordPress admin on edit.php.
     *
     * @param string $hook Hook suffix for the current admin page.
     */
    function wpdocs_selectively_enqueue_admin_script( $hook ) {
        if ( 'edit.php' != $hook ) {
            return;
        }
        wp_enqueue_script( 'my_custom_script', plugin_dir_url( __FILE__ ) . 'myscript.js', array(), '1.0' );
    }
    add_action( 'admin_enqueue_scripts', 'wpdocs_selectively_enqueue_admin_script' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D70%23feedback-editor-70)

02. [Skip to note 12 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-2361)



    **Figure out your $hook name**



    If you are unsure what the $hook name of the current admin page of which you want to conditionally load your script is, add this to your page:





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    $screen = get_current_screen();
    print_r($screen);
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D2361%23feedback-editor-2361)

03. [Skip to note 13 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-69)



    **Enqueue a custom stylesheet in the admin**



    Sometimes you want to load a set of CSS and/or Javascript documents to all admin pages. You can do this from within your plugin or from your themes function file:





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    /**
     * Register and enqueue a custom stylesheet in the WordPress admin.
     */
    function wpdocs_enqueue_custom_admin_style() {
            wp_register_style( 'custom_wp_admin_css', get_template_directory_uri() . '/admin-style.css', false, '1.0.0' );
            wp_enqueue_style( 'custom_wp_admin_css' );
    }
    add_action( 'admin_enqueue_scripts', 'wpdocs_enqueue_custom_admin_style' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D69%23feedback-editor-69)

04. [Skip to note 14 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-2196)



    **Another way to load scripts or css in specific admin page by using this function**



    In this example, we are loading a javascript and a css file in the head section of nav-menus.php page.





    `wp-admin/admin-header.php`
    [Expand code](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)

    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    function add_script_to_menu_page()
    {
    	// $pagenow, is a global variable referring to the filename of the current page,
    	// such as ‘admin.php’, ‘post-new.php’
    	global $pagenow;

    	if ($pagenow != 'nav-menus.php') {
    		return;
    	}

    	// loading css
        wp_register_style( 'some-css', get_template_directory_uri() . '/css/some.css', false, '1.0.0' );
        wp_enqueue_style( 'some-css' );

    	// loading js
    	wp_register_script( 'some-js', get_template_directory_uri().'/js/some.js', array('jquery-core'), false, true );
        wp_enqueue_script( 'some-js' );
    }

    add_action( 'admin_enqueue_scripts', 'add_script_to_menu_page' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D2196%23feedback-editor-2196)

05. [Skip to note 15 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-5681)



    Note: if you are trying to use the $hook\_suffix to check if you are on a submenu page, there is an important bug you should know about. This mostly affects people who are distributing their code in a theme or plugin, where the code will be run on WordPress installations in multiple languages.



    [https://core.trac.wordpress.org/ticket/18857](https://core.trac.wordpress.org/ticket/18857)



    Basically the part of the $hook\_suffix that is the parent menu page slug can be translated, so it will not match the string you are expecting.



    You can work around this bug using code like:





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    function enqueue_my_assets( $hook_suffix ) {
    	$parent_menu_slug = sanitize_title( __( 'Parent Menu Title', 'parent-translation-domain' ) );

    	if ( $parent_menu_slug . '_page_my_sub_menu' != $hook_suffix ) {
    		return;
    	}

    	// we must be on the right page then ...
    }
    add_action( 'admin_enqueue_scripts', 'enqueue_my_assets', 10, 1 );
    ```





    Basically you get the translated parent menu slug first, and use it when checking the $hook\_suffix to make sure you are on the right page.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D5681%23feedback-editor-5681)

06. [Skip to note 16 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-2404)



    **Load css and js only on a particular sub-menu page**





    `wp-admin/admin-header.php`
    [Expand code](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)

    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    // custom css and js
    add_action('admin_enqueue_scripts', 'cstm_css_and_js');

    function cstm_css_and_js($hook) {
        // your-slug =&gt; The slug name to refer to this menu used in &quot;add_submenu_page&quot;
    		// tools_page =&gt; refers to Tools top menu, so it's a Tools' sub-menu page
        if ( 'tools_page_your-slug' != $hook ) {
            return;
        }

        wp_enqueue_style('boot_css', plugins_url('inc/bootstrap.css',__FILE__ ));
        wp_enqueue_script('boot_js', plugins_url('inc/bootstrap.js',__FILE__ ));
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D2404%23feedback-editor-2404)

07. [Skip to note 17 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-5817)



    Load your scripts on your menu page and all sub-menu below your menu page.





    `wp-admin/admin-header.php`
    [Expand code](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)

    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    /** Add Admin Pages **/
    function add_admin_pages() {

        // Add Menu Page
        add_menu_page('Top Level Menu', 'Top Level Menu', 'manage_options', 'top-level-menu', 'your_callback_menu', 'dashicons-admin-tools', 10);

        // Add Sub Menu Page
        add_submenu_page('top-level-menu', 'Sub Menu', 'Sub Menu', 'manage_options', 'sub-menu', 'your_callback_submenu');

    }
    add_action('admin_menu', 'add_admin_pages');

    /** Enqueue Stylesheets **/
    function add_admin_scripts($hook) {

        // global $parent_file defined on admin-header.php line 27
        // https://core.trac.wordpress.org/browser/tags/5.9/src/wp-admin/admin-header.php#L27
        global $parent_file;
        if ('top-level-menu' != $parent_file) {
            return;
        }

        // For example we load sweetalert on your menu page and all sub-menu below your menu page.
        wp_enqueue_script('sweetalert-js', 'https://unpkg.com/sweetalert/dist/sweetalert.min.js');

    }
    add_action('admin_enqueue_scripts', 'add_admin_scripts');
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D5817%23feedback-editor-5817)

08. [Skip to note 18 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-3679)



    What if you want to load CSS, JS to specific pages from your created menu and submenu? ( multiple pages )





    `wp-admin/admin-header.php`
    [Expand code](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)

    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    function addPage()
    {
    global $customMenu, $customSubMenu;
            /**
             * Menu
             */
           $customMenu = add_menu_page( 'Custom Menu', 'Custom Menu', 'manage_options', 'custom-menu', 'customMenuPage', '', 10);
            /**
             * Sub Menu Pages
             */
            $customSubMenu = add_submenu_page( 'custom-menu', 'Settings', 'Settings', 'manage_options', 'settings', 'settings_page');
    }
    add_action( 'admin_menu', 'addPage');

    /** Enqueue Stylesheets **/
    function enqueueAdminStyles( $hook)
        {
            global $customMenu, $customSubMenu;
            $allowed = array( $customMenu, $customSubMenu);
            if( !in_array( $hook, $allowed)  )
            {
                return;
            }
            wp_enqueue_style( '-main-', 'assets/admin/css/ucsi.css', '', '1');
        }
    add_action( 'admin_enqueue_scripts', 'enqueueAdminStyles');
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D3679%23feedback-editor-3679)

09. [Skip to note 19 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-4777)



    The $hook\_suffix is kind of tricky to know it’s value out of your head especially on custom admin pages. This junky little trick can help:





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    function wpdocs_myselective_css_or_js( $hook ) {
        echo '<h1 style="color: crimson;">' . esc_html( $hook ) . '</h1>';
    }

    add_action( 'admin_enqueue_scripts', 'wpdocs_myselective_css_or_js' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D4777%23feedback-editor-4777)

10. [Skip to note 20 content](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#comment-content-6084)



    Here’s how you can hook your namespaced function:





    `wp-admin/admin-header.php`
    [Copy](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/#)




    ```php
    namespace YourNameSpace;

    function register_your_admin_script() {
    	wp_enqueue_script( 'your-admin-script', get_template_directory_uri() . '/js/your-admin-script.js', array(), '1.0.0', true );
    }

    add_action( 'admin_enqueue_scripts', __NAMESPACE__ . '\register_your_admin_script' );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F%3Freplytocom%3D6084%23feedback-editor-6084)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fadmin_enqueue_scripts%2F) before being able to contribute a note or feedback.

Notifications