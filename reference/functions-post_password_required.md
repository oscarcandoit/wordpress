---
url: https://developer.wordpress.org/reference/functions/post_password_required
scraped_at: 2025-10-20T03:22:04.102Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/post_password_required/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

post\_password\_required()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)post\_password\_required()

Search

# post\_password\_required( int\|WP\_Post\|null$post = null ): bool

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/post_password_required/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/post_password_required/#return)
- [Source](https://developer.wordpress.org/reference/functions/post_password_required/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/post_password_required/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/post_password_required/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/post_password_required/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/post_password_required/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/post_password_required/#wp--skip-link--target)

Determines whether the post requires password and whether a correct password has been provided.

## [Parameters](https://developer.wordpress.org/reference/functions/post_password_required/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)\|nulloptional

An optional post. Global $post used if not provided.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/post_password_required/\#return)

bool false if a password is not required or the correct password cookie is present, true otherwise.

## [Source](https://developer.wordpress.org/reference/functions/post_password_required/\#source)

`wp-includes/post-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/post_password_required/#)

[Copy](https://developer.wordpress.org/reference/functions/post_password_required/#)

```php
function post_password_required( $post = null ) {
	$post = get_post( $post );

	if ( empty( $post->post_password ) ) {
		/** This filter is documented in wp-includes/post-template.php */
		return apply_filters( 'post_password_required', false, $post );
	}

	if ( ! isset( $_COOKIE[ 'wp-postpass_' . COOKIEHASH ] ) ) {
		/** This filter is documented in wp-includes/post-template.php */
		return apply_filters( 'post_password_required', true, $post );
	}

	require_once ABSPATH . WPINC . '/class-phpass.php';
	$hasher = new PasswordHash( 8, true );

	$hash = wp_unslash( $_COOKIE[ 'wp-postpass_' . COOKIEHASH ] );
	if ( ! str_starts_with( $hash, '$P$B' ) ) {
		$required = true;
	} else {
		$required = ! $hasher->CheckPassword( $post->post_password, $hash );
	}

	/**
	 * Filters whether a post requires the user to supply a password.
	 *
	 * @since 4.7.0
	 *
	 * @param bool    $required Whether the user needs to supply a password. True if password has not been
	 *                          provided or is incorrect, false if password has been supplied or is not required.
	 * @param WP_Post $post     Post object.
	 */
	return apply_filters( 'post_password_required', $required, $post );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post-template.php#L879) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post-template.php#L879-L912)

## [Hooks](https://developer.wordpress.org/reference/functions/post_password_required/\#hooks)

[apply\_filters( ‘post\_password\_required’, bool$required, WP\_Post$post )](https://developer.wordpress.org/reference/hooks/post_password_required/)

Filters whether a post requires the user to supply a password.

## [Related](https://developer.wordpress.org/reference/functions/post_password_required/\#related)

| Uses | Description |
| --- | --- |
| [wp\_unslash()](https://developer.wordpress.org/reference/functions/wp_unslash/) `wp-includes/formatting.php` | Removes slashes from a string or recursively removes slashes from strings within an array. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

[Show 1 more](https://developer.wordpress.org/reference/functions/post_password_required/#) [Show less](https://developer.wordpress.org/reference/functions/post_password_required/#)

| Used by | Description |
| --- | --- |
| [\_block\_bindings\_post\_meta\_get\_value()](https://developer.wordpress.org/reference/functions/_block_bindings_post_meta_get_value/) `wp-includes/block-bindings/post-meta.php` | Gets value for Post Meta source. |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post output for response. |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_database()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_database/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post for create or update. |
| [WP\_REST\_Comments\_Controller::check\_read\_post\_permission()](https://developer.wordpress.org/reference/classes/wp_rest_comments_controller/check_read_post_permission/) `wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php` | Checks if the post can be read. |
| [wp\_handle\_comment\_submission()](https://developer.wordpress.org/reference/functions/wp_handle_comment_submission/) `wp-includes/comment.php` | Handles the submission of a comment, usually posted to wp-comments-post.php via a comment form. |
| [WP\_Posts\_List\_Table::column\_title()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/column_title/) `wp-admin/includes/class-wp-posts-list-table.php` | Handles the title column output. |
| [WP\_List\_Table::comments\_bubble()](https://developer.wordpress.org/reference/classes/wp_list_table/comments_bubble/) `wp-admin/includes/class-wp-list-table.php` | Displays a comment count bubble. |
| [wp\_dashboard\_recent\_comments()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_comments/) `wp-admin/includes/dashboard.php` | Show Comments section. |
| [WP\_Comments\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_comments_list_table/single_row/) `wp-admin/includes/class-wp-comments-list-table.php` |  |
| [rss\_enclosure()](https://developer.wordpress.org/reference/functions/rss_enclosure/) `wp-includes/feed.php` | Displays the rss enclosure for the current post. |
| [atom\_enclosure()](https://developer.wordpress.org/reference/functions/atom_enclosure/) `wp-includes/feed.php` | Displays the atom enclosure for the current post. |
| [get\_the\_content()](https://developer.wordpress.org/reference/functions/get_the_content/) `wp-includes/post-template.php` | Retrieves the post content. |
| [get\_the\_excerpt()](https://developer.wordpress.org/reference/functions/get_the_excerpt/) `wp-includes/post-template.php` | Retrieves the post excerpt. |
| [get\_post\_class()](https://developer.wordpress.org/reference/functions/get_post_class/) `wp-includes/post-template.php` | Retrieves an array of the class names for the post container element. |
| [wp\_xmlrpc\_server::wp\_newComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new comment. |
| [comments\_popup\_link()](https://developer.wordpress.org/reference/functions/comments_popup_link/) `wp-includes/comment-template.php` | Displays the link to the comments for the current post ID. |
| [get\_comment\_excerpt()](https://developer.wordpress.org/reference/functions/get_comment_excerpt/) `wp-includes/comment-template.php` | Retrieves the excerpt of the given comment. |

[Show 12 more](https://developer.wordpress.org/reference/functions/post_password_required/#) [Show less](https://developer.wordpress.org/reference/functions/post_password_required/#)

## [Changelog](https://developer.wordpress.org/reference/functions/post_password_required/\#changelog)

| Version | Description |
| --- | --- |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/post_password_required/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/post_password_required/#comment-content-5053)



I looked long and hard in trying to find a working example of his function, (couldn’t!)


The code below works, and it works well.



Note 1: Without getting, (and using the post->ID), then the post\_password\_required function doesn’t work.


Note 2: Something else you have to watch is cookies being set once the password has been used once, makes debugging a nightmare, (tip), use an Incognito Window when testing out your code.


Note 3: I have broken with tradition here, and opened (the-Loop) with wide braces instead of the endwhile: condition, I personally find it easier to follow.



Hope it helps.





`wp-includes/post-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/post_password_required/#)

[Copy](https://developer.wordpress.org/reference/functions/post_password_required/#)




```php
<?php

$pass_masterPost = get_post();
if ( post_password_required(  $pass_masterPost->ID ) )
{
       echo get_the_password_form();
       echo '<p>THIS POST IS PASSWORD PROTECTED: PLEASE ENTER IT!</p>';
}
else
{
       if ( have_posts() )
       {
           while ( have_posts() )
           {
               the_post();
               the_content();
   			echo '<hr>';
            }
       }
       else
       {
           echo '<p>Nothing Found!</p>';
       }
}
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fpost_password_required%2F%3Freplytocom%3D5053%23feedback-editor-5053)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fpost_password_required%2F) before being able to contribute a note or feedback.

Notifications