---
url: https://developer.wordpress.org/reference/functions/wp_get_document_title
scraped_at: 2025-10-20T03:15:58.100Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_document_title/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_document\_title()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_document\_title()

Search

# wp\_get\_document\_title(): string

## In this article

Table of Contents

- [Return](https://developer.wordpress.org/reference/functions/wp_get_document_title/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_document_title/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_get_document_title/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_document_title/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_document_title/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_document_title/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_document_title/#wp--skip-link--target)

Returns document title for the current page.

## [Return](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#return)

string Tag with the document title.

## [Source](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_document_title/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_document_title/#)

```php
function wp_get_document_title() {

	/**
	 * Filters the document title before it is generated.
	 *
	 * Passing a non-empty value will short-circuit wp_get_document_title(),
	 * returning that value instead.
	 *
	 * @since 4.4.0
	 *
	 * @param string $title The document title. Default empty string.
	 */
	$title = apply_filters( 'pre_get_document_title', '' );
	if ( ! empty( $title ) ) {
		return $title;
	}

	global $page, $paged;

	$title = array(
		'title' => '',
	);

	// If it's a 404 page, use a "Page not found" title.
	if ( is_404() ) {
		$title['title'] = __( 'Page not found' );

		// If it's a search, use a dynamic search results title.
	} elseif ( is_search() ) {
		/* translators: %s: Search query. */
		$title['title'] = sprintf( __( 'Search Results for &#8220;%s&#8221;' ), get_search_query() );

		// If on the front page, use the site title.
	} elseif ( is_front_page() ) {
		$title['title'] = get_bloginfo( 'name', 'display' );

		// If on a post type archive, use the post type archive title.
	} elseif ( is_post_type_archive() ) {
		$title['title'] = post_type_archive_title( '', false );

		// If on a taxonomy archive, use the term title.
	} elseif ( is_tax() ) {
		$title['title'] = single_term_title( '', false );

		/*
		* If we're on the blog page that is not the homepage
		* or a single post of any post type, use the post title.
		*/
	} elseif ( is_home() || is_singular() ) {
		$title['title'] = single_post_title( '', false );

		// If on a category or tag archive, use the term title.
	} elseif ( is_category() || is_tag() ) {
		$title['title'] = single_term_title( '', false );

		// If on an author archive, use the author's display name.
	} elseif ( is_author() && get_queried_object() ) {
		$author         = get_queried_object();
		$title['title'] = $author->display_name;

		// If it's a date archive, use the date as the title.
	} elseif ( is_year() ) {
		$title['title'] = get_the_date( _x( 'Y', 'yearly archives date format' ) );

	} elseif ( is_month() ) {
		$title['title'] = get_the_date( _x( 'F Y', 'monthly archives date format' ) );

	} elseif ( is_day() ) {
		$title['title'] = get_the_date();
	}

	// Add a page number if necessary.
	if ( ( $paged >= 2 || $page >= 2 ) && ! is_404() ) {
		/* translators: %s: Page number. */
		$title['page'] = sprintf( __( 'Page %s' ), max( $paged, $page ) );
	}

	// Append the description or site title to give context.
	if ( is_front_page() ) {
		$title['tagline'] = get_bloginfo( 'description', 'display' );
	} else {
		$title['site'] = get_bloginfo( 'name', 'display' );
	}

	/**
	 * Filters the separator for the document title.
	 *
	 * @since 4.4.0
	 *
	 * @param string $sep Document title separator. Default '-'.
	 */
	$sep = apply_filters( 'document_title_separator', '-' );

	/**
	 * Filters the parts of the document title.
	 *
	 * @since 4.4.0
	 *
	 * @param array $title {
	 *     The document title parts.
	 *
	 *     @type string $title   Title of the viewed page.
	 *     @type string $page    Optional. Page number if paginated.
	 *     @type string $tagline Optional. Site description when on home page.
	 *     @type string $site    Optional. Site title when not on home page.
	 * }
	 */
	$title = apply_filters( 'document_title_parts', $title );

	$title = implode( " $sep ", array_filter( $title ) );

	/**
	 * Filters the document title.
	 *
	 * @since 5.8.0
	 *
	 * @param string $title Document title.
	 */
	$title = apply_filters( 'document_title', $title );

	return $title;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L1176) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L1176-L1297)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#hooks)

[apply\_filters( ‘document\_title’, string$title )](https://developer.wordpress.org/reference/hooks/document_title/)

Filters the document title.

[apply\_filters( ‘document\_title\_parts’, array$title )](https://developer.wordpress.org/reference/hooks/document_title_parts/)

Filters the parts of the document title.

[apply\_filters( ‘document\_title\_separator’, string$sep )](https://developer.wordpress.org/reference/hooks/document_title_separator/)

Filters the separator for the document title.

[apply\_filters( ‘pre\_get\_document\_title’, string$title )](https://developer.wordpress.org/reference/hooks/pre_get_document_title/)

Filters the document title before it is generated.

## [Related](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#related)

| Uses | Description |
| --- | --- |
| [get\_search\_query()](https://developer.wordpress.org/reference/functions/get_search_query/) `wp-includes/general-template.php` | Retrieves the contents of the search WordPress query variable. |
| [get\_the\_date()](https://developer.wordpress.org/reference/functions/get_the_date/) `wp-includes/general-template.php` | Retrieves the date of the post. |
| [post\_type\_archive\_title()](https://developer.wordpress.org/reference/functions/post_type_archive_title/) `wp-includes/general-template.php` | Displays or retrieves title for a post type archive. |
| [single\_term\_title()](https://developer.wordpress.org/reference/functions/single_term_title/) `wp-includes/general-template.php` | Displays or retrieves page title for taxonomy term archive. |
| [single\_post\_title()](https://developer.wordpress.org/reference/functions/single_post_title/) `wp-includes/general-template.php` | Displays or retrieves page title for post. |
| [is\_404()](https://developer.wordpress.org/reference/functions/is_404/) `wp-includes/query.php` | Determines whether the query has resulted in a 404 (returns no results). |
| [is\_search()](https://developer.wordpress.org/reference/functions/is_search/) `wp-includes/query.php` | Determines whether the query is for a search. |
| [is\_singular()](https://developer.wordpress.org/reference/functions/is_singular/) `wp-includes/query.php` | Determines whether the query is for an existing single post of any post type (post, attachment, page, custom post types). |
| [is\_year()](https://developer.wordpress.org/reference/functions/is_year/) `wp-includes/query.php` | Determines whether the query is for an existing year archive. |
| [is\_front\_page()](https://developer.wordpress.org/reference/functions/is_front_page/) `wp-includes/query.php` | Determines whether the query is for the front page of the site. |
| [is\_tax()](https://developer.wordpress.org/reference/functions/is_tax/) `wp-includes/query.php` | Determines whether the query is for an existing custom taxonomy archive page. |
| [is\_home()](https://developer.wordpress.org/reference/functions/is_home/) `wp-includes/query.php` | Determines whether the query is for the blog homepage. |
| [is\_category()](https://developer.wordpress.org/reference/functions/is_category/) `wp-includes/query.php` | Determines whether the query is for an existing category archive page. |
| [is\_tag()](https://developer.wordpress.org/reference/functions/is_tag/) `wp-includes/query.php` | Determines whether the query is for an existing tag archive page. |
| [is\_author()](https://developer.wordpress.org/reference/functions/is_author/) `wp-includes/query.php` | Determines whether the query is for an existing author archive page. |
| [is\_month()](https://developer.wordpress.org/reference/functions/is_month/) `wp-includes/query.php` | Determines whether the query is for an existing month archive. |
| [is\_day()](https://developer.wordpress.org/reference/functions/is_day/) `wp-includes/query.php` | Determines whether the query is for an existing day archive. |
| [is\_post\_type\_archive()](https://developer.wordpress.org/reference/functions/is_post_type_archive/) `wp-includes/query.php` | Determines whether the query is for an existing post type archive page. |
| [get\_queried\_object()](https://developer.wordpress.org/reference/functions/get_queried_object/) `wp-includes/query.php` | Retrieves the currently queried object. |
| [get\_bloginfo()](https://developer.wordpress.org/reference/functions/get_bloginfo/) `wp-includes/general-template.php` | Retrieves information about the current site. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 16 more](https://developer.wordpress.org/reference/functions/wp_get_document_title/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_document_title/#)

| Used by | Description |
| --- | --- |
| [\_wp\_render\_title\_tag()](https://developer.wordpress.org/reference/functions/_wp_render_title_tag/) `wp-includes/general-template.php` | Displays title tag with content. |
| [\_block\_template\_render\_title\_tag()](https://developer.wordpress.org/reference/functions/_block_template_render_title_tag/) `wp-includes/block-template.php` | Displays title tag with content, regardless of whether theme has title-tag support. |
| [get\_wp\_title\_rss()](https://developer.wordpress.org/reference/functions/get_wp_title_rss/) `wp-includes/feed.php` | Retrieves the blog title for the feed title. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_document_title/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/wp_get_document_title/#comment-content-3966)



Basic Usage:





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_document_title/#)




```php
<head>
   	<meta charset="<?php bloginfo( 'charset' ); ?>">
   	<meta name="viewport" content="width=device-width" />
   	<title><?php echo wp_get_document_title(); ?></title>
   	<?php wp_head(); ?>
</head>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_document_title%2F%3Freplytocom%3D3966%23feedback-editor-3966)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_get_document_title/#comment-content-1631)



To use: add to _header.php_



``





[Show feedback (1)](https://developer.wordpress.org/reference/functions/wp_get_document_title/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_document_title%2F%3Freplytocom%3D1631%23feedback-editor-1631)



- Basic Usage:







`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_document_title/#)




```php
    	&lt;meta charset=&quot;"&gt;
```







[Rami Yushuvaev](https://profiles.wordpress.org/ramiy/) [5 years ago](https://developer.wordpress.org/reference/functions/wp_get_document_title/#comment-3965)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_document_title%2F) before being able to contribute a note or feedback.

Notifications