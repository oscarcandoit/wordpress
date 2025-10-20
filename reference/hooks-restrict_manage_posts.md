---
url: https://developer.wordpress.org/reference/hooks/restrict_manage_posts
scraped_at: 2025-10-20T03:19:57.418Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

restrict\_manage\_posts


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Posts\_List\_Table::extra\_tablenav](https://developer.wordpress.org/reference/classes/wp_posts_list_table/extra_tablenav/)restrict\_manage\_posts

Search

# do\_action( ‘restrict\_manage\_posts’, string$post\_type, string$which )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#source)
- [Related](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#wp--skip-link--target)

Fires before the Filter button on the Posts and Pages list tables.

## [Description](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#description)

The Filter button allows sorting by date and/or category on the Posts list table, and sorting by date on the Pages list table.

## [Parameters](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#parameters)

`$post_type` string

The post type slug.

`$which` string

The location of the extra table nav markup: `'top'` or `'bottom'` for [WP\_Posts\_List\_Table](https://developer.wordpress.org/reference/classes/wp_posts_list_table/), `'bar'` for [WP\_Media\_List\_Table](https://developer.wordpress.org/reference/classes/wp_media_list_table/).

## [Source](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#source)

`wp-admin/includes/class-wp-posts-list-table.php`
[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

```php
do_action( 'restrict_manage_posts', $this->screen->post_type, $which );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/class-wp-posts-list-table.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/class-wp-posts-list-table.php#L594) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/class-wp-posts-list-table.php#L594-L594)

## [Related](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Media\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_media_list_table/extra_tablenav/) `wp-admin/includes/class-wp-media-list-table.php` |  |
| [WP\_Posts\_List\_Table::extra\_tablenav()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/extra_tablenav/) `wp-admin/includes/class-wp-posts-list-table.php` |  |

## [Changelog](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#changelog)

| Version | Description |
| --- | --- |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | The `$which` parameter was added. |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | The `$post_type` parameter was added. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#comment-content-3034)



The example below eliminates the need for `parse_query` when filtering based on taxonomy. It uses the taxonomy slug as URL parameter, just like WordPress does out of the box. The example adds filter dropdowns for two taxonomies, and allows for boolean AND filtering.





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_action( 'restrict_manage_posts', 'add_admin_filters', 10, 1 );

public function add_admin_filters( $post_type ){
   	if( 'my_post_type' !== $post_type ){
   		return;
   	}
   	$taxonomies_slugs = array(
   		'my_taxonomy',
   		'my_other_taxonomy'
   	);
   	// loop through the taxonomy filters array
   	foreach( $taxonomies_slugs as $slug ){
   		$taxonomy = get_taxonomy( $slug );
   		$selected = '';
   		// if the current page is already filtered, get the selected term slug
   		$selected = isset( $_REQUEST[ $slug ] ) ? $_REQUEST[ $slug ] : '';
   		// render a dropdown for this taxonomy's terms
   		wp_dropdown_categories( array(
   			'show_option_all' =>  $taxonomy->labels->all_items,
   			'taxonomy'        =>  $slug,
   			'name'            =>  $slug,
   			'orderby'         =>  'name',
   			'value_field'     =>  'slug',
   			'selected'        =>  $selected,
   			'hierarchical'    =>  true,
   		) );
   	}
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frestrict_manage_posts%2F%3Freplytocom%3D3034%23feedback-editor-3034)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#comment-content-2173)



Use this hook to add a custom taxonomy filter for your post table,





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_action( 'restrict_manage_posts', 'my_post_type_filter', 10, 2 );
function my_post_type_filter( $post_type, $which ) {
   	if ( 'my-post' !== $post_type ) {
   		return; //check to make sure this is your cpt
   	}

   	$taxonomy_slug = 'my-post-type';
   	$taxonomy      = get_taxonomy($taxonomy_slug);
   	$selected      = '';
   	$request_attr  = 'my_type'; //this will show up in the url

   	if ( isset( $_REQUEST[ $request_attr ] ) ) {
   		$selected = $_REQUEST[ $request_attr ]; //in case the current page is already filtered
   	}

   	wp_dropdown_categories(array(
   		'show_option_all' =>  __("Show All {$taxonomy->label}"),
   		'taxonomy'        =>  $taxonomy_slug,
   		'name'            =>  $request_attr,
   		'orderby'         =>  'name',
   		'selected'        =>  $selected,
   		'hierarchical'    =>  true,
   		'depth'           =>  3,
   		'show_count'      =>  true, // Show number of post in parent term
   		'hide_empty'      =>  false, // Don't show posts w/o terms
   	) );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frestrict_manage_posts%2F%3Freplytocom%3D2173%23feedback-editor-2173)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#comment-content-2175)



To add a custom filter based on a meta field for example, you can build a custom dropdown filter,





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_action('restrict_manage_posts','location_filtering',10);
function location_filtering($post_type){
       if('my-custom-post' !== $post_type){
         return; //filter your post
       }
       $selected = '';
       $request_attr = 'my_loc';
       if ( isset($_REQUEST[$request_attr]) ) {
         $selected = $_REQUEST[$request_attr];
       }
       //get unique values of the meta field to filer by.
   	$meta_key = 'my_custom_field_location';
   	global $wpdb;
   	$result = $wpdb->get_col(
   		$wpdb->prepare( "
   			SELECT DISTINCT pm.meta_value FROM {$wpdb->postmeta} pm
   			LEFT JOIN {$wpdb->posts} p ON p.ID = pm.post_id
   			WHERE pm.meta_key = '%s'
   			AND p.post_status IN ('publish', 'draft')
   			ORDER BY pm.meta_value",
   			$meta_key
   		)
       );
      //build a custom dropdown list of values to filter by
       echo '<select id="my-loc" name="my_loc">';
       echo '<option value="0">' . __( 'Show all locations', 'my-custom-domain' ) . ' </option>';
       foreach($results as $location){
         $select = ($org->ID == $selected) ? ' selected="selected"':'';
         echo '<option value="'.$location.'"'.$select.'>' . $location . ' </option>';
       }
       echo '</select>';
     }
```





next we need to ensure the admin query returns the correct set of filtered posts by hooking onto the ‘parse\_query’ filter,





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_filter( 'parse_query', 'filter_request_query' , 10);
function filter_request_query($query){
       //modify the query only if it admin and main query.
       if( !(is_admin() AND $query->is_main_query()) ){
         return $query;
       }
       //we want to modify the query for the targeted custom post and filter option
       if( !('my-custom-post' === $query->query['post_type'] AND isset($_REQUEST['my_loc']) ) ){
         return $query;
       }
       //for the default value of our filter no modification is required
       if(0 == $_REQUEST['my_loc']){
         return $query;
       }
      //modify the query_vars.
       $query->query_vars = array(array(
         'field' => 'my_custom_field_location',
         'value' => $_REQUEST['my_loc'],
         'compare' => '=',
         'type' => 'CHAR'
       ));
       return $query;
     }
```





To build more complex meta field queries, lookup the documentation for the `WP_Meta_Query` object.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frestrict_manage_posts%2F%3Freplytocom%3D2175%23feedback-editor-2175)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#comment-content-2176)



Use this hook to add a custom taxonomy filter for your post table,





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_action('restrict_manage_posts','my_post_type_filter',10,2);
function my_post_type_filter($post_type, $which){
       if('my-post' !== $post_type){
         return; //check to make sure this is your cpt
       }
       $taxonomy_slug = 'my-post-type';
       $taxonomy = get_taxonomy($taxonomy_slug);
       $selected = '';
       $request_attr = 'my_type'; //this will show up in the url
       if ( isset($_REQUEST[$request_attr] ) ) {
         $selected = $_REQUEST[$request_attr]; //in case the current page is already filtered
       }
       wp_dropdown_categories(array(
         'show_option_all' =>  __("Show All {$taxonomy->label}"),
         'taxonomy'        =>  $taxonomy_slug,
         'name'            =>  $request_attr,
         'orderby'         =>  'name',
         'selected'        =>  $selected,
         'hierarchical'    =>  true,
         'depth'           =>  3,
         'show_count'      =>  true, // Show number of post in parent term
         'hide_empty'      =>  false, // Don't show posts w/o terms
       ));
     }
```





to ensure the post table is correctly filtered, the post query needs to be modified to filter the selected term. This is done by hooking the `'parse_query'` filter,





`wp-admin/includes/class-wp-posts-list-table.php`
[Expand code](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/restrict_manage_posts/#)




```php
add_filter( 'parse_query', 'filter_request_query' , 10);
function filter_request_query($query){
       //modify the query only if it is admin and main query.
       if( !(is_admin() AND $query->is_main_query()) ){
         return $query;
       }
       //we want to modify the query for the targeted custom post.
       if( 'my-post' !== $query->query['post_type'] ){
         return $query;
       }
       //type filter
       if( isset($_REQUEST['my_type']) &&  0 != $_REQUEST['my_type']){
         $term =  $_REQUEST['my_type'];
         $taxonomy_slug = 'my-post-type';
         $query->query_vars['tax_query'] = array(
           array(
               'taxonomy'  => $taxonomy_slug,
               'field'     => 'ID',
               'terms'     => array($term)
           )
         );
       }
       return $query;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frestrict_manage_posts%2F%3Freplytocom%3D2176%23feedback-editor-2176)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Frestrict_manage_posts%2F) before being able to contribute a note or feedback.

Notifications