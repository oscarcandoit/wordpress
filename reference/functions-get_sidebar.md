---
url: https://developer.wordpress.org/reference/functions/get_sidebar
scraped_at: 2025-10-20T03:22:31.460Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_sidebar/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_sidebar()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_sidebar()

Search

# get\_sidebar( string\|null$name = null, array$args = array() ): void\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_sidebar/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_sidebar/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_sidebar/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_sidebar/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_sidebar/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_sidebar/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_sidebar/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_sidebar/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_sidebar/#wp--skip-link--target)

Loads sidebar template.

## [Description](https://developer.wordpress.org/reference/functions/get_sidebar/\#description)

Includes the sidebar template for a theme or if a name is specified then a specialized sidebar will be included.

For the parameter, if the file is called "sidebar-special.php" then specify "special".

## [Parameters](https://developer.wordpress.org/reference/functions/get_sidebar/\#parameters)

`$name` string\|nulloptional

The name of the specialized sidebar.

Default: `null`

`$args` arrayoptional

Additional arguments passed to the sidebar template.

Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/get_sidebar/\#return)

void\|false Void on success, false if the template does not exist.

## [Source](https://developer.wordpress.org/reference/functions/get_sidebar/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_sidebar/#)

[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)

```php
function get_sidebar( $name = null, $args = array() ) {
	/**
	 * Fires before the sidebar template file is loaded.
	 *
	 * @since 2.2.0
	 * @since 2.8.0 The `$name` parameter was added.
	 * @since 5.5.0 The `$args` parameter was added.
	 *
	 * @param string|null $name Name of the specific sidebar file to use. Null for the default sidebar.
	 * @param array       $args Additional arguments passed to the sidebar template.
	 */
	do_action( 'get_sidebar', $name, $args );

	$templates = array();
	$name      = (string) $name;
	if ( '' !== $name ) {
		$templates[] = "sidebar-{$name}.php";
	}

	$templates[] = 'sidebar.php';

	if ( ! locate_template( $templates, true, true, $args ) ) {
		return false;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L115) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L115-L139)

## [Hooks](https://developer.wordpress.org/reference/functions/get_sidebar/\#hooks)

[do\_action( ‘get\_sidebar’, string\|null$name, array$args )](https://developer.wordpress.org/reference/hooks/get_sidebar/)

Fires before the sidebar template file is loaded.

## [Related](https://developer.wordpress.org/reference/functions/get_sidebar/\#related)

| Uses | Description |
| --- | --- |
| [locate\_template()](https://developer.wordpress.org/reference/functions/locate_template/) `wp-includes/template.php` | Retrieves the name of the highest priority template file that exists. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_sidebar/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | The `$args` parameter was added. |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_sidebar/\#user-contributed-notes)

1. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-474)



**Simple call**


Assume you have file `wp-content/yourTheme/sidebar-nice-bar.php`. The way you can include this sidebar in your page is:





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<?php get_sidebar('nice-bar'); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D474%23feedback-editor-474)

2. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-476)



**Left and Right Sidebars**


Two sidebars in one theme.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<?php get_header(); ?>
<?php get_sidebar( 'left' ); ?>
<?php get_sidebar( 'right' ); ?>
<?php get_footer(); ?>
```





The file names for the right and left sidebars should be `sidebar-right.php` ` and ` `sidebar-left.php` respectively.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D476%23feedback-editor-476)

3. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-477)



**Multi sidebars**


Different sidebar for different pages.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<?php
if ( is_home() ) :
     get_sidebar( 'home' );
elseif ( is_404() ) :
     get_sidebar( '404' );
else :
     get_sidebar();
endif;
?>
```





The file names for the home and 404 sidebars should be `sidebar-home.php` and `sidebar-404.php` respectively.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D477%23feedback-editor-477)

4. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-475)



**Simple 404 page**


The following code is a simple example of a template for an “HTTP 404: Not Found” error (which you could include in your Theme as 404.php).





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<?php get_header(); ?>
<h2>Error 404 - Not Found</h2>
<?php get_sidebar(); ?>
<?php get_footer(); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D475%23feedback-editor-475)

5. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-4567)



**Call sidebar with $args parameter (Since 5.5.0)**


Consider below is your sidebar call from anywhere inside your theme,





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<?php
$args = array(
   	'title' => 'Shop sidebar'
);

get_sidebar( 'shop', $args );

?>
```





Your codes inside `sidebar-shop.php` file might look a like below.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
<div id="secondary" class="widget-area sidebar-shop" role="complementary">
   	<h2><?php echo esc_html( $args['title'] ); ?><h2>
   	<?php dynamic_sidebar( 'sidebar-shop' ); ?>
</div><!-- #secondary -->
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D4567%23feedback-editor-4567)

6. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/get_sidebar/#comment-content-3136)



**Conditional Statement for Any Sidebar**


In case you are making a plugin template where you do not know if there is a sidebar, for any given theme the plugin may be used with, you may check for `register_sidebar` function to see if any sidebar exists.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
if ( function_exists( 'register_sidebar' ) ) {
   	get_sidebar();
}
```





Or, if you know the theme registered name for the sidebar in question try:





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_sidebar/#)




```php
//for twenty-sixteen theme
       if ( is_active_sidebar( 'content-bottom' ) ) :
           get_sidebar( 'content-bottom' );
       endif;
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F%3Freplytocom%3D3136%23feedback-editor-3136)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_sidebar%2F) before being able to contribute a note or feedback.

Notifications