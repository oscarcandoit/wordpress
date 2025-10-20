---
url: https://developer.wordpress.org/reference/functions/get_term_children
scraped_at: 2025-10-20T03:13:36.924Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_term_children/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_term\_children()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_term\_children()

Search

# get\_term\_children( int$term\_id, string$taxonomy ): array\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_term_children/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_term_children/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_term_children/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_term_children/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_term_children/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_term_children/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_term_children/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_term_children/#wp--skip-link--target)

Merges all term children into a single array of their IDs.

## [Description](https://developer.wordpress.org/reference/functions/get_term_children/\#description)

This recursive function will merge all of the children of $term into the same array of term IDs. Only useful for taxonomies which are hierarchical.

Will return an empty array if $term does not exist in $taxonomy.

## [Parameters](https://developer.wordpress.org/reference/functions/get_term_children/\#parameters)

`$term_id` intrequired

ID of term to get children.

`$taxonomy` stringrequired

Taxonomy name.

## [Return](https://developer.wordpress.org/reference/functions/get_term_children/\#return)

array\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) List of term IDs. [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) returned if `$taxonomy` does not exist.

## [Source](https://developer.wordpress.org/reference/functions/get_term_children/\#source)

`wp-includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_term_children/#)

[Copy](https://developer.wordpress.org/reference/functions/get_term_children/#)

```php
function get_term_children( $term_id, $taxonomy ) {
	if ( ! taxonomy_exists( $taxonomy ) ) {
		return new WP_Error( 'invalid_taxonomy', __( 'Invalid taxonomy.' ) );
	}

	$term_id = (int) $term_id;

	$terms = _get_term_hierarchy( $taxonomy );

	if ( ! isset( $terms[ $term_id ] ) ) {
		return array();
	}

	$children = $terms[ $term_id ];

	foreach ( (array) $terms[ $term_id ] as $child ) {
		if ( $term_id === $child ) {
			continue;
		}

		if ( isset( $terms[ $child ] ) ) {
			$children = array_merge( $children, get_term_children( $child, $taxonomy ) );
		}
	}

	return $children;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/taxonomy.php#L1176) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/taxonomy.php#L1176-L1202)

## [Related](https://developer.wordpress.org/reference/functions/get_term_children/\#related)

| Uses | Description |
| --- | --- |
| [\_get\_term\_hierarchy()](https://developer.wordpress.org/reference/functions/_get_term_hierarchy/) `wp-includes/taxonomy.php` | Retrieves children of taxonomy as term IDs. |
| [get\_term\_children()](https://developer.wordpress.org/reference/functions/get_term_children/) `wp-includes/taxonomy.php` | Merges all term children into a single array of their IDs. |
| [taxonomy\_exists()](https://developer.wordpress.org/reference/functions/taxonomy_exists/) `wp-includes/taxonomy.php` | Determines whether the taxonomy name exists. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_term_children/#) [Show less](https://developer.wordpress.org/reference/functions/get_term_children/#)

| Used by | Description |
| --- | --- |
| [WP\_Term\_Query::get\_terms()](https://developer.wordpress.org/reference/classes/wp_term_query/get_terms/) `wp-includes/class-wp-term-query.php` | Retrieves the query results. |
| [WP\_Tax\_Query::clean\_query()](https://developer.wordpress.org/reference/classes/wp_tax_query/clean_query/) `wp-includes/class-wp-tax-query.php` | Validates a single query. |
| [get\_term\_children()](https://developer.wordpress.org/reference/functions/get_term_children/) `wp-includes/taxonomy.php` | Merges all term children into a single array of their IDs. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_term_children/\#changelog)

| Version | Description |
| --- | --- |
| [2.3.0](https://developer.wordpress.org/reference/since/2.3.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_term_children/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_term_children/#comment-content-579)



**A Basic Example**


Used to get an array of children taxonomies and write them out with links in an unordered list.





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_term_children/#)




```php
<?php
$term_id = 10;
$taxonomy_name = 'products';
$termchildren = get_term_children( $term_id, $taxonomy_name );

echo '<ul>';
foreach ( $termchildren as $child ) {
   	$term = get_term_by( 'id', $child, $taxonomy_name );
   	echo '<li><a href="' . get_term_link( $child, $taxonomy_name ) . '">' . $term->name . '</a></li>';
}
echo '</ul>';
?>
```





This would return something like.





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_term_children/#)




```php
<ul>
<li><a href="link_to_term_page">Term 1</a></li>
<li><a href="link_to_term_page">Term 2</a></li>
</ul>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_term_children%2F%3Freplytocom%3D579%23feedback-editor-579)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_term_children/#comment-content-6104)



Categories and Tags are the two pre-defined Taxonomies. The Taxonomy Name, the second required parameter $taxonomy, is ‘category’ for Categories and ‘post\_tag’ for Tags.



If replacing the deprecated function [get\_category\_children()](https://developer.wordpress.org/reference/functions/get_category_children/) , which returns a String, note that [get\_term\_children()](https://developer.wordpress.org/reference/functions/get_term_children/) returns an array of Category IDs if the second parameter $taxonomy is ‘category’.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_term_children%2F%3Freplytocom%3D6104%23feedback-editor-6104)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_term_children/#comment-content-6491)



If the term exists in the taxonomy, but has no children, the term ID will be returned instead.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_term_children%2F%3Freplytocom%3D6491%23feedback-editor-6491)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_term_children%2F) before being able to contribute a note or feedback.

Notifications