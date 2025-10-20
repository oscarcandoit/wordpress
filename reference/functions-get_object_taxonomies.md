---
url: https://developer.wordpress.org/reference/functions/get_object_taxonomies
scraped_at: 2025-10-20T03:13:53.086Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_object\_taxonomies()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_object\_taxonomies()

Search

# get\_object\_taxonomies( string\|string\[\]\|WP\_Post$object\_type, string$output = 'names' ): string\[\]\| [WP\_Taxonomy](https://developer.wordpress.org/reference/classes/wp_taxonomy/)\[\]

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#wp--skip-link--target)

Returns the names or objects of the taxonomies which are registered for the requested object or object type, such as a post object or post type name.

## [Description](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#description)

Example:

`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

```php
$taxonomies = get_object_taxonomies( 'post' );
```

This results in:

`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

```php
Array( 'category', 'post_tag' )
```

## [Parameters](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#parameters)

`$object_type` string\|string\[\]\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)required

Name of the type of taxonomy object, or an object (row from posts).

`$output` stringoptional

The type of output to return in the array. Accepts either `'names'` or `'objects'`. Default `'names'`.

Default: `'names'`

## [Return](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#return)

string\[\]\| [WP\_Taxonomy](https://developer.wordpress.org/reference/classes/wp_taxonomy/)\[\] The names or objects of all taxonomies of `$object_type`.

## [Source](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#source)

`wp-includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

```php
function get_object_taxonomies( $object_type, $output = 'names' ) {
	global $wp_taxonomies;

	if ( is_object( $object_type ) ) {
		if ( 'attachment' === $object_type->post_type ) {
			return get_attachment_taxonomies( $object_type, $output );
		}
		$object_type = $object_type->post_type;
	}

	$object_type = (array) $object_type;

	$taxonomies = array();
	foreach ( (array) $wp_taxonomies as $tax_name => $tax_obj ) {
		if ( array_intersect( $object_type, (array) $tax_obj->object_type ) ) {
			if ( 'names' === $output ) {
				$taxonomies[] = $tax_name;
			} else {
				$taxonomies[ $tax_name ] = $tax_obj;
			}
		}
	}

	return $taxonomies;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/taxonomy.php#L311) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/taxonomy.php#L311-L335)

## [Related](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#related)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Menu\_Items\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Prepares a single nav menu item output for response. |
| [WP\_REST\_Menu\_Items\_Controller::get\_item\_schema()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/get_item_schema/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Retrieves the nav menu item’s schema, conforming to JSON Schema. |
| [WP\_REST\_Posts\_Controller::prepare\_tax\_query()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_tax_query/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares the ‘tax\_query’ for a collection of posts. |
| [WP\_REST\_Posts\_Controller::prepare\_taxonomy\_limit\_schema()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_taxonomy_limit_schema/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares the collection schema for including and excluding items by terms. |
| [register\_and\_do\_post\_meta\_boxes()](https://developer.wordpress.org/reference/functions/register_and_do_post_meta_boxes/) `wp-admin/includes/meta-boxes.php` | Registers the default post meta boxes, and runs the `do_meta_boxes` actions. |
| [WP\_REST\_Posts\_Controller::get\_available\_actions()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_available_actions/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Gets the link relations available for the post and current user. |
| [WP\_REST\_Posts\_Controller::get\_schema\_links()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_schema_links/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves Link Description Objects that should be added to the Schema for the posts collection. |
| [WP\_REST\_Posts\_Controller::prepare\_links()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_links/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares links for the request. |
| [WP\_REST\_Posts\_Controller::get\_item\_schema()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/get_item_schema/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Retrieves the post’s schema, conforming to JSON Schema. |
| [WP\_REST\_Posts\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Prepares a single post output for response. |
| [WP\_REST\_Posts\_Controller::handle\_terms()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/handle_terms/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Updates the post’s terms from a REST request. |
| [WP\_REST\_Posts\_Controller::check\_assign\_terms\_permission()](https://developer.wordpress.org/reference/classes/wp_rest_posts_controller/check_assign_terms_permission/) `wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php` | Checks whether current user can assign all terms sent with the current request. |
| [WP\_REST\_Taxonomies\_Controller::get\_items\_permissions\_check()](https://developer.wordpress.org/reference/classes/wp_rest_taxonomies_controller/get_items_permissions_check/) `wp-includes/rest-api/endpoints/class-wp-rest-taxonomies-controller.php` | Checks whether a given request has permission to read taxonomies. |
| [WP\_REST\_Taxonomies\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_taxonomies_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-taxonomies-controller.php` | Retrieves all public taxonomies. |
| [WP\_REST\_Post\_Types\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_post_types_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-post-types-controller.php` | Prepares a post type object for serialization. |
| [WP\_Post\_Type::unregister\_taxonomies()](https://developer.wordpress.org/reference/classes/wp_post_type/unregister_taxonomies/) `wp-includes/class-wp-post-type.php` | Removes the post type from all taxonomies. |
| [wp\_queue\_posts\_for\_term\_meta\_lazyload()](https://developer.wordpress.org/reference/functions/wp_queue_posts_for_term_meta_lazyload/) `wp-includes/post.php` | Queues posts for lazy-loading of term meta. |
| [get\_inline\_data()](https://developer.wordpress.org/reference/functions/get_inline_data/) `wp-admin/includes/template.php` | Adds hidden fields with the data for use in the inline editor for posts and pages. |
| [bulk\_edit\_posts()](https://developer.wordpress.org/reference/functions/bulk_edit_posts/) `wp-admin/includes/post.php` | Processes the post data for the bulk editing of posts. |
| [WP\_Posts\_List\_Table::inline\_edit()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/inline_edit/) `wp-admin/includes/class-wp-posts-list-table.php` | Outputs the hidden row displayed when inline editing |
| [WP\_Posts\_List\_Table::get\_columns()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/get_columns/) `wp-admin/includes/class-wp-posts-list-table.php` |  |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |
| [update\_object\_term\_cache()](https://developer.wordpress.org/reference/functions/update_object_term_cache/) `wp-includes/taxonomy.php` | Updates the cache for the given term object ID(s). |
| [get\_the\_taxonomies()](https://developer.wordpress.org/reference/functions/get_the_taxonomies/) `wp-includes/taxonomy.php` | Retrieves all taxonomies associated with a post. |
| [get\_post\_taxonomies()](https://developer.wordpress.org/reference/functions/get_post_taxonomies/) `wp-includes/taxonomy.php` | Retrieves all taxonomy names for the given post. |
| [is\_object\_in\_taxonomy()](https://developer.wordpress.org/reference/functions/is_object_in_taxonomy/) `wp-includes/taxonomy.php` | Determines if the given object type is associated with the given taxonomy. |
| [clean\_object\_term\_cache()](https://developer.wordpress.org/reference/functions/clean_object_term_cache/) `wp-includes/taxonomy.php` | Removes the taxonomy relationship to terms from the cache. |
| [\_wp\_menu\_item\_classes\_by\_context()](https://developer.wordpress.org/reference/functions/_wp_menu_item_classes_by_context/) `wp-includes/nav-menu-template.php` | Adds the class property classes for the current context, if applicable. |
| [\_update\_term\_count\_on\_transition\_post\_status()](https://developer.wordpress.org/reference/functions/_update_term_count_on_transition_post_status/) `wp-includes/post.php` | Updates the custom taxonomies’ term counts when a post’s status is changed. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [wp\_publish\_post()](https://developer.wordpress.org/reference/functions/wp_publish_post/) `wp-includes/post.php` | Publishes a post by transitioning the post status. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wp\_delete\_post()](https://developer.wordpress.org/reference/functions/wp_delete_post/) `wp-includes/post.php` | Trashes or deletes a post or page. |
| [wp\_xmlrpc\_server::\_insert\_post()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_insert_post/) `wp-includes/class-wp-xmlrpc-server.php` | Helper method for wp\_newPost() and wp\_editPost(), containing shared logic. |
| [wp\_xmlrpc\_server::\_prepare\_post()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_post/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares post data for return in an XML-RPC object. |
| [wp\_xmlrpc\_server::\_prepare\_post\_type()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_post_type/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares post data for return in an XML-RPC object. |

[Show 31 more](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#) [Show less](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#changelog)

| Version | Description |
| --- | --- |
| [2.3.0](https://developer.wordpress.org/reference/since/2.3.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_object_taxonomies/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#comment-content-638)



**Taxonomy objects for post type**


If the `$output` parameter is `'objects'`, taxonomy objects will be returned as described in `get_taxonomies()`.





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
<?php
   	$taxonomy_objects = get_object_taxonomies( 'post', 'objects' );
   	print_r( $taxonomy_objects);
?>
```





will output





`wp-includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
Array
(
       [category] => stdClass Object
           (
               [hierarchical] => 1
               [update_count_callback] =>
               [rewrite] =>
               [query_var] => category_name
               [public] => 1
               [show_ui] => 1
               [show_tagcloud] => 1
               [_builtin] => 1
               [labels] => stdClass Object
                   (
                       ...
                   )
               ...
               [name] => category
               [label] => Categories
           )
       [post_tag] => stdClass Object
           (
               ...
           )
       [post_format] => stdClass Object
           (
               ....
           )
)
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_object_taxonomies%2F%3Freplytocom%3D638%23feedback-editor-638)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#comment-content-637)



**Taxonomy names for post type**





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
<?php
   	$taxonomy_names = get_object_taxonomies( 'post' );
   	print_r( $taxonomy_names);
?>
```





will typically output:





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
Array
(
   	[0] => category
   	[1] => post_tag
   	[2] => post_format
)
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_object_taxonomies%2F%3Freplytocom%3D637%23feedback-editor-637)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#comment-content-639)



**Taxonomy names for post object**


To get the taxonomies for the current post, the current post object can be passed instead of the post type.





`wp-includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)

[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
<?php
add_action('wp_head','wpdocs_output_current_post_taxonomies');

/**
    * Output taxonomies for the current post
    */
function wpdocs_output_current_post_taxonomies(){
   	global $post;

   	$taxonomy_names = get_object_taxonomies( $post );
   	print_r( $taxonomy_names );
}
?>
```





will output





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
Array
(
       [0] => category
       [1] => post_tag
       [2] => post_format
)
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_object_taxonomies%2F%3Freplytocom%3D639%23feedback-editor-639)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#comment-content-4685)



**Its nice to know that I can get multiple post type taxonomies at once without making a loop.**





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
<?php
$post_taxonomies_objects = get_object_taxonomies( array( 'page', 'post', 'custom_post_type_slug' ), 'objects' );

/**
    * Output taxonomies objects for the selected post types.
    */
print_r( $post_taxonomies_objects );
?>
```





**or for just a array with taxonomies names**





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/get_object_taxonomies/#)




```php
<?php
$post_taxonomies_names = get_object_taxonomies( array( 'page', 'post', 'custom_post_type_slug' ), 'names );

/**
    * Output taxonomies names for the selected post types.
    */
print_r( $post_taxonomies_names );
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_object_taxonomies%2F%3Freplytocom%3D4685%23feedback-editor-4685)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_object_taxonomies%2F) before being able to contribute a note or feedback.

Notifications