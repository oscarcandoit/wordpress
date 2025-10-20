---
url: https://developer.wordpress.org/reference/functions/register_meta
scraped_at: 2025-10-20T03:26:41.442Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/register_meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

register\_meta()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)register\_meta()

Search

# register\_meta( string$object\_type, string$meta\_key, array$args, string\|array$deprecated = null ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/register_meta/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/register_meta/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/register_meta/#return)
- [Source](https://developer.wordpress.org/reference/functions/register_meta/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/register_meta/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/register_meta/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/register_meta/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/register_meta/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/register_meta/#wp--skip-link--target)

Registers a meta key.

## [Description](https://developer.wordpress.org/reference/functions/register_meta/\#description)

It is recommended to register meta keys for a specific combination of object type and object subtype. If passing an object subtype is omitted, the meta key will be registered for the entire object type, however it can be partly overridden in case a more specific meta key of the same name exists for the same object type and a subtype.

If an object type does not support any subtypes, such as users or comments, you should commonly call this function without passing a subtype.

## [Parameters](https://developer.wordpress.org/reference/functions/register_meta/\#parameters)

`$object_type` stringrequired

Type of object metadata is for. Accepts `'post'`, `'comment'`, `'term'`, `'user'`, or any other object type with an associated meta table.

`$meta_key` stringrequired

Meta key to register.

`$args` arrayrequired

Data used to describe the meta key when registered.

- `object_subtype` string
A subtype; e.g. if the object type is "post", the post type. If left empty, the meta key will be registered on the entire object type. Default empty.

- `type` string
The type of data associated with this meta key.


Valid values are `'string'`, `'boolean'`, `'integer'`, `'number'`, `'array'`, and `'object'`.

- `label` string
A human-readable label of the data attached to this meta key.

- `description` string
A description of the data attached to this meta key.

- `single` bool
Whether the meta key has one value per object, or an array of values per object.

- `default` mixed
The default value returned from [get\_metadata()](https://developer.wordpress.org/reference/functions/get_metadata/) if no value has been set yet.


When using a non-single meta key, the default value is for the first entry.


In other words, when calling [get\_metadata()](https://developer.wordpress.org/reference/functions/get_metadata/) with `$single` set to `false`, the default value given here will be wrapped in an array.

- `sanitize_callback` callable
A function or method to call when sanitizing `$meta_key` data.

- `auth_callback` callable
Optional. A function or method to call when performing edit\_post\_meta, add\_post\_meta, and delete\_post\_meta capability checks.

- `show_in_rest` bool\|array
Whether data associated with this meta key can be considered public and should be accessible via the REST API. A custom post type must also declare support for custom fields for registered meta to be accessible via REST.


When registering complex meta values this argument may optionally be an array with `'schema'` or `'prepare_callback'` keys instead of a boolean.

- `revisions_enabled` bool
Whether to enable revisions support for this meta\_key. Can only be used when the object type is `'post'`.


`$deprecated` string\|arrayoptional

Deprecated. Use `$args` instead.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/register_meta/\#return)

bool True if the meta key was successfully registered in the global array, false if not.

Registering a meta key with distinct sanitize and auth callbacks will fire those callbacks, but will not add to the global registry.

## [Source](https://developer.wordpress.org/reference/functions/register_meta/\#source)

`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_meta/#)

[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)

```php
function register_meta( $object_type, $meta_key, $args, $deprecated = null ) {
	global $wp_meta_keys;

	if ( ! is_array( $wp_meta_keys ) ) {
		$wp_meta_keys = array();
	}

	$defaults = array(
		'object_subtype'    => '',
		'type'              => 'string',
		'label'             => '',
		'description'       => '',
		'default'           => '',
		'single'            => false,
		'sanitize_callback' => null,
		'auth_callback'     => null,
		'show_in_rest'      => false,
		'revisions_enabled' => false,
	);

	// There used to be individual args for sanitize and auth callbacks.
	$has_old_sanitize_cb = false;
	$has_old_auth_cb     = false;

	if ( is_callable( $args ) ) {
		$args = array(
			'sanitize_callback' => $args,
		);

		$has_old_sanitize_cb = true;
	} else {
		$args = (array) $args;
	}

	if ( is_callable( $deprecated ) ) {
		$args['auth_callback'] = $deprecated;
		$has_old_auth_cb       = true;
	}

	/**
	 * Filters the registration arguments when registering meta.
	 *
	 * @since 4.6.0
	 *
	 * @param array  $args        Array of meta registration arguments.
	 * @param array  $defaults    Array of default arguments.
	 * @param string $object_type Type of object metadata is for. Accepts 'post', 'comment', 'term', 'user',
	 *                            or any other object type with an associated meta table.
	 * @param string $meta_key    Meta key.
	 */
	$args = apply_filters( 'register_meta_args', $args, $defaults, $object_type, $meta_key );
	unset( $defaults['default'] );
	$args = wp_parse_args( $args, $defaults );

	// Require an item schema when registering array meta.
	if ( false !== $args['show_in_rest'] && 'array' === $args['type'] ) {
		if ( ! is_array( $args['show_in_rest'] ) || ! isset( $args['show_in_rest']['schema']['items'] ) ) {
			_doing_it_wrong( __FUNCTION__, __( 'When registering an "array" meta type to show in the REST API, you must specify the schema for each array item in "show_in_rest.schema.items".' ), '5.3.0' );

			return false;
		}
	}

	$object_subtype = ! empty( $args['object_subtype'] ) ? $args['object_subtype'] : '';
	if ( $args['revisions_enabled'] ) {
		if ( 'post' !== $object_type ) {
			_doing_it_wrong( __FUNCTION__, __( 'Meta keys cannot enable revisions support unless the object type supports revisions.' ), '6.4.0' );

			return false;
		} elseif ( ! empty( $object_subtype ) && ! post_type_supports( $object_subtype, 'revisions' ) ) {
			_doing_it_wrong( __FUNCTION__, __( 'Meta keys cannot enable revisions support unless the object subtype supports revisions.' ), '6.4.0' );

			return false;
		}
	}

	// If `auth_callback` is not provided, fall back to `is_protected_meta()`.
	if ( empty( $args['auth_callback'] ) ) {
		if ( is_protected_meta( $meta_key, $object_type ) ) {
			$args['auth_callback'] = '__return_false';
		} else {
			$args['auth_callback'] = '__return_true';
		}
	}

	// Back-compat: old sanitize and auth callbacks are applied to all of an object type.
	if ( is_callable( $args['sanitize_callback'] ) ) {
		if ( ! empty( $object_subtype ) ) {
			add_filter( "sanitize_{$object_type}_meta_{$meta_key}_for_{$object_subtype}", $args['sanitize_callback'], 10, 4 );
		} else {
			add_filter( "sanitize_{$object_type}_meta_{$meta_key}", $args['sanitize_callback'], 10, 3 );
		}
	}

	if ( is_callable( $args['auth_callback'] ) ) {
		if ( ! empty( $object_subtype ) ) {
			add_filter( "auth_{$object_type}_meta_{$meta_key}_for_{$object_subtype}", $args['auth_callback'], 10, 6 );
		} else {
			add_filter( "auth_{$object_type}_meta_{$meta_key}", $args['auth_callback'], 10, 6 );
		}
	}

	if ( array_key_exists( 'default', $args ) ) {
		$schema = $args;
		if ( is_array( $args['show_in_rest'] ) && isset( $args['show_in_rest']['schema'] ) ) {
			$schema = array_merge( $schema, $args['show_in_rest']['schema'] );
		}

		$check = rest_validate_value_from_schema( $args['default'], $schema );
		if ( is_wp_error( $check ) ) {
			_doing_it_wrong( __FUNCTION__, __( 'When registering a default meta value the data must match the type provided.' ), '5.5.0' );

			return false;
		}

		if ( ! has_filter( "default_{$object_type}_metadata", 'filter_default_metadata' ) ) {
			add_filter( "default_{$object_type}_metadata", 'filter_default_metadata', 10, 5 );
		}
	}

	// Global registry only contains meta keys registered with the array of arguments added in 4.6.0.
	if ( ! $has_old_auth_cb && ! $has_old_sanitize_cb ) {
		unset( $args['object_subtype'] );

		$wp_meta_keys[ $object_type ][ $object_subtype ][ $meta_key ] = $args;

		return true;
	}

	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/meta.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/meta.php#L1418) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/meta.php#L1418-L1548)

## [Hooks](https://developer.wordpress.org/reference/functions/register_meta/\#hooks)

[apply\_filters( ‘register\_meta\_args’, array$args, array$defaults, string$object\_type, string$meta\_key )](https://developer.wordpress.org/reference/hooks/register_meta_args/)

Filters the registration arguments when registering meta.

## [Related](https://developer.wordpress.org/reference/functions/register_meta/\#related)

| Uses | Description |
| --- | --- |
| [rest\_validate\_value\_from\_schema()](https://developer.wordpress.org/reference/functions/rest_validate_value_from_schema/) `wp-includes/rest-api.php` | Validate a value based on a schema. |
| [has\_filter()](https://developer.wordpress.org/reference/functions/has_filter/) `wp-includes/plugin.php` | Checks if any filter has been registered for a hook. |
| [post\_type\_supports()](https://developer.wordpress.org/reference/functions/post_type_supports/) `wp-includes/post.php` | Checks a post type’s support for a given feature. |
| [is\_protected\_meta()](https://developer.wordpress.org/reference/functions/is_protected_meta/) `wp-includes/meta.php` | Determines whether a meta key is considered protected. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |
| [wp\_parse\_args()](https://developer.wordpress.org/reference/functions/wp_parse_args/) `wp-includes/functions.php` | Merges user defined arguments into defaults array. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) `wp-includes/plugin.php` | Adds a callback function to a filter hook. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 5 more](https://developer.wordpress.org/reference/functions/register_meta/#) [Show less](https://developer.wordpress.org/reference/functions/register_meta/#)

| Used by | Description |
| --- | --- |
| [wp\_register\_persisted\_preferences\_meta()](https://developer.wordpress.org/reference/functions/wp_register_persisted_preferences_meta/) `wp-includes/user.php` | Registers the user meta property for persisted preferences. |
| [register\_term\_meta()](https://developer.wordpress.org/reference/functions/register_term_meta/) `wp-includes/taxonomy.php` | Registers a meta key for terms. |
| [register\_post\_meta()](https://developer.wordpress.org/reference/functions/register_post_meta/) `wp-includes/post.php` | Registers a meta key for posts. |

## [Changelog](https://developer.wordpress.org/reference/functions/register_meta/\#changelog)

| Version | Description |
| --- | --- |
| [6.7.0](https://developer.wordpress.org/reference/since/6.7.0/) | The `label` argument was added to the arguments array. |
| [6.4.0](https://developer.wordpress.org/reference/since/6.4.0/) | The `$revisions_enabled` argument was added to the arguments array. |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | The `$default` argument was added to the arguments array. |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Valid meta types expanded to include "array" and "object". |
| [4.9.8](https://developer.wordpress.org/reference/since/4.9.8/) | The `$object_subtype` argument was added to the arguments array. |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | [Modified to support an array of data to attach to registered meta keys](https://core.trac.wordpress.org/ticket/35658). Previous arguments for `$sanitize_callback` and `$auth_callback` have been folded into this array. |
| [3.3.0](https://developer.wordpress.org/reference/since/3.3.0/) | Introduced. |

[Show 2 more](https://developer.wordpress.org/reference/functions/register_meta/#) [Show less](https://developer.wordpress.org/reference/functions/register_meta/#)

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/register_meta/\#user-contributed-notes)

1. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-2483)



The values of `$object_type` are not documented but I found.

`post` for all post types, `term` for all taxonomies.


There might be other ‘objects’.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D2483%23feedback-editor-2483)

2. [Skip to note 11 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-2933)



As of WordPress 4.9.8 you can use the `object_subtype` parameter to specify a custom post type. Previously you could only register for all post types. For example to register a meta key `my_meta` for only the `my_article` custom post type:





`wp-includes/meta.php`
[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
register_meta('post', 'my_meta', [\
     'object_subtype' => 'my_article',\
     'show_in_rest' => true\
]);
```





Or you can use the new `register_post_meta` function.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D2933%23feedback-editor-2933)

3. [Skip to note 12 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-3416)



For custom meta fields to be returned in the REST API for a custom post type the REST API Handbook notes that the post type **must support custom-fields** in order for the registered meta field to display.



From the handbook:



“Note that for meta fields registered on custom post types, the post type must have custom-fields support. Otherwise the meta fields will not appear in the REST API.”



Source: [https://developer.wordpress.org/rest-api/extending-the-rest-api/modifying-responses/#read-and-write-a-post-meta-field-in-post-responses](https://developer.wordpress.org/rest-api/extending-the-rest-api/modifying-responses/#read-and-write-a-post-meta-field-in-post-responses)





[Show feedback (1)](https://developer.wordpress.org/reference/functions/register_meta/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D3416%23feedback-editor-3416)



- This is also essential for saving values. If the post type doesn’t support `custom-fields`, the values will NOT be saved to the database.



[Mark Howells-Mead](https://profiles.wordpress.org/markhowellsmead/) [3 years ago](https://developer.wordpress.org/reference/functions/register_meta/#comment-6002)


4. [Skip to note 13 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-2061)



As of WordPress 4.7, you can use the function as follows. This will be expanded in future versions.





`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_meta/#)

[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
$object_type = 'post'; // The object type.
   	// For custom post types, this is 'post', for custom comment types, this is 'comment'.

$args1 = array(
       'type'		=> 'string', // Validate and sanitize the meta value as a string.
   		// Default: 'string'.
       	// In 4.7 one of 'string', 'boolean', 'integer', 'number' must be used as 'type'.
       'description'    => 'A meta key associated with a string meta value.', // Shown in the schema for the meta key.
       'single'        => true, // Return a single value of the type. Default: false.
       'show_in_rest'    => true, // Show in the WP REST API response. Default: false.
);

register_meta( $object_type, 'my_postmeta_key', $args1 );


$args2 = array(
       'type'             => 'string', // Validate and sanitize the meta value as a string.
       'description'    => 'A meta key associated with a string meta value.', // Shown in the schema for the meta key.
       'single'        => false, // Return an array with the type used as the items type. Default: false.
       'show_in_rest'    => true, // Show in the WP REST API response. Default: false.
);

register_meta( 'user', 'my_usermeta_key', $args2 );
```





This will return the meta key and meta value in the meta object in the response. For example, an individual post response where id=8 and a meta key \`my\_postmeta\_key\` as registered above:





`wp-includes/meta.php`
[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```js
{
     "id": 8, // the post id
    	...
     "meta": {
       "my_postmeta_key": "the meta value"
     },
   	...
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D2061%23feedback-editor-2061)

5. [Skip to note 14 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-4155)



Prior to WordPress 5.5, the defaults for a custom meta field to be made available to the REST API could only be achieved like this:



(Consider registering a custom checkbox field for certain user input – for example, a post type title toggle)





`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_meta/#)

[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
register_meta(
        'post',
        '_custom_meta_key',
        array(
            'single'       => true,
            'type'         => 'boolean', // or any valid data type
            'show_in_rest' => array(
                'schema' => array(
                    'type'  => 'boolean', // Should match the expected data type
                    'default' => true,
                ),
            ),
        )
    );
```





With WordPress 5.5, this could be done with the additional argument `default`, like this:





`wp-includes/meta.php`
[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
register_meta(
        'post',
        '_custom_meta_key',
        array(
            'single'       => true,
            'type'         => 'boolean',
            'default'      => true, // this is what really does the trick instead of supplying REST schema
            'show_in_rest' => true,
        )
    );
```





_Worth noting,_ this could really be helpful while extending block editor sidebar to make custom fields available via [custom meta boxes](https://developer.wordpress.org/block-editor/tutorials/metabox/). Setting default values for custom fields in the block editor is not straightforward, otherwise.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D4155%23feedback-editor-4155)

6. [Skip to note 15 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-5241)



`auth_callback` and `sanitize_callback` is callable with arguments.



Auth callback is applied in `map_meta_cap()` ( [wp-includes/capabilities.php](https://developer.wordpress.org/reference/functions/map_meta_cap/)).


Sanitize callback is applied in `sanitize_meta()` ( [wp-includes/meta.php](https://developer.wordpress.org/reference/functions/sanitize_meta/)).





`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/register_meta/#)

[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
$status = register_meta( 'post', '_candidate_title', array(
       'type' => 'string',
       'description' => 'event location',
       'object_subtype' => 'resume',
       'single' => true,
       'show_in_rest' => array(
           'schema' => array(
               'type' => 'string',
               'default' => true
           )
       ),
       'auth_callback' => function(  $allowed, $meta_key, $object_id, $user_id, $cap, $caps ) {
           return current_user_can( 'edit_resume', $object_id );
       },
       'sanitize_callback' => function( $meta_value, $meta_key, $object_type, $object_subtype ) {
           return $meta_value;
       }
) );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D5241%23feedback-editor-5241)

7. [Skip to note 16 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-3449)



Note that for the ‘show\_in\_rest’ argument to take effect, the post type should be registered with ‘custom-fields’ support.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D3449%23feedback-editor-3449)

8. [Skip to note 17 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-5403)



In WP Core, \` [register\_meta()](https://developer.wordpress.org/reference/functions/register_meta/) \` is only used by \`register\_post\_meta\` and \` [register\_term\_meta()](https://developer.wordpress.org/reference/functions/register_term_meta/) \`, and otherwise none of these functions are used in Core.



Jetpack uses \` [register\_post\_meta()](https://developer.wordpress.org/reference/functions/register_post_meta/) \`, and \` [register\_meta()](https://developer.wordpress.org/reference/functions/register_meta/) \` for ‘post’ and ‘user’. So Jetpack has code samples to examine for their use.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D5403%23feedback-editor-5403)

9. [Skip to note 18 content](https://developer.wordpress.org/reference/functions/register_meta/#comment-content-1385)



**Basic Example**





`wp-includes/meta.php`
[Copy](https://developer.wordpress.org/reference/functions/register_meta/#)




```php
<?php register_meta( 'post', 'my_registered_meta', 'my_sanitize_callback', '__return_false' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F%3Freplytocom%3D1385%23feedback-editor-1385)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fregister_meta%2F) before being able to contribute a note or feedback.

Notifications