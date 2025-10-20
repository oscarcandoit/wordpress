---
url: https://developer.wordpress.org/reference/functions/user_trailingslashit
scraped_at: 2025-10-20T03:16:14.415Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/user_trailingslashit/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

user\_trailingslashit()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)user\_trailingslashit()

Search

# user\_trailingslashit( string$url, string$type\_of\_url = '' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/user_trailingslashit/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/user_trailingslashit/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/user_trailingslashit/#return)
- [Source](https://developer.wordpress.org/reference/functions/user_trailingslashit/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/user_trailingslashit/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/user_trailingslashit/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/user_trailingslashit/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/user_trailingslashit/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/user_trailingslashit/#wp--skip-link--target)

Retrieves a trailing-slashed string if the site is set for adding trailing slashes.

## [Description](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#description)

Conditionally adds a trailing slash if the permalink structure has a trailing slash, strips the trailing slash if not. The string is passed through the [‘user\_trailingslashit’](https://developer.wordpress.org/reference/hooks/user_trailingslashit/) filter. Will remove trailing slash from string, if site is not set to have them.

## [Parameters](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#parameters)

`$url` stringrequired

URL with or without a trailing slash.

`$type_of_url` stringoptional

The type of URL being considered (e.g. single, category, etc) for use in the filter.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#return)

string The URL with the trailing slash appended or stripped.

## [Source](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/user_trailingslashit/#)

[Copy](https://developer.wordpress.org/reference/functions/user_trailingslashit/#)

```php
function user_trailingslashit( $url, $type_of_url = '' ) {
	global $wp_rewrite;
	if ( $wp_rewrite->use_trailing_slashes ) {
		$url = trailingslashit( $url );
	} else {
		$url = untrailingslashit( $url );
	}

	/**
	 * Filters the trailing-slashed string, depending on whether the site is set to use trailing slashes.
	 *
	 * @since 2.2.0
	 *
	 * @param string $url         URL with or without a trailing slash.
	 * @param string $type_of_url The type of URL being considered. Accepts 'single', 'single_trackback',
	 *                            'single_feed', 'single_paged', 'commentpaged', 'paged', 'home', 'feed',
	 *                            'category', 'page', 'year', 'month', 'day', 'post_type_archive'.
	 */
	return apply_filters( 'user_trailingslashit', $url, $type_of_url );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L47) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L47-L66)

## [Hooks](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#hooks)

[apply\_filters( ‘user\_trailingslashit’, string$url, string$type\_of\_url )](https://developer.wordpress.org/reference/hooks/user_trailingslashit/)

Filters the trailing-slashed string, depending on whether the site is set to use trailing slashes.

## [Related](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#related)

| Uses | Description |
| --- | --- |
| [untrailingslashit()](https://developer.wordpress.org/reference/functions/untrailingslashit/) `wp-includes/formatting.php` | Removes trailing forward slashes and backslashes if they exist. |
| [trailingslashit()](https://developer.wordpress.org/reference/functions/trailingslashit/) `wp-includes/formatting.php` | Appends a trailing slash. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 1 more](https://developer.wordpress.org/reference/functions/user_trailingslashit/#) [Show less](https://developer.wordpress.org/reference/functions/user_trailingslashit/#)

| Used by | Description |
| --- | --- |
| [wp\_get\_canonical\_url()](https://developer.wordpress.org/reference/functions/wp_get_canonical_url/) `wp-includes/link-template.php` | Returns the canonical URL for a post. |
| [get\_post\_embed\_url()](https://developer.wordpress.org/reference/functions/get_post_embed_url/) `wp-includes/embed.php` | Retrieves the URL to embed a specific post in an iframe. |
| [paginate\_links()](https://developer.wordpress.org/reference/functions/paginate_links/) `wp-includes/general-template.php` | Retrieves paginated links for archive post pages. |
| [get\_index\_rel\_link()](https://developer.wordpress.org/reference/functions/get_index_rel_link/) `wp-includes/deprecated.php` | Get site index relational link. |
| [wp\_old\_slug\_redirect()](https://developer.wordpress.org/reference/functions/wp_old_slug_redirect/) `wp-includes/query.php` | Redirect old slugs to the correct permalink. |
| [get\_term\_link()](https://developer.wordpress.org/reference/functions/get_term_link/) `wp-includes/taxonomy.php` | Generates a permalink for a taxonomy term archive. |
| [get\_comments\_pagenum\_link()](https://developer.wordpress.org/reference/functions/get_comments_pagenum_link/) `wp-includes/link-template.php` | Retrieves the comments page number link. |
| [paginate\_comments\_links()](https://developer.wordpress.org/reference/functions/paginate_comments_links/) `wp-includes/link-template.php` | Displays or retrieves pagination links for the comments on the current post. |
| [get\_pagenum\_link()](https://developer.wordpress.org/reference/functions/get_pagenum_link/) `wp-includes/link-template.php` | Retrieves the link for a page number. |
| [get\_post\_type\_archive\_link()](https://developer.wordpress.org/reference/functions/get_post_type_archive_link/) `wp-includes/link-template.php` | Retrieves the permalink for a post type archive. |
| [get\_term\_feed\_link()](https://developer.wordpress.org/reference/functions/get_term_feed_link/) `wp-includes/link-template.php` | Retrieves the feed link for a term. |
| [get\_search\_link()](https://developer.wordpress.org/reference/functions/get_search_link/) `wp-includes/link-template.php` | Retrieves the permalink for a search. |
| [get\_month\_link()](https://developer.wordpress.org/reference/functions/get_month_link/) `wp-includes/link-template.php` | Retrieves the permalink for the month archives with year. |
| [get\_day\_link()](https://developer.wordpress.org/reference/functions/get_day_link/) `wp-includes/link-template.php` | Retrieves the permalink for the day archives with year and month. |
| [get\_feed\_link()](https://developer.wordpress.org/reference/functions/get_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the feed type. |
| [get\_post\_comments\_feed\_link()](https://developer.wordpress.org/reference/functions/get_post_comments_feed_link/) `wp-includes/link-template.php` | Retrieves the permalink for the post comments feed. |
| [get\_author\_feed\_link()](https://developer.wordpress.org/reference/functions/get_author_feed_link/) `wp-includes/link-template.php` | Retrieves the feed link for a given author. |
| [get\_permalink()](https://developer.wordpress.org/reference/functions/get_permalink/) `wp-includes/link-template.php` | Retrieves the full permalink for the current post or post ID. |
| [get\_post\_permalink()](https://developer.wordpress.org/reference/functions/get_post_permalink/) `wp-includes/link-template.php` | Retrieves the permalink for a post of a custom post type. |
| [\_get\_page\_link()](https://developer.wordpress.org/reference/functions/_get_page_link/) `wp-includes/link-template.php` | Retrieves the page permalink. |
| [get\_attachment\_link()](https://developer.wordpress.org/reference/functions/get_attachment_link/) `wp-includes/link-template.php` | Retrieves the permalink for an attachment. |
| [get\_year\_link()](https://developer.wordpress.org/reference/functions/get_year_link/) `wp-includes/link-template.php` | Retrieves the permalink for the year archives. |
| [\_wp\_link\_page()](https://developer.wordpress.org/reference/functions/_wp_link_page/) `wp-includes/post-template.php` | Helper function for [wp\_link\_pages()](https://developer.wordpress.org/reference/functions/wp_link_pages/) . |
| [redirect\_canonical()](https://developer.wordpress.org/reference/functions/redirect_canonical/) `wp-includes/canonical.php` | Redirects incoming links to the proper URL based on the site url. |
| [redirect\_guess\_404\_permalink()](https://developer.wordpress.org/reference/functions/redirect_guess_404_permalink/) `wp-includes/canonical.php` | Attempts to guess the correct URL for a 404 request based on query vars. |
| [get\_author\_posts\_url()](https://developer.wordpress.org/reference/functions/get_author_posts_url/) `wp-includes/author-template.php` | Retrieves the URL to the author page for the user with the ID provided. |
| [get\_trackback\_url()](https://developer.wordpress.org/reference/functions/get_trackback_url/) `wp-includes/comment-template.php` | Retrieves the current post’s trackback URL. |
| [get\_comment\_link()](https://developer.wordpress.org/reference/functions/get_comment_link/) `wp-includes/comment-template.php` | Retrieves the link to a given comment. |

[Show 23 more](https://developer.wordpress.org/reference/functions/user_trailingslashit/#) [Show less](https://developer.wordpress.org/reference/functions/user_trailingslashit/#)

## [Changelog](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#changelog)

| Version | Description |
| --- | --- |
| [2.2.0](https://developer.wordpress.org/reference/since/2.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/user_trailingslashit/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/user_trailingslashit/#comment-content-4533)



you can remove **category** from wordpress url. See example below.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/user_trailingslashit/#)




```php
function wpdocs_remove_category( $string, $type ) {
   	if ( 'single' !== $type && 'category' === $type && false !== strpos( $string, 'category' ) ) {
   		$url_without_category = str_replace( '/category/', '/', $string );
   		return trailingslashit( $url_without_category );
   	}
   	return $string;
}
add_filter( 'user_trailingslashit', 'wpdocs_remove_category', 100, 2 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fuser_trailingslashit%2F%3Freplytocom%3D4533%23feedback-editor-4533)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fuser_trailingslashit%2F) before being able to contribute a note or feedback.

Notifications