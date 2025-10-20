---
url: https://developer.wordpress.org/reference/functions/get_post_ancestors
scraped_at: 2025-10-20T03:21:14.140Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_post_ancestors/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_post\_ancestors()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_post\_ancestors()

Search

# get\_post\_ancestors( int\|WP\_Post$post ): int\[\]

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_post_ancestors/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_post_ancestors/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_post_ancestors/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_post_ancestors/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_post_ancestors/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_ancestors/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_post_ancestors/#wp--skip-link--target)

Retrieves the IDs of the ancestors of a post.

## [Parameters](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)required

Post ID or post object.

## [Return](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#return)

int\[\] Array of ancestor IDs or empty array if there are none.

## [Source](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)

[Copy](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)

```php
function get_post_ancestors( $post ) {
	$post = get_post( $post );

	if ( ! $post || empty( $post->post_parent ) || $post->post_parent === $post->ID ) {
		return array();
	}

	$ancestors = array();

	$id          = $post->post_parent;
	$ancestors[] = $id;

	while ( $ancestor = get_post( $id ) ) {
		// Loop detection: If the ancestor has been seen before, break.
		if ( empty( $ancestor->post_parent ) || $ancestor->post_parent === $post->ID
			|| in_array( $ancestor->post_parent, $ancestors, true )
		) {
			break;
		}

		$id          = $ancestor->post_parent;
		$ancestors[] = $id;
	}

	return $ancestors;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L1137) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L1137-L1162)

## [Related](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#related)

| Uses | Description |
| --- | --- |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

| Used by | Description |
| --- | --- |
| [WP\_Posts\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/single_row/) `wp-admin/includes/class-wp-posts-list-table.php` |  |
| [get\_ancestors()](https://developer.wordpress.org/reference/functions/get_ancestors/) `wp-includes/taxonomy.php` | Gets an array of ancestor IDs for a given object. |
| [WP\_Post::\_\_get()](https://developer.wordpress.org/reference/classes/wp_post/__get/) `wp-includes/class-wp-post.php` | Getter. |

## [Changelog](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_post_ancestors/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_post_ancestors/#comment-content-550)



**Get Ancestors Page Thumbnail**


Get the top level page thumbnail and display it!





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)




```php
<?php
global $post;
$parents = get_post_ancestors( $post );
$id = $post->ID;
/* Get the ID of the 'top most' Page */
if ( ! empty( $parents ) ) {
       $id = array_pop( $parents );
}
if ( has_post_thumbnail( $id ) ) {
       echo get_the_post_thumbnail( $id, 'thumbnail' );
}
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_ancestors%2F%3Freplytocom%3D550%23feedback-editor-550)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_post_ancestors/#comment-content-548)



**Get Ancestors Page Slug**


This example returns the highest page `{slug}` in a tree and uses it as a Body\_Class, so the parent and all children will have the same Body Class!



This example for a twenty eleven child theme in the `header.php` file





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)

[Copy](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)




```php
</head>

<?php
/* Get the Page Slug to Use as a Body Class, this will only return a value on pages! */
$class = '';
/* is it a page */
if( is_page() ) {
   	global $post;
   	/* Get an array of Ancestors and Parents if they exist */
   	$parents = get_post_ancestors( $post->ID );
   	/* Get the top Level page->ID count base 1, array base 0 so -1 */
   	$id = ($parents) ? $parents[count($parents)-1]: $post->ID;
   	/* Get the parent and set the $class with the page slug (post_name) */
   	$parent = get_post( $id );
   	$class = $parent->post_name;
}
?>

<body <?php body_class( $class ); ?>>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_ancestors%2F%3Freplytocom%3D548%23feedback-editor-548)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/get_post_ancestors/#comment-content-549)



**Get Ancestors Post Meta**


If we did not want to use the page slug, we could use a custom field eg: `body_class`, on the top level page and set the class in the post meta.





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)

[Copy](https://developer.wordpress.org/reference/functions/get_post_ancestors/#)




```php
</head>

<?php
$class = '';
if( is_page() ) {
   	global $post;
   	$parents = get_post_ancestors( $post->ID );
   	$id = ($parents) ? $parents[count($parents)-1]: $post->ID;
   	$class = get_post_meta( $id, 'body_class', true );
}
?>

<body <?php body_class( $class ); ?>>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_ancestors%2F%3Freplytocom%3D549%23feedback-editor-549)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/get_post_ancestors/#comment-content-7160)



Suppose we have this pages structure:



- Top level page (ID: 107)
  - 2nd level page (ID: 997)
    - 3rd level page (ID: 1090)
      - Current post

`[0] => int(1090) [1] => int(997) [2] => int(107)`

So, if you want to get its direct parent page, then use the first element, or use the last element if you want to get the top level page.

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_ancestors%2F%3Freplytocom%3D7160%23feedback-editor-7160)

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_post_ancestors%2F) before being able to contribute a note or feedback.

Notifications