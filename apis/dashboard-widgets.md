---
url: https://developer.wordpress.org/apis/dashboard-widgets
scraped_at: 2025-10-20T04:08:42.787Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/dashboard-widgets/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Dashboard widgets API


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Dashboard widgets API

Search

# Dashboard widgets API

## In this article

Table of Contents

- [Overview](https://developer.wordpress.org/apis/dashboard-widgets/#overview)
  - [The main function](https://developer.wordpress.org/apis/dashboard-widgets/#the-main-function)
  - [Usage](https://developer.wordpress.org/apis/dashboard-widgets/#usage)
  - [Action hooks](https://developer.wordpress.org/apis/dashboard-widgets/#action-hooks)
- [Examples](https://developer.wordpress.org/apis/dashboard-widgets/#examples)
  - [Basic usage](https://developer.wordpress.org/apis/dashboard-widgets/#basic-usage)
  - [Forcing your widget to the top](https://developer.wordpress.org/apis/dashboard-widgets/#forcing-your-widget-to-the-top)
  - [Removing default Dashboard Widgets](https://developer.wordpress.org/apis/dashboard-widgets/#removing-default-dashboard-widgets)
  - [Adding Widgets in the right side](https://developer.wordpress.org/apis/dashboard-widgets/#adding-widgets-in-the-right-side)
  - [Aggregating RSS feeds in the dashboard](https://developer.wordpress.org/apis/dashboard-widgets/#aggregating-rss-feeds-in-the-dashboard)
- [Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/#widget-options)
  - [Getting Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/#getting-widget-options)
  - [Get a Single Widget Option](https://developer.wordpress.org/apis/dashboard-widgets/#get-a-single-widget-option)
  - [Update Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/#update-widget-options)

[↑ Back to top](https://developer.wordpress.org/apis/dashboard-widgets/#wp--skip-link--target)

Added in WordPress Version [2.7](https://wordpress.org/support/wordpress-version/version-2-7/), the **Dashboard Widgets API** makes it simple to add new widgets to the [administration dashboard](https://wordpress.org/support/article/dashboard-screen/).

Doing so requires working knowledge of PHP and the WordPress [Plugin API](https://developer.wordpress.org/plugins/), but to plugin or theme authors familiar with hooking actions and filters, it only takes a few minutes and can be a great way to make your plugin even more useful.

[![](https://i0.wp.com/developer.wordpress.org/files/2019/08/admin-dashboard-widget-api.png?resize=1024%2C464&ssl=1)](https://i0.wp.com/developer.wordpress.org/files/2019/08/admin-dashboard-widget-api.png?ssl=1) Default Dashboard Widgets

## [Overview](https://developer.wordpress.org/apis/dashboard-widgets/\#overview)

### [The main function](https://developer.wordpress.org/apis/dashboard-widgets/\#the-main-function)

The main tool needed to add Dashboard Widgets is the [wp\_add\_dashboard\_widget()](https://developer.wordpress.org/reference/functions/wp_add_dashboard_widget/) function. You will find a complete description of this function on that link, but a brief overview is given below.

### [Usage](https://developer.wordpress.org/apis/dashboard-widgets/\#usage)

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
wp_add_dashboard_widget( $widget_id, $widget_name, $callback, $control_callback, $callback_args );
```

- `$widget_id`: an identifying slug for your widget. This will be used as its CSS class and its key in the array of widgets.
- `$widget_name`: this is the name your widget will display in its heading.
- `$callback`: The name of a function you will create that will display the actual contents of your widget.
- `$control_callback` (Optional): The name of a function you create that will handle submission of widget options forms, and will also display the form elements.
- `$callback_args` (Optional): Set of arguments for the callback function.

### [Action hooks](https://developer.wordpress.org/apis/dashboard-widgets/\#action-hooks)

To run the function you will need to hook into the action [wp\_dashboard\_setup](https://developer.wordpress.org/reference/hooks/wp_dashboard_setup/) via [add\_action()](https://developer.wordpress.org/reference/functions/add_action/). For the Network Admin dashboard, use the hook [wp\_network\_dashboard\_setup](https://developer.wordpress.org/reference/hooks/wp_network_dashboard_setup/).

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
/**
 * Add a widget to the dashboard.
 *
 * This function is hooked into the 'wp_dashboard_setup' action below.
 */
function wporg_add_dashboard_widgets() {
	// Add function here
}
add_action( 'wp_dashboard_setup', 'wporg_add_dashboard_widgets' );
```

Network dashboard:

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
/**
 * Add a widget to the network dashboard.
 *
 * This function is hooked into the 'wp_network_dashboard_setup' action below.
 */
function wporg_add_network_dashboard_widgets() {
	// Add function here
}
add_action( 'wp_network_dashboard_setup', 'wporg_add_network_dashboard_widgets' );
```

## [Examples](https://developer.wordpress.org/apis/dashboard-widgets/\#examples)

### [Basic usage](https://developer.wordpress.org/apis/dashboard-widgets/\#basic-usage)

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
/**
 * Add a widget to the dashboard.
 *
 * This function is hooked into the 'wp_dashboard_setup' action below.
 */
function wporg_add_dashboard_widgets() {
	wp_add_dashboard_widget(
		'wporg_dashboard_widget',                          // Widget slug.
		esc_html__( 'Example Dashboard Widget', 'wporg' ), // Title.
		'wporg_dashboard_widget_render'                    // Display function.
	);
}
add_action( 'wp_dashboard_setup', 'wporg_add_dashboard_widgets' );

/**
 * Create the function to output the content of our Dashboard Widget.
 */
function wporg_dashboard_widget_render() {
	// Display whatever you want to show.
	esc_html_e( "Howdy! I'm a great Dashboard Widget.", "wporg" );
}
```

### [Forcing your widget to the top](https://developer.wordpress.org/apis/dashboard-widgets/\#forcing-your-widget-to-the-top)

Normally you should just let the users of your plugin put your Dashboard Widget wherever they want by dragging it around. There currently isn’t an easy API way to pre-sort the default widgets, meaning your new widget will always be at the bottom of the list. Until sorting is added to the API its a bit complicated to get around this problem.

Below is an example hooking function that will try to put your widget before the default ones. It does so by manually altering the internal array of metaboxes (of which dashboard widgets are one type) and putting your widget at the top of the list so it shows first.

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
function wporg_add_dashboard_widgets() {
	wp_add_dashboard_widget(
		'wporg_dashboard_widget',
		esc_html__( 'Example Dashboard Widget', 'wporg' ),
		'wporg_dashboard_widget_function'
	);

	// Globalize the metaboxes array, this holds all the widgets for wp-admin.
	global $wp_meta_boxes;

	// Get the regular dashboard widgets array
	// (which already has our new widget but appended at the end).
	$default_dashboard = $wp_meta_boxes['dashboard']['normal']['core'];

	// Backup and delete our new dashboard widget from the end of the array.
	$example_widget_backup = array( 'example_dashboard_widget' => $default_dashboard['example_dashboard_widget'] );
	unset( $default_dashboard['example_dashboard_widget'] );

	// Merge the two arrays together so our widget is at the beginning.
	$sorted_dashboard = array_merge( $example_widget_backup, $default_dashboard );

	// Save the sorted array back into the original metaboxes.
	$wp_meta_boxes['dashboard']['normal']['core'] = $sorted_dashboard;
}
add_action( 'wp_dashboard_setup', 'wporg_add_dashboard_widgets' );
```

Unfortunately this only works for people who have never re-ordered their widgets. Once a user has done so their existing preferences will override this and they will have to move your widget to the top for it to stay there.

### [Removing default Dashboard Widgets](https://developer.wordpress.org/apis/dashboard-widgets/\#removing-default-dashboard-widgets)

In some situations, especially on multi-user blogs, it may be useful to completely remove widgets from the interface. Each individual user can, by default, turn off any given widget using the _[Screen Options](https://wordpress.org/support/article/administration-screens/#screen-options)_ tab at the top, but if you have a lot of non-technical users it might be nicer for them to not see it at all.

To remove dashboard widget, use the [remove\_meta\_box()](https://developer.wordpress.org/reference/functions/remove_meta_box/) function. See the example codes below for the required parameters.

These are the names of the default widgets on the dashboard:

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
// Main column (left):
// Browser Update Required
$wp_meta_boxes['dashboard']['normal']['high']['dashboard_browser_nag'];
// PHP Update Required
$wp_meta_boxes['dashboard']['normal']['high']['dashboard_php_nag'];

// At a Glance
$wp_meta_boxes['dashboard']['normal']['core']['dashboard_right_now'];
// Right Now
$wp_meta_boxes['dashboard']['normal']['core']['network_dashboard_right_now'];
// Activity
$wp_meta_boxes['dashboard']['normal']['core']['dashboard_activity'];
// Site Health Status
$wp_meta_boxes['dashboard']['normal']['core']['dashboard_site_health'];

// Side Column (right):
// WordPress Events and News
$wp_meta_boxes['dashboard']['side']['core']['dashboard_primary'];
// Quick Draft, Your Recent Drafts
$wp_meta_boxes['dashboard']['side']['core']['dashboard_quick_press'];
```

Here is an example function that removes the QuickPress widget:

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
// Create the function to use in the action hook
function wporg_remove_dashboard_widget() {
	remove_meta_box( 'dashboard_quick_press', 'dashboard', 'side' );
}
// Hook into the 'wp_dashboard_setup' action to register our function
add_action( 'wp_dashboard_setup', 'wporg_remove_dashboard_widget' );
```

The example below removes all Dashboard Widgets:

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
function wporg_remove_all_dashboard_metaboxes() {
	// Remove Welcome panel
	remove_action( 'welcome_panel', 'wp_welcome_panel' );
	// Remove the rest of the dashboard widgets
	remove_meta_box( 'dashboard_primary', 'dashboard', 'side' );
	remove_meta_box( 'dashboard_quick_press', 'dashboard', 'side' );
	remove_meta_box( 'dashboard_site_health', 'dashboard', 'normal' );
	remove_meta_box( 'dashboard_right_now', 'dashboard', 'normal' );
	remove_meta_box( 'dashboard_activity', 'dashboard', 'normal');
}
add_action( 'wp_dashboard_setup', 'wporg_remove_all_dashboard_metaboxes' );
```

### [Adding Widgets in the right side](https://developer.wordpress.org/apis/dashboard-widgets/\#adding-widgets-in-the-right-side)

The function doesn’t allow you to choose where you want your widget to go and will automatically add it to the “core” which is the left side. However you are able to get it on the right side very easily.

You can use the [add\_meta\_box()](https://developer.wordpress.org/reference/functions/add_meta_box/) function instead of `wp_add_dashboard_widget`. Simply specify ‘dashboard’ in place of the $post\_type. For example:

``
[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
add_meta_box(
	'dashboard_widget_id',
	esc_html__( 'Dashboard Widget Title', 'wporg' ),
	'dashboard_widget',
	'dashboard',
	'side', 'high'
);
```

Or, after creating the widget:

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
function wporg_add_dashboard_widget() {
	wp_add_dashboard_widget(
		'wporg_dashboard_widget',
		esc_html__( 'Example Dashboard Widget', 'wporg' ),
		'wporg_dashboard_widget_function'
	);

	// Global the $wp_meta_boxes variable (this will allow us to alter the array).
	global $wp_meta_boxes;

	// Then we make a backup of your widget.
	$wporg_widget = $wp_meta_boxes['dashboard']['normal']['core']['wporg_dashboard_widget'];

	// We then unset that part of the array.
	unset( $wp_meta_boxes['dashboard']['normal']['core']['wporg_dashboard_widget'] );

	// Now we just add your widget back in.
	$wp_meta_boxes['dashboard']['side']['core']['wporg_dashboard_widget'] = $wporg_widget;
}
add_action( 'wp_dashboard_setup', 'wporg_add_dashboard_widget' );
```

### [Aggregating RSS feeds in the dashboard](https://developer.wordpress.org/apis/dashboard-widgets/\#aggregating-rss-feeds-in-the-dashboard)

If you need to aggregate RSS in your widget you should take a look at the way the existing plugins are set up with caching in `[/wp-admin/includes/dashboard.php](https://core.trac.wordpress.org/browser/tags/5.2.1/src//wp-admin/includes/dashboard.php#L0)`.

## [Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/\#widget-options)

WordPress does not provide a built-in way to fetch options for a specific widget. By default, you would need to use `[get\_option( 'dashboard\_widget\_options' )](https://developer.wordpress.org/reference/functions/get_option/)` to fetch all widget options and then filter the returned array manually. This section presents some functions that can easily be added to a theme or plugin to help getting and setting of widget options.

### [Getting Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/\#getting-widget-options)

This function will fetch all widget options, or only options for a specified widget:

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php

/**
 * Gets all widget options, or only options for a specified widget if a widget id is provided.
 *
 * @param string $widget_id Optional. If provided, will only get options for that widget.
 * @return array An associative array
 */
function wporg_get_dashboard_widget_options( $widget_id = '' ) {
    // Fetch ALL dashboard widget options from the db
    $options = get_option( 'dashboard_widget_options' );

    // If no widget is specified, return everything
    if ( empty( $widget_id ) ) {
        return $options;
    }

    // If we request a widget and it exists, return it
    if ( isset( $options[$widget_id] ) ) {
        return $options[$widget_id];
    }

    // Something went wrong...
    return false;
}
```

### [Get a Single Widget Option](https://developer.wordpress.org/apis/dashboard-widgets/\#get-a-single-widget-option)

If you want to easily fetch only a single option (for outputting to a theme), the following function will make that easier.

This example should be used with the previous [Getting Widget Options](https://developer.wordpress.org/apis/handbook/dashboard-widgets/#getting-widget-options) example function.

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
/**
 * Gets one specific option for the specified widget.
 *
 * @param  string $widget_id Widget ID.
 * @param  string $option    Widget option.
 * @param  string $default   Default option.
 *
 * @return string            Returns single widget option.
 */
function wporg_get_dashboard_widget_option( $widget_id, $option, $default = NULL ) {
	$options = wporg_get_dashboard_widget_options( $widget_id );

	// If widget options don't exist, return false.
	if ( ! $options ) {
		return false;
	}

	// Otherwise fetch the option or use default
	if ( isset( $options[$option] ) && ! empty( $options[$option] ) ) {
		return $options[$option];
	} else {
		return ( isset( $default ) ) ? $default : false;
	}
}
```

### [Update Widget Options](https://developer.wordpress.org/apis/dashboard-widgets/\#update-widget-options)

This function can be used to easily update all of a widget’s options. It can also be used to add a widget option non-destructively. Simply set the $add\_option argument to true, and this will **NOT overwrite** any existing options (although it will add any missing ones).

``
[Expand code](https://developer.wordpress.org/apis/dashboard-widgets/#)

[Copy](https://developer.wordpress.org/apis/dashboard-widgets/#)

```php
/**
 * Saves an array of options for a single dashboard widget to the database.
 * Can also be used to define default values for a widget.
 *
 * @param string $widget_id  The name of the widget being updated
 * @param array $args        An associative array of options being saved.
 * @param bool $add_only     Set to true if you don't want to override any existing options.
 */
function update_dashboard_widget_options( $widget_id , $args = array(), $add_only = false ) {
	// Fetch ALL dashboard widget options from the db...
	$options = get_option( 'dashboard_widget_options' );

	// Get just our widget's options, or set empty array.
	$widget_options = ( isset( $options[$widget_id] ) ) ? $options[$widget_id] : array();

	if ( $add_only ) {
		// Flesh out any missing options (existing ones overwrite new ones).
		$options[$widget_id] = array_merge( $args, $widget_options );
	} else {
		// Merge new options with existing ones, and add it back to the widgets array.
		$options[$widget_id] = array_merge( $widget_options, $args );
	}

	// Save the entire widgets array back to the db.
	return update_option( 'dashboard_widget_options', $options );
}
```

First published

August 12, 2019

Last updated

May 30, 2025

[PreviousResponsive ImagesPrevious: Responsive Images](https://developer.wordpress.org/apis/responsive-images/)

[NextDatabase APINext: Database API](https://developer.wordpress.org/apis/database/)

Notifications