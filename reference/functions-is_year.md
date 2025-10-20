---
url: https://developer.wordpress.org/reference/functions/is_year
scraped_at: 2025-10-20T03:22:40.262Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_year/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_year()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_year()

Search

# is\_year(): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/is_year/#description)
- [Return](https://developer.wordpress.org/reference/functions/is_year/#return)
- [Source](https://developer.wordpress.org/reference/functions/is_year/#source)
- [Related](https://developer.wordpress.org/reference/functions/is_year/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_year/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_year/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_year/#wp--skip-link--target)

Determines whether the query is for an existing year archive.

## [Description](https://developer.wordpress.org/reference/functions/is_year/\#description)

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Return](https://developer.wordpress.org/reference/functions/is_year/\#return)

bool Whether the query is for an existing year archive.

## [Source](https://developer.wordpress.org/reference/functions/is_year/\#source)

`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_year/#)

```php
function is_year() {
	global $wp_query;

	if ( ! isset( $wp_query ) ) {
		_doing_it_wrong( __FUNCTION__, __( 'Conditional query tags do not work before the query is run. Before then, they always return false.' ), '3.1.0' );
		return false;
	}

	return $wp_query->is_year();
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/query.php#L834) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/query.php#L834-L843)

## [Related](https://developer.wordpress.org/reference/functions/is_year/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Query::is\_year()](https://developer.wordpress.org/reference/classes/wp_query/is_year/) `wp-includes/class-wp-query.php` | Determines whether the query is for an existing year archive. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |

| Used by | Description |
| --- | --- |
| [wp\_get\_document\_title()](https://developer.wordpress.org/reference/functions/wp_get_document_title/) `wp-includes/general-template.php` | Returns document title for the current page. |
| [get\_the\_archive\_title()](https://developer.wordpress.org/reference/functions/get_the_archive_title/) `wp-includes/general-template.php` | Retrieves the archive title based on the queried object. |
| [redirect\_canonical()](https://developer.wordpress.org/reference/functions/redirect_canonical/) `wp-includes/canonical.php` | Redirects incoming links to the proper URL based on the site url. |

## [Changelog](https://developer.wordpress.org/reference/functions/is_year/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_year/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/is_year/#comment-content-1616)



**Check if current archive is year archive.**





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_year/#)




```php
if ( is_year() ) {
   	// Do awesome.
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_year%2F%3Freplytocom%3D1616%23feedback-editor-1616)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_year%2F) before being able to contribute a note or feedback.

Notifications