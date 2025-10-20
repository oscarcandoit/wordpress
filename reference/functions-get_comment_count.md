---
url: https://developer.wordpress.org/reference/functions/get_comment_count
scraped_at: 2025-10-20T03:14:31.400Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_comment_count/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_comment\_count()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_comment\_count()

Search

# get\_comment\_count( int$post\_id ): int\[\]

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_comment_count/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_comment_count/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_comment_count/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_comment_count/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_comment_count/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_comment_count/#wp--skip-link--target)

Retrieves the total comment counts for the whole site or a single post.

## [Parameters](https://developer.wordpress.org/reference/functions/get_comment_count/\#parameters)

`$post_id` intoptional

Restrict the comment counts to the given post. Default 0, which indicates that comment counts for the whole site will be retrieved.

## [Return](https://developer.wordpress.org/reference/functions/get_comment_count/\#return)

int\[\] The number of comments keyed by their status.

- `approved` int
The number of approved comments.

- `awaiting_moderation` int
The number of comments awaiting moderation (a.k.a. pending).

- `spam` int
The number of spam comments.

- `trash` int
The number of trashed comments.

- `post-trashed` int
The number of comments for posts that are in the trash.

- `total_comments` int
The total number of non-trashed comments, including spam.

- `all` int
The total number of pending or approved comments.


## [Source](https://developer.wordpress.org/reference/functions/get_comment_count/\#source)

`wp-includes/comment.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_comment_count/#)

[Copy](https://developer.wordpress.org/reference/functions/get_comment_count/#)

```php
function get_comment_count( $post_id = 0 ) {
	$post_id = (int) $post_id;

	$comment_count = array(
		'approved'            => 0,
		'awaiting_moderation' => 0,
		'spam'                => 0,
		'trash'               => 0,
		'post-trashed'        => 0,
		'total_comments'      => 0,
		'all'                 => 0,
	);

	$args = array(
		'count'                     => true,
		'update_comment_meta_cache' => false,
		'orderby'                   => 'none',
	);
	if ( $post_id > 0 ) {
		$args['post_id'] = $post_id;
	}
	$mapping       = array(
		'approved'            => 'approve',
		'awaiting_moderation' => 'hold',
		'spam'                => 'spam',
		'trash'               => 'trash',
		'post-trashed'        => 'post-trashed',
	);
	$comment_count = array();
	foreach ( $mapping as $key => $value ) {
		$comment_count[ $key ] = get_comments( array_merge( $args, array( 'status' => $value ) ) );
	}

	$comment_count['all']            = $comment_count['approved'] + $comment_count['awaiting_moderation'];
	$comment_count['total_comments'] = $comment_count['all'] + $comment_count['spam'];

	return array_map( 'intval', $comment_count );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/comment.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/comment.php#L403) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/comment.php#L403-L440)

## [Related](https://developer.wordpress.org/reference/functions/get_comment_count/\#related)

| Uses | Description |
| --- | --- |
| [get\_comments()](https://developer.wordpress.org/reference/functions/get_comments/) `wp-includes/comment.php` | Retrieves a list of comments. |

| Used by | Description |
| --- | --- |
| [wp\_count\_comments()](https://developer.wordpress.org/reference/functions/wp_count_comments/) `wp-includes/comment.php` | Retrieves the total comment counts for the whole site or a single post. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_comment_count/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_comment_count%2F) before being able to contribute a note or feedback.

Notifications