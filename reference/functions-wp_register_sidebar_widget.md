---
url: https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget
scraped_at: 2025-10-20T03:19:19.268Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_register\_sidebar\_widget()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_register\_sidebar\_widget()

Search

# wp\_register\_sidebar\_widget( int\|string$id, string$name, callable$output\_callback, array$options = array(), mixed$params )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#wp--skip-link--target)

Registers an instance of a widget.

## [Description](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#description)

The default widget option is ‘classname’ that can be overridden.

The function can also be used to un-register widgets when `$output_callback` parameter is an empty string.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#parameters)

`$id` int\|stringrequired

Widget ID.

`$name` stringrequired

Widget display title.

`$output_callback` callablerequired

Run when widget is called.

`$options` arrayoptional

An array of supplementary widget options for the instance.

- `classname` string
Class name for the widget’s HTML container. Default is a shortened version of the output callback name.

- `description` string
Widget description for display in the widget administration panel and/or theme.

- `show_instance_in_rest` bool
Whether to show the widget’s instance settings in the REST API.


Only available for [WP\_Widget](https://developer.wordpress.org/reference/classes/wp_widget/) based widgets.


Default: `array()`

`$params` mixedoptional

Optional additional parameters to pass to the callback function when it’s called.

## [Source](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#source)

`wp-includes/widgets.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#)

```php
function wp_register_sidebar_widget( $id, $name, $output_callback, $options = array(), ...$params ) {
	global $wp_registered_widgets, $wp_registered_widget_controls, $wp_registered_widget_updates, $_wp_deprecated_widgets_callbacks;

	$id = strtolower( $id );

	if ( empty( $output_callback ) ) {
		unset( $wp_registered_widgets[ $id ] );
		return;
	}

	$id_base = _get_widget_id_base( $id );
	if ( in_array( $output_callback, $_wp_deprecated_widgets_callbacks, true ) && ! is_callable( $output_callback ) ) {
		unset( $wp_registered_widget_controls[ $id ] );
		unset( $wp_registered_widget_updates[ $id_base ] );
		return;
	}

	$defaults = array( 'classname' => $output_callback );
	$options  = wp_parse_args( $options, $defaults );
	$widget   = array(
		'name'     => $name,
		'id'       => $id,
		'callback' => $output_callback,
		'params'   => $params,
	);
	$widget   = array_merge( $widget, $options );

	if ( is_callable( $output_callback ) && ( ! isset( $wp_registered_widgets[ $id ] ) || did_action( 'widgets_init' ) ) ) {

		/**
		 * Fires once for each registered widget.
		 *
		 * @since 3.0.0
		 *
		 * @param array $widget An array of default widget arguments.
		 */
		do_action( 'wp_register_sidebar_widget', $widget );
		$wp_registered_widgets[ $id ] = $widget;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/widgets.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/widgets.php#L396) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/widgets.php#L396-L435)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#hooks)

[do\_action( ‘wp\_register\_sidebar\_widget’, array$widget )](https://developer.wordpress.org/reference/hooks/wp_register_sidebar_widget/)

Fires once for each registered widget.

## [Related](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#related)

| Uses | Description |
| --- | --- |
| [did\_action()](https://developer.wordpress.org/reference/functions/did_action/) `wp-includes/plugin.php` | Retrieves the number of times an action has been fired during the current request. |
| [\_get\_widget\_id\_base()](https://developer.wordpress.org/reference/functions/_get_widget_id_base/) `wp-includes/widgets.php` | Retrieves the widget ID base value. |
| [wp\_parse\_args()](https://developer.wordpress.org/reference/functions/wp_parse_args/) `wp-includes/functions.php` | Merges user defined arguments into defaults array. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#) [Show less](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#)

| Used by | Description |
| --- | --- |
| [register\_sidebar\_widget()](https://developer.wordpress.org/reference/functions/register_sidebar_widget/) `wp-includes/deprecated.php` | Register widget for sidebar with backward compatibility. |
| [WP\_Widget::\_register\_one()](https://developer.wordpress.org/reference/classes/wp_widget/_register_one/) `wp-includes/class-wp-widget.php` | Registers an instance of the widget class. |
| [wp\_unregister\_sidebar\_widget()](https://developer.wordpress.org/reference/functions/wp_unregister_sidebar_widget/) `wp-includes/widgets.php` | Remove widget from sidebar. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#changelog)

| Version | Description |
| --- | --- |
| [5.8.0](https://developer.wordpress.org/reference/since/5.8.0/) | Added show\_instance\_in\_rest option. |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Formalized the existing and already documented `...$params` parameter by adding it to the function signature. |
| [2.2.0](https://developer.wordpress.org/reference/since/2.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#comment-content-665)



**Example**


The following code will create a widget called “Wpdocs Widget” which will become available in the WordPress Administrative Panels. The widget can then be dragged to an available sidebar for display.



Note that this widget can only be used once in exactly 1 of the sidebars. For recursive widgets (widgets you can add to multiple times and add to multiple sidebars) please see the Register Widget function.





`wp-includes/widgets.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_register_sidebar_widget/#)




```php
wp_register_sidebar_widget(
   	'wpdocs_widget_1',		// wpdocs unique widget id
   	'Wpdocs Widget',		// widget name
   	'wpdocs_widget_display',	// callback function
   	array(				// options
   		'description' => 'Description of what the widget does'
   	)
);

/**
    * Display the wpdocs widget
    */
function wpdocs_widget_display($args) {
      echo $args['before_widget'];
      echo $args['before_title'] . 'The Wpdocs Widget' .  $args['after_title'];
      echo $args['after_widget'];
      // Print some HTML for the widget to display here.
      echo __( 'Wpdocs Widget Test', 'textdomain' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register_sidebar_widget%2F%3Freplytocom%3D665%23feedback-editor-665)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register_sidebar_widget%2F) before being able to contribute a note or feedback.

Notifications