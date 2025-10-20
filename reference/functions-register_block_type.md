---
url: https://developer.wordpress.org/reference/functions/register_block_type
scraped_at: 2025-10-20T03:42:28.776Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/register_block_type/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

register\_block\_type()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)register\_block\_type()

Search

# register\_block\_type( string\|WP\_Block\_Type$block\_type, array$args = array() ): [WP\_Block\_Type](https://developer.wordpress.org/reference/classes/wp_block_type/) \|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/register_block_type/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/register_block_type/#return)
- [Source](https://developer.wordpress.org/reference/functions/register_block_type/#source)
- [Related](https://developer.wordpress.org/reference/functions/register_block_type/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/register_block_type/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/register_block_type/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/register_block_type/#wp--skip-link--target)

Registers a block type. The recommended way is to register a block type using the metadata stored in the `block.json` file.

## [Parameters](https://developer.wordpress.org/reference/functions/register_block_type/\#parameters)

`$block_type` string\|[WP\_Block\_Type](https://developer.wordpress.org/reference/classes/wp_block_type/)required

Block type name including namespace, or alternatively a path to the JSON file with metadata definition for the block, or a path to the folder where the `block.json` file is located, or a complete [WP\_Block\_Type](https://developer.wordpress.org/reference/classes/wp_block_type/) instance.

In case a [WP\_Block\_Type](https://developer.wordpress.org/reference/classes/wp_block_type/) is provided, the $args parameter will be ignored.

`$args` arrayoptional

Array of block type arguments. Accepts any public property of `WP_Block_Type`. See [WP\_Block\_Type::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_block_type/__construct/) for information on accepted arguments.

Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/register_block_type/\#return)

[WP\_Block\_Type](https://developer.wordpress.org/reference/classes/wp_block_type/) \|false The registered block type on success, or false on failure.

## [Source](https://developer.wordpress.org/reference/functions/register_block_type/\#source)

`wp-includes/blocks.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)

```php
function register_block_type( $block_type, $args = array() ) {
	if ( is_string( $block_type ) && file_exists( $block_type ) ) {
		return register_block_type_from_metadata( $block_type, $args );
	}

	return WP_Block_Type_Registry::get_instance()->register( $block_type, $args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/blocks.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/blocks.php#L762) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/blocks.php#L762-L768)

## [Related](https://developer.wordpress.org/reference/functions/register_block_type/\#related)

| Uses | Description |
| --- | --- |
| [register\_block\_type\_from\_metadata()](https://developer.wordpress.org/reference/functions/register_block_type_from_metadata/) `wp-includes/blocks.php` | Registers a block type from the metadata stored in the `block.json` file. |
| [WP\_Block\_Type\_Registry::get\_instance()](https://developer.wordpress.org/reference/classes/wp_block_type_registry/get_instance/) `wp-includes/class-wp-block-type-registry.php` | Utility method to retrieve the main instance of the class. |

## [Changelog](https://developer.wordpress.org/reference/functions/register_block_type/\#changelog)

| Version | Description |
| --- | --- |
| [5.8.0](https://developer.wordpress.org/reference/since/5.8.0/) | First parameter now accepts a path to the `block.json` file. |
| [5.0.0](https://developer.wordpress.org/reference/since/5.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/register_block_type/\#user-contributed-notes)

1. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-5954)



**How to write a plugin with multiple blocks:**



**Setting up the `src` folder**



1. Take the content of the `src` directory created by [@wordpress/create-block](https://developer.wordpress.org/block-editor/getting-started/create-block/#quick-start) and place it in a sub-directory, for example `block-a`.
2. Duplicate the sub-directory to make a second block and name it, for example `block-b`.

Update the `block.json` files in each sub-directory to match the blocks’ requirements.

**Registering the Blocks**

After running `npm run build` corresponding directories will be created in the `build` directory.

The two blocks can be registered by pointing to the matching directory in the build folder.

`wp-includes/blocks.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)

```php
function wpdocs_create_blocks_mysite_block_init() {

	register_block_type( __DIR__ . '/build/block-a' );
	register_block_type( __DIR__ . '/build/block-b' );

}
add_action( 'init', 'wpdocs_create_blocks_mysite_block_init' );
```

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D5954%23feedback-editor-5954)

2. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-3038)



You can pass custom `$attributes` which can be used both on editor and front-end in `render_callback` :





`wp-includes/blocks.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_block_type/#)

[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
register_block_type( 'my_namespace/my_block', [\
   	'render_callback' => 'render_callback',\
   	'attributes'      => [\
   		'some_string' => [\
   			'default' => 'default string',\
   			'type'    => 'string'\
   		],\
   		'some_array'  => [\
   			'type'  => 'array',\
   			'items' => [\
   				'type' => 'string',\
   			],\
   		]\
   	]\
] );
```





**Important (tested in 5.0.3)** : in case of array attributes you MUST specify items type. Otherwise it would trigger a notice.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D3038%23feedback-editor-3038)

3. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-5593)



The name of the JSON file, if provided in the `$block_type` argument, must be “block.json”. If the file does not end with such file name, WordPress will assume it is a path to that file. It seems to be up to the developer choose the file name, but it’s not.





[Show feedback (1)](https://developer.wordpress.org/reference/functions/register_block_type/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D5593%23feedback-editor-5593)



- I hit this problem earlier. I made a block called accordion.json. I had to rename it to accordion-block.json for it to be registered.



[Rocky Kev](https://profiles.wordpress.org/rockykev/) [2 years ago](https://developer.wordpress.org/reference/functions/register_block_type/#comment-6548)


4. [Skip to note 13 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-5721)



You can load `block.json` directly:





`wp-includes/blocks.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
register_block_type( dirname(__FILE__) . '/block.json' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D5721%23feedback-editor-5721)

5. [Skip to note 14 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-3078)



Here is an example snippet that I use for one of my own projects





`wp-includes/blocks.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_block_type/#)

[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
function mcqa_register_block_related_quiz() {
       if ( ! function_exists( 'register_block_type' ) ) {
           // Block editor is not available.
           return;
       }

       register_block_type( 'mcqac/related-quiz', array(
           'editor_script' => 'mcqac-related-quiz-block-script',
           'editor_style'  => 'mcqac-related-quiz-block-editor-style',
           'style'         => 'mcqac-related-quiz-block-frontend-style',
       ) );
}

// Hook: Editor assets.
add_action( 'init', 'mcqa_register_block_related_quiz' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D3078%23feedback-editor-3078)

6. [Skip to note 15 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-5791)



If you wish to set a **dashicon** in the args, you must omit the `dashicons-` prefix:





`wp-includes/blocks.php`
[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
register_block_type(
   	__DIR__ . '/build',
   	array(
   		'icon' => 'admin-home', /* omit 'dashicons-' prefix */
   	)
);
```





This is in contradiction to `add_menu_page()` which requires the inclusion of the prefix. These should be brought into alignment for consistency in my opinion.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D5791%23feedback-editor-5791)

7. [Skip to note 16 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-6248)



To follow on from Michael Levy’s post about registering multiple blocks from the same plugin, I wrote this to automatically register any blocks generated by the `npm run build` command.





`wp-includes/blocks.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_block_type/#)

[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
function wpdocs_register_multiple_blocks() {
   	$build_dir = __DIR__ . '/build';

   	foreach ( scandir( $build_dir ) as $result ) {
   		$block_location = $build_dir . '/' . $result;

   		if ( ! is_dir( $block_location ) || '.' === $result || '..' === $result ) {
   			continue;
   		}

   		register_block_type( $block_location );
   	}
}

add_action( 'init', 'wpdocs_register_multiple_blocks' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D6248%23feedback-editor-6248)

8. [Skip to note 17 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-5589)



If you don’t know why it’s recommended to register a block type using metadata, read this reference [https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D5589%23feedback-editor-5589)

9. [Skip to note 18 content](https://developer.wordpress.org/reference/functions/register_block_type/#comment-content-3714)



The arguments to `register_block_type()` function match the instance vars of `WP_Block_Type` class, i.e., `attributes, render_callback, editor_script, editor_style, script` and `style`.





`wp-includes/blocks.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_block_type/#)

[Copy](https://developer.wordpress.org/reference/functions/register_block_type/#)




```php
           register_block_type(
               'my-custom-blocks/calendar',
               array(
                   'attributes' => array(
                       'align' => array(
                           'type' => 'string',
                           'enum' => array( 'left', 'center', 'right', 'wide', 'full' ),
                       ),
                       'day' => array(
                           'type' => 'integer',
                       ),
                       'month' => array(
                           'type' => 'integer',
                       ),
                       'year' => array(
                           'type' => 'integer',
                       ),
                   ),
                   'render_callback' => 'render_block_my_custom_blocks_calendar',
                   'editor_script'   => 'calendar-editor-js',
                   'editor_style'    => 'calendar-editor-css',
                   'script'          => 'calendar-frontend-js',
                   'style'           => 'calendar-frontend-css',

               )
           );
```





This is because the `register_block_type()` function utilizes the name and arguments provided in the function call to create a new instance of `WP_Block_Type` class and the instance thus created is registered with the global `WP_Block_Type_Registry` instance.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F%3Freplytocom%3D3714%23feedback-editor-3714)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_block_type%2F) before being able to contribute a note or feedback.

Notifications