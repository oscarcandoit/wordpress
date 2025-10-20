---
url: https://developer.wordpress.org/reference/hooks/in_widget_form
scraped_at: 2025-10-20T03:20:00.893Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/in_widget_form/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

in\_widget\_form


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Widget::form\_callback](https://developer.wordpress.org/reference/classes/wp_widget/form_callback/)in\_widget\_form

Search

# do\_action\_ref\_array( ‘in\_widget\_form’, WP\_Widget$widget, null$return, array$instance )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/in_widget_form/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/in_widget_form/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/in_widget_form/#source)
- [Related](https://developer.wordpress.org/reference/hooks/in_widget_form/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/in_widget_form/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/in_widget_form/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/in_widget_form/#wp--skip-link--target)

Fires at the end of the widget control form.

## [Description](https://developer.wordpress.org/reference/hooks/in_widget_form/\#description)

Use this hook to add extra fields to the widget form. The hook is only fired if the value passed to the ‘widget\_form\_callback’ hook is not false.

Note: If the widget has no form, the text echoed from the default form method can be hidden using CSS.

## [Parameters](https://developer.wordpress.org/reference/hooks/in_widget_form/\#parameters)

`$widget` [WP\_Widget](https://developer.wordpress.org/reference/classes/wp_widget/)

The widget instance (passed by reference).

`$return` null

Return null if new fields are added.

`$instance` array

An array of the widget’s settings.

## [Source](https://developer.wordpress.org/reference/hooks/in_widget_form/\#source)

`wp-includes/class-wp-widget.php`
[Copy](https://developer.wordpress.org/reference/hooks/in_widget_form/#)

```php
do_action_ref_array( 'in_widget_form', array( &$this, &$return, $instance ) );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-widget.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-widget.php#L553) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-widget.php#L553-L553)

## [Related](https://developer.wordpress.org/reference/hooks/in_widget_form/\#related)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Widget\_Types\_Controller::get\_widget\_form()](https://developer.wordpress.org/reference/classes/wp_rest_widget_types_controller/get_widget_form/) `wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php` | Returns the output of [WP\_Widget::form()](https://developer.wordpress.org/reference/classes/wp_widget/form/) when called with the provided instance. Used by encode\_form\_data() to preview a widget’s form. |
| [WP\_Widget::form\_callback()](https://developer.wordpress.org/reference/classes/wp_widget/form_callback/) `wp-includes/class-wp-widget.php` | Generates the widget control form (Do NOT override). |

## [Changelog](https://developer.wordpress.org/reference/hooks/in_widget_form/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/in_widget_form/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/in_widget_form/#comment-content-4291)



Add custom widget field end of the widgets control form.





`wp-includes/class-wp-widget.php`
[Expand code](https://developer.wordpress.org/reference/hooks/in_widget_form/#)

[Copy](https://developer.wordpress.org/reference/hooks/in_widget_form/#)




```php
if ( ! function_exists( 'wpdocs_display_custom_field_in_widget_form' ) ) {

       add_action( 'in_widget_form', 'wpdocs_display_custom_field_in_widget_form', 10, 3 );

       /**
        * Append custom field end of the widgets control form
        * Fires at the end of the widget control form.
        */
       function wpdocs_display_custom_field_in_widget_form( $widget, $return, $instance ) {
           $column = isset( $instance['column'] ) ? $instance['column'] : '';

           ob_start();
           ?>

           <p>
               <label for="<?php echo esc_attr( $widget->get_field_id( 'itclan_bs_grid_class' ) ) ?>"><?php _e( 'Column Label', 'text_domain' ) ?>
                   <input class="widefat" value="<?php echo esc_attr( $column ) ?>" id="<?php echo esc_attr( $widget->get_field_id( 'column' ) ) ?>" name="<?php echo esc_attr( $widget->get_field_name( 'column' ) ) ?>" type="text" />
                   <small><?php _e( 'Some additional description.', 'text_domain' ) ?></small>
               </label>
           </p>

           <?php
           echo ob_get_clean();
       }
}
```





Filter widget’s settings before saving. It will save our custom field `column` data.





`wp-includes/class-wp-widget.php`
[Expand code](https://developer.wordpress.org/reference/hooks/in_widget_form/#)

[Copy](https://developer.wordpress.org/reference/hooks/in_widget_form/#)




```php
if ( ! function_exists( 'wpdocs_update_custom_field_in_widget_form' ) ) {

       add_action( 'widget_update_callback', 'wpdocs_update_custom_field_in_widget_form', 10, 2 );

       /**
        * Update widget fields
        * Filters a widget’s settings before saving.
        */
       function wpdocs_update_custom_field_in_widget_form( $instance, $new_instance ) {
           $instance['column'] = ! empty( $new_instance['column'] ) ? $new_instance['column'] : '';
           return $instance;
       }
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fin_widget_form%2F%3Freplytocom%3D4291%23feedback-editor-4291)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fin_widget_form%2F) before being able to contribute a note or feedback.

Notifications