---
url: https://developer.wordpress.org/reference/functions/bloginfo
scraped_at: 2025-10-20T03:39:52.703Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/bloginfo/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

bloginfo()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)bloginfo()

Search

# bloginfo( string$show = '' )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/bloginfo/#description)
  - [See also](https://developer.wordpress.org/reference/functions/bloginfo/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/bloginfo/#parameters)
- [More Information](https://developer.wordpress.org/reference/functions/bloginfo/#more-information)
  - [Possible values for $show](https://developer.wordpress.org/reference/functions/bloginfo/#possible-values-for-show)
- [Source](https://developer.wordpress.org/reference/functions/bloginfo/#source)
- [Related](https://developer.wordpress.org/reference/functions/bloginfo/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/bloginfo/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/bloginfo/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/bloginfo/#wp--skip-link--target)

Displays information about the current site.

## [Description](https://developer.wordpress.org/reference/functions/bloginfo/\#description)

### [See also](https://developer.wordpress.org/reference/functions/bloginfo/\#see-also)

- [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo): For possible `$show` values

## [Parameters](https://developer.wordpress.org/reference/functions/bloginfo/\#parameters)

`$show` stringoptional

Site information to display.

Default: `''`

## [More Information](https://developer.wordpress.org/reference/functions/bloginfo/\#more-information)

Displays information about your site, mostly gathered from the information you supply in your [User Profile](https://codex.wordpress.org/Administration_Panels#Your_Profile "Administration Panels") and [General Settings](https://codex.wordpress.org/Administration_Panels#General_Settings "Administration Panels") WordPress [Administration Screens](https://codex.wordpress.org/Administration_Screens "Administration Screens"). It can be used anywhere within a template file. This always prints a result to the browser. If you need the values for use in PHP, use [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/ "Function Reference/get bloginfo").

### [Possible values for $show](https://developer.wordpress.org/reference/functions/bloginfo/\#possible-values-for-show)

- ‘ **name**‘ – Displays the “Site Title” set in Settings > General. This data is retrieved from the “blogname” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description").
- ‘ **description**‘ – Displays the “Tagline” set in Settings > General. This data is retrieved from the “blogdescription” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description").
- ‘ **wpurl**‘ – Displays the “WordPress address (URL)” set in Settings > General. This data is retrieved from the “siteurl” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description"). Consider echoing [site\_url()](https://developer.wordpress.org/reference/functions/site_url/ "Function Reference/site url") instead, especially for multi-site configurations using paths instead of subdomains (it will return the root site not the current sub-site).
- ‘ **url**‘ – Displays the “Site address (URL)” set in Settings > General. This data is retrieved from the “home” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description"). Consider echoing [home\_url()](https://developer.wordpress.org/reference/functions/home_url/ "Function Reference/home url") instead.
- ‘ **admin\_email**‘ – Displays the “E-mail address” set in Settings > General. This data is retrieved from the “admin\_email” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description").
- ‘ **charset**‘ – Displays the “Encoding for pages and feeds” set in Settings > Reading. This data is retrieved from the “blog\_charset” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description"). **Note:** this parameter always echoes “UTF-8”, which is the default encoding of WordPress.
- ‘ **version**‘ – Displays the WordPress Version you use. This data is retrieved from the `$wp_version` variable set in `wp-includes/version.php`.
- ‘ **html\_type**‘ – Displays the Content-Type of WordPress HTML pages (default: “text/html”). This data is retrieved from the “html\_type” record in the [wp\_options table](https://codex.wordpress.org/Database_Description#Table:_wp_options "Database Description"). Themes and plugins can override the default value using the `[pre\_option\_html\_type](https://developer.wordpress.org/reference/hooks/pre_option_option/ "Plugin API/Filter Reference")` filter.
- ‘ **text\_direction**‘ – Displays the Text Direction of WordPress HTML pages. Consider using [is\_rtl()](https://developer.wordpress.org/reference/functions/is_rtl/ "Function Reference/is rtl") instead.
- ‘ **language**‘ – Displays the language of WordPress.
- ‘ **stylesheet\_url**‘ – Displays the primary CSS (usually _style.css_) file URL of the active theme. Consider echoing [get\_stylesheet\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_uri/ "Function Reference/get stylesheet uri") instead.
- ‘ **stylesheet\_directory**‘ – Displays the stylesheet directory URL of the active theme. (Was a local path in earlier WordPress versions.) Consider echoing [get\_stylesheet\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory_uri/ "Function Reference/get stylesheet directory uri") instead.
- ‘ **template\_url**‘ / ‘ **template\_directory**‘ – URL of the active theme’s directory. Within child themes, both get\_bloginfo(‘template\_url’) and [get\_template()](https://developer.wordpress.org/reference/functions/get_template/) will return the _parent_ theme directory. Consider echoing [get\_template\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_template_directory_uri/ "Function Reference/get template directory uri") instead (for the parent template directory) or [get\_stylesheet\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory_uri/ "Function Reference/get stylesheet directory uri") (for the child template directory).
- ‘ **pingback\_url**‘ – Displays the Pingback XML-RPC file URL ( _xmlrpc.php_).
- ‘ **atom\_url**‘ – Displays the Atom feed URL ( _/feed/atom_).
- ‘ **rdf\_url**‘ – Displays the RDF/RSS 1.0 feed URL ( _/feed/rfd_).
- ‘ **rss\_url**‘ – Displays the RSS 0.92 feed URL ( _/feed/rss_).
- ‘ **rss2\_url**‘ – Displays the RSS 2.0 feed URL ( _/feed_).
- ‘ **comments\_atom\_url**‘ – Displays the comments Atom feed URL ( _/comments/feed_).
- ‘ **comments\_rss2\_url**‘ – Displays the comments RSS 2.0 feed URL ( _/comments/feed_).
- ‘ **siteurl**‘ – Deprecated since version 2.2. Echo [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) , or use bloginfo(‘url’).
- ‘ **home**‘ – Deprecated since version 2.2. Echo [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) , or use bloginfo(‘url’).

## [Source](https://developer.wordpress.org/reference/functions/bloginfo/\#source)

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)

```php
function bloginfo( $show = '' ) {
	echo get_bloginfo( $show, 'display' );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L761) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L761-L763)

## [Related](https://developer.wordpress.org/reference/functions/bloginfo/\#related)

| Uses | Description |
| --- | --- |
| [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/) `wp-includes/general-template.php` | Retrieves information about the current site. |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Widget\_Types\_Controller::render\_legacy\_widget\_preview\_iframe()](https://developer.wordpress.org/reference/classes/wp_rest_widget_types_controller/render_legacy_widget_preview_iframe/) `wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php` | Renders a page containing a preview of the requested Legacy Widget block. |
| [login\_header()](https://developer.wordpress.org/reference/functions/login_header/) `wp-login.php` | Outputs the login page header. |
| [\_wp\_admin\_html\_begin()](https://developer.wordpress.org/reference/functions/_wp_admin_html_begin/) `wp-admin/includes/template.php` | Prints out the beginning of the admin HTML header. |
| [iframe\_header()](https://developer.wordpress.org/reference/functions/iframe_header/) `wp-admin/includes/template.php` | Generic Iframe header for use with Thickbox. |
| [wp\_iframe()](https://developer.wordpress.org/reference/functions/wp_iframe/) `wp-admin/includes/media.php` | Outputs the iframe to display the media upload page. |
| [Custom\_Image\_Header::step\_1()](https://developer.wordpress.org/reference/classes/custom_image_header/step_1/) `wp-admin/includes/class-custom-image-header.php` | Displays first step of custom header image page. |

[Show 1 more](https://developer.wordpress.org/reference/functions/bloginfo/#) [Show less](https://developer.wordpress.org/reference/functions/bloginfo/#)

## [Changelog](https://developer.wordpress.org/reference/functions/bloginfo/\#changelog)

| Version | Description |
| --- | --- |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/bloginfo/\#user-contributed-notes)

1. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-979)



If using bloginfo as a variable, for example: `$url = bloginfo('url');` it will return null. This is because `bloginfo()` echos the result immediately. So if you want to use any of the `bloginfo()` parameters as variables use [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/). This function returns the result as a string.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D979%23feedback-editor-979)

2. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-301)



**Show Blog Title**



Display your blog's title in a tag.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<h1><?php bloginfo( 'name' ); ?></h1>
```







[Show feedback (1)](https://developer.wordpress.org/reference/functions/bloginfo/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D301%23feedback-editor-301)



- “title” also seems to work instead of “name.”



[Dan Knauss](https://profiles.wordpress.org/dpknauss/) [1 year ago](https://developer.wordpress.org/reference/functions/bloginfo/#comment-7125)


3. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-516)



**Show Blog Description**



Displays the tagline of your blog as set in Settings > General.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<p><?php bloginfo('description'); ?> </p>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D516%23feedback-editor-516)

4. [Skip to note 13 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-514)



**Show Blog Title in Link**



Displays your blog’s title in a link.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<a href="<?php bloginfo('url'); ?>" title="<?php bloginfo('name'); ?>"><?php bloginfo('name'); ?></a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D514%23feedback-editor-514)

5. [Skip to note 14 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-1697)



Practical example that could be used as it is in themes. Hides description if empty.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<?php if ( get_bloginfo( 'description' )  !== '' ) { ?>
   	<a class="site-description"><?php bloginfo( 'description' ); ?></a>
<?php } ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D1697%23feedback-editor-1697)

6. [Skip to note 15 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-517)



**Example output**



In this example case, the Site Address (URL) is shown as [http://www.example.com/home](http://www.example.com/home), and the WordPress address (URL) is displayed as [http://www.example.com/home/wp](http://www.example.com/home/wp).



Please note that directory URLs are missing trailing slashes.





`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/bloginfo/#)

[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
admin_email          = admin@example.com
atom_url             = http://www.example.com/home/feed/atom
charset              = UTF-8
comments_atom_url    = http://www.example.com/home/comments/feed/atom
comments_rss2_url    = http://www.example.com/home/comments/feed
description          = Just another WordPress blog
home                 = http://www.example.com/home (DEPRECATED! use url option instead)
html_type            = text/html
language             = en-US
name                 = Testpilot
pingback_url         = http://www.example.com/home/wp/xmlrpc.php
rdf_url              = http://www.example.com/home/feed/rdf
rss2_url             = http://www.example.com/home/feed
rss_url              = http://www.example.com/home/feed/rss
siteurl              = http://www.example.com/home (DEPRECATED! use url option instead)
stylesheet_directory = http://www.example.com/home/wp/wp-content/themes/largo
stylesheet_url       = http://www.example.com/home/wp/wp-content/themes/largo/style.css
template_directory   = http://www.example.com/home/wp/wp-content/themes/largo
template_url         = http://www.example.com/home/wp/wp-content/themes/largo
text_direction       = ltr
url                  = http://www.example.com/home
version              = 3.5
wpurl                = http://www.example.com/home/wp
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D517%23feedback-editor-517)

7. [Skip to note 16 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-515)



**Show Character Set**



Displays the character set your blog is using (e.g. “utf-8”).

**NOTE:** In version 3.5 and later, default character encoding is set to UTF-8 and is not configurable from the Administration Screen.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<p>Character set: <?php bloginfo('charset'); ?> </p>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D515%23feedback-editor-515)

8. [Skip to note 17 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-2973)





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<h1><a href="<?php bloginfo( 'url' ); ?>"><?php bloginfo( 'name' ); ?></a></h1>
   			<h3><?php bloginfo( 'description' ); ?></h3>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D2973%23feedback-editor-2973)

9. [Skip to note 18 content](https://developer.wordpress.org/reference/functions/bloginfo/#comment-content-2877)



show website blog name in header





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/bloginfo/#)




```php
<title><?php bloginfo('name') ?></title>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F%3Freplytocom%3D2877%23feedback-editor-2877)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fbloginfo%2F) before being able to contribute a note or feedback.

Notifications