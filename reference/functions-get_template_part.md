---
url: https://developer.wordpress.org/reference/functions/get_template_part
scraped_at: 2025-10-20T03:43:42.089Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_template_part/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_template\_part()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_template\_part()

Search

# get\_template\_part( string$slug, string\|null$name = null, array$args = array() ): void\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_template_part/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_template_part/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_template_part/#return)
- [More Information](https://developer.wordpress.org/reference/functions/get_template_part/#more-information)
  - [Usage](https://developer.wordpress.org/reference/functions/get_template_part/#usage)
- [Source](https://developer.wordpress.org/reference/functions/get_template_part/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_template_part/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_template_part/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_template_part/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_template_part/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_template_part/#wp--skip-link--target)

Loads a template part into a template.

## [Description](https://developer.wordpress.org/reference/functions/get_template_part/\#description)

Provides a simple mechanism for child themes to overload reusable sections of code in the theme.

Includes the named template part for a theme or if a name is specified then a specialized part will be included. If the theme contains no {slug}.php file then no template will be included.

The template is included using require, not require\_once, so you may include the same template part multiple times.

For the $name parameter, if the file is called "{slug}-special.php" then specify "special".

## [Parameters](https://developer.wordpress.org/reference/functions/get_template_part/\#parameters)

`$slug` stringrequired

The slug name for the generic template.

`$name` string\|nulloptional

The name of the specialized template.

Default: `null`

`$args` arrayoptional

Additional arguments passed to the template.

Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/get_template_part/\#return)

void\|false Void on success, false if the template does not exist.

## [More Information](https://developer.wordpress.org/reference/functions/get_template_part/\#more-information)

### [Usage](https://developer.wordpress.org/reference/functions/get_template_part/\#usage)

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
get_template_part( $slug );
```

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
get_template_part( $slug, $name );
```

Note: `get_template_part()` fails silently

## [Source](https://developer.wordpress.org/reference/functions/get_template_part/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_template_part/#)

[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
function get_template_part( $slug, $name = null, $args = array() ) {
	/**
	 * Fires before the specified template part file is loaded.
	 *
	 * The dynamic portion of the hook name, `$slug`, refers to the slug name
	 * for the generic template part.
	 *
	 * @since 3.0.0
	 * @since 5.5.0 The `$args` parameter was added.
	 *
	 * @param string      $slug The slug name for the generic template.
	 * @param string|null $name The name of the specialized template
	 *                          or null if there is none.
	 * @param array       $args Additional arguments passed to the template.
	 */
	do_action( "get_template_part_{$slug}", $slug, $name, $args );

	$templates = array();
	$name      = (string) $name;
	if ( '' !== $name ) {
		$templates[] = "{$slug}-{$name}.php";
	}

	$templates[] = "{$slug}.php";

	/**
	 * Fires before an attempt is made to locate and load a template part.
	 *
	 * @since 5.2.0
	 * @since 5.5.0 The `$args` parameter was added.
	 *
	 * @param string   $slug      The slug name for the generic template.
	 * @param string   $name      The name of the specialized template
	 *                            or an empty string if there is none.
	 * @param string[] $templates Array of template files to search for, in order.
	 * @param array    $args      Additional arguments passed to the template.
	 */
	do_action( 'get_template_part', $slug, $name, $templates, $args );

	if ( ! locate_template( $templates, true, false, $args ) ) {
		return false;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L167) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L167-L209)

## [Hooks](https://developer.wordpress.org/reference/functions/get_template_part/\#hooks)

[do\_action( ‘get\_template\_part’, string$slug, string$name, string\[\]$templates, array$args )](https://developer.wordpress.org/reference/hooks/get_template_part/)

Fires before an attempt is made to locate and load a template part.

[do\_action( “get\_template\_part\_{$slug}”, string$slug, string\|null$name, array$args )](https://developer.wordpress.org/reference/hooks/get_template_part_slug/)

Fires before the specified template part file is loaded.

## [Related](https://developer.wordpress.org/reference/functions/get_template_part/\#related)

| Uses | Description |
| --- | --- |
| [locate\_template()](https://developer.wordpress.org/reference/functions/locate_template/) `wp-includes/template.php` | Retrieves the name of the highest priority template file that exists. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_template_part/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | The `$args` parameter was added. |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_template_part/\#user-contributed-notes)

01. [Skip to note 17 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4130)



    **Passing variables after WordPress 5.5 update**


    ======================================



    **When calling function**





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    get_template_part(
    	'template-part',
    	'name',
    	array(
    		'key'	=> 'value',
    		'key2'	=> 'value2'
    	)
    );
    ```





    **In your template part**





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    var_dump( $args );	// Everything
    echo $args['key'];	// Specific values
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4130%23feedback-editor-4130)

02. [Skip to note 18 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-358)



    **Using with theme subfolders**



    To use this function with subfolders in your theme directory, simply prepend the folder name before the slug. For example, if you have a folder called “partials” in your theme directory and a template part called “content-page.php” in that sub-folder, you would use `get_template_part()` like this:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php get_template_part( 'partials/content', 'page' ); ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D358%23feedback-editor-358)

03. [Skip to note 19 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-2349)



    _the old codex had this entry about “Passing Variables to Template”_



    Because the template is being required, it will not have access to any variables you define within the calling theme’s PHP code, unless you explicitly declare them as global.



    However, [load\_template()](https://developer.wordpress.org/reference/functions/load_template/) , which is called indirectly by [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) extracts all of the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) query variables, into the scope of the loaded template. So you can use [set\_query\_var()](https://developer.wordpress.org/reference/functions/set_query_var/) to make your variable available to the template part.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    // You wish to make $my_var available to the template part at `content-part.php`
    set_query_var( 'my_var', $my_var );
    get_template_part( 'content', 'part' );
    ```







    [Show feedback (2)](https://developer.wordpress.org/reference/functions/get_template_part/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D2349%23feedback-editor-2349)



- Minor suggestion, it should rather be ‘Because _of where in the code execution_ the template is being required’. The fact that is is being required vs being included is not the reason one has to use the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) query variables.



[Jonathan Bossenger](https://profiles.wordpress.org/psykro/) [6 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-3303)

- // Since WP version 5.5, we can set the args directly like the following // Note: array method requires PHP 7.\* $args = \[ ‘my\_var\_1’ => $my\_var\_1, ‘my\_var\_2’ => $my\_var\_2, \]; get\_template\_part( ‘content’, ‘part’, $args );



[Santukon](https://profiles.wordpress.org/santukon/) [5 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-4151)


04. [Skip to note 20 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-357)



    **Using loop.php in child themes**


    Assuming the theme folder is `wp-content/themes`, that the parent theme is twentyten, and the child theme is twentytenchild, then the following code —





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php get_template_part( 'loop', 'index' ); ?>
    ```





    will do a PHP `require()` for the first file that exists among these, in this priority:



    wp-content/themes/twentytenchild/loop-index.php


    wp-content/themes/twentyten/loop-index.php


    wp-content/themes/twentytenchild/loop.php


    wp-content/themes/twentyten/loop.php





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D357%23feedback-editor-357)

05. [Skip to note 21 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-359)



    **Navigation**


    Adding a navigation bar to theme using a generic `nav.php` template file:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php get_template_part( 'nav' );           // Navigation bar (nav.php) ?>
    <?php get_template_part( 'nav', '2' );      // Navigation bar #2 (nav-2.php) ?>
    <?php get_template_part( 'nav', 'single' ); // Navigation bar to use in single pages (nav-single.php) ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D359%23feedback-editor-359)

06. [Skip to note 22 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4159)



    A simple example of how to use the `$args` parameter in WordPress 5.5 in your template parts.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php

    $args = array( 'section_title' => 'hello world' );

    get_template_part( 'template-parts/file', 'name', $args ); // template-parts/file-name.php
    ```





    In your template part.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <h2><?php echo __( $args['section_title'] ); ?></h2>
    ```





    Output:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <h2>hello world</h2>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4159%23feedback-editor-4159)

07. [Skip to note 23 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4906)



    Sometime since January 2019, the function has changed to return false if no template file is found. This isn’t noted in the code comments or changelog. The note that the function fails silently is no longer correct.



    This now makes it easy for plugins to provide a template fallback (or allow a template override, depending on your perspective) like this:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    if ( false === get_template_part( $slug, $name, $args ) ) {
    	// default output
    }
    ```







    [Show feedback (1)](https://developer.wordpress.org/reference/functions/get_template_part/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4906%23feedback-editor-4906)



- Return value was added in June 2020 in [changeset 48209](https://core.trac.wordpress.org/changeset/48209) to fix [ticket 40969](https://core.trac.wordpress.org/ticket/40969).



[crstauf](https://profiles.wordpress.org/crstauf/) [5 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-4913)


08. [Skip to note 24 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-1963)



    **Get a specific file**



    Although this kind of defeats the purpose of this function, it’s also possible to load a specific template file with it. All you have to do is use just one argument:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php get_template_part('template-parts/layout'); ?>
    ```





    will include `layout.php` from _template-parts_ subdirectory placed in the root of your theme folder.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D1963%23feedback-editor-1963)

09. [Skip to note 25 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4133)



    Since WP 5.5 the $args parameter is used to pass variables through the template.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php

    $args = ['some data', 'to use'];
    get_template_part( 'content', '', $args ); ?>

    /* content.php */
    <?php print_r($args); ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4133%23feedback-editor-4133)

10. [Skip to note 26 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4240)



    You can also access the template variables in your template part file by doing this:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    extract( $args );

    echo $variable1;
    echo $variable2;
    ```





    Your `get_template_part` will look something like this:





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    $args = array(
    	'variable1' => '$variable1 Value',
    	'variable2' => '$variable2 Value',
    );

    get_template_part( 'template-parts/template-part-file', null, $args );
    ```





    – Keep in mind that the third argument `$args` has been added since version 5.5





    [Show feedback (1)](https://developer.wordpress.org/reference/functions/get_template_part/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4240%23feedback-editor-4240)



- WordPress PHP coding standards do not permit the use of `extract()`.



[crstauf](https://profiles.wordpress.org/crstauf/) [5 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-4247)


11. [Skip to note 27 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-6174)



    Please note that this function only works for _Classic_ WordPress themes. To print a template part in a Block theme, use [block\_template\_part()](https://developer.wordpress.org/reference/functions/block_template_part/) instead.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D6174%23feedback-editor-6174)

12. [Skip to note 28 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-5092)



    Use a boolean in the $args





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php get_template_part(
        'template-parts/blocks/inc/content',
        'section-header',
        array( 'hasBtn' => true )
    ); ?>
    ```







    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php if ( ! empty( $args['hasBtn'] ) ) { ?>
            //show the btn on the template part
    <?php } ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D5092%23feedback-editor-5092)

13. [Skip to note 29 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-5437)



    **get\_template\_part(foldername/filename without .php extension)**





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    <?php
    if(is_user_logged_in()){
    	get_template_part('template-parts/loginuser');
    }
    else{
    	get_template_part('template-parts/nonloginuser');
    }
    ?>
    ```





    Create a folder in the theme main directory



    Folder name “template-parts” then add two .php files in “template-parts” folder loginuser.php and nonloginuser.php



    If user login show loginuser.php file content



    If the user do not login show nonloginuser.php file content



    **Note: Use any folder & files name above I have use random folder name and files name.**





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D5437%23feedback-editor-5437)

14. [Skip to note 30 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4005)



    If your web server is using **ModSecurity**, it will likely block attempts to inline SVGs using a PHP method like `file_get_contents()`. You can use `get_template_part()` to inline SVGs.



1. Create a duplicate of your SVG, where `icon.svg` becomes `inline-icon.svg.php`
2. Inline them in your template using `get_template_part( 'images/inline', 'icon.svg' );`

At the time of writing, this works to get around the default OWASP rule set for ModSecurity. Not tested with other rule sets.

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4005%23feedback-editor-4005)

15. [Skip to note 31 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-3229)



    **Passing variables to [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/)**



    It’s not possible to pass variables to a template loaded via [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) . I came up with a workaround that doesn’t rely on global variables for it to work.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    /* functions.php */
    function get_custom_template($file = '', $arguments = []) {
      extract($arguments);
      include( locate_template( $file .'.php', false, false ) );
    }
    ```







    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    /* loop.php */
    while( have_posts() ):
      the_post();
      get_custom_template( 'content', [\
    	'is_featured' => true\
      ]);
    endwhile;
    ```





    Now, when we try to use $is\_featured, it will be available to **content.php** only.





    `wp-includes/general-template.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)




    ```php
    /* content.php */
    the_title();
    the_content();
    var_dump($is_featured); // true
    ```







    [Show feedback (2)](https://developer.wordpress.org/reference/functions/get_template_part/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D3229%23feedback-editor-3229)



- Since WP 5.5 this is no longer needed. Use the $args parameter.



[jabbadu](https://profiles.wordpress.org/jabbadu/) [5 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-4132)

- WordPress PHP coding standards do not permit the use of **extract()**



[Yakovos Frountas](https://profiles.wordpress.org/ifrountas/) [5 years ago](https://developer.wordpress.org/reference/functions/get_template_part/#comment-4762)


16. [Skip to note 32 content](https://developer.wordpress.org/reference/functions/get_template_part/#comment-content-4332)



    **How to passing variables to [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) correctly: WordPress + 5.5**



1- Setup variable

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
$data = array(
	'location' 	=> 'slider',
	'number'	=>	3
);
```

2- Passing variable to get\_template\_part

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
get_template_part( 'templates/slider', 'full', $data ); //templates/slider-full.php
```

3- get data in part of template

`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_template_part/#)

```php
global $data; //dont forget use globally
print_r($data); // output: array('location' => 'slider', 'number' => 3)
```

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F%3Freplytocom%3D4332%23feedback-editor-4332)

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_template_part%2F) before being able to contribute a note or feedback.

Notifications