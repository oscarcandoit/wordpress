---
url: https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes
scraped_at: 2025-10-20T03:13:41.124Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

sanitize\_title\_with\_dashes()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)sanitize\_title\_with\_dashes()

Search

# sanitize\_title\_with\_dashes( string$title, string$raw\_title = '', string$context = 'display' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#return)
- [More Information](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#source)
- [Related](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#wp--skip-link--target)

Sanitizes a title, replacing whitespace and a few other characters with dashes.

## [Description](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#description)

Limits the output to alphanumeric characters, underscore (\_) and dash (-).

Whitespace becomes a dash.

## [Parameters](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#parameters)

`$title` stringrequired

The title to be sanitized.

`$raw_title` stringoptional

Not used.

Default: `''`

`$context` stringoptional

The operation for which the string is sanitized.

When set to `'save'`, additional entities are converted to hyphens or stripped entirely. Default `'display'`.

Default: `'display'`

## [Return](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#return)

string The sanitized title.

## [More Information](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#more-information)

- This function does not replace special accented characters.
- This function does not apply the [sanitize\_title](https://developer.wordpress.org/reference/hooks/sanitize_title/) filter to the title.

## [Source](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#source)

`wp-includes/formatting.php`
[Expand code](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#)

[Copy](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#)

```php
function sanitize_title_with_dashes( $title, $raw_title = '', $context = 'display' ) {
	$title = strip_tags( $title );
	// Preserve escaped octets.
	$title = preg_replace( '|%([a-fA-F0-9][a-fA-F0-9])|', '---$1---', $title );
	// Remove percent signs that are not part of an octet.
	$title = str_replace( '%', '', $title );
	// Restore octets.
	$title = preg_replace( '|---([a-fA-F0-9][a-fA-F0-9])---|', '%$1', $title );

	if ( seems_utf8( $title ) ) {
		if ( function_exists( 'mb_strtolower' ) ) {
			$title = mb_strtolower( $title, 'UTF-8' );
		}
		$title = utf8_uri_encode( $title, 200 );
	}

	$title = strtolower( $title );

	if ( 'save' === $context ) {
		// Convert &nbsp, &ndash, and &mdash to hyphens.
		$title = str_replace( array( '%c2%a0', '%e2%80%93', '%e2%80%94' ), '-', $title );
		// Convert &nbsp, &ndash, and &mdash HTML entities to hyphens.
		$title = str_replace( array( '&nbsp;', '&#160;', '&ndash;', '&#8211;', '&mdash;', '&#8212;' ), '-', $title );
		// Convert forward slash to hyphen.
		$title = str_replace( '/', '-', $title );

		// Strip these characters entirely.
		$title = str_replace(
			array(
				// Soft hyphens.
				'%c2%ad',
				// &iexcl and &iquest.
				'%c2%a1',
				'%c2%bf',
				// Angle quotes.
				'%c2%ab',
				'%c2%bb',
				'%e2%80%b9',
				'%e2%80%ba',
				// Curly quotes.
				'%e2%80%98',
				'%e2%80%99',
				'%e2%80%9c',
				'%e2%80%9d',
				'%e2%80%9a',
				'%e2%80%9b',
				'%e2%80%9e',
				'%e2%80%9f',
				// Bullet.
				'%e2%80%a2',
				// &copy, &reg, &deg, &hellip, and &trade.
				'%c2%a9',
				'%c2%ae',
				'%c2%b0',
				'%e2%80%a6',
				'%e2%84%a2',
				// Acute accents.
				'%c2%b4',
				'%cb%8a',
				'%cc%81',
				'%cd%81',
				// Grave accent, macron, caron.
				'%cc%80',
				'%cc%84',
				'%cc%8c',
				// Non-visible characters that display without a width.
				'%e2%80%8b', // Zero width space.
				'%e2%80%8c', // Zero width non-joiner.
				'%e2%80%8d', // Zero width joiner.
				'%e2%80%8e', // Left-to-right mark.
				'%e2%80%8f', // Right-to-left mark.
				'%e2%80%aa', // Left-to-right embedding.
				'%e2%80%ab', // Right-to-left embedding.
				'%e2%80%ac', // Pop directional formatting.
				'%e2%80%ad', // Left-to-right override.
				'%e2%80%ae', // Right-to-left override.
				'%ef%bb%bf', // Byte order mark.
				'%ef%bf%bc', // Object replacement character.
			),
			'',
			$title
		);

		// Convert non-visible characters that display with a width to hyphen.
		$title = str_replace(
			array(
				'%e2%80%80', // En quad.
				'%e2%80%81', // Em quad.
				'%e2%80%82', // En space.
				'%e2%80%83', // Em space.
				'%e2%80%84', // Three-per-em space.
				'%e2%80%85', // Four-per-em space.
				'%e2%80%86', // Six-per-em space.
				'%e2%80%87', // Figure space.
				'%e2%80%88', // Punctuation space.
				'%e2%80%89', // Thin space.
				'%e2%80%8a', // Hair space.
				'%e2%80%a8', // Line separator.
				'%e2%80%a9', // Paragraph separator.
				'%e2%80%af', // Narrow no-break space.
			),
			'-',
			$title
		);

		// Convert &times to 'x'.
		$title = str_replace( '%c3%97', 'x', $title );
	}

	// Remove HTML entities.
	$title = preg_replace( '/&.+?;/', '', $title );
	$title = str_replace( '.', '-', $title );

	$title = preg_replace( '/[^%a-z0-9 _-]/', '', $title );
	$title = preg_replace( '/\s+/', '-', $title );
	$title = preg_replace( '|-+|', '-', $title );
	$title = trim( $title, '-' );

	return $title;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L2261) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L2261-L2380)

## [Related](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#related)

| Uses | Description |
| --- | --- |
| [seems\_utf8()](https://developer.wordpress.org/reference/functions/seems_utf8/) `wp-includes/formatting.php` | Checks to see if a string is utf8 encoded. |
| [utf8\_uri\_encode()](https://developer.wordpress.org/reference/functions/utf8_uri_encode/) `wp-includes/formatting.php` | Encodes the Unicode values to be used in the URI. |

| Used by | Description |
| --- | --- |
| [wp\_privacy\_generate\_personal\_data\_export\_group\_html()](https://developer.wordpress.org/reference/functions/wp_privacy_generate_personal_data_export_group_html/) `wp-admin/includes/privacy-tools.php` | Generate a single group for the personal data export report. |
| [wp\_privacy\_generate\_personal\_data\_export\_file()](https://developer.wordpress.org/reference/functions/wp_privacy_generate_personal_data_export_file/) `wp-admin/includes/privacy-tools.php` | Generate the personal data export file. |
| [WP\_Taxonomy::set\_props()](https://developer.wordpress.org/reference/classes/wp_taxonomy/set_props/) `wp-includes/class-wp-taxonomy.php` | Sets taxonomy properties. |
| [WP\_Post\_Type::set\_props()](https://developer.wordpress.org/reference/classes/wp_post_type/set_props/) `wp-includes/class-wp-post-type.php` | Sets post type properties. |
| [install\_dashboard()](https://developer.wordpress.org/reference/functions/install_dashboard/) `wp-admin/includes/plugin-install.php` | Displays the Featured tab of Add Plugins screen. |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [sanitize\_file\_name()](https://developer.wordpress.org/reference/functions/sanitize_file_name/) `wp-includes/formatting.php` | Sanitizes a filename, replacing whitespace with dashes. |

[Show 2 more](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#) [Show less](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#)

## [Changelog](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#comment-content-1081)



**Basic Example**





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#)




```php
<?php
echo sanitize_title_with_dashes("I'm in LOVE with WordPress!!!1");
// this will print: im-in-love-with-wordpress1
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_title_with_dashes%2F%3Freplytocom%3D1081%23feedback-editor-1081)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#comment-content-2852)



**Add Current Child-Site Body Class – WordPress Multisite**





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/#)




```php
// Add Current Child-Site Body Class – WordPress Multisite
function wpdocs_childSiteClass( $classes ) {
   	$site_title =  sanitize_title_with_dashes( get_bloginfo( 'name' ) );
   	$classes[] = 'website-' . $site_title;

   	return $classes;
}
add_filter( 'body_class', 'wpdocs_childSiteClass' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_title_with_dashes%2F%3Freplytocom%3D2852%23feedback-editor-2852)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_title_with_dashes%2F) before being able to contribute a note or feedback.

Notifications