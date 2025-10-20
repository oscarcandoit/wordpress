---
url: https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments
scraped_at: 2025-10-20T03:16:41.860Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_ajax\_query\_attachments()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_ajax\_query\_attachments()

Search

# wp\_ajax\_query\_attachments()

## In this article

Table of Contents

- [Source](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#wp--skip-link--target)

Handles querying attachments via AJAX.

## [Source](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/\#source)

`wp-admin/includes/ajax-actions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#)

```php
function wp_ajax_query_attachments() {
	if ( ! current_user_can( 'upload_files' ) ) {
		wp_send_json_error();
	}

	$query = isset( $_REQUEST['query'] ) ? (array) $_REQUEST['query'] : array();
	$keys  = array(
		's',
		'order',
		'orderby',
		'posts_per_page',
		'paged',
		'post_mime_type',
		'post_parent',
		'author',
		'post__in',
		'post__not_in',
		'year',
		'monthnum',
	);

	foreach ( get_taxonomies_for_attachments( 'objects' ) as $t ) {
		if ( $t->query_var && isset( $query[ $t->query_var ] ) ) {
			$keys[] = $t->query_var;
		}
	}

	$query              = array_intersect_key( $query, array_flip( $keys ) );
	$query['post_type'] = 'attachment';

	if (
		MEDIA_TRASH &&
		! empty( $_REQUEST['query']['post_status'] ) &&
		'trash' === $_REQUEST['query']['post_status']
	) {
		$query['post_status'] = 'trash';
	} else {
		$query['post_status'] = 'inherit';
	}

	if ( current_user_can( get_post_type_object( 'attachment' )->cap->read_private_posts ) ) {
		$query['post_status'] .= ',private';
	}

	// Filter query clauses to include filenames.
	if ( isset( $query['s'] ) ) {
		add_filter( 'wp_allow_query_attachment_by_filename', '__return_true' );
	}

	/**
	 * Filters the arguments passed to WP_Query during an Ajax
	 * call for querying attachments.
	 *
	 * @since 3.7.0
	 *
	 * @see WP_Query::parse_query()
	 *
	 * @param array $query An array of query variables.
	 */
	$query             = apply_filters( 'ajax_query_attachments_args', $query );
	$attachments_query = new WP_Query( $query );
	update_post_parent_caches( $attachments_query->posts );

	$posts       = array_map( 'wp_prepare_attachment_for_js', $attachments_query->posts );
	$posts       = array_filter( $posts );
	$total_posts = $attachments_query->found_posts;

	if ( $total_posts < 1 ) {
		// Out-of-bounds, run the query again without LIMIT for total count.
		unset( $query['paged'] );

		$count_query = new WP_Query();
		$count_query->query( $query );
		$total_posts = $count_query->found_posts;
	}

	$posts_per_page = (int) $attachments_query->get( 'posts_per_page' );

	$max_pages = $posts_per_page ? (int) ceil( $total_posts / $posts_per_page ) : 0;

	header( 'X-WP-Total: ' . (int) $total_posts );
	header( 'X-WP-TotalPages: ' . $max_pages );

	wp_send_json_success( $posts );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/ajax-actions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/ajax-actions.php#L3018) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/ajax-actions.php#L3018-L3102)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/\#hooks)

[apply\_filters( ‘ajax\_query\_attachments\_args’, array$query )](https://developer.wordpress.org/reference/hooks/ajax_query_attachments_args/)

Filters the arguments passed to [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) during an Ajax call for querying attachments.

## [Related](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/\#related)

| Uses | Description |
| --- | --- |
| [update\_post\_parent\_caches()](https://developer.wordpress.org/reference/functions/update_post_parent_caches/) `wp-includes/post.php` | Updates parent post caches for a list of post objects. |
| [WP\_Query::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_query/__construct/) `wp-includes/class-wp-query.php` | Constructor. |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [wp\_send\_json\_error()](https://developer.wordpress.org/reference/functions/wp_send_json_error/) `wp-includes/functions.php` | Sends a JSON response back to an Ajax request, indicating failure. |
| [wp\_send\_json\_success()](https://developer.wordpress.org/reference/functions/wp_send_json_success/) `wp-includes/functions.php` | Sends a JSON response back to an Ajax request, indicating success. |
| [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) `wp-includes/plugin.php` | Adds a callback function to a filter hook. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post\_type\_object()](https://developer.wordpress.org/reference/functions/get_post_type_object/) `wp-includes/post.php` | Retrieves a post type object by name. |

[Show 6 more](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#) [Show less](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_ajax_query_attachments/\#changelog)

| Version | Description |
| --- | --- |
| [3.5.0](https://developer.wordpress.org/reference/since/3.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_ajax_query_attachments%2F) before being able to contribute a note or feedback.

Notifications