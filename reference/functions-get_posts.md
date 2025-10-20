---
url: https://developer.wordpress.org/reference/functions/get_posts
scraped_at: 2025-10-20T03:39:36.538Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_posts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_posts()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_posts()

Search

# get\_posts( array$args = null ): [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)\[\]\|int\[\]

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_posts/#description)
  - [See also](https://developer.wordpress.org/reference/functions/get_posts/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/get_posts/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_posts/#return)
- [More Information](https://developer.wordpress.org/reference/functions/get_posts/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/get_posts/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_posts/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_posts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_posts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_posts/#wp--skip-link--target)

Retrieves an array of the latest posts, or posts matching the given criteria.

## [Description](https://developer.wordpress.org/reference/functions/get_posts/\#description)

For more information on the accepted arguments, see the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) documentation in the Developer Handbook.

The `$ignore_sticky_posts` and `$no_found_rows` arguments are ignored by this function and both are set to `true`.

The defaults are as follows:

### [See also](https://developer.wordpress.org/reference/functions/get_posts/\#see-also)

- [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query)
- [WP\_Query::parse\_query()](https://developer.wordpress.org/reference/classes/WP_Query/parse_query)

## [Parameters](https://developer.wordpress.org/reference/functions/get_posts/\#parameters)

`$args` arrayoptional

Arguments to retrieve posts. See [WP\_Query::parse\_query()](https://developer.wordpress.org/reference/classes/wp_query/parse_query/) for all available arguments.

- `numberposts` int
Total number of posts to retrieve. Is an alias of `$posts_per_page` in [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). Accepts -1 for all. Default 5.

- `category` int\|string
Category ID or comma-separated list of IDs (this or any children).


Is an alias of `$cat` in [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). Default 0.

- `include` int\[\]
An array of post IDs to retrieve, sticky posts will be included.


Is an alias of `$post__in` in [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/). Default empty array.

- `exclude` int\[\]
An array of post IDs not to retrieve. Default empty array.

- `suppress_filters` bool
Whether to suppress filters. Default true.


Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/get_posts/\#return)

[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)\[\]\|int\[\] Array of post objects or post IDs.

## [More Information](https://developer.wordpress.org/reference/functions/get_posts/\#more-information)

The most appropriate use for get\_posts is to create an array of posts based on a set of parameters. It retrieves a list of recent posts or posts matching this criteria. get\_posts can also be used to create Multiple Loops, though a more direct reference to [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) using new [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) is preferred in this case.

The parameters of get\_posts are similar to those of get\_pages but are implemented quite differently, and should be used in appropriate scenarios. get\_posts uses [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/), whereas get\_pages queries the database more directly. Each have parameters that reflect this difference in implementation.

query\_posts also uses [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/), but is not recommended because it directly alters the main loop by changing the variables of the global variable $wp\_query. get\_posts, on the other hand, simply references a new [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) object, and therefore does not affect or alter the main loop.

If you would like to alter the main query before it is executed, you can hook into it using pre\_get\_posts. If you would just like to call an array of posts based on a small and simple set of parameters within a page, then get\_posts is your best option.

## [Source](https://developer.wordpress.org/reference/functions/get_posts/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

[Copy](https://developer.wordpress.org/reference/functions/get_posts/#)

```php
function get_posts( $args = null ) {
	$defaults = array(
		'numberposts'      => 5,
		'category'         => 0,
		'orderby'          => 'date',
		'order'            => 'DESC',
		'include'          => array(),
		'exclude'          => array(),
		'meta_key'         => '',
		'meta_value'       => '',
		'post_type'        => 'post',
		'suppress_filters' => true,
	);

	$parsed_args = wp_parse_args( $args, $defaults );
	if ( empty( $parsed_args['post_status'] ) ) {
		$parsed_args['post_status'] = ( 'attachment' === $parsed_args['post_type'] ) ? 'inherit' : 'publish';
	}
	if ( ! empty( $parsed_args['numberposts'] ) && empty( $parsed_args['posts_per_page'] ) ) {
		$parsed_args['posts_per_page'] = $parsed_args['numberposts'];
	}
	if ( ! empty( $parsed_args['category'] ) ) {
		$parsed_args['cat'] = $parsed_args['category'];
	}
	if ( ! empty( $parsed_args['include'] ) ) {
		$incposts                      = wp_parse_id_list( $parsed_args['include'] );
		$parsed_args['posts_per_page'] = count( $incposts );  // Only the number of posts included.
		$parsed_args['post__in']       = $incposts;
	} elseif ( ! empty( $parsed_args['exclude'] ) ) {
		$parsed_args['post__not_in'] = wp_parse_id_list( $parsed_args['exclude'] );
	}

	$parsed_args['ignore_sticky_posts'] = true;
	$parsed_args['no_found_rows']       = true;

	$get_posts = new WP_Query();
	return $get_posts->query( $parsed_args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L2543) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L2543-L2580)

## [Related](https://developer.wordpress.org/reference/functions/get_posts/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Query::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_query/__construct/) `wp-includes/class-wp-query.php` | Constructor. |
| [wp\_parse\_id\_list()](https://developer.wordpress.org/reference/functions/wp_parse_id_list/) `wp-includes/functions.php` | Cleans up an array, comma- or space-separated list of IDs. |
| [wp\_parse\_args()](https://developer.wordpress.org/reference/functions/wp_parse_args/) `wp-includes/functions.php` | Merges user defined arguments into defaults array. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_posts/#) [Show less](https://developer.wordpress.org/reference/functions/get_posts/#)

| Used by | Description |
| --- | --- |
| [do\_all\_trackbacks()](https://developer.wordpress.org/reference/functions/do_all_trackbacks/) `wp-includes/comment.php` | Performs all trackbacks. |
| [do\_all\_enclosures()](https://developer.wordpress.org/reference/functions/do_all_enclosures/) `wp-includes/comment.php` | Performs all enclosures. |
| [do\_all\_pingbacks()](https://developer.wordpress.org/reference/functions/do_all_pingbacks/) `wp-includes/comment.php` | Performs all pingbacks. |
| [WP\_Customize\_Manager::get\_changeset\_posts()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_changeset_posts/) `wp-includes/class-wp-customize-manager.php` | Gets changeset posts. |
| [wp\_add\_trashed\_suffix\_to\_post\_name\_for\_trashed\_posts()](https://developer.wordpress.org/reference/functions/wp_add_trashed_suffix_to_post_name_for_trashed_posts/) `wp-includes/post.php` | Adds a suffix if any trashed posts have a given slug. |
| [WP\_Customize\_Nav\_Menus::load\_available\_items\_query()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/load_available_items_query/) `wp-includes/class-wp-customize-nav-menus.php` | Performs the post\_type and taxonomy queries for loading available menu items. |
| [get\_children()](https://developer.wordpress.org/reference/functions/get_children/) `wp-includes/post.php` | Retrieves all children of the post parent ID. |
| [wp\_generate\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_generate_attachment_metadata/) `wp-admin/includes/image.php` | Generates attachment meta data and create image sub-sizes for images. |
| [wp\_dashboard\_recent\_drafts()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_drafts/) `wp-admin/includes/dashboard.php` | Show recent drafts of the user on the dashboard. |
| [wp\_ajax\_find\_posts()](https://developer.wordpress.org/reference/functions/wp_ajax_find_posts/) `wp-admin/includes/ajax-actions.php` | Handles querying posts for the Find Posts modal via AJAX. |
| [wp\_nav\_menu\_item\_post\_type\_meta\_box()](https://developer.wordpress.org/reference/functions/wp_nav_menu_item_post_type_meta_box/) `wp-admin/includes/nav-menu.php` | Displays a meta box for a post type menu item. |
| [get\_uploaded\_header\_images()](https://developer.wordpress.org/reference/functions/get_uploaded_header_images/) `wp-includes/theme.php` | Gets the header images uploaded for the active theme. |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |
| [get\_boundary\_post()](https://developer.wordpress.org/reference/functions/get_boundary_post/) `wp-includes/link-template.php` | Retrieves the boundary post. |
| [wp\_get\_recent\_posts()](https://developer.wordpress.org/reference/functions/wp_get_recent_posts/) `wp-includes/post.php` | Retrieves a number of recent posts. |
| [wp\_get\_nav\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_items/) `wp-includes/nav-menu.php` | Retrieves all menu items of a navigation menu. |
| [wp\_xmlrpc\_server::wp\_getMediaLibrary()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getmedialibrary/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a collection of media library items (or attachments). |
| [wp\_xmlrpc\_server::wp\_getPages()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_getpages/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves Pages. |

[Show 13 more](https://developer.wordpress.org/reference/functions/get_posts/#) [Show less](https://developer.wordpress.org/reference/functions/get_posts/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_posts/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_posts/\#user-contributed-notes)

01. [Skip to note 23 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-2101)



    Returns an array of [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) objects with attributes,





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    WP_Post Object
    (
        [ID] =>
        [post_author] =>
        [post_date] =>
        [post_date_gmt] =>
        [post_content] =>
        [post_title] =>
        [post_excerpt] =>
        [post_status] =>
        [comment_status] =>
        [ping_status] =>
        [post_password] =>
        [post_name] =>
        [to_ping] =>
        [pinged] =>
        [post_modified] =>
        [post_modified_gmt] =>
        [post_content_filtered] =>
        [post_parent] =>
        [guid] =>
        [menu_order] =>
        [post_type] =>
        [post_mime_type] =>
        [comment_count] =>
        [filter] =>
    )
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D2101%23feedback-editor-2101)

02. [Skip to note 24 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-3553)



    **Array of post IDs**



    To return ids instead of post objects use the `fields` argument.





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array('fields' => 'ids');
    $posts = get_posts($args);
    // if any posts are found $posts will be an array with their ids
    ```





    The `fields` argument can be set to `'ids'`, `'all'` ( _default_) or `'id=>parent'`. The last two (arguments) will return an array of stdClass objects.



    Source:

    [https://developer.wordpress.org/reference/classes/wp\_query/#return-fields-parameter](https://developer.wordpress.org/reference/classes/wp_query/#return-fields-parameter)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D3553%23feedback-editor-3553)

03. [Skip to note 25 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-811)



    Example to get the latest 10 posts in the blog:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array(
      'numberposts' => 10
    );

    $latest_posts = get_posts( $args );
    ```





    You can also pass the `post_type` argument if you want to get posts from a Custom Post Type, like:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array(
      'numberposts' => 10,
      'post_type'   => 'book'
    );

    $latest_books = get_posts( $args );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D811%23feedback-editor-811)

04. [Skip to note 26 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1196)



    **Custom Field Parameters**



    Show posts associated with a certain custom field. Following example displays posts from the ‘product’ post type that have meta key ‘featured’ with value ‘yes’, using ‘meta\_query’:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array(
    	'post_type'  => 'product',
    	'meta_query' => array(
    		array(
    			'key'   => 'featured',
    			'value' => 'yes',
    		)
    	)
    );
    $postslist = get_posts( $args );
    ```





    Refer to the custom fields parameters section of the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) documentation for more examples.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1196%23feedback-editor-1196)

05. [Skip to note 27 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1188)



    **Posts with Previous Next Navigation**



    You can also using the custom queries to make the post with Previous and Next Post Navigation. Here is the following method to make it workable.





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php
    $post_list = get_posts( array(
    	'orderby'    => 'menu_order',
    	'sort_order' => 'asc'
    ) );

    $posts = array();

    foreach ( $post_list as $post ) {
       $posts[] += $post->ID;
    }

    $current = array_search( get_the_ID(), $posts );

    $prevID = $posts[ $current-1 ];
    $nextID = $posts[ $current+1 ];
    ?>

    <div class="navigation">
    <?php if ( ! empty( $prevID ) ): ?>
    	<div class="alignleft">
    		<a href="<?php echo get_permalink( $prevID ); ?>" alt="<?php echo get_the_title( $prevID ); ?>">
    			<?php _e( 'Previous', 'textdomain' ); ?>
    		</a>
    	</div>
    <?php endif;

    if ( ! empty( $nextID ) ) : ?>
    	<div class="alignright">
    		<a href="<?php echo get_permalink( $nextID ); ?>" alt="<?php echo get_the_title( $nextID ); ?>">
    			<?php _e( 'Next', 'textdomain' ); ?>
    		</a>
    	</div>
    <?php endif; ?>
    </div><!-- .navigation -->
    ```





    **Reset after Postlists with offset**



    If you need after the loop, the post you had before joining the foreach, you can use this:





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <ul>
    	<?php
    	global $post;

    	$myposts = get_posts( array(
    		'posts_per_page' => 5,
    		'offset'         => 1,
    		'category'       => 1
    	) );

    	if ( $myposts ) {
    		foreach ( $myposts as $post ) :
    			setup_postdata( $post ); ?>
    			<li><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></li>
    		<?php
    		endforeach;
    		wp_reset_postdata();
    	}
    	?>
    </ul>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1188%23feedback-editor-1188)

06. [Skip to note 28 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1189)



    **Access all post data**



    Some post-related data is not available to get\_posts by default, such as post content through [the\_content()](https://developer.wordpress.org/reference/functions/the_content/) , or the numeric ID. This is resolved by calling an internal function [setup\_postdata()](https://developer.wordpress.org/reference/functions/setup_postdata/) , with the $post array as its argument:





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php
    $lastposts = get_posts( array(
    	'posts_per_page' => 3
    ) );

    if ( $lastposts ) {
    	foreach ( $lastposts as $post ) :
    		setup_postdata( $post ); ?>
    		<h2><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></h2>
    		<?php the_content(); ?>
    	<?php
    	endforeach;
    	wp_reset_postdata();
    }
    ```





    To access a post’s ID or content without calling [setup\_postdata()](https://developer.wordpress.org/reference/functions/setup_postdata/) , or in fact any post-specific data (data retained in the posts table), you can use $post->COLUMN, where COLUMN is the table column name for the data. So $post->ID holds the ID, $post->post\_content the content, and so on. To display or print this data on your page use the PHP echo command, like so:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php echo $post->ID; ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1189%23feedback-editor-1189)

07. [Skip to note 29 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1195)



    **Taxonomy Parameters**



    Show posts associated with certain taxonomy. If specifying a taxonomy registered to a custom post type then instead of using ‘category’ you would use ‘{custom\_taxonomy\_name}’. For instance, if you had a custom taxonomy called “genre” and wanted to only show posts from the “jazz” genre you would use the below code.





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $show_albums = get_posts( array(
    	 'posts_per_page' => 8,
    	 'orderby'        => 'rand',
    	 'post_type'      => 'albums',
    	 'genre'          => 'jazz',
    	 'post_status'    => 'publish'
    ) );
    ```





    Following example displays posts tagged with ‘jazz’, under ‘genre’ custom taxonomy, using ‘tax\_query’:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array(
    	'tax_query' => array(
    		array(
    			'taxonomy' => 'genre',
    			'field'    => 'slug',
    			'terms'    => 'jazz'
    		)
    	)
    );
    $postslist = get_posts( $args );
    ```





    Refer to the taxonomy parameters section of the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) documentation for more examples.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1195%23feedback-editor-1195)

08. [Skip to note 30 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-4148)



    Get all published posts of ANY post type:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $posts = get_posts( array(
      'post_type' => get_post_types(),
      'post_status' => 'publish',
      'numberposts' => -1,
    ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D4148%23feedback-editor-4148)

09. [Skip to note 31 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1194)



    **Get a post by its slug**



    Allows you to get a post ID by post slug.





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php
    $the_slug = 'my-slug';
    $args=array(
    	'name'           => $the_slug,
    	'post_type'      => 'post',
    	'post_status'    => 'publish',
    	'posts_per_page' => 1
    );
    $my_posts = get_posts( $args );

    if ( $my_posts ) {
    	printf( __( 'ID on the first post found %s', 'textdomain' ), esc_html( $my_posts[0]->ID ) );
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1194%23feedback-editor-1194)

10. [Skip to note 32 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-871)



    `orderby` also accepts the value `post__in`. (Note two underscores between post and in.) If you used `include` to retrieve specific posts, the posts will be supplied in the order you supplied to include. For example:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $posts = get_posts( array(
    	'include'   => '3,8,1,17',
    	'post_type' => 'attachment',
    	'orderby'   => 'post__in',
    ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D871%23feedback-editor-871)

11. [Skip to note 33 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-987)



    You can check all the parameters that can be used on `get_posts` on [https://codex.wordpress.org/Class\_Reference/WP\_Query#Parameters](https://codex.wordpress.org/Class_Reference/WP_Query#Parameters)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D987%23feedback-editor-987)

12. [Skip to note 34 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1192)



    **Show all attachments**



    Do this outside any Loops in your template.





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php
    $attachments = get_posts( array(
    	'post_type'      => 'attachment',
    	'posts_per_page' => 500,
    	'post_status'    => 'any',
    	'post_parent'    => null
    ) );

    if ( $attachments ) {
    	foreach ( $attachments as $post ) {
    		setup_postdata( $post );
    		the_title();
    		the_attachment_link( $post->ID, false );
    		the_excerpt();
    	}
    	wp_reset_postdata();
    }
    ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1192%23feedback-editor-1192)

13. [Skip to note 35 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1685)



    It is not considered an error condition if no posts are found based on the specified and default parameter values. Instead, an empty array (“ `array()`“) is returned by the function.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1685%23feedback-editor-1685)

14. [Skip to note 36 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-2516)



    Example to display posts or post type ‘album’, tagged with ‘jazz’ or ‘improv’ under the ‘genre’ custom taxonomy:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $args = array(
        'post_type' => 'album',
        'post_status' => 'publish',
        'tax_query' => array(
            array(
                'taxonomy' => 'genre',
                'field'    => 'slug',
                'terms'    => array( 'jazz', 'improv' )
            )
        )
    );
    $postslist = get_posts( $args );
    ```





    Note that the simple `'{custom_taxonomy_name}' => 'jazz'` has been deprecated in favor of `tax_query`. More complex examples can be found on [https://codex.wordpress.org/Class\_Reference/WP\_Query#Taxonomy\_Parameters](https://codex.wordpress.org/Class_Reference/WP_Query#Taxonomy_Parameters)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D2516%23feedback-editor-2516)

15. [Skip to note 37 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-5314)



    **To Find Post By Title**



    To find a post by its title the array key is ‘title’, **NOT** ‘post\_title’:





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $post_array = get_posts( array(
      'post_status' => 'publish',
      'title' => 'my_post_title',
    ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D5314%23feedback-editor-5314)

16. [Skip to note 38 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1190)



    **Latest posts ordered by title**



    To show the last ten posts sorted alphabetically in ascending order, the following will display their post date, title and excerpt:





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $postslist = get_posts( array(
    	'posts_per_page' => 10,
    	'order'          => 'ASC',
    	'orderby'        => 'title'
    ) );

    if ( $postslist ) {
    	foreach ( $postslist as $post ) :
    		setup_postdata( $post );
    		?>
    		<div>
    			<?php the_date(); ?>
    			<br />
    			<?php the_title(); ?>
    			<?php the_excerpt(); ?>
    		</div>
    	<?php
    	endforeach;
    	wp_reset_postdata();
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1190%23feedback-editor-1190)

17. [Skip to note 39 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1191)



    **Random posts**



    Display a list of 5 posts selected randomly by using the MySQL RAND() function for the orderby parameter value:





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <ul>
    	<?php
    	$rand_posts = get_posts( array(
    		'posts_per_page' => 5,
    		'orderby'        => 'rand'
    	) );

    	if ( $rand_posts ) {
    	foreach ( $rand_posts as $post ) :
    		setup_postdata( $post );
    		?>
    		<li><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></li>
    		<?php
    	endforeach;
    	wp_reset_postdata();
    	}
    	?>
    </ul>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1191%23feedback-editor-1191)

18. [Skip to note 40 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1193)



    **Show attachments for the current post**



    Do this inside The Loop (where $post->ID is available).





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $attachments = get_posts( array(
    	'post_type'      => 'attachment',
    	'posts_per_page' => -1,
    	'post_status'    => 'any',
    	'post_parent'    => $post->ID
    ) );

    if ( $attachments ) {
    	foreach ( $attachments as $attachment ) {
    		echo apply_filters( 'the_title' , $attachment->post_title );
    		the_attachment_link( $attachment->ID , false );
    	}
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1193%23feedback-editor-1193)

19. [Skip to note 41 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-3635)



    **Order results by post types names**



    If you have an array of custom post types you can also order the results by post\_type name, this works if you need to “group” the results.





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <?php
    		$args = array(
    			'posts_per_page' => 10,
    			'post_type'      => array('page','post'),
    			'post_status'    => 'publish',
    			'offset'	 => 0,
    			's'    		 => 'Lorem',
    			'orderby'        => 'post_type',
            		'order'          => 'ASC'
    		);
    		 $posts = get_posts( $args );
    ?>
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D3635%23feedback-editor-3635)

20. [Skip to note 42 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-6670)



    **Only Published Posts Will Be Found Unless Status Specified**



    If you are searching for a post that is in draft, private, etc status and _not_ in publish status, get\_posts will not find your post unless you include the post\_status in the array.





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    $post_array = get_posts( array(
    	'post_status' => get_post_stasuses(),
    	'title'       => 'my_post_title'
    ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D6670%23feedback-editor-6670)

21. [Skip to note 43 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-6718)



    If you use `any` as the `post_status`, it will return all post\_status except for `trash` and `auto-draft`.





    `wp-includes/post.php`
    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    // Returns any post status except trash and auto-draft
    $posts = get_posts( array( 'post_status' => 'any' ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D6718%23feedback-editor-6718)

22. [Skip to note 44 content](https://developer.wordpress.org/reference/functions/get_posts/#comment-content-1187)



    **Posts list with offset**



    If you have your blog configured to show just one post on the front page, but also want to list links to the previous five posts in category ID 1, you can use this:





    `wp-includes/post.php`
    [Expand code](https://developer.wordpress.org/reference/functions/get_posts/#)

    [Copy](https://developer.wordpress.org/reference/functions/get_posts/#)




    ```php
    <ul>
    	<?php
    	$myposts = get_posts( $array(
    		'posts_per_page' => 5,
    		'offset'         => 1,
    		'category'       => 1
    	) );

    	if ( $myposts ) {
    		foreach ( $myposts as $post ) :
    			setup_postdata( $post );
    			?>
    			<li>
    				<a href="<?php the_permalink(); ?>"><?php the_title(); ?></a>
    			</li>
    		<?php
    		endforeach;
    		wp_reset_postdata();
    	}
    	?>
    </ul>
    ```





    Note: With use of the offset, the above query should be used only on a category that has more than one post in it, otherwise there’ll be no output.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F%3Freplytocom%3D1187%23feedback-editor-1187)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_posts%2F) before being able to contribute a note or feedback.

Notifications