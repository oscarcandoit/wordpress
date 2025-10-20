---
url: https://developer.wordpress.org/reference/hooks/mce_buttons_2
scraped_at: 2025-10-20T03:21:32.009Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

mce\_buttons\_2


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[\_WP\_Editors::editor\_settings](https://developer.wordpress.org/reference/classes/_wp_editors/editor_settings/)mce\_buttons\_2

Search

# apply\_filters( ‘mce\_buttons\_2’, array$mce\_buttons\_2, string$editor\_id )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#source)
- [Related](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#wp--skip-link--target)

Filters the second-row list of TinyMCE buttons (Visual tab).

## [Parameters](https://developer.wordpress.org/reference/hooks/mce_buttons_2/\#parameters)

`$mce_buttons_2` array

Second-row list of buttons.

`$editor_id` string

Unique editor identifier, e.g. `'content'`. Accepts `'classic-block'` when called from block editor’s Classic block.

## [Source](https://developer.wordpress.org/reference/hooks/mce_buttons_2/\#source)

`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#)

```php
$mce_buttons_2 = apply_filters( 'mce_buttons_2', $mce_buttons_2, $editor_id );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-editor.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-editor.php#L709) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-editor.php#L709-L709)

## [Related](https://developer.wordpress.org/reference/hooks/mce_buttons_2/\#related)

| Used by | Description |
| --- | --- |
| [wp\_tinymce\_inline\_scripts()](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/) `wp-includes/script-loader.php` | Adds inline scripts required for the TinyMCE in the block editor. |
| [\_WP\_Editors::editor\_settings()](https://developer.wordpress.org/reference/classes/_wp_editors/editor_settings/) `wp-includes/class-wp-editor.php` |  |

## [Changelog](https://developer.wordpress.org/reference/hooks/mce_buttons_2/\#changelog)

| Version | Description |
| --- | --- |
| [3.3.0](https://developer.wordpress.org/reference/since/3.3.0/) | The `$editor_id` parameter was added. |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/mce_buttons_2/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#comment-content-4795)



Example Migrated from Codex:



The example below will reveal the hidden “Styles” dropdown in the _advanced_ toolbar.





`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#)




```php
add_filter( 'mce_buttons_2', 'myplugin_tinymce_buttons' );

function myplugin_tinymce_buttons( $buttons ) {
         //Add style selector to the beginning of the toolbar
         array_unshift( $buttons, 'styleselect' );

         return $buttons;
    }
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fmce_buttons_2%2F%3Freplytocom%3D4795%23feedback-editor-4795)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#comment-content-4796)



Example Migrated from Codex:



The example below will remove the text color selector from the _advanced_ toolbar.





`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#)




```php
add_filter( 'mce_buttons_2', 'myplugin_tinymce_buttons' );

function myplugin_tinymce_buttons( $buttons ) {
         //Remove the text color selector
         $remove = 'forecolor';

         //Find the array key and then unset
         if ( ( $key = array_search( $remove, $buttons ) ) !== false )
   		unset( $buttons[$key] );

         return $buttons;
    }
```





Or, if you want to remove more buttons at the same time:





`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/mce_buttons_2/#)




```php
add_filter( 'mce_buttons_2', 'myplugin_tinymce_buttons' );

function myplugin_tinymce_buttons( $buttons ) {
   	//Remove the format dropdown select and text color selector
   	$remove = array( 'formatselect', 'forecolor' );

   	return array_diff( $buttons, $remove );
    }
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fmce_buttons_2%2F%3Freplytocom%3D4796%23feedback-editor-4796)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fmce_buttons_2%2F) before being able to contribute a note or feedback.

Notifications