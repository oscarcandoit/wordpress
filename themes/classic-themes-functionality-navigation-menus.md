---
url: https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus
scraped_at: 2025-10-20T03:31:56.616Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Navigation Menus


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)Navigation Menus

Search

# Navigation Menus

## In this article

Table of Contents

- [Register Menus](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#register-menus)
- [Display Menus](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#display-menus)
- [Display Additional Contents](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#display-additional-contents)
- [Define Callback](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#define-callback)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#wp--skip-link--target)

Navigation Menus are customizable menus in your theme. They allow users to add Pages, Posts, Categories, and URLs to the menu. To create a navigation menu you’ll need to register it, and then display the menu in the appropriate location in your theme.

## [Register Menus](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/\#register-menus)

In your theme’s functions.php, you need to register your menu(s). This sets the name that will appear at **Appearance -> Menus**.

First of all, you will use [register\_nav\_menus()](https://developer.wordpress.org/reference/functions/register_nav_menus/) to register the menu.

In this example, two locations are added to the “Manage Locations” tab: “Header Menu” and “Extra Menu”.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#)

```php
function register_my_menus() {
  register_nav_menus(
    array(
      'header-menu' => __( 'Header Menu' ),
      'extra-menu' => __( 'Extra Menu' )
     )
   );
 }
 add_action( 'init', 'register_my_menus' );
```

## [Display Menus](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/\#display-menus)

Once you’ve registered your menus, you need to use [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) to tell your theme where to display them. For example, add the following code to your `header.php` file to display the header-menu that was registered above.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#)

```php
wp_nav_menu( array( 'theme_location' => 'header-menu' ) );
```

A full list of parameters can be found in the [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) page in the function reference

Repeat this process for any additional menus you want to display in your theme. Optionally, you can add a container class which allows you to style the menu with CSS.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#)

```php
wp_nav_menu(
  array(
    'theme_location' => 'extra-menu',
    'container_class' => 'my_extra_menu_class'
  )
);
```

A full list of CSS Classes can be found in the [wp\_nav\_menu()](https://developer.wordpress.org/reference/functions/wp_nav_menu/) page in the function reference. You can use these to style your menus.

## [Display Additional Contents](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/\#display-additional-contents)

Below is a simplified version of the Twenty Seventeen footer social menu, which displays `span` elements before and after the menu item label text.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#)

```php
wp_nav_menu(
  array(
    'menu' => 'primary',
    'link_before' => '<span class="screen-reader-text">',
    'link_after' => '</span>',
  )
);
```

The output will display as…

\[html\]

<div class="menu-social-container">

<ul id="menu-social">

<li id="menu-item-1">

<a href="http://twitter.com/"><span class="screen-reader-text">Twitter</span>

</li>

</ul>

</div>

\[/html\]

To display text between the `<li>` and `<a>` elements for each menu item, use `before` and `after` parameters.

## [Define Callback](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/\#define-callback)

By default, WordPress displays the first non-empty menu when the specified menu or location is not found, or generates a Page menu when there is no custom menu selected. To prevent this, use the `theme_location` and `fallback_cb` parameters.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/#)

```php
wp_nav_menu(
  array(
    'menu' => 'primary',
    // do not fall back to first non-empty menu
    'theme_location' => '__no_such_location',
    // do not fall back to wp_page_menu()
    'fallback_cb' => false
  )
);
```

First published

October 22, 2014

Last updated

March 17, 2017

[PreviousVideoPrevious: Video](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/)

[NextPaginationNext: Pagination](https://developer.wordpress.org/themes/classic-themes/functionality/pagination/)

Notifications