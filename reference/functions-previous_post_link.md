---
url: https://developer.wordpress.org/reference/functions/previous_post_link
scraped_at: 2025-10-20T03:22:18.352Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/previous_post_link/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

previous\_post\_link()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)previous\_post\_link()

Search

# previous\_post\_link( string$format = '&laquo; %link', string$link = '%title', bool$in\_same\_term = false, int\[\]\|string$excluded\_terms = '', string$taxonomy = 'category' )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/previous_post_link/#description)
  - [See also](https://developer.wordpress.org/reference/functions/previous_post_link/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/previous_post_link/#parameters)
- [More Information](https://developer.wordpress.org/reference/functions/previous_post_link/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/previous_post_link/#source)
- [Related](https://developer.wordpress.org/reference/functions/previous_post_link/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/previous_post_link/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/previous_post_link/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/previous_post_link/#wp--skip-link--target)

Displays the previous post link that is adjacent to the current post.

## [Description](https://developer.wordpress.org/reference/functions/previous_post_link/\#description)

### [See also](https://developer.wordpress.org/reference/functions/previous_post_link/\#see-also)

- [get\_previous\_post\_link()](https://developer.wordpress.org/reference/functions/get_previous_post_link)

## [Parameters](https://developer.wordpress.org/reference/functions/previous_post_link/\#parameters)

`$format` stringoptional

Link anchor format. Default ‘« %link’.

Default: `'&laquo; %link'`

`$link` stringoptional

Link permalink format. Default `'%title'`.

Default: `'%title'`

`$in_same_term` booloptional

Whether link should be in the same taxonomy term.

Default: `false`

`$excluded_terms` int\[\]\|stringoptional

Array or comma-separated list of excluded term IDs.

Default: `''`

`$taxonomy` stringoptional

Taxonomy, if `$in_same_term` is true. Default `'category'`.

Default: `'category'`

## [More Information](https://developer.wordpress.org/reference/functions/previous_post_link/\#more-information)

Used on single post permalink pages, this template tag displays a link to the previous post which exists in chronological order from the current post. This tag must be used in The Loop.

`$format` is the format string for the link. This is where to control what comes before and after the link. `'%link'` in string will be replaced with whatever is declared as `'link'` (see next parameter). `'Go to %link'` will generate “Go to <a href=…” Put HTML tags here to style the final results.

`$in_same_term ` indicates whether previous post must be within the same taxonomy term as the current post. If set to `'true'`, only posts from the current taxonomy term will be displayed. If the post is in both the parent and subcategory, or more than one term, the previous post link will lead to the previous post in any of those terms.`$excluded_terms` is an array or a comma-separated list of numeric terms IDs from which the next post should not be listed. For example `array(1, 5)` or `'1,5'`. This argument used to accept a list of IDs separated by `'and'`, this was deprecated in WordPress 3.3.

## [Source](https://developer.wordpress.org/reference/functions/previous_post_link/\#source)

`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)

```php
function previous_post_link( $format = '&laquo; %link', $link = '%title', $in_same_term = false, $excluded_terms = '', $taxonomy = 'category' ) {
	echo get_previous_post_link( $format, $link, $in_same_term, $excluded_terms, $taxonomy );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L2277) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L2277-L2279)

## [Related](https://developer.wordpress.org/reference/functions/previous_post_link/\#related)

| Uses | Description |
| --- | --- |
| [get\_previous\_post\_link()](https://developer.wordpress.org/reference/functions/get_previous_post_link/) `wp-includes/link-template.php` | Retrieves the previous post link that is adjacent to the current post. |

## [Changelog](https://developer.wordpress.org/reference/functions/previous_post_link/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/previous_post_link/\#user-contributed-notes)

1. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1235)



**Post Title As Link, Within Same Custom Taxonomy**



Displays link to previous post in the same custom taxonomy term. You have a Custom Post Type called Buildings, and a custom taxonomy called Neighborhood



`Previous Title in Neighborhood`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link( '%link', '%title', true, ' ', 'neighborhood' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1235%23feedback-editor-1235)

2. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1231)



**Bold Post Title As Link**



Displays link with previous chronological post’s title wrapped in ‘strong’ tags (typically sets text to bold).



`Previous Post Title`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link( '<strong>%link</strong>' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1231%23feedback-editor-1231)

3. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1230)



**Default Usage**



Displays link with left angular quote («) followed by the post title of the previous post (chronological post date order).



`« Previous Post Title`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link(); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1230%23feedback-editor-1230)

4. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1232)



**Text As Link, Without Post Title, Within Same Category**



Displays custom text as link to the previous post within the same category as the current post. Post title is not included here. “Previous in category” is the custom text, which can be changed to fit your requirements.



`Previous in category`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link( '%link', __( 'Previous in category', 'textdomain' ), true ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1232%23feedback-editor-1232)

5. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1233)



**Within Same Category, Excluding One**



Displays link to previous post in the same category, as long as it is not in category 13 (the category ID #). You can change the number to any category you wish to exclude. Array or comma-separated list of category ID(s) from which the previous post should not be listed. For example array( 1, 5) or ‘1,5’.



`Previous in category`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link( '%link', 'Previous in category', true, '13' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1233%23feedback-editor-1233)

6. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/previous_post_link/#comment-content-1234)



**Within Same Taxonomy**



Displays link to previous post in the same taxonomy term. Post Formats are a taxonomy so the following would link to the previous post with the same post format.



`Previous post in taxonomy`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/previous_post_link/#)




```php
<?php previous_post_link( '%link', 'Previous post in category', true, ' ', 'post_format' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F%3Freplytocom%3D1234%23feedback-editor-1234)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprevious_post_link%2F) before being able to contribute a note or feedback.

Notifications