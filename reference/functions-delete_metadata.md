---
url: https://developer.wordpress.org/reference/functions/delete_metadata
scraped_at: 2025-10-20T03:27:12.046Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/delete_metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

delete\_metadata()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)delete\_metadata()

Search

# delete\_metadata( string$meta\_type, int$object\_id, string$meta\_key, mixed$meta\_value = '', bool$delete\_all = false ): bool

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/delete_metadata/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/delete_metadata/#return)
- [Source](https://developer.wordpress.org/reference/functions/delete_metadata/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/delete_metadata/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/delete_metadata/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/delete_metadata/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/delete_metadata/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/delete_metadata/#wp--skip-link--target)

Deletes metadata for the specified object.

## [Parameters](https://developer.wordpress.org/reference/functions/delete_metadata/\#parameters)

`$meta_type` stringrequired

Type of object metadata is for. Accepts `'post'`, `'comment'`, `'term'`, `'user'`, or any other object type with an associated meta table.

`$object_id` intrequired

ID of the object metadata is for.

`$meta_key` stringrequired

Metadata key.

`$meta_value` mixedoptional

Metadata value. Must be serializable if non-scalar.

If specified, only delete metadata entries with this value.

Otherwise, delete all entries with the specified meta\_key.

Pass `null`, `false`, or an empty string to skip this check.

(For backward compatibility, it is not possible to pass an empty string to delete those entries with an empty string for a value.)

Default: `''`

`$delete_all` booloptional

If true, delete matching metadata entries for all objects, ignoring the specified object\_id. Otherwise, only delete matching metadata entries for the specified object\_id.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/delete_metadata/\#return)

bool True on successful delete, false on failure.

## [Source](https://developer.wordpress.org/reference/functions/delete_metadata/\#source)

`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/delete_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/delete_metadata/#)

```php
function delete_metadata( $meta_type, $object_id, $meta_key, $meta_value = '', $delete_all = false ) {
	global $wpdb;

	if ( ! $meta_type || ! $meta_key || ! is_numeric( $object_id ) && ! $delete_all ) {
		return false;
	}

	$object_id = absint( $object_id );
	if ( ! $object_id && ! $delete_all ) {
		return false;
	}

	$table = _get_meta_table( $meta_type );
	if ( ! $table ) {
		return false;
	}

	$type_column = sanitize_key( $meta_type . '_id' );
	$id_column   = ( 'user' === $meta_type ) ? 'umeta_id' : 'meta_id';

	// expected_slashed ($meta_key)
	$meta_key   = wp_unslash( $meta_key );
	$meta_value = wp_unslash( $meta_value );

	/**
	 * Short-circuits deleting metadata of a specific type.
	 *
	 * The dynamic portion of the hook name, `$meta_type`, refers to the meta object type
	 * (post, comment, term, user, or any other type with an associated meta table).
	 * Returning a non-null value will effectively short-circuit the function.
	 *
	 * Possible hook names include:
	 *
	 *  - `delete_post_metadata`
	 *  - `delete_comment_metadata`
	 *  - `delete_term_metadata`
	 *  - `delete_user_metadata`
	 *
	 * @since 3.1.0
	 *
	 * @param null|bool $delete     Whether to allow metadata deletion of the given type.
	 * @param int       $object_id  ID of the object metadata is for.
	 * @param string    $meta_key   Metadata key.
	 * @param mixed     $meta_value Metadata value. Must be serializable if non-scalar.
	 * @param bool      $delete_all Whether to delete the matching metadata entries
	 *                              for all objects, ignoring the specified $object_id.
	 *                              Default false.
	 */
	$check = apply_filters( "delete_{$meta_type}_metadata", null, $object_id, $meta_key, $meta_value, $delete_all );
	if ( null !== $check ) {
		return (bool) $check;
	}

	$_meta_value = $meta_value;
	$meta_value  = maybe_serialize( $meta_value );

	$query = $wpdb->prepare( "SELECT $id_column FROM $table WHERE meta_key = %s", $meta_key );

	if ( ! $delete_all ) {
		$query .= $wpdb->prepare( " AND $type_column = %d", $object_id );
	}

	if ( '' !== $meta_value && null !== $meta_value && false !== $meta_value ) {
		$query .= $wpdb->prepare( ' AND meta_value = %s', $meta_value );
	}

	$meta_ids = $wpdb->get_col( $query );
	if ( ! count( $meta_ids ) ) {
		return false;
	}

	if ( $delete_all ) {
		if ( '' !== $meta_value && null !== $meta_value && false !== $meta_value ) {
			$object_ids = $wpdb->get_col( $wpdb->prepare( "SELECT $type_column FROM $table WHERE meta_key = %s AND meta_value = %s", $meta_key, $meta_value ) );
		} else {
			$object_ids = $wpdb->get_col( $wpdb->prepare( "SELECT $type_column FROM $table WHERE meta_key = %s", $meta_key ) );
		}
	}

	/**
	 * Fires immediately before deleting metadata of a specific type.
	 *
	 * The dynamic portion of the hook name, `$meta_type`, refers to the meta object type
	 * (post, comment, term, user, or any other type with an associated meta table).
	 *
	 * Possible hook names include:
	 *
	 *  - `delete_post_meta`
	 *  - `delete_comment_meta`
	 *  - `delete_term_meta`
	 *  - `delete_user_meta`
	 *
	 * @since 3.1.0
	 *
	 * @param string[] $meta_ids    An array of metadata entry IDs to delete.
	 * @param int      $object_id   ID of the object metadata is for.
	 * @param string   $meta_key    Metadata key.
	 * @param mixed    $_meta_value Metadata value.
	 */
	do_action( "delete_{$meta_type}_meta", $meta_ids, $object_id, $meta_key, $_meta_value );

	// Old-style action.
	if ( 'post' === $meta_type ) {
		/**
		 * Fires immediately before deleting metadata for a post.
		 *
		 * @since 2.9.0
		 *
		 * @param string[] $meta_ids An array of metadata entry IDs to delete.
		 */
		do_action( 'delete_postmeta', $meta_ids );
	}

	$query = "DELETE FROM $table WHERE $id_column IN( " . implode( ',', $meta_ids ) . ' )';

	$count = $wpdb->query( $query );

	if ( ! $count ) {
		return false;
	}

	if ( $delete_all ) {
		$data = (array) $object_ids;
	} else {
		$data = array( $object_id );
	}
	wp_cache_delete_multiple( $data, $meta_type . '_meta' );

	/**
	 * Fires immediately after deleting metadata of a specific type.
	 *
	 * The dynamic portion of the hook name, `$meta_type`, refers to the meta object type
	 * (post, comment, term, user, or any other type with an associated meta table).
	 *
	 * Possible hook names include:
	 *
	 *  - `deleted_post_meta`
	 *  - `deleted_comment_meta`
	 *  - `deleted_term_meta`
	 *  - `deleted_user_meta`
	 *
	 * @since 2.9.0
	 *
	 * @param string[] $meta_ids    An array of metadata entry IDs to delete.
	 * @param int      $object_id   ID of the object metadata is for.
	 * @param string   $meta_key    Metadata key.
	 * @param mixed    $_meta_value Metadata value.
	 */
	do_action( "deleted_{$meta_type}_meta", $meta_ids, $object_id, $meta_key, $_meta_value );

	// Old-style action.
	if ( 'post' === $meta_type ) {
		/**
		 * Fires immediately after deleting metadata for a post.
		 *
		 * @since 2.9.0
		 *
		 * @param string[] $meta_ids An array of metadata entry IDs to delete.
		 */
		do_action( 'deleted_postmeta', $meta_ids );
	}

	return true;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/meta.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/meta.php#L386) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/meta.php#L386-L549)

## [Hooks](https://developer.wordpress.org/reference/functions/delete_metadata/\#hooks)

[do\_action( ‘deleted\_postmeta’, string\[\]$meta\_ids )](https://developer.wordpress.org/reference/hooks/deleted_postmeta/)

Fires immediately after deleting metadata for a post.

[do\_action( “deleted\_{$meta\_type}\_meta”, string\[\]$meta\_ids, int$object\_id, string$meta\_key, mixed$\_meta\_value )](https://developer.wordpress.org/reference/hooks/deleted_meta_type_meta/)

Fires immediately after deleting metadata of a specific type.

[do\_action( ‘delete\_postmeta’, string\[\]$meta\_ids )](https://developer.wordpress.org/reference/hooks/delete_postmeta/)

Fires immediately before deleting metadata for a post.

[do\_action( “delete\_{$meta\_type}\_meta”, string\[\]$meta\_ids, int$object\_id, string$meta\_key, mixed$\_meta\_value )](https://developer.wordpress.org/reference/hooks/delete_meta_type_meta/)

Fires immediately before deleting metadata of a specific type.

[apply\_filters( “delete\_{$meta\_type}\_metadata”, null\|bool$delete, int$object\_id, string$meta\_key, mixed$meta\_value, bool$delete\_all )](https://developer.wordpress.org/reference/hooks/delete_meta_type_metadata/)

Short-circuits deleting metadata of a specific type.

## [Related](https://developer.wordpress.org/reference/functions/delete_metadata/\#related)

| Uses | Description |
| --- | --- |
| [wp\_cache\_delete\_multiple()](https://developer.wordpress.org/reference/functions/wp_cache_delete_multiple/) `wp-includes/cache.php` | Deletes multiple values from the cache in one call. |
| [maybe\_serialize()](https://developer.wordpress.org/reference/functions/maybe_serialize/) `wp-includes/functions.php` | Serializes data, if needed. |
| [wpdb::get\_col()](https://developer.wordpress.org/reference/classes/wpdb/get_col/) `wp-includes/class-wpdb.php` | Retrieves one column from the database. |
| [wpdb::query()](https://developer.wordpress.org/reference/classes/wpdb/query/) `wp-includes/class-wpdb.php` | Performs a database query, using current database connection. |
| [\_get\_meta\_table()](https://developer.wordpress.org/reference/functions/_get_meta_table/) `wp-includes/meta.php` | Retrieves the name of the metadata table for the specified object type. |
| [wp\_unslash()](https://developer.wordpress.org/reference/functions/wp_unslash/) `wp-includes/formatting.php` | Removes slashes from a string or recursively removes slashes from strings within an array. |
| [sanitize\_key()](https://developer.wordpress.org/reference/functions/sanitize_key/) `wp-includes/formatting.php` | Sanitizes a string key. |
| [absint()](https://developer.wordpress.org/reference/functions/absint/) `wp-includes/load.php` | Converts a value to non-negative integer. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [wpdb::prepare()](https://developer.wordpress.org/reference/classes/wpdb/prepare/) `wp-includes/class-wpdb.php` | Prepares a SQL query for safe execution. |

[Show 6 more](https://developer.wordpress.org/reference/functions/delete_metadata/#) [Show less](https://developer.wordpress.org/reference/functions/delete_metadata/#)

| Used by | Description |
| --- | --- |
| [wp\_autosave\_post\_revisioned\_meta\_fields()](https://developer.wordpress.org/reference/functions/wp_autosave_post_revisioned_meta_fields/) `wp-admin/includes/post.php` | Autosaves the revisioned meta fields. |
| [delete\_site\_meta()](https://developer.wordpress.org/reference/functions/delete_site_meta/) `wp-includes/ms-site.php` | Removes metadata matching criteria from a site. |
| [delete\_site\_meta\_by\_key()](https://developer.wordpress.org/reference/functions/delete_site_meta_by_key/) `wp-includes/ms-site.php` | Deletes everything from site meta matching meta key. |
| [wp\_initialize\_site()](https://developer.wordpress.org/reference/functions/wp_initialize_site/) `wp-includes/ms-site.php` | Runs the initialization routine for a given site. |
| [WP\_REST\_Meta\_Fields::delete\_meta\_value()](https://developer.wordpress.org/reference/classes/wp_rest_meta_fields/delete_meta_value/) `wp-includes/rest-api/fields/class-wp-rest-meta-fields.php` | Deletes a meta value for an object. |
| [WP\_REST\_Meta\_Fields::update\_multi\_meta\_value()](https://developer.wordpress.org/reference/classes/wp_rest_meta_fields/update_multi_meta_value/) `wp-includes/rest-api/fields/class-wp-rest-meta-fields.php` | Updates multiple meta values for an object. |
| [delete\_term\_meta()](https://developer.wordpress.org/reference/functions/delete_term_meta/) `wp-includes/taxonomy.php` | Removes metadata matching criteria from a term. |
| [WP\_User\_Meta\_Session\_Tokens::drop\_sessions()](https://developer.wordpress.org/reference/classes/wp_user_meta_session_tokens/drop_sessions/) `wp-includes/class-wp-user-meta-session-tokens.php` | Destroys all sessions for all users. |
| [delete\_user\_meta()](https://developer.wordpress.org/reference/functions/delete_user_meta/) `wp-includes/user.php` | Removes metadata matching criteria from a user. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [delete\_post\_meta()](https://developer.wordpress.org/reference/functions/delete_post_meta/) `wp-includes/post.php` | Deletes a post meta field for the given post ID. |
| [delete\_post\_meta\_by\_key()](https://developer.wordpress.org/reference/functions/delete_post_meta_by_key/) `wp-includes/post.php` | Deletes everything from post meta matching the given meta key. |
| [install\_blog()](https://developer.wordpress.org/reference/functions/install_blog/) `wp-includes/ms-deprecated.php` | Install an empty blog. |
| [delete\_comment\_meta()](https://developer.wordpress.org/reference/functions/delete_comment_meta/) `wp-includes/comment.php` | Removes metadata matching criteria from a comment. |

[Show 9 more](https://developer.wordpress.org/reference/functions/delete_metadata/#) [Show less](https://developer.wordpress.org/reference/functions/delete_metadata/#)

## [Changelog](https://developer.wordpress.org/reference/functions/delete_metadata/\#changelog)

| Version | Description |
| --- | --- |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/delete_metadata/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/delete_metadata/#comment-content-2844)





`wp-includes/meta.php`
[Expand code](https://developer.wordpress.org/reference/functions/delete_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/delete_metadata/#)




```php
/*
   		 * Remove all post meta data for Custom Post Type (CPT)
   		 * at the time of uninstall of plugin that created this CPT.
   		 * So that plugin do not leave behind any orphan post meta data
   		 * related to its CPT.
   		 *
   		 * You may place this code in uninstall.php file in your plugin root directory.
   		 */
   		$meta_type  = 'post';           // since we are deleting data for CPT
   		$object_id  = 0;                // no need to put id of object since we are deleting all
   		$meta_key   = 'my_meta_key';    // Your target meta_key added using update_post_meta()
   		$meta_value = '';               // No need to check for value since we are deleting all
   		$delete_all = true;             // This is important to have TRUE to delete all post meta

   		// This will delete all post meta data having the specified key
   		delete_metadata( $meta_type, $object_id, $meta_key, $meta_value, $delete_all );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdelete_metadata%2F%3Freplytocom%3D2844%23feedback-editor-2844)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/delete_metadata/#comment-content-3648)



Be VERY careful when using this function to delete a specific key-value pair. As stated, providing an empty string for `$meta_value` will cause the check to be skipped entirely, resulting in all keys being deleted!



> **$meta\_value** …If specified, only delete metadata entries with this value. _Otherwise, delete all entries with the specified meta\_key_…



To avoid accidentally deleting ALL key instances, use a short-circuit check:





`wp-includes/meta.php`
[Copy](https://developer.wordpress.org/reference/functions/delete_metadata/#)




```php
$value_to_delete = My_Class::get_value(); // may return empty string
if ( $value_to_delete != '' && delete_metadata( 'post', 27, 'key', $value_to_delete ) ) {
    // the key-value pair was safely deleted
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdelete_metadata%2F%3Freplytocom%3D3648%23feedback-editor-3648)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdelete_metadata%2F) before being able to contribute a note or feedback.

Notifications