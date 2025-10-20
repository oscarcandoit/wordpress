---
url: https://developer.wordpress.org/reference/functions/in_the_loop
scraped_at: 2025-10-20T03:25:39.781Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/in_the_loop/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

in\_the\_loop()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)in\_the\_loop()

Search

# in\_the\_loop(): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/in_the_loop/#description)
- [Return](https://developer.wordpress.org/reference/functions/in_the_loop/#return)
- [Source](https://developer.wordpress.org/reference/functions/in_the_loop/#source)
- [Related](https://developer.wordpress.org/reference/functions/in_the_loop/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/in_the_loop/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/in_the_loop/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/in_the_loop/#wp--skip-link--target)

Determines whether the caller is in the Loop.

## [Description](https://developer.wordpress.org/reference/functions/in_the_loop/\#description)

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Return](https://developer.wordpress.org/reference/functions/in_the_loop/\#return)

bool True if caller is within loop, false if loop hasn’t started or ended.

## [Source](https://developer.wordpress.org/reference/functions/in_the_loop/\#source)

`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/in_the_loop/#)

```php
function in_the_loop() {
	global $wp_query;

	if ( ! isset( $wp_query ) ) {
		return false;
	}

	return $wp_query->in_the_loop;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/query.php#L964) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/query.php#L964-L972)

## [Related](https://developer.wordpress.org/reference/functions/in_the_loop/\#related)

| Used by | Description |
| --- | --- |
| [wp\_get\_loading\_attr\_default()](https://developer.wordpress.org/reference/functions/wp_get_loading_attr_default/) `wp-includes/deprecated.php` | Gets the default value to use for a `loading` attribute on an element. |
| [get\_the\_post\_thumbnail()](https://developer.wordpress.org/reference/functions/get_the_post_thumbnail/) `wp-includes/post-thumbnail-template.php` | Retrieves the post thumbnail. |

## [Changelog](https://developer.wordpress.org/reference/functions/in_the_loop/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/in_the_loop/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/in_the_loop/#comment-content-1364)



**Modify Single Post Entry Titles**



For use in your functions file, this code example enables you to modify the default output of your entry titles.





`wp-includes/query.php`
[Copy](https://developer.wordpress.org/reference/functions/in_the_loop/#)




```php
function wpdocs_modify_single_post_entry_titles( $title ) {

   	if ( is_singular( 'post' ) && in_the_loop() ) {
   		/* Modify $title */
   	}

   	return $title;
}
add_filter( 'the_title', 'wpdocs_modify_single_post_entry_titles' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fin_the_loop%2F%3Freplytocom%3D1364%23feedback-editor-1364)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fin_the_loop%2F) before being able to contribute a note or feedback.

Notifications