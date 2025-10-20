---
url: https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories
scraped_at: 2025-10-20T03:19:33.778Z
---

[Skip to content](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Determining Plugin and Content Directories


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Plugin Basics](https://developer.wordpress.org/plugins/plugin-basics/)Determining Plugin and Content Directories

Search

# Determining Plugin and Content Directories

## In this article

Table of Contents

- [Common Usage](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#common-usage)
- [Available Functions](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#available-functions)
  - [Plugins](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#plugins)
  - [Themes](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#themes)
  - [Site Home](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#site-home)
  - [WordPress](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#wordpress)
  - [Multisite](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#multisite)
- [Constants](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#constants)
- [Related](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#related)

[↑ Back to top](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#wp--skip-link--target)

When coding WordPress plugins you often need to reference various files and folders throughout the WordPress installation and within your plugin or theme.

WordPress provides several functions for easily determining where a given file or directory lives. Always use these functions in your plugins instead of hard-coding references to the wp-content directory or using the WordPress internal constants.

WordPress allows users to place their wp-content directory anywhere they want and rename it whatever they want. Never assume that plugins will be in wp-content/plugins, uploads will be in wp-content/uploads, or that themes will be in wp-content/themes.

PHP’s `__FILE__` magic-constant resolves symlinks automatically, so if the `wp-content` or `wp-content/plugins` or even the individual plugin directory is symlinked, hardcoded paths will not work correctly.

## [Common Usage](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#common-usage)

If your plugin includes JavaScript files, CSS files or other external files, then it’s likely you’ll need the URL to these files so you can load them into the page. To do this you should use the [plugins\_url()](https://developer.wordpress.org/reference/functions/plugins_url/) function like so:

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
plugins_url( 'myscript.js', __FILE__ );
```

This will return the full URL to myscript.js, such as `example.com/wp-content/plugins/myplugin/myscript.js`.

To load your plugins’ JavaScript or CSS into the page you should use [`wp_enqueue_script()`](https://developer.wordpress.org/reference/functions/wp_enqueue_script/) or [`wp_enqueue_style()`](https://developer.wordpress.org/reference/functions/wp_enqueue_style/) respectively, passing the result of `plugins_url()` as the file URL.

## [Available Functions](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#available-functions)

WordPress includes many other functions for determining paths and URLs to files or directories within plugins, themes, and WordPress itself. See the individual DevHub pages for each function for complete information on their use.

### [Plugins](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#plugins)

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
plugins_url()
plugin_dir_url()
plugin_dir_path()
plugin_basename()
```

### [Themes](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#themes)

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
get_template_directory_uri()
get_stylesheet_directory_uri()
get_stylesheet_uri()
get_theme_root_uri()
get_theme_root()
get_theme_roots()
get_stylesheet_directory()
get_template_directory()
```

### [Site Home](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#site-home)

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
home_url()
get_home_path()
```

### [WordPress](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#wordpress)

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
admin_url()
site_url()
content_url()
includes_url()
wp_upload_dir()
```

### [Multisite](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#multisite)

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
get_admin_url()
get_home_url()
get_site_url()
network_admin_url()
network_site_url()
network_home_url()
```

## [Constants](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#constants)

WordPress makes use of the following constants when determining the path to the content and plugin directories. These should not be used directly by plugins or themes, but are listed here for completeness.

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/#)

```php
WP_CONTENT_DIR  // no trailing slash, full paths only
WP_CONTENT_URL  // full url
WP_PLUGIN_DIR  // full path, no trailing slash
WP_PLUGIN_URL  // full url, no trailing slash

// Available per default in MS, not set in single site install
// Can be used in single site installs (as usual: at your own risk)
UPLOADS // (If set, uploads folder, relative to ABSPATH) (for e.g.: /wp-content/uploads)
```

## [Related](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/\#related)

**WordPress Directories**:

|     |     |     |
| --- | --- | --- |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) | Home URL | [http://www.example.com](http://www.example.com/) |
| [site\_url()](https://developer.wordpress.org/reference/functions/site_url/) | Site directory URL | [http://www.example.com](http://www.example.com/) or [http://www.example.com/wordpress](http://www.example.com/wordpress) |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) | Admin directory URL | [http://www.example.com/wp-admin](http://www.example.com/wp-admin) |
| [includes\_url()](https://developer.wordpress.org/reference/functions/includes_url/) | Includes directory URL | [http://www.example.com/wp-includes](http://www.example.com/wp-includes) |
| [content\_url()](https://developer.wordpress.org/reference/functions/content_url/) | Content directory URL | [http://www.example.com/wp-content](http://www.example.com/wp-content) |
| [plugins\_url()](https://developer.wordpress.org/reference/functions/plugins_url/) | Plugins directory URL | [http://www.example.com/wp-content/plugins](http://www.example.com/wp-content/plugins) |
| [wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) | Upload directory URL (returns an array) | [http://www.example.com/wp-content/uploads](http://www.example.com/wp-content/uploads) |

First published

March 22, 2019

Last updated

February 20, 2024

[PreviousBest PracticesPrevious: Best Practices](https://developer.wordpress.org/plugins/plugin-basics/best-practices/)

[NextIncluding a Software LicenseNext: Including a Software License](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/)

Notifications