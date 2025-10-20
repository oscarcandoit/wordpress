---
url: https://developer.wordpress.org/reference/functions/locate_template
scraped_at: 2025-10-20T03:43:53.368Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/locate_template/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

locate\_template()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)locate\_template()

Search

# locate\_template( string\|array$template\_names, bool$load = false, bool$load\_once = true, array$args = array() ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/locate_template/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/locate_template/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/locate_template/#return)
- [Source](https://developer.wordpress.org/reference/functions/locate_template/#source)
- [Related](https://developer.wordpress.org/reference/functions/locate_template/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/locate_template/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/locate_template/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/locate_template/#wp--skip-link--target)

Retrieves the name of the highest priority template file that exists.

## [Description](https://developer.wordpress.org/reference/functions/locate_template/\#description)

Searches in the stylesheet directory before the template directory and wp-includes/theme-compat so that themes which inherit from a parent theme can just overload one file.

## [Parameters](https://developer.wordpress.org/reference/functions/locate_template/\#parameters)

`$template_names` string\|arrayrequired

Template file(s) to search for, in order.

`$load` booloptional

If true the template file will be loaded if it is found.

Default: `false`

`$load_once` booloptional

Whether to require\_once or require. Has no effect if `$load` is false.

Default: `true`

`$args` arrayoptional

Additional arguments passed to the template.

Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/locate_template/\#return)

string The template filename if one is located.

## [Source](https://developer.wordpress.org/reference/functions/locate_template/\#source)

`wp-includes/template.php`
[Expand code](https://developer.wordpress.org/reference/functions/locate_template/#)

[Copy](https://developer.wordpress.org/reference/functions/locate_template/#)

```php
function locate_template( $template_names, $load = false, $load_once = true, $args = array() ) {
	global $wp_stylesheet_path, $wp_template_path;

	if ( ! isset( $wp_stylesheet_path ) || ! isset( $wp_template_path ) ) {
		wp_set_template_globals();
	}

	$is_child_theme = is_child_theme();

	$located = '';
	foreach ( (array) $template_names as $template_name ) {
		if ( ! $template_name ) {
			continue;
		}
		if ( file_exists( $wp_stylesheet_path . '/' . $template_name ) ) {
			$located = $wp_stylesheet_path . '/' . $template_name;
			break;
		} elseif ( $is_child_theme && file_exists( $wp_template_path . '/' . $template_name ) ) {
			$located = $wp_template_path . '/' . $template_name;
			break;
		} elseif ( file_exists( ABSPATH . WPINC . '/theme-compat/' . $template_name ) ) {
			$located = ABSPATH . WPINC . '/theme-compat/' . $template_name;
			break;
		}
	}

	if ( $load && '' !== $located ) {
		load_template( $located, $load_once, $args );
	}

	return $located;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/template.php#L718) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/template.php#L718-L749)

## [Related](https://developer.wordpress.org/reference/functions/locate_template/\#related)

| Uses | Description |
| --- | --- |
| [wp\_set\_template\_globals()](https://developer.wordpress.org/reference/functions/wp_set_template_globals/) `wp-includes/template.php` | Set up the globals used for template loading. |
| [is\_child\_theme()](https://developer.wordpress.org/reference/functions/is_child_theme/) `wp-includes/theme.php` | Whether a child theme is in use. |
| [load\_template()](https://developer.wordpress.org/reference/functions/load_template/) `wp-includes/template.php` | Requires the template file with WordPress environment. |

| Used by | Description |
| --- | --- |
| [get\_header()](https://developer.wordpress.org/reference/functions/get_header/) `wp-includes/general-template.php` | Loads header template. |
| [get\_footer()](https://developer.wordpress.org/reference/functions/get_footer/) `wp-includes/general-template.php` | Loads footer template. |
| [get\_sidebar()](https://developer.wordpress.org/reference/functions/get_sidebar/) `wp-includes/general-template.php` | Loads sidebar template. |
| [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) `wp-includes/general-template.php` | Loads a template part into a template. |
| [get\_search\_form()](https://developer.wordpress.org/reference/functions/get_search_form/) `wp-includes/general-template.php` | Displays search form. |
| [get\_query\_template()](https://developer.wordpress.org/reference/functions/get_query_template/) `wp-includes/template.php` | Retrieves path to a template. |

[Show 1 more](https://developer.wordpress.org/reference/functions/locate_template/#) [Show less](https://developer.wordpress.org/reference/functions/locate_template/#)

## [Changelog](https://developer.wordpress.org/reference/functions/locate_template/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | The `$args` parameter was added. |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/locate_template/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/locate_template/#comment-content-2405)



Note that `locate_template()` does not prevent directory traversal attacks, so if you’re passing a user-provided template name to the function, be sure to verify that it’s from one of the three appropriate locations (active theme directory, parent theme directory, or /wp-includes/theme-compat/ directory).



Example:





`wp-includes/template.php`
[Expand code](https://developer.wordpress.org/reference/functions/locate_template/#)

[Copy](https://developer.wordpress.org/reference/functions/locate_template/#)




```php
$template = locate_template( $template_filename_from_unsanitized_user_input );

// Only allow templates that are in the active theme directory, parent theme
// directory, or the /wp-includes/theme-compat/ directory (prevent directory
// traversal attacks).
$template_in_theme_or_parent_theme_or_compat = (
   	// Template is in current theme folder.
   	0 === strpos( realpath( $template ), realpath( STYLESHEETPATH ) ) ||
   	// Template is in current or parent theme folder.
   	0 === strpos( realpath( $template ), realpath( TEMPLATEPATH ) ) ||
   	// Template is in theme-compat folder.
   	0 === strpos( realpath( $template ), realpath( ABSPATH . WPINC . '/theme-compat/' ) )
);

if ( $template_in_theme_or_parent_theme_or_compat ) {
   	require_once( $template );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flocate_template%2F%3Freplytocom%3D2405%23feedback-editor-2405)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/locate_template/#comment-content-605)



**Example**


Load a specific template part based on the current pagename.





`wp-includes/template.php`
[Copy](https://developer.wordpress.org/reference/functions/locate_template/#)




```php
if (locate_template('content-' . $pageName . '.php') != '') {
   	// yep, load the page template
   	get_template_part('content', $pageName);
} else {
   	// nope, load the content
   	the_content();
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flocate_template%2F%3Freplytocom%3D605%23feedback-editor-605)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flocate_template%2F) before being able to contribute a note or feedback.

Notifications