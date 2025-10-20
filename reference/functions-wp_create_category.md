---
url: https://developer.wordpress.org/reference/functions/wp_create_category
scraped_at: 2025-10-20T03:19:11.981Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_create_category/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_create\_category()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_create\_category()

Search

# wp\_create\_category( int\|string$cat\_name, int$category\_parent ): int\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_create_category/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_create_category/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_create_category/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_create_category/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_create_category/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_create_category/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_create_category/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_create_category/#wp--skip-link--target)

Adds a new category to the database if it does not already exist.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_create_category/\#parameters)

`$cat_name` int\|stringrequired

Category name.

`$category_parent` intoptional

ID of parent category.

## [Return](https://developer.wordpress.org/reference/functions/wp_create_category/\#return)

int\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## [More Information](https://developer.wordpress.org/reference/functions/wp_create_category/\#more-information)

Parameters:

- `$cat_name`: Name for the new category.
- `$parent`: Category ID of the parent category.

Returns:

- 0 on failure, category id on success.

`[wp\_create\_category()](https://developer.wordpress.org/reference/functions/wp_create_category/) ` is a thin wrapper around `[wp\_insert\_category()](https://codex.wordpress.org/Function_Reference/wp_insert_category "Function Reference/wp insert category")`.

Because this is a wrapper, it is not suitable for entering a complex custom taxonomy element.

If the category already exists, it is not duplicated. The ID of the original existing category is returned without error.

## [Source](https://developer.wordpress.org/reference/functions/wp_create_category/\#source)

`wp-admin/includes/taxonomy.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_create_category/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_create_category/#)

```php
function wp_create_category( $cat_name, $category_parent = 0 ) {
	$id = category_exists( $cat_name, $category_parent );
	if ( $id ) {
		return $id;
	}

	return wp_insert_category(
		array(
			'cat_name'        => $cat_name,
			'category_parent' => $category_parent,
		)
	);
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/taxonomy.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/taxonomy.php#L55) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/taxonomy.php#L55-L67)

## [Related](https://developer.wordpress.org/reference/functions/wp_create_category/\#related)

| Uses | Description |
| --- | --- |
| [category\_exists()](https://developer.wordpress.org/reference/functions/category_exists/) `wp-admin/includes/taxonomy.php` | Checks whether a category exists. |
| [wp\_insert\_category()](https://developer.wordpress.org/reference/functions/wp_insert_category/) `wp-admin/includes/taxonomy.php` | Updates an existing Category or creates a new Category. |

| Used by | Description |
| --- | --- |
| [wp\_create\_categories()](https://developer.wordpress.org/reference/functions/wp_create_categories/) `wp-admin/includes/taxonomy.php` | Creates categories for the given post. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_create_category/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_create_category/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/wp_create_category/#comment-content-6705)



An example of how you can use the **[wp\_create\_category()](https://developer.wordpress.org/reference/functions/wp_create_category/)** function.





`wp-admin/includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_create_category/#)




```php
$category_name = 'New Category'; // Name of the category you want to create
$parent_category_id = 3; // ID of the parent category (change this to your desired parent category)

// Attempt to create a new category
$category_id = wp_create_category( $category_name, $parent_category_id );

if ( ! is_wp_error( $category_id ) ) {
       echo 'Category created with ID: ' . $category_id;
} else {
       echo 'Error creating category: ' . $category_id->get_error_message();
}
```





**In this example:**



`$category_name` is set to “New Category”, which is the name of the category you want to create.

`$parent_category_id` is set to 3, which is the ID of the parent category where you want to create the new category. You should replace this with the actual ID of the desired parent category.


The `wp_create_category()` function is called with both the category name and the parent category ID as arguments. If the category is successfully created, it will return the category ID as an integer. If there’s an error during the creation process, it will return a `WP_Error` object.



The code then checks if the result is a `WP_Error` object using `is_wp_error()`. If it’s not an error, it means the category was created successfully, and it will display a message with the category ID. If an error occurred, it will display an error message using the `get_error_message()` method of the `WP_Error` object.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_create_category%2F%3Freplytocom%3D6705%23feedback-editor-6705)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_create_category/#comment-content-723)



**Examples**



In order to create a simple category use:





`wp-admin/includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_create_category/#)




```php
    wp_create_category( 'My category name' );
```





To create a category that is a child of Uncategorized (or whatever category has the ID 0), use:





`wp-admin/includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_create_category/#)




```php
wp_create_category( 'Child of Uncategorized', 0 );
```





To get id of category created and put value in variable:





`wp-admin/includes/taxonomy.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_create_category/#)




```php
$id = wp_create_category( 'Child of Uncategorized', 0 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_create_category%2F%3Freplytocom%3D723%23feedback-editor-723)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_create_category%2F) before being able to contribute a note or feedback.

Notifications