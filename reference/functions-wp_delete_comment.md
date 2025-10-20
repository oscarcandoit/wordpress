---
url: https://developer.wordpress.org/reference/functions/wp_delete_comment
scraped_at: 2025-10-20T03:21:46.516Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_delete_comment/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_delete\_comment()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_delete\_comment()

Search

# wp\_delete\_comment( int\|WP\_Comment$comment\_id, bool$force\_delete = false ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_delete_comment/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_delete_comment/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_delete_comment/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_delete_comment/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_delete_comment/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_delete_comment/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_delete_comment/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_delete_comment/#wp--skip-link--target)

Trashes or deletes a comment.

## [Description](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#description)

The comment is moved to Trash instead of permanently deleted unless Trash is disabled, item is already in the Trash, or $force\_delete is true.

The post comment count will be updated if the comment was approved and has a post ID available.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#parameters)

`$comment_id` int\|[WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/)required

Comment ID or [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object.

`$force_delete` booloptional

Whether to bypass Trash and force deletion.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#return)

bool True on success, false on failure.

## [Source](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#source)

`wp-includes/comment.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_delete_comment/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_delete_comment/#)

```php
function wp_delete_comment( $comment_id, $force_delete = false ) {
	global $wpdb;

	$comment = get_comment( $comment_id );
	if ( ! $comment ) {
		return false;
	}

	if ( ! $force_delete && EMPTY_TRASH_DAYS && ! in_array( wp_get_comment_status( $comment ), array( 'trash', 'spam' ), true ) ) {
		return wp_trash_comment( $comment_id );
	}

	/**
	 * Fires immediately before a comment is deleted from the database.
	 *
	 * @since 1.2.0
	 * @since 4.9.0 Added the `$comment` parameter.
	 *
	 * @param string     $comment_id The comment ID as a numeric string.
	 * @param WP_Comment $comment    The comment to be deleted.
	 */
	do_action( 'delete_comment', $comment->comment_ID, $comment );

	// Move children up a level.
	$children = $wpdb->get_col( $wpdb->prepare( "SELECT comment_ID FROM $wpdb->comments WHERE comment_parent = %d", $comment->comment_ID ) );
	if ( ! empty( $children ) ) {
		$wpdb->update( $wpdb->comments, array( 'comment_parent' => $comment->comment_parent ), array( 'comment_parent' => $comment->comment_ID ) );
		clean_comment_cache( $children );
	}

	// Delete metadata.
	$meta_ids = $wpdb->get_col( $wpdb->prepare( "SELECT meta_id FROM $wpdb->commentmeta WHERE comment_id = %d", $comment->comment_ID ) );
	foreach ( $meta_ids as $mid ) {
		delete_metadata_by_mid( 'comment', $mid );
	}

	if ( ! $wpdb->delete( $wpdb->comments, array( 'comment_ID' => $comment->comment_ID ) ) ) {
		return false;
	}

	/**
	 * Fires immediately after a comment is deleted from the database.
	 *
	 * @since 2.9.0
	 * @since 4.9.0 Added the `$comment` parameter.
	 *
	 * @param string     $comment_id The comment ID as a numeric string.
	 * @param WP_Comment $comment    The deleted comment.
	 */
	do_action( 'deleted_comment', $comment->comment_ID, $comment );

	$post_id = $comment->comment_post_ID;
	if ( $post_id && '1' === $comment->comment_approved ) {
		wp_update_comment_count( $post_id );
	}

	clean_comment_cache( $comment->comment_ID );

	/** This action is documented in wp-includes/comment.php */
	do_action( 'wp_set_comment_status', $comment->comment_ID, 'delete' );

	wp_transition_comment_status( 'delete', $comment->comment_approved, $comment );

	return true;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/comment.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/comment.php#L1499) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/comment.php#L1499-L1563)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#hooks)

[do\_action( ‘deleted\_comment’, string$comment\_id, WP\_Comment$comment )](https://developer.wordpress.org/reference/hooks/deleted_comment/)

Fires immediately after a comment is deleted from the database.

[do\_action( ‘delete\_comment’, string$comment\_id, WP\_Comment$comment )](https://developer.wordpress.org/reference/hooks/delete_comment/)

Fires immediately before a comment is deleted from the database.

[do\_action( ‘wp\_set\_comment\_status’, string$comment\_id, string$comment\_status )](https://developer.wordpress.org/reference/hooks/wp_set_comment_status/)

Fires immediately after transitioning a comment’s status from one to another in the database and removing the comment from the object cache, but prior to all status transition hooks.

## [Related](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#related)

| Uses | Description |
| --- | --- |
| [wpdb::get\_col()](https://developer.wordpress.org/reference/classes/wpdb/get_col/) `wp-includes/class-wpdb.php` | Retrieves one column from the database. |
| [wpdb::update()](https://developer.wordpress.org/reference/classes/wpdb/update/) `wp-includes/class-wpdb.php` | Updates a row in the table. |
| [wpdb::delete()](https://developer.wordpress.org/reference/classes/wpdb/delete/) `wp-includes/class-wpdb.php` | Deletes a row in the table. |
| [clean\_comment\_cache()](https://developer.wordpress.org/reference/functions/clean_comment_cache/) `wp-includes/comment.php` | Removes a comment from the object cache. |
| [wp\_update\_comment\_count()](https://developer.wordpress.org/reference/functions/wp_update_comment_count/) `wp-includes/comment.php` | Updates the comment count for post(s). |
| [wp\_get\_comment\_status()](https://developer.wordpress.org/reference/functions/wp_get_comment_status/) `wp-includes/comment.php` | Retrieves the status of a comment by comment ID. |
| [wp\_transition\_comment\_status()](https://developer.wordpress.org/reference/functions/wp_transition_comment_status/) `wp-includes/comment.php` | Calls hooks for when a comment status transition occurs. |
| [wp\_trash\_comment()](https://developer.wordpress.org/reference/functions/wp_trash_comment/) `wp-includes/comment.php` | Moves a comment to the Trash |
| [delete\_metadata\_by\_mid()](https://developer.wordpress.org/reference/functions/delete_metadata_by_mid/) `wp-includes/meta.php` | Deletes metadata by meta ID. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [wpdb::prepare()](https://developer.wordpress.org/reference/classes/wpdb/prepare/) `wp-includes/class-wpdb.php` | Prepares a SQL query for safe execution. |
| [get\_comment()](https://developer.wordpress.org/reference/functions/get_comment/) `wp-includes/comment.php` | Retrieves comment data given a comment ID or comment object. |

[Show 7 more](https://developer.wordpress.org/reference/functions/wp_delete_comment/#) [Show less](https://developer.wordpress.org/reference/functions/wp_delete_comment/#)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Comments\_Controller::delete\_item()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/delete_item/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Deletes a comment. |
| [wp\_ajax\_delete\_comment()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_comment/) `wp-admin/includes/ajax-actions.php` | Handles deleting a comment via AJAX. |
| [wp\_scheduled\_delete()](https://developer.wordpress.org/reference/functions/wp_scheduled_delete/) `wp-includes/functions.php` | Permanently deletes comments or posts of any type that have held a status of ‘trash’ for the number of days defined in EMPTY\_TRASH\_DAYS. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [wp\_delete\_post()](https://developer.wordpress.org/reference/functions/wp_delete_post/) `wp-includes/post.php` | Trashes or deletes a post or page. |
| [wp\_xmlrpc\_server::wp\_deleteComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_deletecomment/) `wp-includes/class-wp-xmlrpc-server.php` | Deletes a comment. |
| [wp\_trash\_comment()](https://developer.wordpress.org/reference/functions/wp_trash_comment/) `wp-includes/comment.php` | Moves a comment to the Trash |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_delete_comment/#) [Show less](https://developer.wordpress.org/reference/functions/wp_delete_comment/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_delete_comment/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_delete_comment%2F) before being able to contribute a note or feedback.

Notifications