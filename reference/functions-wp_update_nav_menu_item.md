---
url: https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item
scraped_at: 2025-10-20T03:15:39.079Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_update\_nav\_menu\_item()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_update\_nav\_menu\_item()

Search

# wp\_update\_nav\_menu\_item( int$menu\_id, int$menu\_item\_db\_id, array$menu\_item\_data = array(), bool$fire\_after\_hooks = true ): int\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#wp--skip-link--target)

Saves the properties of a menu item or create a new one.

## [Description](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#description)

The menu-item-title, menu-item-description and menu-item-attr-title are expected to be pre-slashed since they are passed directly to APIs that expect slashed data.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#parameters)

`$menu_id` intrequired

The ID of the menu. If 0, makes the menu item a draft orphan.

`$menu_item_db_id` intrequired

The ID of the menu item. If 0, creates a new menu item.

`$menu_item_data` arrayoptional

The menu item’s data.

Default: `array()`

`$fire_after_hooks` booloptional

Whether to fire the after insert hooks.

Default: `true`

## [Return](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#return)

int\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) The menu item’s database ID or [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) object on failure.

## [Source](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#source)

`wp-includes/nav-menu.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

```php
function wp_update_nav_menu_item( $menu_id = 0, $menu_item_db_id = 0, $menu_item_data = array(), $fire_after_hooks = true ) {
	$menu_id         = (int) $menu_id;
	$menu_item_db_id = (int) $menu_item_db_id;

	// Make sure that we don't convert non-nav_menu_item objects into nav_menu_item objects.
	if ( ! empty( $menu_item_db_id ) && ! is_nav_menu_item( $menu_item_db_id ) ) {
		return new WP_Error( 'update_nav_menu_item_failed', __( 'The given object ID is not that of a menu item.' ) );
	}

	$menu = wp_get_nav_menu_object( $menu_id );

	if ( ! $menu && 0 !== $menu_id ) {
		return new WP_Error( 'invalid_menu_id', __( 'Invalid menu ID.' ) );
	}

	if ( is_wp_error( $menu ) ) {
		return $menu;
	}

	$defaults = array(
		'menu-item-db-id'         => $menu_item_db_id,
		'menu-item-object-id'     => 0,
		'menu-item-object'        => '',
		'menu-item-parent-id'     => 0,
		'menu-item-position'      => 0,
		'menu-item-type'          => 'custom',
		'menu-item-title'         => '',
		'menu-item-url'           => '',
		'menu-item-description'   => '',
		'menu-item-attr-title'    => '',
		'menu-item-target'        => '',
		'menu-item-classes'       => '',
		'menu-item-xfn'           => '',
		'menu-item-status'        => '',
		'menu-item-post-date'     => '',
		'menu-item-post-date-gmt' => '',
	);

	$args = wp_parse_args( $menu_item_data, $defaults );

	if ( 0 === $menu_id ) {
		$args['menu-item-position'] = 1;
	} elseif ( 0 === (int) $args['menu-item-position'] ) {
		$menu_items = array();

		if ( 0 !== $menu_id ) {
			$menu_items = (array) wp_get_nav_menu_items( $menu_id, array( 'post_status' => 'publish,draft' ) );
		}

		$last_item = array_pop( $menu_items );

		if ( $last_item && isset( $last_item->menu_order ) ) {
			$args['menu-item-position'] = 1 + $last_item->menu_order;
		} else {
			$args['menu-item-position'] = count( $menu_items );
		}
	}

	$original_parent = 0 < $menu_item_db_id ? get_post_field( 'post_parent', $menu_item_db_id ) : 0;

	if ( 'custom' === $args['menu-item-type'] ) {
		// If custom menu item, trim the URL.
		$args['menu-item-url'] = trim( $args['menu-item-url'] );
	} else {
		/*
		 * If non-custom menu item, then:
		 * - use the original object's URL.
		 * - blank default title to sync with the original object's title.
		 */

		$args['menu-item-url'] = '';

		$original_title = '';

		if ( 'taxonomy' === $args['menu-item-type'] ) {
			$original_object = get_term( $args['menu-item-object-id'], $args['menu-item-object'] );

			if ( $original_object instanceof WP_Term ) {
				$original_parent = get_term_field( 'parent', $args['menu-item-object-id'], $args['menu-item-object'], 'raw' );
				$original_title  = get_term_field( 'name', $args['menu-item-object-id'], $args['menu-item-object'], 'raw' );
			}
		} elseif ( 'post_type' === $args['menu-item-type'] ) {
			$original_object = get_post( $args['menu-item-object-id'] );

			if ( $original_object instanceof WP_Post ) {
				$original_parent = (int) $original_object->post_parent;
				$original_title  = $original_object->post_title;
			}
		} elseif ( 'post_type_archive' === $args['menu-item-type'] ) {
			$original_object = get_post_type_object( $args['menu-item-object'] );

			if ( $original_object instanceof WP_Post_Type ) {
				$original_title = $original_object->labels->archives;
			}
		}

		if ( wp_unslash( $args['menu-item-title'] ) === wp_specialchars_decode( $original_title ) ) {
			$args['menu-item-title'] = '';
		}

		// Hack to get wp to create a post object when too many properties are empty.
		if ( '' === $args['menu-item-title'] && '' === $args['menu-item-description'] ) {
			$args['menu-item-description'] = ' ';
		}
	}

	// Populate the menu item object.
	$post = array(
		'menu_order'   => $args['menu-item-position'],
		'ping_status'  => 0,
		'post_content' => $args['menu-item-description'],
		'post_excerpt' => $args['menu-item-attr-title'],
		'post_parent'  => $original_parent,
		'post_title'   => $args['menu-item-title'],
		'post_type'    => 'nav_menu_item',
	);

	$post_date = wp_resolve_post_date( $args['menu-item-post-date'], $args['menu-item-post-date-gmt'] );
	if ( $post_date ) {
		$post['post_date'] = $post_date;
	}

	$update = 0 !== $menu_item_db_id;

	// New menu item. Default is draft status.
	if ( ! $update ) {
		$post['ID']          = 0;
		$post['post_status'] = 'publish' === $args['menu-item-status'] ? 'publish' : 'draft';
		$menu_item_db_id     = wp_insert_post( $post, true, $fire_after_hooks );
		if ( ! $menu_item_db_id || is_wp_error( $menu_item_db_id ) ) {
			return $menu_item_db_id;
		}

		/**
		 * Fires immediately after a new navigation menu item has been added.
		 *
		 * @since 4.4.0
		 *
		 * @see wp_update_nav_menu_item()
		 *
		 * @param int   $menu_id         ID of the updated menu.
		 * @param int   $menu_item_db_id ID of the new menu item.
		 * @param array $args            An array of arguments used to update/add the menu item.
		 */
		do_action( 'wp_add_nav_menu_item', $menu_id, $menu_item_db_id, $args );
	}

	/*
	 * Associate the menu item with the menu term.
	 * Only set the menu term if it isn't set to avoid unnecessary wp_get_object_terms().
	 */
	if ( $menu_id && ( ! $update || ! is_object_in_term( $menu_item_db_id, 'nav_menu', (int) $menu->term_id ) ) ) {
		$update_terms = wp_set_object_terms( $menu_item_db_id, array( $menu->term_id ), 'nav_menu' );
		if ( is_wp_error( $update_terms ) ) {
			return $update_terms;
		}
	}

	if ( 'custom' === $args['menu-item-type'] ) {
		$args['menu-item-object-id'] = $menu_item_db_id;
		$args['menu-item-object']    = 'custom';
	}

	$menu_item_db_id = (int) $menu_item_db_id;

	// Reset invalid `menu_item_parent`.
	if ( (int) $args['menu-item-parent-id'] === $menu_item_db_id ) {
		$args['menu-item-parent-id'] = 0;
	}

	update_post_meta( $menu_item_db_id, '_menu_item_type', sanitize_key( $args['menu-item-type'] ) );
	update_post_meta( $menu_item_db_id, '_menu_item_menu_item_parent', (string) ( (int) $args['menu-item-parent-id'] ) );
	update_post_meta( $menu_item_db_id, '_menu_item_object_id', (string) ( (int) $args['menu-item-object-id'] ) );
	update_post_meta( $menu_item_db_id, '_menu_item_object', sanitize_key( $args['menu-item-object'] ) );
	update_post_meta( $menu_item_db_id, '_menu_item_target', sanitize_key( $args['menu-item-target'] ) );

	$args['menu-item-classes'] = array_map( 'sanitize_html_class', explode( ' ', $args['menu-item-classes'] ) );
	$args['menu-item-xfn']     = implode( ' ', array_map( 'sanitize_html_class', explode( ' ', $args['menu-item-xfn'] ) ) );
	update_post_meta( $menu_item_db_id, '_menu_item_classes', $args['menu-item-classes'] );
	update_post_meta( $menu_item_db_id, '_menu_item_xfn', $args['menu-item-xfn'] );
	update_post_meta( $menu_item_db_id, '_menu_item_url', sanitize_url( $args['menu-item-url'] ) );

	if ( 0 === $menu_id ) {
		update_post_meta( $menu_item_db_id, '_menu_item_orphaned', (string) time() );
	} elseif ( get_post_meta( $menu_item_db_id, '_menu_item_orphaned' ) ) {
		delete_post_meta( $menu_item_db_id, '_menu_item_orphaned' );
	}

	// Update existing menu item. Default is publish status.
	if ( $update ) {
		$post['ID']          = $menu_item_db_id;
		$post['post_status'] = ( 'draft' === $args['menu-item-status'] ) ? 'draft' : 'publish';

		$update_post = wp_update_post( $post, true );
		if ( is_wp_error( $update_post ) ) {
			return $update_post;
		}
	}

	/**
	 * Fires after a navigation menu item has been updated.
	 *
	 * @since 3.0.0
	 *
	 * @see wp_update_nav_menu_item()
	 *
	 * @param int   $menu_id         ID of the updated menu.
	 * @param int   $menu_item_db_id ID of the updated menu item.
	 * @param array $args            An array of arguments used to update a menu item.
	 */
	do_action( 'wp_update_nav_menu_item', $menu_id, $menu_item_db_id, $args );

	return $menu_item_db_id;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/nav-menu.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/nav-menu.php#L421) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/nav-menu.php#L421-L634)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#hooks)

[do\_action( ‘wp\_add\_nav\_menu\_item’, int$menu\_id, int$menu\_item\_db\_id, array$args )](https://developer.wordpress.org/reference/hooks/wp_add_nav_menu_item/)

Fires immediately after a new navigation menu item has been added.

[do\_action( ‘wp\_update\_nav\_menu\_item’, int$menu\_id, int$menu\_item\_db\_id, array$args )](https://developer.wordpress.org/reference/hooks/wp_update_nav_menu_item/)

Fires after a navigation menu item has been updated.

## [Related](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#related)

| Uses | Description |
| --- | --- |
| [wp\_resolve\_post\_date()](https://developer.wordpress.org/reference/functions/wp_resolve_post_date/) `wp-includes/post.php` | Uses wp\_checkdate to return a valid Gregorian-calendar value for post\_date. |
| [wp\_specialchars\_decode()](https://developer.wordpress.org/reference/functions/wp_specialchars_decode/) `wp-includes/formatting.php` | Converts a number of HTML entities into their special characters. |
| [sanitize\_url()](https://developer.wordpress.org/reference/functions/sanitize_url/) `wp-includes/formatting.php` | Sanitizes a URL for database or redirect usage. |
| [is\_object\_in\_term()](https://developer.wordpress.org/reference/functions/is_object_in_term/) `wp-includes/taxonomy.php` | Determines if the given object is associated with any of the given terms. |
| [wp\_set\_object\_terms()](https://developer.wordpress.org/reference/functions/wp_set_object_terms/) `wp-includes/taxonomy.php` | Creates term and taxonomy relationships. |
| [get\_term\_field()](https://developer.wordpress.org/reference/functions/get_term_field/) `wp-includes/taxonomy.php` | Gets sanitized term field. |
| [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) `wp-includes/post.php` | Inserts or update a post. |
| [wp\_update\_post()](https://developer.wordpress.org/reference/functions/wp_update_post/) `wp-includes/post.php` | Updates a post with new post data. |
| [update\_post\_meta()](https://developer.wordpress.org/reference/functions/update_post_meta/) `wp-includes/post.php` | Updates a post meta field based on the given post ID. |
| [delete\_post\_meta()](https://developer.wordpress.org/reference/functions/delete_post_meta/) `wp-includes/post.php` | Deletes a post meta field for the given post ID. |
| [get\_post\_field()](https://developer.wordpress.org/reference/functions/get_post_field/) `wp-includes/post.php` | Retrieves data from a post field based on Post ID. |
| [is\_nav\_menu\_item()](https://developer.wordpress.org/reference/functions/is_nav_menu_item/) `wp-includes/nav-menu.php` | Determines whether the given ID is a nav menu item. |
| [wp\_get\_nav\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_items/) `wp-includes/nav-menu.php` | Retrieves all menu items of a navigation menu. |
| [wp\_get\_nav\_menu\_object()](https://developer.wordpress.org/reference/functions/wp_get_nav_menu_object/) `wp-includes/nav-menu.php` | Returns a navigation menu object. |
| [wp\_unslash()](https://developer.wordpress.org/reference/functions/wp_unslash/) `wp-includes/formatting.php` | Removes slashes from a string or recursively removes slashes from strings within an array. |
| [sanitize\_key()](https://developer.wordpress.org/reference/functions/sanitize_key/) `wp-includes/formatting.php` | Sanitizes a string key. |
| [wp\_parse\_args()](https://developer.wordpress.org/reference/functions/wp_parse_args/) `wp-includes/functions.php` | Merges user defined arguments into defaults array. |
| [get\_term()](https://developer.wordpress.org/reference/functions/get_term/) `wp-includes/taxonomy.php` | Gets all term data from database by term ID. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [get\_post\_meta()](https://developer.wordpress.org/reference/functions/get_post_meta/) `wp-includes/post.php` | Retrieves a post meta field for the given post ID. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |
| [get\_post\_type\_object()](https://developer.wordpress.org/reference/functions/get_post_type_object/) `wp-includes/post.php` | Retrieves a post type object by name. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 19 more](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#) [Show less](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Menu\_Items\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Creates a single nav menu item. |
| [WP\_REST\_Menu\_Items\_Controller::update\_item()](https://developer.wordpress.org/reference/classes/wp_rest_menu_items_controller/update_item/) `wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php` | Updates a single nav menu item. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::update()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/update/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Creates/updates the nav\_menu\_item post for this setting. |
| [wp\_nav\_menu\_update\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_nav_menu_update_menu_items/) `wp-admin/includes/nav-menu.php` | Saves nav menu items. |
| [wp\_save\_nav\_menu\_items()](https://developer.wordpress.org/reference/functions/wp_save_nav_menu_items/) `wp-admin/includes/nav-menu.php` | Save posted nav menu item data. |
| [\_wp\_auto\_add\_pages\_to\_menu()](https://developer.wordpress.org/reference/functions/_wp_auto_add_pages_to_menu/) `wp-includes/nav-menu.php` | Automatically add newly published page objects to menus with that as an option. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#) [Show less](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#changelog)

| Version | Description |
| --- | --- |
| [5.9.0](https://developer.wordpress.org/reference/since/5.9.0/) | Added the `$fire_after_hooks` parameter. |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#comment-content-2334)



The `$menu_item_data` argument accepts an array of data. Depending upon the type of nav menu item you are attempting to add, it requires different parameters:



Note that in several cases, `menu-item-object` must be included, and it must be set to the post type of the nav item you are referencing.



**Page**





`wp-includes/nav-menu.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
$page = get_post(123); // etc
wp_update_nav_menu_item($menu_id, 0, array(
       'menu-item-title' => 'My Link',
       'menu-item-object-id' => $page->ID,
       'menu-item-object' => 'page',
       'menu-item-status' => 'publish',
       'menu-item-type' => 'post_type',
));
```





**Post**





`wp-includes/nav-menu.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
$post = get_post(123); // etc
wp_update_nav_menu_item($menu_id, 0, array(
       'menu-item-title' => 'My Link',
       'menu-item-object-id' => $post->ID,
       'menu-item-object' => 'post',
       'menu-item-status' => 'publish',
       'menu-item-type' => 'post_type',
));
```





**Custom**



When adding a custom link to your nav menu, you can omit the `menu-item-type` because it defaults to `custom`.





`wp-includes/nav-menu.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
wp_update_nav_menu_item($menu_id, 0, array(
       'menu-item-title' => 'My Link',
       'menu-item-url' => 'http://example.com/',
       'menu-item-status' => 'publish',
       'menu-item-type' => 'custom', // optional
));
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_nav_menu_item%2F%3Freplytocom%3D2334%23feedback-editor-2334)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#comment-content-5031)



When adding a link for a custom post type.



In addition to the other minimum required parameters, pass these values to the $menu\_item\_data parameter:





`wp-includes/nav-menu.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
'menu-item-object'	=> 'your-registered-post-type-name', // i.e., foo-bar, foo_bar, 'event-scheduler'
'menu-item-type' 	=> 'post_type',

// For example:
$menu_item_data = [\
   	'menu-item-object-id'   => $post->ID, // Or however, you get the post's id.\
   	'menu-item-object'      => 'wpdocs-foo-bar',\
   	'menu-item-type'        => 'post_type',\
   	'menu-item-status'      => 'publish',\
   	'menu-item-title'       => esc_html__( 'It\'s all Foo Bar' ),\
   	'menu-item-description' => esc_html__( 'Page about how, It\'s all Foo Bar' ),\
   	'menu-item-classes'     => 'wpdocs-foo-bar',\
];

wp_update_nav_menu_item( $menu_id, 0, $menu_item_data )
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_nav_menu_item%2F%3Freplytocom%3D5031%23feedback-editor-5031)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#comment-content-5975)



Example on how to work with taxonomies: automatically add a new menu item when a new woocommerce product category has been created. Also if it’s a subcategory – add it as a respective subitem.





`wp-includes/nav-menu.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
// on woocommerce product category creation add it to menu:

add_action( 'create_product_cat', 'wpdocs_add_menu_item_on_create_product_cat' );

function wpdocs_add_menu_item_on_create_product_cat( $term_id ) {
   	// get target menu from menu location:
   	$menu_ids = get_nav_menu_locations();
   	$menu_id = $menu_ids['menu-1'];
   	$args = array(
   		'menu-item-object-id' => $term_id,
   		'menu-item-object'    => 'product_cat',
   		'menu-item-type'      => 'taxonomy',
   		'menu-item-status'    => 'publish',
   	);

   	// also check if current category is a subcategory, and if so,
   	// if it's parent category has a menu item - then assign current item
   	// as a subitem to that:
   	$parent_term_id = get_term_field( 'parent', $term_id, 'product_cat', 'raw' );

   	if ( $parent_term_id ) {
   		$parent_term_menu_item = get_posts( array(
   			'numberposts' => 1,
   			'post_type'   => 'nav_menu_item',
   			'meta_key'    => '_menu_item_object_id',
   			'meta_value'  => $parent_term_id,
   			'fields'      => 'ids'
   		) );

   		if ( ! empty( $parent_term_menu_item ) ) {
   			$args['menu-item-parent-id'] = $parent_term_menu_item[0];
   		}
   	}

   	wp_update_nav_menu_item( $menu_id, 0, $args );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_nav_menu_item%2F%3Freplytocom%3D5975%23feedback-editor-5975)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#comment-content-6902)



If you’re updating an existing menu item and want to keep the ordering, pass `'menu-item-position'`. Otherwise, the item will move to the end of the menu.





`wp-includes/nav-menu.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/#)




```php
$menu_item_data = array(
       'menu-item-position' => $item->menu_order,
       'menu-item-parent-id' => $item->menu_item_parent,
       'menu-item-type' => 'custom',
       'menu-item-url' => $url,
       'menu-item-title' => $item->title,
       'menu-item-status' => $item->post_status,
);
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_nav_menu_item%2F%3Freplytocom%3D6902%23feedback-editor-6902)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_nav_menu_item%2F) before being able to contribute a note or feedback.

Notifications