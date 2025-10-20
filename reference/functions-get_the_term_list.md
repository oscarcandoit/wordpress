---
url: https://developer.wordpress.org/reference/functions/get_the_term_list
scraped_at: 2025-10-20T03:16:02.014Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_the_term_list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_the\_term\_list()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_the\_term\_list()

Search

# get\_the\_term\_list( int$post\_id, string$taxonomy, string$before = '', string$sep = '', string$after = '' ): string\|false\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_the_term_list/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_the_term_list/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_the_term_list/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_the_term_list/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_the_term_list/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_the_term_list/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_the_term_list/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_the_term_list/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_the_term_list/#wp--skip-link--target)

Retrieves a post’s terms as a list with specified format.

## [Description](https://developer.wordpress.org/reference/functions/get_the_term_list/\#description)

Terms are linked to their respective term listing pages.

## [Parameters](https://developer.wordpress.org/reference/functions/get_the_term_list/\#parameters)

`$post_id` intrequired

Post ID.

`$taxonomy` stringrequired

Taxonomy name.

`$before` stringoptional

String to use before the terms.

Default: `''`

`$sep` stringoptional

String to use between the terms.

Default: `''`

`$after` stringoptional

String to use after the terms.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/get_the_term_list/\#return)

string\|false\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) A list of terms on success, false if there are no terms, [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on failure.

## [Source](https://developer.wordpress.org/reference/functions/get_the_term_list/\#source)

`wp-includes/category-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_the_term_list/#)

[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)

```php
function get_the_term_list( $post_id, $taxonomy, $before = '', $sep = '', $after = '' ) {
	$terms = get_the_terms( $post_id, $taxonomy );

	if ( is_wp_error( $terms ) ) {
		return $terms;
	}

	if ( empty( $terms ) ) {
		return false;
	}

	$links = array();

	foreach ( $terms as $term ) {
		$link = get_term_link( $term, $taxonomy );
		if ( is_wp_error( $link ) ) {
			return $link;
		}
		$links[] = '<a href="' . esc_url( $link ) . '" rel="tag">' . $term->name . '</a>';
	}

	/**
	 * Filters the term links for a given taxonomy.
	 *
	 * The dynamic portion of the hook name, `$taxonomy`, refers
	 * to the taxonomy slug.
	 *
	 * Possible hook names include:
	 *
	 *  - `term_links-category`
	 *  - `term_links-post_tag`
	 *  - `term_links-post_format`
	 *
	 * @since 2.5.0
	 *
	 * @param string[] $links An array of term links.
	 */
	$term_links = apply_filters( "term_links-{$taxonomy}", $links );  // phpcs:ignore WordPress.NamingConventions.ValidHookName.UseUnderscores

	return $before . implode( $sep, $term_links ) . $after;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/category-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/category-template.php#L1338) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/category-template.php#L1338-L1378)

## [Hooks](https://developer.wordpress.org/reference/functions/get_the_term_list/\#hooks)

[apply\_filters( “term\_links-{$taxonomy}”, string\[\]$links )](https://developer.wordpress.org/reference/hooks/term_links-taxonomy/)

Filters the term links for a given taxonomy.

## [Related](https://developer.wordpress.org/reference/functions/get_the_term_list/\#related)

| Uses | Description |
| --- | --- |
| [get\_the\_terms()](https://developer.wordpress.org/reference/functions/get_the_terms/) `wp-includes/category-template.php` | Retrieves the terms of the taxonomy that are attached to the post. |
| [get\_term\_link()](https://developer.wordpress.org/reference/functions/get_term_link/) `wp-includes/taxonomy.php` | Generates a permalink for a taxonomy term archive. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_the_term_list/#) [Show less](https://developer.wordpress.org/reference/functions/get_the_term_list/#)

| Used by | Description |
| --- | --- |
| [the\_terms()](https://developer.wordpress.org/reference/functions/the_terms/) `wp-includes/category-template.php` | Displays the terms for a post in a list. |
| [get\_the\_tag\_list()](https://developer.wordpress.org/reference/functions/get_the_tag_list/) `wp-includes/category-template.php` | Retrieves the tags for a post formatted as a string. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_the_term_list/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_the_term_list/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_the_term_list/#comment-content-3214)



You can use this function with `strip_tags` function to print not linked term list:





`wp-includes/category-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)




```php
echo strip_tags( get_the_term_list( $post->ID, 'job_titles', '', ', ') )
```





This prints something like this:



`Designer, Front-end Developer, Developer`





[Show feedback (1)](https://developer.wordpress.org/reference/functions/get_the_term_list/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_the_term_list%2F%3Freplytocom%3D3214%23feedback-editor-3214)



- WordPress coding standards suggest that instead of \`strip\_tags\` we should use the more comprehensive \`wp\_strip\_all\_tags\` instead.



[hanopcan](https://profiles.wordpress.org/hanopcan/) [5 years ago](https://developer.wordpress.org/reference/functions/get_the_term_list/#comment-4877)


2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_the_term_list/#comment-content-1111)



**Basic Example**



Used inside the loop this outputs the terms from the people taxonomy for a specific post.





`wp-includes/category-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)




```php
<?php echo get_the_term_list( $post->ID, 'people', 'People: ', ', ' ); ?>
```





This would return something like.





`wp-includes/category-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)




```php
People: <a href="person1">Person 1</a>, <a href="person2">Person 2</a>, ...
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_the_term_list%2F%3Freplytocom%3D1111%23feedback-editor-1111)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_the_term_list/#comment-content-1112)



**Returning an HTML List**



Used inside the loop this outputs the terms from the styles taxonomy for a specific post as an (x)html list.





`wp-includes/category-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)




```php
echo get_the_term_list( $post->ID, 'styles', '<ul class="styles"><li>', ',</li><li>', '</li></ul>' );
```





This would return something like.





`wp-includes/category-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_the_term_list/#)




```php
<ul class="styles">
       <li><a href="person1">Style 1</a>,</li>
       <li><a href="person2">Style 2</a></li>
</ul>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_the_term_list%2F%3Freplytocom%3D1112%23feedback-editor-1112)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_the_term_list%2F) before being able to contribute a note or feedback.

Notifications