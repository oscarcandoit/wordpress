---
url: https://developer.wordpress.org/reference/functions/get_post_format_string
scraped_at: 2025-10-20T03:23:32.952Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_post_format_string/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_post\_format\_string()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_post\_format\_string()

Search

# get\_post\_format\_string( string$slug ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_post_format_string/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_post_format_string/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_post_format_string/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_post_format_string/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_post_format_string/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_post_format_string/#wp--skip-link--target)

Returns a pretty, translated version of a post format slug

## [Parameters](https://developer.wordpress.org/reference/functions/get_post_format_string/\#parameters)

`$slug` stringrequired

A post format slug.

## [Return](https://developer.wordpress.org/reference/functions/get_post_format_string/\#return)

string The translated post format name.

## [Source](https://developer.wordpress.org/reference/functions/get_post_format_string/\#source)

`wp-includes/post-formats.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_format_string/#)

```php
function get_post_format_string( $slug ) {
	$strings = get_post_format_strings();
	if ( ! $slug ) {
		return $strings['standard'];
	} else {
		return ( isset( $strings[ $slug ] ) ) ? $strings[ $slug ] : '';
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post-formats.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post-formats.php#L132) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post-formats.php#L132-L139)

## [Related](https://developer.wordpress.org/reference/functions/get_post_format_string/\#related)

| Uses | Description |
| --- | --- |
| [get\_post\_format\_strings()](https://developer.wordpress.org/reference/functions/get_post_format_strings/) `wp-includes/post-formats.php` | Returns an array of post format slugs to their translated and pretty display versions |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Post\_Format\_Search\_Handler::search\_items()](https://developer.wordpress.org/reference/classes/wp_rest_post_format_search_handler/search_items/) `wp-includes/rest-api/search/class-wp-rest-post-format-search-handler.php` | Searches the post formats for a given search request. |
| [WP\_REST\_Post\_Format\_Search\_Handler::prepare\_item()](https://developer.wordpress.org/reference/classes/wp_rest_post_format_search_handler/prepare_item/) `wp-includes/rest-api/search/class-wp-rest-post-format-search-handler.php` | Prepares the search result for a given post format. |
| [WP\_Posts\_List\_Table::formats\_dropdown()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/formats_dropdown/) `wp-admin/includes/class-wp-posts-list-table.php` | Displays a formats drop-down for filtering items. |
| [post\_format\_meta\_box()](https://developer.wordpress.org/reference/functions/post_format_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post format form elements. |
| [WP\_Posts\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/inline_edit/) `wp-admin/includes/class-wp-posts-list-table.php` | Outputs the hidden row displayed when inline editing |
| [\_post\_format\_get\_term()](https://developer.wordpress.org/reference/functions/_post_format_get_term/) `wp-includes/post-formats.php` | Remove the post format prefix from the name property of the term object created by [get\_term()](https://developer.wordpress.org/reference/functions/get_term/) . |
| [\_post\_format\_get\_terms()](https://developer.wordpress.org/reference/functions/_post_format_get_terms/) `wp-includes/post-formats.php` | Remove the post format prefix from the name property of the term objects created by [get\_terms()](https://developer.wordpress.org/reference/functions/get_terms/) . |
| [\_post\_format\_wp\_get\_object\_terms()](https://developer.wordpress.org/reference/functions/_post_format_wp_get_object_terms/) `wp-includes/post-formats.php` | Remove the post format prefix from the name property of the term objects created by [wp\_get\_object\_terms()](https://developer.wordpress.org/reference/functions/wp_get_object_terms/) . |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_post_format_string/#) [Show less](https://developer.wordpress.org/reference/functions/get_post_format_string/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_post_format_string/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_format_string%2F) before being able to contribute a note or feedback.

Notifications