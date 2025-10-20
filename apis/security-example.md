---
url: https://developer.wordpress.org/apis/security/example
scraped_at: 2025-10-20T04:09:43.450Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/security/example/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Example


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Security](https://developer.wordpress.org/apis/security/)Example

Search

# Example

[↑ Back to top](https://developer.wordpress.org/apis/security/example/#wp--skip-link--target)

Complete example using capability checks, data validation, secure input, secure output and nonces:

``
[Expand code](https://developer.wordpress.org/apis/security/example/#)

[Copy](https://developer.wordpress.org/apis/security/example/#)

```php
/**
 * Generate a Delete link based on the homepage url.
 *
 * @param string $content   Existing content.
 *
 * @return string|null
 */
function wporg_generate_delete_link( $content ) {
	// Run only for single post page.
	if ( is_single() && in_the_loop() && is_main_query() ) {
		// Add query arguments: action, post, nonce
		$url = add_query_arg(
			[\
				'action' => 'wporg_frontend_delete',\
				'post'   => get_the_ID(),\
				'nonce'  => wp_create_nonce( 'wporg_frontend_delete' ),\
			], home_url()
		);

		return $content . ' <a href="' . esc_url( $url ) . '">' . esc_html__( 'Delete Post', 'wporg' ) . '</a>';
	}

	return null;
}

/**
 * Request handler
 */
function wporg_delete_post() {
	if ( isset( $_GET['action'] )
         && isset( $_GET['nonce'] )
         && 'wporg_frontend_delete' === $_GET['action']
         && wp_verify_nonce( $_GET['nonce'], 'wporg_frontend_delete' ) ) {

		// Verify we have a post id.
		$post_id = ( isset( $_GET['post'] ) ) ? ( $_GET['post'] ) : ( null );

		// Verify there is a post with such a number.
		$post = get_post( (int) $post_id );
		if ( empty( $post ) ) {
			return;
		}

		// Delete the post.
		wp_trash_post( $post_id );

		// Redirect to admin page.
		$redirect = admin_url( 'edit.php' );
		wp_safe_redirect( $redirect );

		// We are done.
		die;
	}
}

/**
 * Add delete post ability
 */
add_action('plugins_loaded', 'wporg_add_delete_post_ability');

function wporg_add_delete_post_ability() {
    if ( current_user_can( 'edit_others_posts' ) ) {
        /**
         * Add the delete link to the end of the post content.
         */
        add_filter( 'the_content', 'wporg_generate_delete_link' );

        /**
         * Register our request handler with the init hook.
         */
        add_action( 'init', 'wporg_delete_post' );
    }
}
```

First published

November 20, 2022

Last updated

November 20, 2022

[PreviousCommon VulnerabilitiesPrevious: Common Vulnerabilities](https://developer.wordpress.org/apis/security/common-vulnerabilities/)

[NextSettingsNext: Settings](https://developer.wordpress.org/apis/settings/)

Notifications