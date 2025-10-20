---
url: https://developer.wordpress.org/reference/functions/single_post_title
scraped_at: 2025-10-20T03:16:09.623Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/single_post_title/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

single\_post\_title()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)single\_post\_title()

Search

# single\_post\_title( string$prefix = '', bool$display = true ): string\|void

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/single_post_title/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/single_post_title/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/single_post_title/#return)
- [Source](https://developer.wordpress.org/reference/functions/single_post_title/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/single_post_title/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/single_post_title/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/single_post_title/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/single_post_title/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/single_post_title/#wp--skip-link--target)

Displays or retrieves page title for post.

## [Description](https://developer.wordpress.org/reference/functions/single_post_title/\#description)

This is optimized for single.php template file for displaying the post title.

It does not support placing the separator after the title, but by leaving the prefix parameter empty, you can set the title separator manually. The prefix does not automatically place a space between the prefix, so if there should be a space, the parameter value will need to have it at the end.

## [Parameters](https://developer.wordpress.org/reference/functions/single_post_title/\#parameters)

`$prefix` stringoptional

What to display before the title.

Default: `''`

`$display` booloptional

Whether to display or retrieve title.

Default: `true`

## [Return](https://developer.wordpress.org/reference/functions/single_post_title/\#return)

string\|void Title when retrieving.

## [Source](https://developer.wordpress.org/reference/functions/single_post_title/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/single_post_title/#)

[Copy](https://developer.wordpress.org/reference/functions/single_post_title/#)

```php
function single_post_title( $prefix = '', $display = true ) {
	$_post = get_queried_object();

	if ( ! isset( $_post->post_title ) ) {
		return;
	}

	/**
	 * Filters the page title for a single post.
	 *
	 * @since 0.71
	 *
	 * @param string  $_post_title The single post page title.
	 * @param WP_Post $_post       The current post.
	 */
	$title = apply_filters( 'single_post_title', $_post->post_title, $_post );
	if ( $display ) {
		echo $prefix . $title;
	} else {
		return $prefix . $title;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L1484) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L1484-L1505)

## [Hooks](https://developer.wordpress.org/reference/functions/single_post_title/\#hooks)

[apply\_filters( ‘single\_post\_title’, string$\_post\_title, WP\_Post$\_post )](https://developer.wordpress.org/reference/hooks/single_post_title/)

Filters the page title for a single post.

## [Related](https://developer.wordpress.org/reference/functions/single_post_title/\#related)

| Uses | Description |
| --- | --- |
| [get\_queried\_object()](https://developer.wordpress.org/reference/functions/get_queried_object/) `wp-includes/query.php` | Retrieves the currently queried object. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [wp\_get\_document\_title()](https://developer.wordpress.org/reference/functions/wp_get_document_title/) `wp-includes/general-template.php` | Returns document title for the current page. |
| [wp\_title()](https://developer.wordpress.org/reference/functions/wp_title/) `wp-includes/general-template.php` | Displays or retrieves page title for all areas of blog. |

## [Changelog](https://developer.wordpress.org/reference/functions/single_post_title/\#changelog)

| Version | Description |
| --- | --- |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/single_post_title/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/single_post_title/#comment-content-555)



**Example**





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/single_post_title/#)




```php
<h2><?php single_post_title( 'Current post: ' ); ?></h2>
```





Result:



`Current post: Single Post Title`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsingle_post_title%2F%3Freplytocom%3D555%23feedback-editor-555)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsingle_post_title%2F) before being able to contribute a note or feedback.

Notifications