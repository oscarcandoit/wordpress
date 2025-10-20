---
url: https://developer.wordpress.org/reference/functions/wp_ajax_find_posts
scraped_at: 2025-10-20T03:18:39.754Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_ajax\_find\_posts()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_ajax\_find\_posts()

Search

# wp\_ajax\_find\_posts()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#description)
  - [See also](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#see-also)
- [Source](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#wp--skip-link--target)

Handles querying posts for the Find Posts modal via AJAX.

## [Description](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/\#description)

### [See also](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/\#see-also)

- [window.findPosts](https://developer.wordpress.org/reference/functions/window-findposts)

## [Source](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/\#source)

`wp-admin/includes/ajax-actions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#)

```php
function wp_ajax_find_posts() {
	check_ajax_referer( 'find-posts' );

	$post_types = get_post_types( array( 'public' => true ), 'objects' );
	unset( $post_types['attachment'] );

	$args = array(
		'post_type'      => array_keys( $post_types ),
		'post_status'    => 'any',
		'posts_per_page' => 50,
	);

	$search = wp_unslash( $_POST['ps'] );

	if ( '' !== $search ) {
		$args['s'] = $search;
	}

	$posts = get_posts( $args );

	if ( ! $posts ) {
		wp_send_json_error( __( 'No items found.' ) );
	}

	$html = '<table class="widefat"><thead><tr><th class="found-radio"><br /></th><th>' . __( 'Title' ) . '</th><th class="no-break">' . __( 'Type' ) . '</th><th class="no-break">' . __( 'Date' ) . '</th><th class="no-break">' . __( 'Status' ) . '</th></tr></thead><tbody>';
	$alt  = '';
	foreach ( $posts as $post ) {
		$title = trim( $post->post_title ) ? $post->post_title : __( '(no title)' );
		$alt   = ( 'alternate' === $alt ) ? '' : 'alternate';

		switch ( $post->post_status ) {
			case 'publish':
			case 'private':
				$stat = __( 'Published' );
				break;
			case 'future':
				$stat = __( 'Scheduled' );
				break;
			case 'pending':
				$stat = __( 'Pending Review' );
				break;
			case 'draft':
				$stat = __( 'Draft' );
				break;
		}

		if ( '0000-00-00 00:00:00' === $post->post_date ) {
			$time = '';
		} else {
			/* translators: Date format in table columns, see https://www.php.net/manual/datetime.format.php */
			$time = mysql2date( __( 'Y/m/d' ), $post->post_date );
		}

		$html .= '<tr class="' . trim( 'found-posts ' . $alt ) . '"><td class="found-radio"><input type="radio" id="found-' . $post->ID . '" name="found_post_id" value="' . esc_attr( $post->ID ) . '"></td>';
		$html .= '<td><label for="found-' . $post->ID . '">' . esc_html( $title ) . '</label></td><td class="no-break">' . esc_html( $post_types[ $post->post_type ]->labels->singular_name ) . '</td><td class="no-break">' . esc_html( $time ) . '</td><td class="no-break">' . esc_html( $stat ) . ' </td></tr>' . "\n\n";
	}

	$html .= '</tbody></table>';

	wp_send_json_success( $html );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/ajax-actions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/ajax-actions.php#L2237) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/ajax-actions.php#L2237-L2297)

## [Related](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/\#related)

| Uses | Description |
| --- | --- |
| [mysql2date()](https://developer.wordpress.org/reference/functions/mysql2date/) `wp-includes/functions.php` | Converts given MySQL date string into a different format. |
| [get\_posts()](https://developer.wordpress.org/reference/functions/get_posts/) `wp-includes/post.php` | Retrieves an array of the latest posts, or posts matching the given criteria. |
| [wp\_unslash()](https://developer.wordpress.org/reference/functions/wp_unslash/) `wp-includes/formatting.php` | Removes slashes from a string or recursively removes slashes from strings within an array. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [esc\_html()](https://developer.wordpress.org/reference/functions/esc_html/) `wp-includes/formatting.php` | Escaping for HTML blocks. |
| [check\_ajax\_referer()](https://developer.wordpress.org/reference/functions/check_ajax_referer/) `wp-includes/pluggable.php` | Verifies the Ajax request to prevent processing requests external of the blog. |
| [wp\_send\_json\_error()](https://developer.wordpress.org/reference/functions/wp_send_json_error/) `wp-includes/functions.php` | Sends a JSON response back to an Ajax request, indicating failure. |
| [wp\_send\_json\_success()](https://developer.wordpress.org/reference/functions/wp_send_json_success/) `wp-includes/functions.php` | Sends a JSON response back to an Ajax request, indicating success. |
| [get\_post\_types()](https://developer.wordpress.org/reference/functions/get_post_types/) `wp-includes/post.php` | Gets a list of all registered post type objects. |

[Show 7 more](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#) [Show less](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_ajax_find_posts%2F) before being able to contribute a note or feedback.

Notifications