---
url: https://developer.wordpress.org/reference/functions/wp_get_comment_status
scraped_at: 2025-10-20T03:13:10.760Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_comment\_status()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_comment\_status()

Search

# wp\_get\_comment\_status( int\|WP\_Comment$comment\_id ): string\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#wp--skip-link--target)

Retrieves the status of a comment by comment ID.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#parameters)

`$comment_id` int\|[WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/)required

Comment ID or [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object

## [Return](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#return)

string\|false Status might be `'trash'`, `'approved'`, `'unapproved'`, `'spam'`. False on failure.

## [Source](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#source)

`wp-includes/comment.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#)

```php
function wp_get_comment_status( $comment_id ) {
	$comment = get_comment( $comment_id );
	if ( ! $comment ) {
		return false;
	}

	$approved = $comment->comment_approved;

	if ( null === $approved ) {
		return false;
	} elseif ( '1' === $approved ) {
		return 'approved';
	} elseif ( '0' === $approved ) {
		return 'unapproved';
	} elseif ( 'spam' === $approved ) {
		return 'spam';
	} elseif ( 'trash' === $approved ) {
		return 'trash';
	} else {
		return false;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/comment.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/comment.php#L1777) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/comment.php#L1777-L1798)

## [Related](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#related)

| Uses | Description |
| --- | --- |
| [get\_comment()](https://developer.wordpress.org/reference/functions/get_comment/) `wp-includes/comment.php` | Retrieves comment data given a comment ID or comment object. |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Comments\_Controller::handle\_status\_param()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/handle_status_param/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Sets the comment\_status of a given comment object when creating or updating a comment. |
| [WP\_Comments\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/handle_row_actions/) `wp-admin/includes/class-wp-comments-list-table.php` | Generates and displays row actions links. |
| [\_wp\_dashboard\_recent\_comments\_row()](https://developer.wordpress.org/reference/functions/_wp_dashboard_recent_comments_row/) `wp-admin/includes/dashboard.php` | Outputs a row for the Recent Comments widget. |
| [wp\_ajax\_delete\_comment()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_comment/) `wp-admin/includes/ajax-actions.php` | Handles deleting a comment via AJAX. |
| [wp\_ajax\_dim\_comment()](https://developer.wordpress.org/reference/functions/wp_ajax_dim_comment/) `wp-admin/includes/ajax-actions.php` | Handles dimming a comment via AJAX. |
| [WP\_Comments\_List\_Table::column\_date()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/column_date/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [WP\_Comments\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/single_row/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [wp\_new\_comment()](https://developer.wordpress.org/reference/functions/wp_new_comment/) `wp-includes/comment.php` | Adds a new comment to the database. |
| [wp\_delete\_comment()](https://developer.wordpress.org/reference/functions/wp_delete_comment/) `wp-includes/comment.php` | Trashes or deletes a comment. |

[Show 4 more](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#changelog)

| Version | Description |
| --- | --- |
| [1.0.0](https://developer.wordpress.org/reference/since/1.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_comment_status/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#comment-content-1496)



**Check whether comment is approved**





`wp-includes/comment.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_comment_status/#)




```php
$status = wp_get_comment_status( $comment_id );
if ( 'approved' === $status ) {
     // Show the comment.
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_comment_status%2F%3Freplytocom%3D1496%23feedback-editor-1496)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_comment_status%2F) before being able to contribute a note or feedback.

Notifications