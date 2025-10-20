---
url: https://developer.wordpress.org/reference/functions/wp_update_category
scraped_at: 2025-10-20T03:23:37.116Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_update_category/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_update\_category()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_update\_category()

Search

# wp\_update\_category( array$catarr ): int\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_update_category/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_update_category/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_update_category/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_update_category/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_update_category/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_update_category/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_update_category/#wp--skip-link--target)

Aliases [wp\_insert\_category()](https://developer.wordpress.org/reference/functions/wp_insert_category/) with minimal args.

## [Description](https://developer.wordpress.org/reference/functions/wp_update_category/\#description)

If you want to update only some fields of an existing category, call this function with only the new values set inside $catarr.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_update_category/\#parameters)

`$catarr` arrayrequired

The `'cat_ID'` value is required. All other keys are optional.

## [Return](https://developer.wordpress.org/reference/functions/wp_update_category/\#return)

int\|false The ID number of the new or updated Category on success. Zero or FALSE on failure.

## [Source](https://developer.wordpress.org/reference/functions/wp_update_category/\#source)

`wp-admin/includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_update_category/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_update_category/#)

```php
function wp_update_category( $catarr ) {
	$cat_id = (int) $catarr['cat_ID'];

	if ( isset( $catarr['category_parent'] ) && ( $cat_id === (int) $catarr['category_parent'] ) ) {
		return false;
	}

	// First, get all of the original fields.
	$category = get_term( $cat_id, 'category', ARRAY_A );
	_make_cat_compat( $category );

	// Escape data pulled from DB.
	$category = wp_slash( $category );

	// Merge old and new fields with new fields overwriting old ones.
	$catarr = array_merge( $category, $catarr );

	return wp_insert_category( $catarr );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/taxonomy.php#L188) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/taxonomy.php#L188-L206)

## [Related](https://developer.wordpress.org/reference/functions/wp_update_category/\#related)

| Uses | Description |
| --- | --- |
| [wp\_insert\_category()](https://developer.wordpress.org/reference/functions/wp_insert_category/) `wp-admin/includes/taxonomy.php` | Updates an existing Category or creates a new Category. |
| [\_make\_cat\_compat()](https://developer.wordpress.org/reference/functions/_make_cat_compat/) `wp-includes/category.php` | Updates category structure to old pre-2.3 from new taxonomy structure. |
| [wp\_slash()](https://developer.wordpress.org/reference/functions/wp_slash/) `wp-includes/formatting.php` | Adds slashes to a string or recursively adds slashes to strings within an array. |
| [get\_term()](https://developer.wordpress.org/reference/functions/get_term/) `wp-includes/taxonomy.php` | Gets all term data from database by term ID. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_update_category/#) [Show less](https://developer.wordpress.org/reference/functions/wp_update_category/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_update_category/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_category%2F) before being able to contribute a note or feedback.

Notifications