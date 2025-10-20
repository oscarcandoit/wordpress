---
url: https://make.wordpress.org/core/handbook/best-practices/core-apis/
scraped_at: 2025-10-20T02:59:57.008Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcore%2Fhandbook%2Fbest-practices%2Fcore-apis%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/core/handbook/best-practices/core-apis/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Core](https://make.wordpress.org/core)

Core APIs

[Home](https://make.wordpress.org/core)[Handbook](https://make.wordpress.org/core/handbook/)[Best Practices](https://make.wordpress.org/core/handbook/best-practices/)Core APIs

Search

# Core APIs

## In this article

Table of Contents

- [Why You Should Use The Core APIs](https://make.wordpress.org/core/handbook/best-practices/core-apis/#why-you-should-use-the-core-apis)
- [WordPress Core APIs](https://make.wordpress.org/core/handbook/best-practices/core-apis/#wordpress-core-apis)
  - [Dashboard Widgets API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#dashboard-widgets-api)
  - [Database API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#database-api)
  - [File Header API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#file-header-api)
  - [Filesystem API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#filesystem-api)
  - [HTTP API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#http-api)
  - [Metadata API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#metadata-api)
  - [Options API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#options-api)
  - [Plugin API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#plugin-api)
  - [Quicktags API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#quicktags-api)
  - [Rewrite API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#rewrite-api)
  - [Settings API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#settings-api)
  - [Shortcode API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#shortcode-api)
  - [Theme Modification API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#theme-modification-api)
  - [Theme Customization API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#theme-customization-api)
  - [Transients API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#transients-api)
  - [Widgets API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#widgets-api)
  - [XML-RPC WordPress API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#xml-rpc-wordpress-api)
- [WordPress.org API](https://make.wordpress.org/core/handbook/best-practices/core-apis/#wordpress-org-api)
- [Other Resources](https://make.wordpress.org/core/handbook/best-practices/core-apis/#other-resources)

[↑ Back to top](https://make.wordpress.org/core/handbook/best-practices/core-apis/#wp--skip-link--target)

The [WordPress Core Application Programming Interface (API)](https://codex.wordpress.org/WordPress_APIs "WordPress Core Application Programming Interface (API)") is comprised of several individual APIs, each one covering the functions involved in, and use of, a given set of functionality. Together, these form the project interface which allows plugins and themes to interact with, alter, and extend WordPress core functionality.

## [Why You Should Use The Core APIs](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#why-you-should-use-the-core-apis)

Using the core APIs when developing for WordPress is strongly encouraged because:

- Core APIs make building things for WordPress easier by providing hooks, actions, filters, helper functions.
- WordPress does the “heavy lifting” for you (database calls, input validation, security, form building) so you don’t have to.
- Using core APIs ensures your code will be both backward-compatible and future-proof.
- The APIs allow seamless integration into wp-admin for plugin/theme options pages, inline help documentation, etc.

## [WordPress Core APIs](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#wordpress-core-apis)

The following is an overview of the individual APIs that make up the WordPress Core API. More information on each API can be found on their respective Codex pages.

### [Dashboard Widgets API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#dashboard-widgets-api)

The [Dashboard Widgets API](https://developer.wordpress.org/apis/handbook/dashboard-widgets/ "Dashboard Widgets API"), added in WordPress 2.7, makes it very simple for plugin or theme authors to add new widgets to the admin dashboard. Widgets created using the API will automatically appear on the admin dashboard, will contain all the standard custom features including drag/drop, minimize, and configure, and appear in the screen options so users can hide them, if desired.

### [Database API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#database-api)

The [Database API](https://developer.wordpress.org/apis/handbook/database/ "Database API"), added in WordPress 0.71, provides the correct method for accessing data as named values which are stored in the database layer.

### [File Header API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#file-header-api)

The [File Header API](https://codex.wordpress.org/File_Header_API "File Header API"), added in WordPress 1.5 and extended in WordPress 2.9 and 3.0, consists of functions and hooks regarding the use of file headers in themes and plugins, and provides the ability to pull meta-information (Name, Version, Author, URI, Description, etc.) from those files.

### [Filesystem API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#filesystem-api)

The [Filesystem API](https://codex.wordpress.org/Filesystem_API "Filesystem API"), added in WordPress 2.6, was originally created for WordPress’ own automatic updates feature. The API abstracts out the functionality needed for reading and writing local files to the filesystem to be done securely, on a variety of host types, using the **WP\_Filesystem\_Base** class, and several sub-classes which implement different ways of connecting to the local filesystem, depending on individual host support.

### [HTTP API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#http-api)

The [HTTP API](https://developer.wordpress.org/plugins/http-api/ "HTTP API"), added in WordPress 2.7 and extended further in WordPress 2.8, standardizes the HTTP requests for WordPress. The API handles cookies, gzip encoding and decoding, chunk decoding (if HTTP 1.1), and various other HTTP protocol implementations. The API standardizes requests, tests each method prior to sending, and, based on your server configuration, uses the appropriate method to make the request.

### [Metadata API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#metadata-api)

The [Metadata API](https://codex.wordpress.org/Metadata_API "Metadata API"), added in WordPress 2.9, is a simple and standardized way for retrieving and manipulating metadata of various WordPress object types. Metadata for an object is a represented by a simple key-value pair. Objects may contain multiple metadata entries that share the same key, and differ only in their value.

### [Options API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#options-api)

The [Options API](https://codex.wordpress.org/Options_API "Options API"), added in WordPress 1.0 and extended in versions 1.2 and 1.5, is a simple and standardized way of storing data in the database. The API makes it easy to create, access, update, and delete those options. All the data is being stored in the `wp_options` table under a given custom name.

### [Plugin API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#plugin-api)

The [Plugin API](https://codex.wordpress.org/Plugin_API "Plugin API"), added in WordPress 1.5, allows for creating actions and filters in hooking functions and methods. The functions or methods will then be run when the action or filter is called. Hooks are provided by WordPress to allow your plugin to _hook into_ the rest of WordPress; that is, to call functions in your plugin at specific times, and set your plugin in motion.

### [Quicktags API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#quicktags-api)

The [Quicktags API](https://codex.wordpress.org/Quicktags_API "Quicktags API"), added in WordPress 3.3, allows you to include additional buttons in the Text (HTML) mode of the WordPress editor.

### [Rewrite API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#rewrite-api)

The [Rewrite API](https://codex.wordpress.org/Rewrite_API "Rewrite API"), added in WordPress 2.1, is used to manage the rewrite rules that allow you to use the **Pretty Permalinks** feature. It has several methods that generate the rewrite rules from values in the database. It is used internally when updating the rewrite rules, and also to find the URL of a specific post, page, category archive, etc. It also allows theme and plugin developers to specify new, custom rewrite rules.

### [Settings API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#settings-api)

The [Settings API](https://codex.wordpress.org/Settings_API "Settings API"), added in WordPress 2.7, allows admin pages containing settings forms to be created and managed semi-automatically. It lets plugin and theme developers define settings pages, sections within those pages, and fields within the sections. New settings pages can be registered, and new settings sections or fields can be added to existing settings pages.

### [Shortcode API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#shortcode-api)

The [Shortcode API](https://codex.wordpress.org/Shortcode_API "Shortcode API"), added in WordPress 2.5, is a set of functions that create a simple hook used to pull in content. Using the API, plugin developers can create special kinds of content (e.g. forms, content generators, galleries, etc.) that users can add to posts or pages by inserting the corresponding **\[shortcode\]** into the content.

### [Theme Modification API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#theme-modification-api)

The [Theme Modification API](https://codex.wordpress.org/Theme_Modification_API "Theme Modification API"), added in WordPress 2.1, consists of the functions and hooks related to the use of theme modification values. These functions can be used by theme authors to save and retrieve modifications to their themes as options.

### [Theme Customization API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#theme-customization-api)

The [Theme Customization API](https://codex.wordpress.org/Theme_Customization_API "Theme Customization API"), added in WordPress 3.4, allows theme developers to add custom options specific to their theme to the Theme Customization admin screen (aka Theme Customizer).

### [Transients API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#transients-api)

The [Transients API](https://developer.wordpress.org/apis/handbook/transients/ "Transients API"), added in WordPress 2.8, offers a simple and standardized way of storing cached data in the database temporarily by giving it a custom name and a timeframe, after which it will expire and be deleted. The Transients API is very similar to the Options API, but with the added feature of an expiration time, which simplifies the process of using the `wp_options` database table to temporarily store cached information.

### [Widgets API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#widgets-api)

The [Widgets API](https://codex.wordpress.org/Widgets_API "Widgets API"), added in WordPress 2.8, allows developers to build custom widgets for use in sidebars and other widgetized areas of a theme. The API simplifies the widget creation process, and makes all widgets multiple instance capable.

### [XML-RPC WordPress API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#xml-rpc-wordpress-api)

The [XML-RPC WordPress API](https://codex.wordpress.org/XML-RPC_WordPress_API "XML-RPC WordPress API"), added in WordPress 1.5, allows other systems to connect to and communicate with WordPress, even remotely, including publishing clients (desktop and mobile), and other software that perform batch tasks like creating multiple posts from a file, etc.

## [WordPress.org API](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#wordpress-org-api)

There are also APIs available for the [WordPress.org site](https://codex.wordpress.org/WordPress.org_API "WordPress.org API"):

- **Secret Key**: Secret key and salt generator for `wp-config.php`.
- **Stats API**: Stats about the systems websites are running WordPress on.
- **Version Check API**: WordPress version checker.
- **Translations API**: Provides information on available translations for plugins and themes.
- **Credits API**: Details about the various individuals who contribute to the WordPress code base, which are used in the **Credits screen** in `/wp-admin/`.
- **Popular Import Plugin API**: List of popular import plugins in the WordPress Plugin Directory, which is used by the **Tools > Import screen** in `/wp-admin/`.
- **Plugins API**: Provides information on plugins hosted on WordPress.org, and allows WordPress to check the repository for updates to those plugins.
- **Themes API**: Provides information on themes hosted on WordPress.org, and allows WordPress to check the repository for updates to those themes.
- **Editor API**: Used by the theme and plugin editor to get a reference to documentation generated with phpDocumentor..
- **Events API**: Upcoming WordCamps and meetup events, filterable by location.
- **Browse Happy API**: Latest browser release matrix.
- **Serve Happy API**: WordPress PHP version compatibility matrix.

## [Other Resources](https://make.wordpress.org/core/handbook/best-practices/core-apis/\#other-resources)

- The WordPress Settings API (WordCamp Sofia 2012) \[ [Read](http://kovshenin.com/2012/the-wordpress-settings-api/ "Read the blog post")\] \[ [Watch](http://wordpress.tv/2012/10/31/konstantin-kovshenin-settings-api/ "Watch the video on WordPress.tv")\]

First published

May 25, 2013

Last updated

August 20, 2021

[PreviousBrowser supportPrevious: Browser support](https://make.wordpress.org/core/handbook/best-practices/browser-support/)

[NextSpellingNext: Spelling](https://make.wordpress.org/core/handbook/best-practices/spelling/)

[WordPress.org](https://wordpress.org/)[WordPress.org](https://wordpress.org/)

- [Visit our X (formerly Twitter) account](https://www.x.com/WordPress)
- [Visit our Bluesky account](https://bsky.app/profile/wordpress.org)
- [Visit our Mastodon account](https://mastodon.world/@WordPress)
- [Visit our Threads account](https://www.threads.net/@wordpress)
- [Visit our Facebook page](https://www.facebook.com/WordPress/)
- [Visit our Instagram account](https://www.instagram.com/wordpress/)
- [Visit our LinkedIn account](https://www.linkedin.com/company/wordpress)
- [Visit our TikTok account](https://www.tiktok.com/@wordpress)
- [Visit our YouTube channel](https://www.youtube.com/wordpress)
- [Visit our Tumblr account](https://wordpress.tumblr.com/)

![Code is Poetry](https://s.w.org/style/images/code-is-poetry-for-dark-bg.svg)

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment