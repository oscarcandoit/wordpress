---
url: https://developer.wordpress.org/plugins/users/working-with-users
scraped_at: 2025-10-20T03:16:21.790Z
---

[Skip to content](https://developer.wordpress.org/plugins/users/working-with-users/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Working with Users


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Users](https://developer.wordpress.org/plugins/users/)Working with Users

Search

# Working with Users

## In this article

Table of Contents

- [Adding Users](https://developer.wordpress.org/plugins/users/working-with-users/#adding-users)
  - [Create User](https://developer.wordpress.org/plugins/users/working-with-users/#create-user)
  - [Insert User](https://developer.wordpress.org/plugins/users/working-with-users/#insert-user)
- [Updating Users](https://developer.wordpress.org/plugins/users/working-with-users/#updating-users)
- [Deleting Users](https://developer.wordpress.org/plugins/users/working-with-users/#deleting-users)

[↑ Back to top](https://developer.wordpress.org/plugins/users/working-with-users/#wp--skip-link--target)

## [Adding Users](https://developer.wordpress.org/plugins/users/working-with-users/\#adding-users)

To add a user you can use `wp_create_user()` or `wp_insert_user()`.

`wp_create_user()` creates a user using only the username, password and email parameters while `wp_insert_user()` accepts an array or object describing the user and its properties.

### [Create User](https://developer.wordpress.org/plugins/users/working-with-users/\#create-user)

`wp_create_user()` allows you to create a new WordPress user.

It uses [wp\_slash()](https://developer.wordpress.org/reference/functions/wp_slash/) to escape the values. The PHP compact() function to create an array with these values. The [wp\_insert\_user()](https://developer.wordpress.org/reference/functions/wp_insert_user/) to perform the insert operation.

Please refer to the Function Reference about `wp_create_user()` for full explanation about the used parameters.

#### [Example Create](https://developer.wordpress.org/plugins/users/working-with-users/\#example-create)

``
[Expand code](https://developer.wordpress.org/plugins/users/working-with-users/#)

[Copy](https://developer.wordpress.org/plugins/users/working-with-users/#)

```php
// check if the username is taken
$user_id = username_exists( $user_name );

// check that the email address does not belong to a registered user
if ( ! $user_id && email_exists( $user_email ) === false ) {
	// create a random password
	$random_password = wp_generate_password( 12, false );
	// create the user
	$user_id = wp_create_user(
		$user_name,
		$random_password,
		$user_email
	);
}
```

### [Insert User](https://developer.wordpress.org/plugins/users/working-with-users/\#insert-user)

``
[Copy](https://developer.wordpress.org/plugins/users/working-with-users/#)

```php
wp_insert_user( $userdata );
```

The function calls a filter for most predefined properties.

The function performs the action `user_register` when creating a user (user ID does not exist).

The function performs the action `profile_update` when updating the user (user ID exists).

Please refer to the Function Reference about `wp_insert_user()` for full explanation about the used parameters.

#### [Example Insert](https://developer.wordpress.org/plugins/users/working-with-users/\#example-insert)

Below is an example showing how to insert a new user with the website profile field filled in.

``
[Expand code](https://developer.wordpress.org/plugins/users/working-with-users/#)

[Copy](https://developer.wordpress.org/plugins/users/working-with-users/#)

```php
$username  = $_POST['username'];
$password  = $_POST['password'];
$website   = $_POST['website'];
$user_data = [\
	'user_login' => $username,\
	'user_pass'  => $password,\
	'user_url'   => $website,\
];

$user_id = wp_insert_user( $user_data );

// success
if ( ! is_wp_error( $user_id ) ) {
	echo 'User created: ' . $user_id;
}
```

## [Updating Users](https://developer.wordpress.org/plugins/users/working-with-users/\#updating-users)

`wp_update_user()` Updates a single user in the database. The update data is passed along in the `$userdata` array/object.

To update a single piece of user meta data, use `update_user_meta()` instead. To create a new user, use `wp_insert_user()` instead.

If current user’s password is being updated, then the cookies will be cleared!

Please refer to the Function Reference about `wp_update_user()` for full explanation about the used parameters.

#### [Example Update](https://developer.wordpress.org/plugins/users/working-with-users/\#example-update)

Below is an example showing how to update a user’s website profile field.

``
[Expand code](https://developer.wordpress.org/plugins/users/working-with-users/#)

[Copy](https://developer.wordpress.org/plugins/users/working-with-users/#)

```php
$user_id = 1;
$website = 'https://wordpress.org';

$user_id = wp_update_user(
	array(
		'ID'       => $user_id,
		'user_url' => $website,
	)
);

if ( is_wp_error( $user_id ) ) {
	// error
} else {
	// success
}
```

## [Deleting Users](https://developer.wordpress.org/plugins/users/working-with-users/\#deleting-users)

`wp_delete_user()` deletes the user and optionally reassign associated entities to another user ID.

The function performs the action `deleted_user` after the user have been deleted.

If the $reassign parameter is not set to a valid user ID, then all entities belonging to the deleted user will be deleted!

Please refer to the Function Reference about `wp_delete_user()` for full explanation about the used parameters.

First published

September 24, 2014

Last updated

November 17, 2022

[PreviousWorking with User MetadataPrevious: Working with User Metadata](https://developer.wordpress.org/plugins/users/working-with-user-metadata/)

[NextHTTP APINext: HTTP API](https://developer.wordpress.org/plugins/http-api/)

Notifications