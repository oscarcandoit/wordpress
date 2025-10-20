---
url: https://developer.wordpress.org/reference/functions/add_management_page
scraped_at: 2025-10-20T03:26:02.950Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/add_management_page/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

add\_management\_page()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)add\_management\_page()

Search

# add\_management\_page( string$page\_title, string$menu\_title, string$capability, string$menu\_slug, callable$callback = '', int$position = null ): string\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/add_management_page/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/add_management_page/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/add_management_page/#return)
- [More Information](https://developer.wordpress.org/reference/functions/add_management_page/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/add_management_page/#source)
- [Related](https://developer.wordpress.org/reference/functions/add_management_page/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/add_management_page/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_management_page/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/add_management_page/#wp--skip-link--target)

Adds a submenu page to the Tools main menu.

## [Description](https://developer.wordpress.org/reference/functions/add_management_page/\#description)

This function takes a capability which will be used to determine whether or not a page is included in the menu.

The function which is hooked in to handle the output of the page must check that the user has the required capability as well.

## [Parameters](https://developer.wordpress.org/reference/functions/add_management_page/\#parameters)

`$page_title` stringrequired

The text to be displayed in the title tags of the page when the menu is selected.

`$menu_title` stringrequired

The text to be used for the menu.

`$capability` stringrequired

The capability required for this menu to be displayed to the user.

`$menu_slug` stringrequired

The slug name to refer to this menu by (should be unique for this menu).

`$callback` callableoptional

The function to be called to output the content for this page.

Default: `''`

`$position` intoptional

The position in the menu order this item should appear.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/add_management_page/\#return)

string\|false The resulting page’s hook\_suffix, or false if the user does not have the capability required.

## [More Information](https://developer.wordpress.org/reference/functions/add_management_page/\#more-information)

##### [Example:](https://developer.wordpress.org/reference/functions/add_management_page/\#example)

`add_management_page( 'Custom Permalinks', 'Custom Permalinks', 'manage_options', 'my-unique-identifier', 'custom_permalinks_options_page' );`

##### [Notes:](https://developer.wordpress.org/reference/functions/add_management_page/\#notes)

If you’re running into the » `You do not have sufficient permissions to access this page.`« message in a \` `wp_die()` \` screen, then you’ve hooked too early. The hook you should use is \` `admin_menu` \`.

## [Source](https://developer.wordpress.org/reference/functions/add_management_page/\#source)

`wp-admin/includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_management_page/#)

```php
function add_management_page( $page_title, $menu_title, $capability, $menu_slug, $callback = '', $position = null ) {
	return add_submenu_page( 'tools.php', $page_title, $menu_title, $capability, $menu_slug, $callback, $position );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/plugin.php#L1586) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/plugin.php#L1586-L1588)

## [Related](https://developer.wordpress.org/reference/functions/add_management_page/\#related)

| Uses | Description |
| --- | --- |
| [add\_submenu\_page()](https://developer.wordpress.org/reference/functions/add_submenu_page/) `wp-admin/includes/plugin.php` | Adds a submenu page. |

## [Changelog](https://developer.wordpress.org/reference/functions/add_management_page/\#changelog)

| Version | Description |
| --- | --- |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Added the `$position` parameter. |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_management_page/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/add_management_page/#comment-content-963)



Example for adding a tool page :





`wp-admin/includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_management_page/#)

[Copy](https://developer.wordpress.org/reference/functions/add_management_page/#)




```php
class MyWPTool {

   	function __construct() {
   		   add_action( 'admin_menu', array( $this, 'admin_menu' ) );
   	}


   	function admin_menu() {
   		   $hook = add_management_page( 'My WP Tool Page', 'My WP Tool', 'install_plugins', 'mywptool', array( $this, 'admin_page' ), '' );
   		   add_action( "load-$hook", array( $this, 'admin_page_load' ) );
   	}


   	function admin_page_load() {
   		// ...
   	}

   	function admin_page() {
   		// ...
   	}

}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_management_page%2F%3Freplytocom%3D963%23feedback-editor-963)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/add_management_page/#comment-content-2983)





`wp-admin/includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/add_management_page/#)




```php
// Example
add_action ('admin_menu', function () {
   	add_management_page('Some page title', 'Title in the menu', 'install_plugins', 'some_unique_string', 'my_custom_page_render_function', '');
});

function my_custom_page_render_function()
{
   	echo 'This is content of the page';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_management_page%2F%3Freplytocom%3D2983%23feedback-editor-2983)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_management_page%2F) before being able to contribute a note or feedback.

Notifications