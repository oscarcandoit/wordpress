---
url: https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript
scraped_at: 2025-10-20T03:13:23.216Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Including CSS & JavaScript (Archived)


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Basics](https://developer.wordpress.org/themes/classic-themes/basics/)Including CSS & JavaScript (Archived)

Search

# Including CSS & JavaScript (Archived)

## In this article

Table of Contents

- [Enqueuing Scripts and Styles](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#enqueuing-scripts-and-styles)
  - [Stylesheets](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#stylesheets)
- [Including CSS for block styles](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#including-css-for-block-styles)
  - [Scripts](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#scripts)
  - [Delayed Script Loading](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#delayed-script-loading)
  - [The Comment Reply Script](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#the-comment-reply-script)
  - [Combining Enqueue Functions](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#combining-enqueue-functions)
- [Default Scripts Included and Registered by WordPress](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#default-scripts-included-and-registered-by-wordpress)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#wp--skip-link--target)

This is an old page that has been archived in favor of the newer [Including Assets documentation](https://developer.wordpress.org/themes/core-concepts/including-assets/) in the Core Concepts chapter. This page will eventually be removed and redirect to the newer doc.

When you’re creating your theme, you may want to create additional stylesheets or JavaScript files. However, remember that a WordPress website will not just have your theme active, it will also be using many different plugins. So that everything works harmoniously, it’s important that theme and plugins load scripts and stylesheets using the standard WordPress method. This will ensure the site remains efficient and that there are no incompatibility issues.

Adding scripts and styles to WordPress is a fairly simple process.   Essentially, you will create a function that will enqueue all of your scripts and styles. When enqueuing a script or stylesheet, WordPress creates a handle and path to find your file and any dependencies it may have (like jQuery) and then you will use a hook that will insert your scripts and stylesheets.

## [Enqueuing Scripts and Styles](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#enqueuing-scripts-and-styles)

The proper way to add scripts and styles to your theme is to enqueue them in the `functions.php` files. The `style.css` file is required in all themes, but it may be necessary to add other files to extend the functionality of your theme.

Tip: WordPress includes a number of JavaScript files as part of the software package, including commonly used libraries such as jQuery. Before adding your own JavaScript, [check to see if you can make use of an included library](https://developer.wordpress.org/themes/basics/including-css-javascript/#default-scripts-included-and-registered-by-wordpress).

The basics are:

1. Enqueue the script or style using `wp_enqueue_script()`, `wp_enqueue_style()`, or `wp_enqueue_block_style`.

### [Stylesheets](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#stylesheets)

Your CSS stylesheets are used to customize the presentation of your theme. A stylesheet is also the file where information about your theme is stored. For this reason, the `style.css` file is **required in every theme.**

Rather then loading the stylesheet in your `header.php` file, you should load it in using `wp_enqueue_style`. In order to load your main stylesheet, you can enqueue it in `functions.php`

To enqueue `style.css`:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_enqueue_style( 'style', get_stylesheet_uri() );
```

This will look for a stylesheet named “style” and load it.

The basic function for enqueuing a style is:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_enqueue_style( $handle, $src, $deps, $ver, $media );
```

You can include these parameters:

- **$handle** is simply the name of the stylesheet.
- **$src** is where it is located. The rest of the parameters are optional.
- **$deps** refers to whether or not this stylesheet is dependent on another stylesheet. If this is set, this stylesheet will not be loaded unless its dependent stylesheet is loaded first.
- **$ver** sets the version number.
- **$media** can specify which type of media to load this stylesheet in, such as ‘all’, ‘screen’, ‘print’ or ‘handheld.’

So if you wanted to load a stylesheet named “slider.css” in a folder named “CSS” in you theme’s root directory, you would use:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_enqueue_style( 'slider', get_template_directory_uri() . '/css/slider.css', false, '1.1', 'all');
```

## [Including CSS for block styles](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#including-css-for-block-styles)

In addition to `wp_enqueue_style()`, you can use `wp_enqueue_block_style()` to enqueue styles for blocks. [wp\_enqueue\_block\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_style/) requires WordPress version 5.9 or later.

A key part of creating block themes is performance. With, `wp_enqueue_block_style()`, the theme only loads the CSS for the selected block when the block is used on the page.

The additional style is loaded in the editor and the front, after the block style provided by WordPress and the Gutenberg plugin. You can use this method to add block styles that you can not add via `theme.json`. For example, media queries.

This code example changes the size and text color of the date in the latest comments block. Because this is a `time` HTML element that is nested inside other HTML elements, can not be styled using `theme.json`.

First, create a new CSS file with the name of the block: `latest-comments.css`.

Where you place the file depends on how you organize your theme files. In the example, the file is placed inside the folders `assets/CSS/blocks`.

The CSS class for the time element is `wp-block-latest-comments__comment-date`. The prefix and the block name are followed by the partial, separated by two underscores.

You can read more about the naming convention for the block editor in the [coding guidelines](https://developer.wordpress.org/block-editor/contributors/code/coding-guidelines/#naming).

The text color and font size are added with CSS custom properties that are generated from `theme.json`:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```css
.wp-block-latest-comments__comment-date {
	color: var(--wp--preset--color--primary);
	font-size: var(--wp--preset--font-size--small);
}
```

Next, enqueue the block style inside the themes setup function.

The block name is placed inside an array to load more than one block style.

A `foreach` loop walks through each block in the array and creates a handle, src (source), and path argument.

`wp_enqueue_block_style()` then enqueues the file using the block name and argument:

`wp_enqueue_block_style( "prefix/blockname", $args );`

In the code example, the prefix is “core” since the style is for a core block. When you style blocks from plugins, you need to adjust the prefix.

``
[Expand code](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
function myfirsttheme_setup() {
	/*
	 * Load additional block styles.
	 */
	$styled_blocks = ['latest-comments'];
	foreach ( $styled_blocks as $block_name ) {
		$args = array(
			'handle' => "myfirsttheme-$block_name",
			'src'    => get_theme_file_uri( "assets/css/blocks/$block_name.css" ),
			$args['path'] = get_theme_file_path( "assets/css/blocks/$block_name.css" ),
		);
		wp_enqueue_block_style( "core/$block_name", $args );
	}
}
add_action( 'after_setup_theme', 'myfirsttheme_setup' );

```

### [Scripts](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#scripts)

Any additional JavaScript files required by a theme should be loaded using `wp_enqueue_script`. This ensures proper loading and caching, and allows the use conditional tags to target specific pages. These are **optional**.

`wp_enqueue_script` uses a similar syntax to `wp_enqueue_style`.

Enqueue your script:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_enqueue_script( $handle, $src, $deps, $ver, $args );
```

- **$handle** is the name for the script.
- **$src** defines where the script is located.
- **$deps** is an array that can handle any script that your new script depends on, such as jQuery.
- **$ver** lets you list a version number.
- **$args** an array of arguments that define footer printing (via an `in_footer` key) and script loading strategies (via a `strategy` key) such as `defer` or `async`. This replaces/overloads the `$in_footer` parameter as of WordPress version 6.3.

Your enqueue function may look like this:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_enqueue_script( 'script', get_template_directory_uri() . '/js/script.js', array( 'jquery' ), 1.1, true);
```

### [Delayed Script Loading](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#delayed-script-loading)

WordPress provides support for specifying a script loading strategy via the `wp_register_script()` and `wp_enqueue_script()` functions, by way of the `strategy` key within the new `$args` array parameter introduced in WordPress 6.3.

Supported strategies are as follows:

- **defer**
  - Added by specifying an array key value pair of `'strategy' => 'defer'` to the $args parameter.
  - Scripts marked for deferred execution — via the `defer` script attribute — are only executed once the DOM tree has fully loaded (but before the `DOMContentLoaded` and window load events). Deferred scripts are executed in the same order they were printed/added in the DOM, unlike asynchronous scripts.
- **async**
  - Added by specifying an array key value pair of `'strategy' => 'async'` to the `$args` parameter.
  - Scripts marked for asynchronous execution — via the `async` script attribute — are executed as soon as they are loaded by the browser. Asynchronous scripts do not have a guaranteed execution order, as script B (although added to the DOM after script A) may execute first given that it may complete loading prior to script A. Such scripts may execute either before the DOM has been fully constructed or after the `DOMContentLoaded` event.

Following is an example of specifying a loading strategy during script registration:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
wp_register_script(
    'foo',
    '/path/to/foo.js',
    array(),
    '1.0.0',
    array(
        'strategy'  => 'defer',
    )
);
```

The same approach applies when using `wp_enqueue_script()`.

When specifying a delayed script loading strategy, consideration of the script’s dependency tree (its dependencies and/or dependents) is taken into account when deciding on an “eligible strategy” so as not to result in application of a strategy that is valid for one script but detrimental to others in the tree by causing an unintended out of order of execution. As a result of such logic, the intended loading strategy that you pass via the `$args` parameter may not be the final (chosen) strategy, but it will never be detrimental to (or stricter than) the intended strategy.

### [The Comment Reply Script](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#the-comment-reply-script)

WordPress comments have quite a bit of functionality in them right out of the box, including threaded comments and enhanced comment forms. In order for comments to work properly, they require some JavaScript. However, since there are certain options that need to be defined within this JavaScript, the comment-reply script should be added to every classic theme that uses comments.

**In block themes, the script is included when you place a comment block. You do not need to add it manually.**

The proper way to include comment reply in classic themes is to use conditional tags to check if certain conditions exist, so that the script isn’t being loaded unnecessarily. For instance, you can only load scripts on single post pages using `[is\_singular](https://developer.wordpress.org/reference/functions/is_singular/)`, and check to make sure that “Enable threaded comments” is selected by the user. So you can set up a function like:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
if ( is_singular() && comments_open() && get_option( 'thread_comments' ) ) {
	wp_enqueue_script( 'comment-reply' );
}
```

If comments are enabled by the user, and we are on a post page, then the comment reply script will be loaded. Otherwise, it will not.

### [Combining Enqueue Functions](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#combining-enqueue-functions)

It is best to combine all enqueued scripts and styles into a single function, and then call them using the `wp_enqueue_scripts` action. This function and action should be located somewhere below the initial setup (performed above):

``
[Copy](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/#)

```php
function add_theme_scripts() {
	wp_enqueue_style( 'style', get_stylesheet_uri() );

	wp_enqueue_style( 'slider', get_template_directory_uri() . '/css/slider.css', array(), '1.1', 'all' );

	wp_enqueue_script( 'script', get_template_directory_uri() . '/js/script.js', array( 'jquery' ), 1.1, true );

	if ( is_singular() && comments_open() && get_option( 'thread_comments' ) ) {
		wp_enqueue_script( 'comment-reply' );
	}
}
add_action( 'wp_enqueue_scripts', 'add_theme_scripts' );
```

## [Default Scripts Included and Registered by WordPress](https://developer.wordpress.org/themes/classic-themes/basics/including-css-javascript/\#default-scripts-included-and-registered-by-wordpress)

By default, WordPress includes many popular scripts commonly used by web developers, as well as the scripts used by WordPress itself. Some of them are listed on this reference page:

> [wp\_enqueue\_script()](https://developer.wordpress.org/reference/functions/wp_enqueue_script/)

wp\_enqueue\_script() – Function \| Developer.WordPress.org

[wp\_enqueue\_script( ... )](https://developer.wordpress.org/reference/functions/wp_enqueue_script/)

Enqueues a script.

###### Parameters:

- `$handle` string
- `$src` string
- `$deps` string\[\]
- `$ver` string \| bool \| null
- ... 1 more

[![](https://developer.wordpress.org/wp-includes/images/w-logo-blue.png)WordPress Developer Resources](https://developer.wordpress.org/)

- WordPress Embed
- HTML Embed

Copy and paste this URL into your WordPress site to embed

<blockquote class="wp-embedded-content" data-secret="dYsl0P8Qsn"><a href="https://developer.wordpress.org/reference/functions/wp\_enqueue\_script/">wp\_enqueue\_script</a></blockquote><iframe sandbox="allow-scripts" security="restricted" src="https://developer.wordpress.org/reference/functions/wp\_enqueue\_script/embed/#?secret=dYsl0P8Qsn" width="600" height="400" title="&#8220;wp\_enqueue\_script&#8221; &#8212; WordPress Developer Resources" data-secret="dYsl0P8Qsn" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" class="wp-embedded-content"></iframe><script>
/\*! This file is auto-generated \*/
!function(d,l){"use strict";l.querySelector&&d.addEventListener&&"undefined"!=typeof URL&&(d.wp=d.wp\|\|{},d.wp.receiveEmbedMessage\|\|(d.wp.receiveEmbedMessage=function(e){var t=e.data;if((t\|\|t.secret\|\|t.message\|\|t.value)&&!/\[^a-zA-Z0-9\]/.test(t.secret)){for(var s,r,n,a=l.querySelectorAll('iframe\[data-secret="'+t.secret+'"\]'),o=l.querySelectorAll('blockquote\[data-secret="'+t.secret+'"\]'),c=new RegExp("^https?:$","i"),i=0;i<o.length;i++)o\[i\].style.display="none";for(i=0;i<a.length;i++)s=a\[i\],e.source===s.contentWindow&&(s.removeAttribute("style"),"height"===t.message?(1e3<(r=parseInt(t.value,10))?r=1e3:~~r<200&&(r=200),s.height=r):"link"===t.message&&(r=new URL(s.getAttribute("src")),n=new URL(t.value),c.test(n.protocol))&&n.host===r.host&&l.activeElement===s&&(d.top.location.href=t.value))}},d.addEventListener("message",d.wp.receiveEmbedMessage,!1),l.addEventListener("DOMContentLoaded",function(){for(var e,t,s=l.querySelectorAll("iframe.wp-embedded-content"),r=0;r<s.length;r++)(t=(e=s\[r\]).getAttribute("data-secret"))\|\|(t=Math.random().toString(36).substring(2,12),e.src+="#?secret="+t,e.setAttribute("data-secret",t)),e.contentWindow.postMessage({message:"ready",secret:t},"\*")},!1)))}(window,document);
//# sourceURL=https://developer.wordpress.org/wp-includes/js/wp-embed.min.js
</script>

Copy and paste this code into your site to embed

**The list is far from complete.** You can find a full list of included files in [wp-includes/script-loader.php](https://core.trac.wordpress.org/browser/trunk/src/wp-includes/script-loader.php).

/

Changelog:

- Updated 2023-02-24: Added information about [wp\_enqueue\_block\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_style/) .
- Updated 2024-06-06: Added alert to point readers to new doc.

First published

October 22, 2014

Last updated

June 6, 2024

[PreviousConditional TagsPrevious: Conditional Tags](https://developer.wordpress.org/themes/classic-themes/basics/conditional-tags/)

[NextLinking Theme Files & DirectoriesNext: Linking Theme Files & Directories](https://developer.wordpress.org/themes/classic-themes/basics/linking-theme-files-directories/)

Notifications