---
url: https://developer.wordpress.org/reference/functions/comment_class
scraped_at: 2025-10-20T03:16:28.901Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/comment_class/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

comment\_class()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)comment\_class()

Search

# comment\_class( string\|string\[\]$css\_class = '', int\|WP\_Comment$comment = null, int\|WP\_Post$post = null, bool$display = true ): void\|string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/comment_class/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/comment_class/#return)
- [More Information](https://developer.wordpress.org/reference/functions/comment_class/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/comment_class/#source)
- [Related](https://developer.wordpress.org/reference/functions/comment_class/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/comment_class/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/comment_class/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/comment_class/#wp--skip-link--target)

Generates semantic classes for each comment element.

## [Parameters](https://developer.wordpress.org/reference/functions/comment_class/\#parameters)

`$css_class` string\|string\[\]optional

One or more classes to add to the class list.

Default: `''`

`$comment` int\|[WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/)optional

Comment ID or [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object. Default current comment.

Default: `null`

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Post ID or [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) object. Default current post.

Default: `null`

`$display` booloptional

Whether to print or return the output.

Default: `true`

## [Return](https://developer.wordpress.org/reference/functions/comment_class/\#return)

void\|string Void if `$display` argument is true, comment classes if `$display` is false.

## [More Information](https://developer.wordpress.org/reference/functions/comment_class/\#more-information)

[comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) will apply the following classes, based on the following conditions:

- comment\_type: for normal comments, adds class “comment”. For all other types, it adds the value of the comment\_type as the class
- user\_id: if the comment was made by a registered user, then adds class “byuser” and “comment-author-” + the user\_nicename sanitized (i.e. spaces removed). Also, if the comment is by the original author of the post, the class “bypostauthor” is added.
- Odd/Even: if the comment number is even, adds class “even”. Otherwise, adds class “alt” and “odd”.
- Comment Depth: The class “depth=” + the comment depth is always added
- Top-level Comments: If comment depth is top level (1), then adds “thread-even” or “thread-alt” and “thread-odd” depending on whether the comment number is even or odd.
- If the optional class parameter is passed to [comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) , then that class gets added to all the others. This is useful for defining your own custom comment class.

[comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) uses the following [global variables](https://developer.wordpress.org/apis/handbook/global-variables/). So these variables can be set prior to calling [comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) to effect the output:

- **`$comment_alt`**
- **`$comment_depth`**
- **`$comment_thread_alt`**

For example, you can force `$comment_alt = FALSE` if you always want to start with the first comment being even. The [comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) function will then alternate this variable for you.

## [Source](https://developer.wordpress.org/reference/functions/comment_class/\#source)

`wp-includes/comment-template.php`
[Copy](https://developer.wordpress.org/reference/functions/comment_class/#)

```php
function comment_class( $css_class = '', $comment = null, $post = null, $display = true ) {
	// Separates classes with a single space, collates classes for comment DIV.
	$css_class = 'class="' . implode( ' ', get_comment_class( $css_class, $comment, $post ) ) . '"';

	if ( $display ) {
		echo $css_class;
	} else {
		return $css_class;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/comment-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/comment-template.php#L493) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/comment-template.php#L493-L502)

## [Related](https://developer.wordpress.org/reference/functions/comment_class/\#related)

| Uses | Description |
| --- | --- |
| [get\_comment\_class()](https://developer.wordpress.org/reference/functions/get_comment_class/) `wp-includes/comment-template.php` | Returns the classes for the comment div as an array. |

| Used by | Description |
| --- | --- |
| [\_wp\_dashboard\_recent\_comments\_row()](https://developer.wordpress.org/reference/functions/_wp_dashboard_recent_comments_row/) `wp-admin/includes/dashboard.php` | Outputs a row for the Recent Comments widget. |
| [Walker\_Comment::comment()](https://developer.wordpress.org/reference/classes/walker_comment/comment/) `wp-includes/class-walker-comment.php` | Outputs a single comment. |
| [Walker\_Comment::html5\_comment()](https://developer.wordpress.org/reference/classes/walker_comment/html5_comment/) `wp-includes/class-walker-comment.php` | Outputs a comment in the HTML5 format. |
| [Walker\_Comment::ping()](https://developer.wordpress.org/reference/classes/walker_comment/ping/) `wp-includes/class-walker-comment.php` | Outputs a pingback comment. |

## [Changelog](https://developer.wordpress.org/reference/functions/comment_class/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Added the ability for `$comment` to also accept a [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object. |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/comment_class/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/comment_class/#comment-content-1283)



**Example**





`wp-includes/comment-template.php`
[Copy](https://developer.wordpress.org/reference/functions/comment_class/#)




```php
<li <?php comment_class(); ?> id="li-comment-<?php comment_ID() ?>">
```





The [comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) outputs the class=”whatever” piece for that div. This includes several different classes of value: comment, even (or odd), thread-even, depth-1, etc. These make it easy to style different parts of the theme in different ways.



Specifically, it will apply the following classes, based on the following conditions:



**comment\_type**: for normal comments, adds class “comment”. For all other types, it adds the value of the comment\_type as the class

**user\_id**: if the comment was made by a registered user, then adds class “byuser” and “comment-author-” + the user\_nicename sanitized (i.e. spaces removed). Also, if the comment is by the original author of the post, the class “bypostauthor” is added.

**Odd/Even**: if the comment number is even, adds class “even”. Otherwise, adds class “alt” and “odd”.

**Comment Depth**: The class “depth=” + the comment depth is always added

**Top-level Comments**: If comment depth is top level (1), then adds “thread-even” or “thread-alt” and “thread-odd” depending on whether the comment number is even or odd.


If the optional class parameter is passed to [comment\_class()](https://developer.wordpress.org/reference/functions/comment_class/) , then that class gets added to all the others. This is useful for defining your own custom comment class.



For special cases where you want to add your own classes, comment\_class supports that too:





`wp-includes/comment-template.php`
[Copy](https://developer.wordpress.org/reference/functions/comment_class/#)




```php
<?php comment_class( 'special' ); ?>
```





This will add “special” to the class list.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_class%2F%3Freplytocom%3D1283%23feedback-editor-1283)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_class%2F) before being able to contribute a note or feedback.

Notifications