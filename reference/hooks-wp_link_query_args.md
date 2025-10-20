---
url: https://developer.wordpress.org/reference/hooks/wp_link_query_args
scraped_at: 2025-10-20T03:13:20.246Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_link\_query\_args


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[\_WP\_Editors::wp\_link\_query](https://developer.wordpress.org/reference/classes/_wp_editors/wp_link_query/)wp\_link\_query\_args

Search

# apply\_filters( ‘wp\_link\_query\_args’, array$query )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#description)
  - [See also](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#see-also)
- [Parameters](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#source)
- [Related](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#wp--skip-link--target)

Filters the link query arguments.

## [Description](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#description)

Allows modification of the link query arguments before querying.

### [See also](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#see-also)

- [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query): for a full list of arguments

## [Parameters](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#parameters)

`$query` array

An array of [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) arguments.

## [More Information](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#more-information)

The “ `wp_link_query_args`” filter is used to filter the array of arguments passed to the `wp_link_query` function which is responsible for building the list of linkable content in the modal window that displays when you insert a link. `wp_link_query_args` allows you to alter the query before the list is rendered on the page.

## [Source](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#source)

`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#)

```php
$query = apply_filters( 'wp_link_query_args', $query );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-editor.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-editor.php#L1813) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-editor.php#L1813-L1813)

## [Related](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#related)

| Used by | Description |
| --- | --- |
| [\_WP\_Editors::wp\_link\_query()](https://developer.wordpress.org/reference/classes/_wp_editors/wp_link_query/) `wp-includes/class-wp-editor.php` | Performs post queries for internal linking. |

## [Changelog](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#changelog)

| Version | Description |
| --- | --- |
| [3.7.0](https://developer.wordpress.org/reference/since/3.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_link_query_args/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#comment-content-4846)



Example Migrated from Codex:



Any allowable [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) parameters can be passed to `wp_link_query_args`. One example is filtering out post types:



**Show only posts and pages**



If you wanted only allow posts and pages to show up in the linked results, you could do something like this. In this example, we’re going to check to make sure we aren’t in the admin, so results would only be filtered on the front end, but admins could still add links to all post types.





`wp-includes/class-wp-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#)




```php
add_filter( 'wp_link_query_args', 'my_wp_link_query_args' );

function my_wp_link_query_args( $query ) {
       // check to make sure we are not in the admin
       if ( !is_admin() ) {
           $query['post_type'] = array( 'post', 'pages' ); // show only posts and pages
       }

       return $query;
}
```





**Remove specific post types from results**



You’d use something like this if you only wanted to remove specific post types from the results.





`wp-includes/class-wp-editor.php`
[Expand code](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#)

[Copy](https://developer.wordpress.org/reference/hooks/wp_link_query_args/#)




```php
add_filter( 'wp_link_query_args', 'remove_these_post_types_from_wp_link_query_args' );

function remove_these_post_types_from_wp_link_query_args( $query ) {
       // this is the post type I want to exclude
       $cpt_to_remove = 'article';

       // find the corresponding array key
       $key = array_search( $cpt_to_remove, $query['post_type'] );

       // remove the array item
       if( $key )
           unset( $query['post_type'][$key] );

       return $query;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_link_query_args%2F%3Freplytocom%3D4846%23feedback-editor-4846)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_link_query_args%2F) before being able to contribute a note or feedback.

Notifications