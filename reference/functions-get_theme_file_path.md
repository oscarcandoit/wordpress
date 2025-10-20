---
url: https://developer.wordpress.org/reference/functions/get_theme_file_path
scraped_at: 2025-10-20T03:14:07.130Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_theme_file_path/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_theme\_file\_path()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_theme\_file\_path()

Search

# get\_theme\_file\_path( string$file = '' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_theme_file_path/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_theme_file_path/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_theme_file_path/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_theme_file_path/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_theme_file_path/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_theme_file_path/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_theme_file_path/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_theme_file_path/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_theme_file_path/#wp--skip-link--target)

Retrieves the path of a file in the theme.

## [Description](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#description)

Searches in the stylesheet directory before the template directory so themes which inherit from a parent theme can just override one file.

## [Parameters](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#parameters)

`$file` stringoptional

File to search for in the stylesheet directory.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#return)

string The path of the file.

## [Source](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_theme_file_path/#)

[Copy](https://developer.wordpress.org/reference/functions/get_theme_file_path/#)

```php
function get_theme_file_path( $file = '' ) {
	$file = ltrim( $file, '/' );

	$stylesheet_directory = get_stylesheet_directory();
	$template_directory   = get_template_directory();

	if ( empty( $file ) ) {
		$path = $stylesheet_directory;
	} elseif ( $stylesheet_directory !== $template_directory && file_exists( $stylesheet_directory . '/' . $file ) ) {
		$path = $stylesheet_directory . '/' . $file;
	} else {
		$path = $template_directory . '/' . $file;
	}

	/**
	 * Filters the path to a file in the theme.
	 *
	 * @since 4.7.0
	 *
	 * @param string $path The file path.
	 * @param string $file The requested file to search for.
	 */
	return apply_filters( 'theme_file_path', $path, $file );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L4659) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L4659-L4682)

## [Hooks](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#hooks)

[apply\_filters( ‘theme\_file\_path’, string$path, string$file )](https://developer.wordpress.org/reference/hooks/theme_file_path/)

Filters the path to a file in the theme.

## [Related](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#related)

| Uses | Description |
| --- | --- |
| [get\_stylesheet\_directory()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory/) `wp-includes/theme.php` | Retrieves stylesheet directory path for the active theme. |
| [get\_template\_directory()](https://developer.wordpress.org/reference/functions/get_template_directory/) `wp-includes/theme.php` | Retrieves template directory path for the active theme. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_theme_file_path/#) [Show less](https://developer.wordpress.org/reference/functions/get_theme_file_path/#)

| Used by | Description |
| --- | --- |
| [get\_block\_editor\_theme\_styles()](https://developer.wordpress.org/reference/functions/get_block_editor_theme_styles/) `wp-includes/block-editor.php` | Creates an array of theme styles to load into the block editor. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#changelog)

| Version | Description |
| --- | --- |
| [4.7.0](https://developer.wordpress.org/reference/since/4.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_theme_file_path/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/get_theme_file_path/#comment-content-2955)



We can use this function to allow child theme to overwrite the functional file of the parent theme.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_theme_file_path/#)




```php
get_theme_file_path( '/inc/template-functions.php' );
```





Thanks





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_theme_file_path%2F%3Freplytocom%3D2955%23feedback-editor-2955)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_theme_file_path%2F) before being able to contribute a note or feedback.

Notifications