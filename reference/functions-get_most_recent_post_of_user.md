---
url: https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user
scraped_at: 2025-10-20T03:24:30.732Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_most\_recent\_post\_of\_user()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_most\_recent\_post\_of\_user()

Search

# get\_most\_recent\_post\_of\_user( int$user\_id ): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#wp--skip-link--target)

Gets a user’s most recent post.

## [Description](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#description)

Walks through each of a user’s blogs to find the post with the most recent post\_date\_gmt.

## [Parameters](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#parameters)

`$user_id` intrequired

User ID.

## [Return](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#return)

array Contains the blog\_id, post\_id, post\_date\_gmt, and post\_gmt\_ts.

## [Source](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#source)

`wp-includes/ms-functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#)

[Copy](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#)

```php
function get_most_recent_post_of_user( $user_id ) {
	global $wpdb;

	$user_blogs       = get_blogs_of_user( (int) $user_id );
	$most_recent_post = array();

	/*
	 * Walk through each blog and get the most recent post
	 * published by $user_id.
	 */
	foreach ( (array) $user_blogs as $blog ) {
		$prefix      = $wpdb->get_blog_prefix( $blog->userblog_id );
		$recent_post = $wpdb->get_row( $wpdb->prepare( "SELECT ID, post_date_gmt FROM {$prefix}posts WHERE post_author = %d AND post_type = 'post' AND post_status = 'publish' ORDER BY post_date_gmt DESC LIMIT 1", $user_id ), ARRAY_A );

		// Make sure we found a post.
		if ( isset( $recent_post['ID'] ) ) {
			$post_gmt_ts = strtotime( $recent_post['post_date_gmt'] );

			/*
			 * If this is the first post checked
			 * or if this post is newer than the current recent post,
			 * make it the new most recent post.
			 */
			if ( ! isset( $most_recent_post['post_gmt_ts'] ) || ( $post_gmt_ts > $most_recent_post['post_gmt_ts'] ) ) {
				$most_recent_post = array(
					'blog_id'       => $blog->userblog_id,
					'post_id'       => $recent_post['ID'],
					'post_date_gmt' => $recent_post['post_date_gmt'],
					'post_gmt_ts'   => $post_gmt_ts,
				);
			}
		}
	}

	return $most_recent_post;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/ms-functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/ms-functions.php#L1992) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/ms-functions.php#L1992-L2027)

## [Related](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#related)

| Uses | Description |
| --- | --- |
| [get\_blogs\_of\_user()](https://developer.wordpress.org/reference/functions/get_blogs_of_user/) `wp-includes/user.php` | Gets the sites a user belongs to. |
| [wpdb::get\_row()](https://developer.wordpress.org/reference/classes/wpdb/get_row/) `wp-includes/class-wpdb.php` | Retrieves one row from the database. |
| [wpdb::get\_blog\_prefix()](https://developer.wordpress.org/reference/classes/wpdb/get_blog_prefix/) `wp-includes/class-wpdb.php` | Gets blog prefix. |
| [wpdb::prepare()](https://developer.wordpress.org/reference/classes/wpdb/prepare/) `wp-includes/class-wpdb.php` | Prepares a SQL query for safe execution. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#) [Show less](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_most_recent_post_of_user/\#changelog)

| Version | Description |
| --- | --- |
| [MU (3.0.0)](https://developer.wordpress.org/reference/since/mu.3.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_most_recent_post_of_user%2F) before being able to contribute a note or feedback.

Notifications