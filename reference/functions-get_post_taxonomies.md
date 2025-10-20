---
url: https://developer.wordpress.org/reference/functions/get_post_taxonomies
scraped_at: 2025-10-20T03:14:22.899Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_post\_taxonomies()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_post\_taxonomies()

Search

# get\_post\_taxonomies( int\|WP\_Post$post ): string\[\]

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#wp--skip-link--target)

Retrieves all taxonomy names for the given post.

## [Parameters](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Post ID or [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) object. Default is global $post.

## [Return](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#return)

string\[\] An array of all taxonomy names for the given post.

## [Source](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#source)

`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#)

```php
function get_post_taxonomies( $post = 0 ) {
	$post = get_post( $post );

	return get_object_taxonomies( $post );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/taxonomy.php#L4855) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/taxonomy.php#L4855-L4859)

## [Related](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#related)

| Uses | Description |
| --- | --- |
| [get\_object\_taxonomies()](https://developer.wordpress.org/reference/functions/get_object_taxonomies/) `wp-includes/taxonomy.php` | Returns the names or objects of the taxonomies which are registered for the requested object or object type, such as a post object or post type name. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_taxonomies/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#comment-content-1488)



**Displays all taxonomies of a post.**





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#)




```php
$taxonomy_names = get_post_taxonomies();
print_r( $taxonomy_names );
```





Output:





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#)




```php
Array
(
       [0] => category
       [1] => post_tag
       [2] => post_format
)
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_taxonomies%2F%3Freplytocom%3D1488%23feedback-editor-1488)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#comment-content-1776)



#return section should say that the function returns an array of all taxonomy names for the given post or post object instead of just an array.


This highlights the main point of difference between get\_post\_taxonomies and get\_object\_taxonomies which can return an array of all taxonomy names **or** an array of all taxonomy objects.



[https://codex.wordpress.org/Function\_Reference/get\_post\_taxonomies](https://codex.wordpress.org/Function_Reference/get_post_taxonomies)



[https://developer.wordpress.org/reference/functions/get\_object\_taxonomies/](https://developer.wordpress.org/reference/functions/get_object_taxonomies/)





[Show feedback (1)](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_taxonomies%2F%3Freplytocom%3D1776%23feedback-editor-1776)



- I’ve pushed a fix for this in trunk and fixed the description manually for now. See [r40298](https://core.trac.wordpress.org/changeset/40298) for the commit where you’re credited.



[Drew Jaynes](https://profiles.wordpress.org/drewapicture/) [9 years ago](https://developer.wordpress.org/reference/functions/get_post_taxonomies/#comment-2152)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_taxonomies%2F) before being able to contribute a note or feedback.

Notifications