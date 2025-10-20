---
url: https://developer.wordpress.org/reference/functions/update_term_meta
scraped_at: 2025-10-20T03:19:28.263Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/update_term_meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

update\_term\_meta()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)update\_term\_meta()

Search

# update\_term\_meta( int$term\_id, string$meta\_key, mixed$meta\_value, mixed$prev\_value = '' ): int\|bool\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/update_term_meta/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/update_term_meta/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/update_term_meta/#return)
- [Source](https://developer.wordpress.org/reference/functions/update_term_meta/#source)
- [Related](https://developer.wordpress.org/reference/functions/update_term_meta/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/update_term_meta/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/update_term_meta/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/update_term_meta/#wp--skip-link--target)

Updates term metadata.

## [Description](https://developer.wordpress.org/reference/functions/update_term_meta/\#description)

Use the `$prev_value` parameter to differentiate between meta fields with the same key and term ID.

If the meta field for the term does not exist, it will be added.

## [Parameters](https://developer.wordpress.org/reference/functions/update_term_meta/\#parameters)

`$term_id` intrequired

Term ID.

`$meta_key` stringrequired

Metadata key.

`$meta_value` mixedrequired

Metadata value. Must be serializable if non-scalar.

`$prev_value` mixedoptional

Previous value to check before updating.

If specified, only update existing metadata entries with this value. Otherwise, update all entries.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/update_term_meta/\#return)

int\|bool\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) Meta ID if the key didn’t exist. true on successful update, false on failure or if the value passed to the function is the same as the one that is already in the database.

[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) when term\_id is ambiguous between taxonomies.

## [Source](https://developer.wordpress.org/reference/functions/update_term_meta/\#source)

`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/update_term_meta/#)

```php
function update_term_meta( $term_id, $meta_key, $meta_value, $prev_value = '' ) {
	if ( wp_term_is_shared( $term_id ) ) {
		return new WP_Error( 'ambiguous_term_id', __( 'Term meta cannot be added to terms that are shared between taxonomies.' ), $term_id );
	}

	return update_metadata( 'term', $term_id, $meta_key, $meta_value, $prev_value );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/taxonomy.php#L1471) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/taxonomy.php#L1471-L1477)

## [Related](https://developer.wordpress.org/reference/functions/update_term_meta/\#related)

| Uses | Description |
| --- | --- |
| [wp\_term\_is\_shared()](https://developer.wordpress.org/reference/functions/wp_term_is_shared/) `wp-includes/taxonomy.php` | Determines whether a term is shared between multiple taxonomies. |
| [update\_metadata()](https://developer.wordpress.org/reference/functions/update_metadata/) `wp-includes/meta.php` | Updates metadata for the specified object. If no value already exists for the specified object ID and metadata key, the metadata will be added. |
| [WP\_Error::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_error/__construct/) `wp-includes/class-wp-error.php` | Initializes the error. |

[Show 1 more](https://developer.wordpress.org/reference/functions/update_term_meta/#) [Show less](https://developer.wordpress.org/reference/functions/update_term_meta/#)

## [Changelog](https://developer.wordpress.org/reference/functions/update_term_meta/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/update_term_meta/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/update_term_meta/#comment-content-5619)



Basic usage:





`wp-includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/update_term_meta/#)




```php
$term_id = 23;

update_term_meta( $term_id, 'meta_key', 'Hello world!' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fupdate_term_meta%2F%3Freplytocom%3D5619%23feedback-editor-5619)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fupdate_term_meta%2F) before being able to contribute a note or feedback.

Notifications