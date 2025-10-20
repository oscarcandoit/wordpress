---
url: https://developer.wordpress.org/reference/functions/is_tax
scraped_at: 2025-10-20T03:19:08.500Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_tax/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_tax()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_tax()

Search

# is\_tax( string\|string\[\]$taxonomy = '', int\|string\|int\[\]\|string\[\]$term = '' ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/is_tax/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/is_tax/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/is_tax/#return)
- [Source](https://developer.wordpress.org/reference/functions/is_tax/#source)
- [Related](https://developer.wordpress.org/reference/functions/is_tax/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_tax/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_tax/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_tax/#wp--skip-link--target)

Determines whether the query is for an existing custom taxonomy archive page.

## [Description](https://developer.wordpress.org/reference/functions/is_tax/\#description)

If the $taxonomy parameter is specified, this function will additionally check if the query is for that specific $taxonomy.

If the $term parameter is specified in addition to the $taxonomy parameter, this function will additionally check if the query is for one of the terms specified.

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Parameters](https://developer.wordpress.org/reference/functions/is_tax/\#parameters)

`$taxonomy` string\|string\[\]optional

Taxonomy slug or slugs to check against.

Default: `''`

`$term` int\|string\|int\[\]\|string\[\]optional

Term ID, name, slug, or array of such to check against.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/is_tax/\#return)

bool Whether the query is for an existing custom taxonomy archive page.

True for custom taxonomy archive pages, false for built-in taxonomies (category and tag archives).

## [Source](https://developer.wordpress.org/reference/functions/is_tax/\#source)

`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)

```php
function is_tax( $taxonomy = '', $term = '' ) {
	global $wp_query;

	if ( ! isset( $wp_query ) ) {
		_doing_it_wrong( __FUNCTION__, __( 'Conditional query tags do not work before the query is run. Before then, they always return false.' ), '3.1.0' );
		return false;
	}

	return $wp_query->is_tax( $taxonomy, $term );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/query.php#L337) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/query.php#L337-L346)

## [Related](https://developer.wordpress.org/reference/functions/is_tax/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Query::is\_tax()](https://developer.wordpress.org/reference/classes/wp_query/is_tax/) `wp-includes/class-wp-query.php` | Determines whether the query is for an existing custom taxonomy archive page. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |

| Used by | Description |
| --- | --- |
| [rest\_get\_queried\_resource\_route()](https://developer.wordpress.org/reference/functions/rest_get_queried_resource_route/) `wp-includes/rest-api.php` | Gets the REST route for the currently queried object. |
| [wp\_get\_document\_title()](https://developer.wordpress.org/reference/functions/wp_get_document_title/) `wp-includes/general-template.php` | Returns document title for the current page. |
| [get\_the\_archive\_title()](https://developer.wordpress.org/reference/functions/get_the_archive_title/) `wp-includes/general-template.php` | Retrieves the archive title based on the queried object. |
| [term\_description()](https://developer.wordpress.org/reference/functions/term_description/) `wp-includes/category-template.php` | Retrieves term description. |
| [wp\_list\_categories()](https://developer.wordpress.org/reference/functions/wp_list_categories/) `wp-includes/category-template.php` | Displays or retrieves the HTML list of categories. |
| [feed\_links\_extra()](https://developer.wordpress.org/reference/functions/feed_links_extra/) `wp-includes/general-template.php` | Displays the links to the extra feeds such as category feeds. |
| [wp\_title()](https://developer.wordpress.org/reference/functions/wp_title/) `wp-includes/general-template.php` | Displays or retrieves page title for all areas of blog. |
| [single\_term\_title()](https://developer.wordpress.org/reference/functions/single_term_title/) `wp-includes/general-template.php` | Displays or retrieves page title for taxonomy term archive. |
| [WP::handle\_404()](https://developer.wordpress.org/reference/classes/wp/handle_404/) `wp-includes/class-wp.php` | Set the Headers for 404, if nothing is found for requested URL. |
| [get\_body\_class()](https://developer.wordpress.org/reference/functions/get_body_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the body element. |
| [redirect\_canonical()](https://developer.wordpress.org/reference/functions/redirect_canonical/) `wp-includes/canonical.php` | Redirects incoming links to the proper URL based on the site url. |

[Show 6 more](https://developer.wordpress.org/reference/functions/is_tax/#) [Show less](https://developer.wordpress.org/reference/functions/is_tax/#)

## [Changelog](https://developer.wordpress.org/reference/functions/is_tax/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_tax/\#user-contributed-notes)

1. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-806)



Examples





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
is_tax();
// When any custom taxonomy archive page is being displayed.

is_tax( 'channel' );
// When the archive page for taxonomy of 'channel' is being displayed.

is_tax( 'channel', 'BBC1' );
// When the archive page for taxonomy of 'channel' is being displayed
// and the 'channel' taxonomy term is 'BBC1'.
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D806%23feedback-editor-806)

2. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-3736)



How to limit the number of posts that appear in a landing page for a specific taxonomy:



If you are making a custom archive landing page that is based on a taxonomy and NOT a category or tag you can place the following code in your `functions.php` file:





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
add_action( 'pre_get_posts', function( $query) {
       if ( $query->is_tax( 'NAME_OF_TAXONOMY' ) ) { // Replace with the name of the taxonomy you want to target
           $query->set( 'posts_per_page', 6 ); // change '6' to the number of posts you want to appear
       }

} );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D3736%23feedback-editor-3736)

3. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-4984)



To check for more than one taxonomy, you can use an array. That’s useful when you want to display some code only on those taxonomy pages.





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
if ( is_tax( array('channel', 'broadcaster') ) ) {
// your code goes here
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D4984%23feedback-editor-4984)

4. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-6845)



**Check for any taxonomy archive**

`is_tax()` only checks if the current query is for a custom taxonomy.



This doesn’t include the default category and tag taxonomies. You can check for any taxonomy archive by using [is\_category()](https://developer.wordpress.org/reference/functions/is_category/) and [is\_tag()](https://developer.wordpress.org/reference/functions/is_tag/) alongside the [is\_tax()](https://developer.wordpress.org/reference/functions/is_tax/) function





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
if ( is_category() || is_tag() || is_tax() ){
   	// Is any taxonomy archive page
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D6845%23feedback-editor-6845)

5. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-3668)



The $term parameter also accepts term objects.





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
is_tax( 'custom_taxonomy', $taxonomy_term_object );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D3668%23feedback-editor-3668)

6. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/is_tax/#comment-content-807)



**Post Formats**


The taxonomy slug for Post Formats differs from the Post Format slug. The `register_taxonomy()` function appends a `post-format-` base to the Post Format slug. So, e.g. while the “Aside” Post Format type has a slug of aside, the `post_format` taxonomy term “Aside” has a slug of `post-format-aside`.





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/is_tax/#)




```php
// When the archive page for any Post Format term is being displayed.
is_tax( 'post_format' );

// When the archive page for Post Format type 'aside' is being displayed.
is_tax( 'post_format', 'post-format-aside' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F%3Freplytocom%3D807%23feedback-editor-807)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_tax%2F) before being able to contribute a note or feedback.

Notifications