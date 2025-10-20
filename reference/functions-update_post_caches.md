---
url: https://developer.wordpress.org/reference/functions/update_post_caches
scraped_at: 2025-10-20T03:16:45.242Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/update_post_caches/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

update\_post\_caches()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)update\_post\_caches()

Search

# update\_post\_caches( WP\_Post\[\]$posts, string$post\_type = 'post', bool$update\_term\_cache = true, bool$update\_meta\_cache = true )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/update_post_caches/#parameters)
- [More Information](https://developer.wordpress.org/reference/functions/update_post_caches/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/update_post_caches/#source)
- [Related](https://developer.wordpress.org/reference/functions/update_post_caches/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/update_post_caches/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/update_post_caches/#wp--skip-link--target)

Updates post, term, and metadata caches for a list of post objects.

## [Parameters](https://developer.wordpress.org/reference/functions/update_post_caches/\#parameters)

`$posts` [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)\[\]required

Array of post objects (passed by reference).

`$post_type` stringoptional

Post type. Default `'post'`.

Default: `'post'`

`$update_term_cache` booloptional

Whether to update the term cache.

Default: `true`

`$update_meta_cache` booloptional

Whether to update the meta cache.

Default: `true`

## [More Information](https://developer.wordpress.org/reference/functions/update_post_caches/\#more-information)

`update_post_caches( $posts, $post_type, $update_term_cache, $update_meta_cache );`

## [Source](https://developer.wordpress.org/reference/functions/update_post_caches/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/update_post_caches/#)

[Copy](https://developer.wordpress.org/reference/functions/update_post_caches/#)

```php
function update_post_caches( &$posts, $post_type = 'post', $update_term_cache = true, $update_meta_cache = true ) {
	// No point in doing all this work if we didn't match any posts.
	if ( ! $posts ) {
		return;
	}

	update_post_cache( $posts );

	$post_ids = array();
	foreach ( $posts as $post ) {
		$post_ids[] = $post->ID;
	}

	if ( ! $post_type ) {
		$post_type = 'any';
	}

	if ( $update_term_cache ) {
		if ( is_array( $post_type ) ) {
			$ptypes = $post_type;
		} elseif ( 'any' === $post_type ) {
			$ptypes = array();
			// Just use the post_types in the supplied posts.
			foreach ( $posts as $post ) {
				$ptypes[] = $post->post_type;
			}
			$ptypes = array_unique( $ptypes );
		} else {
			$ptypes = array( $post_type );
		}

		if ( ! empty( $ptypes ) ) {
			update_object_term_cache( $post_ids, $ptypes );
		}
	}

	if ( $update_meta_cache ) {
		update_postmeta_cache( $post_ids );
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L7688) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L7688-L7727)

## [Related](https://developer.wordpress.org/reference/functions/update_post_caches/\#related)

| Uses | Description |
| --- | --- |
| [update\_object\_term\_cache()](https://developer.wordpress.org/reference/functions/update_object_term_cache/) `wp-includes/taxonomy.php` | Updates the cache for the given term object ID(s). |
| [update\_postmeta\_cache()](https://developer.wordpress.org/reference/functions/update_postmeta_cache/) `wp-includes/post.php` | Updates metadata cache for a list of post IDs. |
| [update\_post\_cache()](https://developer.wordpress.org/reference/functions/update_post_cache/) `wp-includes/post.php` | Updates posts in cache. |

| Used by | Description |
| --- | --- |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |

## [Changelog](https://developer.wordpress.org/reference/functions/update_post_caches/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fupdate_post_caches%2F) before being able to contribute a note or feedback.

Notifications