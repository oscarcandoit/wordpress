---
url: https://developer.wordpress.org/reference/functions/the_post_thumbnail_url
scraped_at: 2025-10-20T03:16:24.207Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

the\_post\_thumbnail\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)the\_post\_thumbnail\_url()

Search

# the\_post\_thumbnail\_url( string\|int\[\]$size = 'post-thumbnail' )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#source)
- [Related](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#wp--skip-link--target)

Displays the post thumbnail URL.

## [Parameters](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/\#parameters)

`$size` string\|int\[\]optional

Image size to use. Accepts any valid image size, or an array of width and height values in pixels (in that order).

Default `'post-thumbnail'`.

Default: `'post-thumbnail'`

## [Source](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/\#source)

`wp-includes/post-thumbnail-template.php`
[Copy](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#)

```php
function the_post_thumbnail_url( $size = 'post-thumbnail' ) {
	$url = get_the_post_thumbnail_url( null, $size );

	if ( $url ) {
		echo esc_url( $url );
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post-thumbnail-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post-thumbnail-template.php#L281) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post-thumbnail-template.php#L281-L287)

## [Related](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/\#related)

| Uses | Description |
| --- | --- |
| [get\_the\_post\_thumbnail\_url()](https://developer.wordpress.org/reference/functions/get_the_post_thumbnail_url/) `wp-includes/post-thumbnail-template.php` | Returns the post thumbnail URL. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |

## [Changelog](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#comment-content-3629)



**background Div Post thumbnail**





`wp-includes/post-thumbnail-template.php`
[Copy](https://developer.wordpress.org/reference/functions/the_post_thumbnail_url/#)




```php
<div class="post" style="background-image: url(<?php the_post_thumbnail_url(); ?>)"></div>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fthe_post_thumbnail_url%2F%3Freplytocom%3D3629%23feedback-editor-3629)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fthe_post_thumbnail_url%2F) before being able to contribute a note or feedback.

Notifications