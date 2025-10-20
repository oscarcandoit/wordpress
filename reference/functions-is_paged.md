---
url: https://developer.wordpress.org/reference/functions/is_paged
scraped_at: 2025-10-20T03:15:10.592Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_paged/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_paged()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_paged()

Search

# is\_paged(): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/is_paged/#description)
- [Return](https://developer.wordpress.org/reference/functions/is_paged/#return)
- [Source](https://developer.wordpress.org/reference/functions/is_paged/#source)
- [Related](https://developer.wordpress.org/reference/functions/is_paged/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_paged/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_paged/#wp--skip-link--target)

Determines whether the query is for a paged result and not for the first page.

## [Description](https://developer.wordpress.org/reference/functions/is_paged/\#description)

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Return](https://developer.wordpress.org/reference/functions/is_paged/\#return)

bool Whether the query is for a paged result.

## [Source](https://developer.wordpress.org/reference/functions/is_paged/\#source)

`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_paged/#)

```php
function is_paged() {
	global $wp_query;

	if ( ! isset( $wp_query ) ) {
		_doing_it_wrong( __FUNCTION__, __( 'Conditional query tags do not work before the query is run. Before then, they always return false.' ), '3.1.0' );
		return false;
	}

	return $wp_query->is_paged();
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/query.php#L608) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/query.php#L608-L617)

## [Related](https://developer.wordpress.org/reference/functions/is_paged/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Query::is\_paged()](https://developer.wordpress.org/reference/classes/wp_query/is_paged/) `wp-includes/class-wp-query.php` | Determines whether the query is for a paged result and not for the first page. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |

| Used by | Description |
| --- | --- |
| [get\_custom\_logo()](https://developer.wordpress.org/reference/functions/get_custom_logo/) `wp-includes/general-template.php` | Returns a custom logo, linked to home unless the theme supports removing the link on the home page. |
| [WP::handle\_404()](https://developer.wordpress.org/reference/classes/wp/handle_404/) `wp-includes/class-wp.php` | Set the Headers for 404, if nothing is found for requested URL. |
| [wp\_page\_menu()](https://developer.wordpress.org/reference/functions/wp_page_menu/) `wp-includes/post-template.php` | Displays or retrieves a list of pages with an optional home link. |
| [get\_post\_class()](https://developer.wordpress.org/reference/functions/get_post_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the post container element. |
| [get\_body\_class()](https://developer.wordpress.org/reference/functions/get_body_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the body element. |

## [Changelog](https://developer.wordpress.org/reference/functions/is_paged/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_paged%2F) before being able to contribute a note or feedback.

Notifications