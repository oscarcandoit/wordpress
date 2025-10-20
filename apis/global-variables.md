---
url: https://developer.wordpress.org/apis/global-variables
scraped_at: 2025-10-20T04:08:35.288Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/global-variables/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Global Variables


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Global Variables

Search

# Global Variables

## In this article

Table of Contents

- [Introduction](https://developer.wordpress.org/apis/global-variables/#introduction)
  - [Inside the Loop variables](https://developer.wordpress.org/apis/global-variables/#inside-the-loop-variables)
  - [Browser Detection Booleans](https://developer.wordpress.org/apis/global-variables/#browser-detection-booleans)
  - [Web Server Detection Booleans](https://developer.wordpress.org/apis/global-variables/#web-server-detection-booleans)
  - [Version Variables](https://developer.wordpress.org/apis/global-variables/#version-variables)
  - [Misc](https://developer.wordpress.org/apis/global-variables/#misc)
  - [Admin Globals](https://developer.wordpress.org/apis/global-variables/#admin-globals)

[↑ Back to top](https://developer.wordpress.org/apis/global-variables/#wp--skip-link--target)

## [Introduction](https://developer.wordpress.org/apis/global-variables/\#introduction)

WordPress-specific global variables are used throughout WordPress code for various reasons. Almost all data that WordPress generates can be found in a global variable.

Note that it’s best to use the appropriate API functions when available, instead of modifying globals directly.

To access a global variable in your code, you first need to globalize the variable with `global $variable;`.

**Accessing other globals besides the ones listed below is not recommended.**

### [Inside the Loop variables](https://developer.wordpress.org/apis/global-variables/\#inside-the-loop-variables)

While inside the loop, these globals are set, containing information about the current post being processed.

- `$post` ( [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)): The post object for the current post. Object described in [WP\_Post Class Reference](https://developer.wordpress.org/reference/classes/wp_post/).
- `$posts`: Used by some core functions, not to be mistaken for `$query->$posts`.
- `$authordata` ( [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)): The author object for the current post. Object described in [WP\_User Class Reference](https://developer.wordpress.org/reference/classes/wp_user/).
- `$currentday` (string): Day that the current post was published.
- `$currentmonth` (string): Month that the curent post was published.
- `$page` (int): The page of the current post being viewed. Specified by the query var page.
- `$pages` (array): The content of the pages of the current post. Each page elements contains part of the content separated by the `<!--nextpage-->` tag.
- `$multipage` (boolean): Flag to know if the current post has multiple pages or not. Returns `true` if the post has multiple pages, related to `$pages`.
- `$more` (boolean): Flag to know if WordPress should enforce the `<!--more-->` tag for the current post. WordPress will not enforce the more tag if `true`.
- `$numpages` (int): Returns the number of pages in the post, related to `$pages`.

### [Browser Detection Booleans](https://developer.wordpress.org/apis/global-variables/\#browser-detection-booleans)

These globals store data about which browser the user is on.

- `$is_iphone` (boolean): iPhone Safari
- `$is_chrome` (boolean): Google Chrome
- `$is_safari` (boolean): Safari
- `$is_NS4` (boolean): Netscape 4
- `$is_opera` (boolean): Opera
- `$is_macIE` (boolean): Mac Internet Explorer
- `$is_winIE` (boolean): Windows Internet Explorer
- `$is_gecko` (boolean): FireFox
- `$is_lynx` (boolean): Lynx
- `$is_IE` (boolean): Internet Explorer
- `$is_edge` (boolean): Microsoft Edge

### [Web Server Detection Booleans](https://developer.wordpress.org/apis/global-variables/\#web-server-detection-booleans)

These globals store data about which web server WordPress is running on.

- `$is_apache` (boolean): Apache HTTP Server
- `$is_IIS` (boolean): Microsoft Internet Information Services (IIS)
- `$is_iis7` (boolean): Microsoft Internet Information Services (IIS) v7.x
- `$is_nginx` (boolean): Nginx web server

### [Version Variables](https://developer.wordpress.org/apis/global-variables/\#version-variables)

- `$wp_version` (string): The installed version of WordPress
- `$wp_db_version` (int): The version number of the database
- `$tinymce_version` (string): The installed version of TinyMCE
- `$manifest_version` (string): The cache manifest version
- `$required_php_version` (string): The version of PHP this install of WordPress requires
- `$required_mysql_version` (string): The version of MySQL this install of WordPress requires

### [Misc](https://developer.wordpress.org/apis/global-variables/\#misc)

- `$super_admins` (array): An array of user IDs that should be granted super admin privileges (multisite). This global is only set by the site owner (e.g., in `wp-config.php`), and contains an array of IDs of users who should have super admin privileges. If set it will override the list of super admins in the database.
- `$wp_query` (object): The global instance of the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) class.
- `$wp_rewrite` (object): The global instance of the [WP\_Rewrite](https://developer.wordpress.org/reference/classes/wp_rewrite/) class.
- `$wp` (object): The global instance of the [WP](https://developer.wordpress.org/reference/classes/wp/) environment setup class.
- `$wpdb` (object): The global instance of the [wpdb](https://developer.wordpress.org/reference/classes/wpdb/) class.
- `$wp_locale` (object): The global instance of the [WP\_Locale](https://developer.wordpress.org/reference/classes/wp_locale/) class.
- `$wp_admin_bar` (object): The global instance of the [WP\_Admin\_Bar](https://developer.wordpress.org/reference/classes/wp_admin_bar/) class.
- `$wp_roles` (object): The global instance of the [WP\_Roles](https://developer.wordpress.org/reference/classes/wp_roles/) class.
- `$wp_meta_boxes` (array): Object containing all registered metaboxes, including their id’s, args, callback functions and title for all post types including custom.
- `$wp_registered_sidebars` (array)
- `$wp_registered_widgets` (array)
- `$wp_registered_widget_controls` (array)
- `$wp_registered_widget_updates` (array)

### [Admin Globals](https://developer.wordpress.org/apis/global-variables/\#admin-globals)

- `$pagenow` (string): Used in wp-admin.

See also [get\_current\_screen()](https://developer.wordpress.org/reference/functions/get_current_screen/) for the WordPress Admin Screen API.
- `$post_type` (string): Used in wp-admin
- `$allowedposttags` (array)
- `$allowedtags` (array)
- `$menu` (array)

First published

August 12, 2019

Last updated

November 21, 2022

[PreviousFilesystemPrevious: Filesystem](https://developer.wordpress.org/apis/filesystem/)

[NextMetadataNext: Metadata](https://developer.wordpress.org/apis/metadata/)

Notifications