---
url: https://developer.wordpress.org/reference/classes/wp_user_query
scraped_at: 2025-10-20T03:23:26.047Z
---

[Skip to content](https://developer.wordpress.org/reference/classes/wp_user_query/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

WP\_User\_Query


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Classes](https://developer.wordpress.org/reference/classes/)WP\_User\_Query

Search

# class WP\_User\_Query {}

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/classes/wp_user_query/#description)
  - [See also](https://developer.wordpress.org/reference/classes/wp_user_query/#see-also)
- [More Information](https://developer.wordpress.org/reference/classes/wp_user_query/#more-information)
- [Usage](https://developer.wordpress.org/reference/classes/wp_user_query/#usage)
- [Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#parameters)
  - [User Role Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#user-role-parameter)
  - [Include & Exclude Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#include-exclude-parameters)
  - [Blog Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#blog-parameter)
  - [Search Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#search-parameters)
  - [Pagination Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#pagination-parameters)
  - [Order & Orderby Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#order-orderby-parameters)
  - [Date Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#date-parameters)
  - [Custom Field Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/#custom-field-parameters)
  - [Who Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#who-parameter)
  - [Total Count Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#total-count-parameter)
  - [Has Published Posts Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#has-published-posts-parameter)
  - [Return Fields Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/#return-fields-parameter)
- [Return Values](https://developer.wordpress.org/reference/classes/wp_user_query/#return-values)
- [Filters](https://developer.wordpress.org/reference/classes/wp_user_query/#filters)
- [Methods](https://developer.wordpress.org/reference/classes/wp_user_query/#methods)
- [Source](https://developer.wordpress.org/reference/classes/wp_user_query/#source)
- [Changelog](https://developer.wordpress.org/reference/classes/wp_user_query/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_user_query/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/classes/wp_user_query/#wp--skip-link--target)

Core class used for querying users.

## [Description](https://developer.wordpress.org/reference/classes/wp_user_query/\#description)

### [See also](https://developer.wordpress.org/reference/classes/wp_user_query/\#see-also)

- [WP\_User\_Query::prepare\_query()](https://developer.wordpress.org/reference/classes/WP_User_Query/prepare_query): for information on accepted arguments.

## [More Information](https://developer.wordpress.org/reference/classes/wp_user_query/\#more-information)

This class allows querying WordPress database tables ‘ `wp_users`‘ and ‘ `wp_usermeta`‘.

## [Usage](https://developer.wordpress.org/reference/classes/wp_user_query/\#usage)

```
<?php
$args = array(
	.
	.
	.
);

// The Query
$user_query = new WP_User_Query( $args );

// User Loop
if ( ! empty( $user_query->get_results() ) ) {
	foreach ( $user_query->get_results() as $user ) {
		echo '<p>' . $user->display_name . '</p>';
	}
} else {
	echo 'No users found.';
}
?>

```

## [Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#parameters)

### [User Role Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#user-role-parameter)

Show users associated with certain role.

- **`role`** ( _string / array_) – use [User Role](https://wordpress.org/support/article/roles-and-capabilities/ "Roles and Capabilities"). An array or a comma-separated list of role names that users must match to be included in results. Note that this is an inclusive list: users must match \*each\* role. Default empty.
- **`role__in`** ( _array_) – An array of role names. Matched users must have at least one of these roles. Default empty array. (since [Version 4.4](https://codex.wordpress.org/Version_4.4 "Version 4.4")).
- **`role__not_in`** ( _array_) – An array of role names to exclude. Users matching one or more of these roles will not be included in results. Default empty array. (since [Version 4.4](https://codex.wordpress.org/Version_4.4 "Version 4.4")).

**Display Administrator role users**

```
$user_query = new WP_User_Query( array( 'role' => 'Administrator' ) );

```

**Display Subscriber role users**

```
$user_query = new WP_User_Query( array( 'role' => 'Subscriber' ) );

```

**Display all users except Subscriber role users**

```
$user_query = new WP_User_Query( array( 'role__not_in' => 'Subscriber' ) );

```

### [Include & Exclude Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#include-exclude-parameters)

Show specific users.

- **`include`** ( _array_) – List of users to be included.
- **`exclude`** ( _array_) – List of users to be excluded.

**Display specific users list**

```
$user_query = new WP_User_Query( array( 'include' => array( 1, 2, 3 ) ) );

```

**Display all users except a specific list of users**

```
$user_query = new WP_User_Query( array( 'exclude' => array( 4, 5, 6 ) ) );

```

### [Blog Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#blog-parameter)

Show users associated with certain blog on the network.

- **`blog_id`** ( _int_) – The blog id on a multisite environment. Defaults to the current blog id.

**Display users from blog 33**

```
$user_query = new WP_User_Query( array( 'blog_id' => 33 ) );

```

### [Search Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#search-parameters)

Search users.

- **`search`** ( _string_) – Searches for possible string matches on columns. Use of the \* wildcard before and/or after the string will match on columns `starting with*`, `*ending with`, or `*containing*` the string you enter.
- **`search_columns`** ( _array_) – List of [database table columns](https://codex.wordpress.org/Database_Description#Table:_wp_users "Database Description") to matches the search string across multiple columns.

  - ‘ `ID`‘ – Search by user id.
  - ‘ `user_login`‘ – Search by user login.
  - ‘ `user_nicename`‘ – Search by user nicename.
  - ‘ `user_email`‘ – Search by user email.
  - ‘ `user_url`‘ – Search by user url.

We can use the [user\_search\_columns](https://developer.wordpress.org/reference/hooks/user_search_columns/ "Plugin API/Filter Reference/user search columns") filter to modify the search columns.

**Display users based on a keyword search**

```
$user_query = new WP_User_Query( array( 'search' => 'Rami' ) );

```

**Display users based on a keyword search, only on login and email columns**

```
$args = array(
	'search'         => 'Rami',
	'search_columns' => array( 'user_login', 'user_email' )
);
$user_query = new WP_User_Query( $args );

```

### [Pagination Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#pagination-parameters)

Limit retrieved Users.

- **`number`** ( _int_) – The maximum returned number of results (needed in pagination).
- **`offset`** ( _int_) – Offset the returned results (needed in pagination).
- **`paged`** ( _int_) – When used with number, defines the page of results to return. Default 1. (since [Version 4.4](https://codex.wordpress.org/Version_4.4 "Version 4.4")).

**Display 10 users**

```
$user_query = new WP_User_Query( array( 'number' => 10 ) );

```

**Display 5 users starting from 25**

```
$user_query = new WP_User_Query( array( 'number' => 5, 'offset' => 25 ) );

```

### [Order & Orderby Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#order-orderby-parameters)

Sort retrieved Users.

- **`orderby`** ( _string\|array_) – Sort retrieved users by parameter. Defaults to ‘login’. It can be a string with a single field, a string containing a list of values separated by commas or spaces, or an array with fields.

  - ‘ `ID`‘ – Order by user id.
  - ‘ `display_name`‘ – Order by user display name.
  - ‘ `name`‘ / ‘ `user_name`‘ – Order by user name.
  - ‘ `include`‘ – Order by the included list of user\_ids (requires the include parameter) (since [Version 4.1](https://codex.wordpress.org/Version_4.1 "Version 4.1")).
  - ‘ `login`‘ / ‘ `user_login`‘ – Order by user login.
  - ‘ `nicename`‘ / ‘ `user_nicename`‘ – Order by user nicename.
  - ‘ `email`‘ / ‘ `user_email`‘ – Order by user email.
  - ‘ `url`‘ / ‘ `user_url`‘ – Order by user url.
  - ‘ `registered`‘ / ‘ `user_registered`‘ – Order by user registered date.
  - ‘ `post_count`‘ – Order by user post count.
  - ‘ `meta_value`‘ – Note that a ‘meta\_key=keyname’ must also be present in the query (available with [Version 3.7](https://codex.wordpress.org/Version_3.7 "Version 3.7")).
  - ‘ `meta_value_num`‘ – Note that a ‘meta\_key=keyname’ must also be present in the query (available with [Version 4.2](https://codex.wordpress.org/Version_4.2 "Version 4.2")).
- **`order`** ( _string_) – Designates the ascending or descending order of the ‘ `orderby`‘ parameter. Defaults to ‘ASC’.

  - ‘ `ASC`‘ – ascending order from lowest to highest values (1, 2, 3; a, b, c).
  - ‘ `DESC`‘ – descending order from highest to lowest values (3, 2, 1; c, b, a).

**Display users sorted by Post Count, Descending order**

```
$user_query = new WP_User_Query( array ( 'orderby' => 'post_count', 'order' => 'DESC' ) );

```

**Display users sorted by registered, Ascending order**

```
$user_query = new WP_User_Query( array ( 'orderby' => 'registered', 'order' => 'ASC' ) );

```

### [Date Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#date-parameters)

Date queries are handled through to the `[WP\_Date\_Query](https://developer.wordpress.org/reference/classes/wp_date_query/)` object and are applied to the `user_registered` field.

Available since [version 4.1](https://codex.wordpress.org/Version_4.1).

- **`date_query`** ( _array_) – See the documentation for the `[WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/ "Class Reference/WP Query")` class.

**Find users that registered during the last 12 hours:**

```
$args = array(
    'date_query' => array(
        array( 'after' => '12 hours ago', 'inclusive' => true )
    )
);
$user_query = new WP_User_Query( $args );

```

### [Custom Field Parameters](https://developer.wordpress.org/reference/classes/wp_user_query/\#custom-field-parameters)

Show users associated with a certain custom field.

The `[WP\_Meta\_Query](https://developer.wordpress.org/reference/classes/wp_meta_query/ "Class Reference/WP Meta Query")` class is used to parse this part of the query since [3.2.0](https://codex.wordpress.org/Version_3.2 "Version 3.2"), so check the docs for that class for the full, up to date [list of arguments](https://developer.wordpress.org/reference/classes/wp_meta_query/ "Class Reference/WP Meta Query").

- **`meta_key`** ( _string_) – Custom field key.
- **`meta_value`** ( _string_) – Custom field value.
- **`meta_compare`** ( _string_) – Operator to test the ‘ `meta_value`‘. See `'compare'` below.
- **`meta_query`** ( _array_) – Custom field parameters (available with [Version 3.5](https://codex.wordpress.org/Version_3.5 "Version 3.5")).

  - **`key`** ( _string_) – Custom field key.
  - **`value`** ( _string_ \| _array_) – Custom field value ( _Note_: Array support is limited to a compare value of ‘IN’, ‘NOT IN’, ‘BETWEEN’, ‘NOT BETWEEN’, ‘EXISTS’ or ‘NOT EXISTS’)
  - **`compare`** ( _string_) – Operator to test. Possible values are ‘=’, ‘!=’, ‘>’, ‘>=’, ‘<‘, ‘<=’, ‘LIKE’, ‘NOT LIKE’, ‘IN’, ‘NOT IN’, ‘BETWEEN’, ‘NOT BETWEEN’, ‘EXISTS’, and ‘NOT EXISTS’ ; ‘REGEXP’, ‘NOT REGEXP’ and ‘RLIKE’ were added in WordPress 3.7. Default value is ‘=’.

    **Note:** Currently `'NOT EXISTS'` does not always work as intended if `'relation'` is `'OR'` when, (1) using the [`'role'`](https://codex.wordpress.org/Class_Reference/WP_User_Query#User_Role_Parameter) parameter on single site installs, or (2) for any query on multisite. See [ticket #23849](https://core.trac.wordpress.org/ticket/23849).

    **Note 2:** with ‘LIKE’ the value parameter is change to ‘%<value>%’. So the string is searched anywhere in the custom field value. If value parameter contain a ‘%’ it is escaped. So it bans to search a string beginning by some characters, for exemple… To construct this query you must use ‘REGEXP’ with a regular expression in value parameter (ex : ‘^n.\*’ matchs all values that beginning by “n” or “N”).
  - **`type`** ( _string_) – Custom field type. Possible values are ‘NUMERIC’, ‘BINARY’, ‘CHAR’, ‘DATE’, ‘DATETIME’, ‘DECIMAL’, ‘SIGNED’, ‘TIME’, ‘UNSIGNED’. Default value is ‘CHAR’. You can also specify precision and scale for the ‘DECIMAL’ and ‘NUMERIC’ types (for example, ‘DECIMAL(10,5)’ or ‘NUMERIC(10)’ are valid).

**Display users from Israel**

```
$user_query = new WP_User_Query( array( 'meta_key' => 'country', 'meta_value' => 'Israel' ) );

```

**Display users under 30 years old**

```
$user_query = new WP_User_Query( array( 'meta_key' => 'age', 'meta_value' => '30', 'meta_compare' => '<' ) );

```

**Multiple custom user fields handling**

```
$args = array(
	'meta_query' => array(
		'relation' => 'OR',
			array(
				'key'     => 'country',
				'value'   => 'Israel',
	 			'compare' => '='
			),
			array(
				'key'     => 'age',
				'value'   => array( 20, 30 ),
				'type'    => 'numeric',
				'compare' => 'BETWEEN'
			)
	)
 );
$user_query = new WP_User_Query( $args );

```

### [Who Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#who-parameter)

Which users?

- **`who`** ( _string_) – Which users to query. Currently only ‘authors’ is supported. Default is all users.

**Display only authors**

```
$user_query = new WP_User_Query( array( 'who' => 'authors' ) );

```

Equals to:

```
$args = array(
	'meta_key'     => 'user_level',
	'meta_value'   => '0',
	'meta_compare' => '!=',
	'blog_id'      => 0
)
$user_query = new WP_User_Query( $args );

```

### [Total Count Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#total-count-parameter)

- **`count_total`** ( _boolean_) – Whether to count the total number of users found. When `true` (default), the total number of results for the query can be retrieved using the `get_total()` method. If you don’t need the total number of results, set this to `false`.

### [Has Published Posts Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#has-published-posts-parameter)

- **`has_published_posts`** ( _boolean / array_) – Pass an array of post types to filter results to users who have published posts in those post types. `true` is an alias for all public post types. Default is `null`. Since [Version 4.3](https://codex.wordpress.org/Version_4.3 "Version 4.3").

### [Return Fields Parameter](https://developer.wordpress.org/reference/classes/wp_user_query/\#return-fields-parameter)

Set return values.

- **`fields`** ( _string\|array_) – Which fields to return. Defaults to _all_.

  - ‘ `ID`‘ – Return an array of user id’s.
  - ‘ `display_name`‘ – Return an array of user display names.
  - ‘ `login`‘ / ‘ `user_login`‘ – Return an array of user login names.
  - ‘ `nicename`‘ / ‘ `user_nicename`‘ – Return an array of user nicenames.
  - ‘ `email`‘ / ‘ `user_email`‘ – Return an array of user emails.
  - ‘ `url`‘ / ‘ `user_url`‘ – Return an array of user urls.
  - ‘ `registered`‘ / ‘ `user_registered`‘ – Return an array of user registered dates.
  - ‘ `all` (default) or `all_with_meta`‘ – Returns an array of [WP\_User](https://codex.wordpress.org/Class_Reference/WP_User "Class Reference/WP User") objects. Must pass an array to subset fields returned. \*’all\_with\_meta’ currently returns the same fields as ‘all’ which does not include user fields stored in wp\_usermeta. You must create a second query to get the user meta fields by ID or use the \_\_get PHP magic method to get the values of these fields.

**Return an array of [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object**

```
$user_query = new WP_User_Query( array( 'role' => 'editor', 'fields' => 'all' ) );

```

**Return List all blog editors, return limited fields in resulting row objects:**

```
$user_fields = array( 'user_login', 'user_nicename', 'user_email', 'user_url' );
$user_query = new WP_User_Query( array( 'role' => 'editor', 'fields' => $user_fields ) );

```

## [Return Values](https://developer.wordpress.org/reference/classes/wp_user_query/\#return-values)

(Array)An array of IDs, stdClass objects, or [WP\_User](https://codex.wordpress.org/Class_Reference/WP_User "Class Reference/WP User") objects, depending on the value of the ‘ `fields`‘ parameter.

- If ‘ `fields`‘ is set to ‘all’ (default), or ‘all\_with\_meta’, it will return an array of [WP\_User](https://codex.wordpress.org/Class_Reference/WP_User "Class Reference/WP User") objects (does not include related user meta fields even with ‘all\_with\_meta’ set) .
- If ‘ `fields`‘ is set to an array of `[wp\_users](https://codex.wordpress.org/Database_Description#Table:_wp_users "Database Description")` table fields, it will return an array of stdClass objects with only those fields.
- If ‘ `fields`‘ is set to any individual `[wp\_users](https://codex.wordpress.org/Database_Description#Table:_wp_users "Database Description")` table field, an array of IDs will be returned.

## [Filters](https://developer.wordpress.org/reference/classes/wp_user_query/\#filters)

- **`[found\_users\_query](https://developer.wordpress.org/reference/hooks/found_users_query/ "Plugin API/Filter Reference/found users query (page does not exist)")`** – Alters SQL ‘SELECT FOUND\_ROWS()’ clause to the query that returns the count total.

## [Methods](https://developer.wordpress.org/reference/classes/wp_user_query/\#methods)

| Name | Description |
| --- | --- |
| [WP\_User\_Query::\_\_call](https://developer.wordpress.org/reference/classes/wp_user_query/__call/) | Makes private/protected methods readable for backward compatibility. |
| [WP\_User\_Query::\_\_construct](https://developer.wordpress.org/reference/classes/wp_user_query/__construct/) | Constructor. |
| [WP\_User\_Query::\_\_get](https://developer.wordpress.org/reference/classes/wp_user_query/__get/) | Makes private properties readable for backward compatibility. |
| [WP\_User\_Query::\_\_isset](https://developer.wordpress.org/reference/classes/wp_user_query/__isset/) | Makes private properties checkable for backward compatibility. |
| [WP\_User\_Query::\_\_set](https://developer.wordpress.org/reference/classes/wp_user_query/__set/) | Makes private properties settable for backward compatibility. |
| [WP\_User\_Query::\_\_unset](https://developer.wordpress.org/reference/classes/wp_user_query/__unset/) | Makes private properties un-settable for backward compatibility. |
| [WP\_User\_Query::fill\_query\_vars](https://developer.wordpress.org/reference/classes/wp_user_query/fill_query_vars/) | Fills in missing query variables with default values. |
| [WP\_User\_Query::generate\_cache\_key](https://developer.wordpress.org/reference/classes/wp_user_query/generate_cache_key/) | Generate cache key. |
| [WP\_User\_Query::get](https://developer.wordpress.org/reference/classes/wp_user_query/get/) | Retrieves query variable. |
| [WP\_User\_Query::get\_results](https://developer.wordpress.org/reference/classes/wp_user_query/get_results/) | Returns the list of users. |
| [WP\_User\_Query::get\_search\_sql](https://developer.wordpress.org/reference/classes/wp_user_query/get_search_sql/) | Used internally to generate an SQL string for searching across multiple columns. |
| [WP\_User\_Query::get\_total](https://developer.wordpress.org/reference/classes/wp_user_query/get_total/) | Returns the total number of users for the current query. |
| [WP\_User\_Query::parse\_order](https://developer.wordpress.org/reference/classes/wp_user_query/parse_order/) | Parses an ‘order’ query variable and casts it to ASC or DESC as necessary. |
| [WP\_User\_Query::parse\_orderby](https://developer.wordpress.org/reference/classes/wp_user_query/parse_orderby/) | Parses and sanitizes ‘orderby’ keys passed to the user query. |
| [WP\_User\_Query::prepare\_query](https://developer.wordpress.org/reference/classes/wp_user_query/prepare_query/) | Prepares the query variables. |
| [WP\_User\_Query::query](https://developer.wordpress.org/reference/classes/wp_user_query/query/) | Executes the query, with the current variables. |
| [WP\_User\_Query::set](https://developer.wordpress.org/reference/classes/wp_user_query/set/) | Sets query variable. |

## [Source](https://developer.wordpress.org/reference/classes/wp_user_query/\#source)

`wp-includes/class-wp-user-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_user_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)

```php
class WP_User_Query {

	/**
	 * Query vars, after parsing
	 *
	 * @since 3.5.0
	 * @var array
	 */
	public $query_vars = array();

	/**
	 * List of found user IDs.
	 *
	 * @since 3.1.0
	 * @var array
	 */
	private $results;

	/**
	 * Total number of found users for the current query
	 *
	 * @since 3.1.0
	 * @var int
	 */
	private $total_users = 0;

	/**
	 * Metadata query container.
	 *
	 * @since 4.2.0
	 * @var WP_Meta_Query
	 */
	public $meta_query = false;

	/**
	 * The SQL query used to fetch matching users.
	 *
	 * @since 4.4.0
	 * @var string
	 */
	public $request;

	private $compat_fields = array( 'results', 'total_users' );

	// SQL clauses.
	public $query_fields;
	public $query_from;
	public $query_where;
	public $query_orderby;
	public $query_limit;

	/**
	 * Constructor.
	 *
	 * @since 3.1.0
	 *
	 * @param null|string|array $query Optional. The query variables.
	 *                                 See WP_User_Query::prepare_query() for information on accepted arguments.
	 */
	public function __construct( $query = null ) {
		if ( ! empty( $query ) ) {
			$this->prepare_query( $query );
			$this->query();
		}
	}

	/**
	 * Fills in missing query variables with default values.
	 *
	 * @since 4.4.0
	 *
	 * @param string|array $args Query vars, as passed to `WP_User_Query`.
	 * @return array Complete query variables with undefined ones filled in with defaults.
	 */
	public static function fill_query_vars( $args ) {
		$defaults = array(
			'blog_id'             => get_current_blog_id(),
			'role'                => '',
			'role__in'            => array(),
			'role__not_in'        => array(),
			'capability'          => '',
			'capability__in'      => array(),
			'capability__not_in'  => array(),
			'meta_key'            => '',
			'meta_value'          => '',
			'meta_compare'        => '',
			'include'             => array(),
			'exclude'             => array(),
			'search'              => '',
			'search_columns'      => array(),
			'orderby'             => 'login',
			'order'               => 'ASC',
			'offset'              => '',
			'number'              => '',
			'paged'               => 1,
			'count_total'         => true,
			'fields'              => 'all',
			'who'                 => '',
			'has_published_posts' => null,
			'nicename'            => '',
			'nicename__in'        => array(),
			'nicename__not_in'    => array(),
			'login'               => '',
			'login__in'           => array(),
			'login__not_in'       => array(),
			'cache_results'       => true,
		);

		return wp_parse_args( $args, $defaults );
	}

	/**
	 * Prepares the query variables.
	 *
	 * @since 3.1.0
	 * @since 4.1.0 Added the ability to order by the `include` value.
	 * @since 4.2.0 Added 'meta_value_num' support for `$orderby` parameter. Added multi-dimensional array syntax
	 *              for `$orderby` parameter.
	 * @since 4.3.0 Added 'has_published_posts' parameter.
	 * @since 4.4.0 Added 'paged', 'role__in', and 'role__not_in' parameters. The 'role' parameter was updated to
	 *              permit an array or comma-separated list of values. The 'number' parameter was updated to support
	 *              querying for all users with using -1.
	 * @since 4.7.0 Added 'nicename', 'nicename__in', 'nicename__not_in', 'login', 'login__in',
	 *              and 'login__not_in' parameters.
	 * @since 5.1.0 Introduced the 'meta_compare_key' parameter.
	 * @since 5.3.0 Introduced the 'meta_type_key' parameter.
	 * @since 5.9.0 Added 'capability', 'capability__in', and 'capability__not_in' parameters.
	 *              Deprecated the 'who' parameter.
	 * @since 6.3.0 Added 'cache_results' parameter.
	 *
	 * @global wpdb     $wpdb     WordPress database abstraction object.
	 * @global WP_Roles $wp_roles WordPress role management object.
	 *
	 * @param string|array $query {
	 *     Optional. Array or string of query parameters.
	 *
	 *     @type int             $blog_id             The site ID. Default is the current site.
	 *     @type string|string[] $role                An array or a comma-separated list of role names that users
	 *                                                must match to be included in results. Note that this is
	 *                                                an inclusive list: users must match *each* role. Default empty.
	 *     @type string[]        $role__in            An array of role names. Matched users must have at least one
	 *                                                of these roles. Default empty array.
	 *     @type string[]        $role__not_in        An array of role names to exclude. Users matching one or more
	 *                                                of these roles will not be included in results. Default empty array.
	 *     @type string|string[] $meta_key            Meta key or keys to filter by.
	 *     @type string|string[] $meta_value          Meta value or values to filter by.
	 *     @type string          $meta_compare        MySQL operator used for comparing the meta value.
	 *                                                See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_compare_key    MySQL operator used for comparing the meta key.
	 *                                                See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_type           MySQL data type that the meta_value column will be CAST to for comparisons.
	 *                                                See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_type_key       MySQL data type that the meta_key column will be CAST to for comparisons.
	 *                                                See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type array           $meta_query          An associative array of WP_Meta_Query arguments.
	 *                                                See WP_Meta_Query::__construct() for accepted values.
	 *     @type string|string[] $capability          An array or a comma-separated list of capability names that users
	 *                                                must match to be included in results. Note that this is
	 *                                                an inclusive list: users must match *each* capability.
	 *                                                Does NOT work for capabilities not in the database or filtered
	 *                                                via 'map_meta_cap'. Default empty.
	 *     @type string[]        $capability__in      An array of capability names. Matched users must have at least one
	 *                                                of these capabilities.
	 *                                                Does NOT work for capabilities not in the database or filtered
	 *                                                via 'map_meta_cap'. Default empty array.
	 *     @type string[]        $capability__not_in  An array of capability names to exclude. Users matching one or more
	 *                                                of these capabilities will not be included in results.
	 *                                                Does NOT work for capabilities not in the database or filtered
	 *                                                via 'map_meta_cap'. Default empty array.
	 *     @type int[]           $include             An array of user IDs to include. Default empty array.
	 *     @type int[]           $exclude             An array of user IDs to exclude. Default empty array.
	 *     @type string          $search              Search keyword. Searches for possible string matches on columns.
	 *                                                When `$search_columns` is left empty, it tries to determine which
	 *                                                column to search in based on search string. Default empty.
	 *     @type string[]        $search_columns      Array of column names to be searched. Accepts 'ID', 'user_login',
	 *                                                'user_email', 'user_url', 'user_nicename', 'display_name'.
	 *                                                Default empty array.
	 *     @type string|array    $orderby             Field(s) to sort the retrieved users by. May be a single value,
	 *                                                an array of values, or a multi-dimensional array with fields as
	 *                                                keys and orders ('ASC' or 'DESC') as values. Accepted values are:
	 *                                                - 'ID'
	 *                                                - 'display_name' (or 'name')
	 *                                                - 'include'
	 *                                                - 'user_login' (or 'login')
	 *                                                - 'login__in'
	 *                                                - 'user_nicename' (or 'nicename')
	 *                                                - 'nicename__in'
	 *                                                - 'user_email' (or 'email')
	 *                                                - 'user_url' (or 'url')
	 *                                                - 'user_registered' (or 'registered')
	 *                                                - 'post_count'
	 *                                                - 'meta_value'
	 *                                                - 'meta_value_num'
	 *                                                - The value of `$meta_key`
	 *                                                - An array key of `$meta_query`
	 *                                                To use 'meta_value' or 'meta_value_num', `$meta_key`
	 *                                                must be also be defined. Default 'user_login'.
	 *     @type string          $order               Designates ascending or descending order of users. Order values
	 *                                                passed as part of an `$orderby` array take precedence over this
	 *                                                parameter. Accepts 'ASC', 'DESC'. Default 'ASC'.
	 *     @type int             $offset              Number of users to offset in retrieved results. Can be used in
	 *                                                conjunction with pagination. Default 0.
	 *     @type int             $number              Number of users to limit the query for. Can be used in
	 *                                                conjunction with pagination. Value -1 (all) is supported, but
	 *                                                should be used with caution on larger sites.
	 *                                                Default -1 (all users).
	 *     @type int             $paged               When used with number, defines the page of results to return.
	 *                                                Default 1.
	 *     @type bool            $count_total         Whether to count the total number of users found. If pagination
	 *                                                is not needed, setting this to false can improve performance.
	 *                                                Default true.
	 *     @type string|string[] $fields              Which fields to return. Single or all fields (string), or array
	 *                                                of fields. Accepts:
	 *                                                - 'ID'
	 *                                                - 'display_name'
	 *                                                - 'user_login'
	 *                                                - 'user_nicename'
	 *                                                - 'user_email'
	 *                                                - 'user_url'
	 *                                                - 'user_registered'
	 *                                                - 'user_pass'
	 *                                                - 'user_activation_key'
	 *                                                - 'user_status'
	 *                                                - 'spam' (only available on multisite installs)
	 *                                                - 'deleted' (only available on multisite installs)
	 *                                                - 'all' for all fields and loads user meta.
	 *                                                - 'all_with_meta' Deprecated. Use 'all'.
	 *                                                Default 'all'.
	 *     @type string          $who                 Deprecated, use `$capability` instead.
	 *                                                Type of users to query. Accepts 'authors'.
	 *                                                Default empty (all users).
	 *     @type bool|string[]   $has_published_posts Pass an array of post types to filter results to users who have
	 *                                                published posts in those post types. `true` is an alias for all
	 *                                                public post types.
	 *     @type string          $nicename            The user nicename. Default empty.
	 *     @type string[]        $nicename__in        An array of nicenames to include. Users matching one of these
	 *                                                nicenames will be included in results. Default empty array.
	 *     @type string[]        $nicename__not_in    An array of nicenames to exclude. Users matching one of these
	 *                                                nicenames will not be included in results. Default empty array.
	 *     @type string          $login               The user login. Default empty.
	 *     @type string[]        $login__in           An array of logins to include. Users matching one of these
	 *                                                logins will be included in results. Default empty array.
	 *     @type string[]        $login__not_in       An array of logins to exclude. Users matching one of these
	 *                                                logins will not be included in results. Default empty array.
	 *     @type bool            $cache_results       Whether to cache user information. Default true.
	 * }
	 */
	public function prepare_query( $query = array() ) {
		global $wpdb, $wp_roles;

		if ( empty( $this->query_vars ) || ! empty( $query ) ) {
			$this->query_limit = null;
			$this->query_vars  = $this->fill_query_vars( $query );
		}

		/**
		 * Fires before the WP_User_Query has been parsed.
		 *
		 * The passed WP_User_Query object contains the query variables,
		 * not yet passed into SQL.
		 *
		 * @since 4.0.0
		 *
		 * @param WP_User_Query $query Current instance of WP_User_Query (passed by reference).
		 */
		do_action_ref_array( 'pre_get_users', array( &$this ) );

		// Ensure that query vars are filled after 'pre_get_users'.
		$qv =& $this->query_vars;
		$qv = $this->fill_query_vars( $qv );

		$allowed_fields = array(
			'id',
			'user_login',
			'user_pass',
			'user_nicename',
			'user_email',
			'user_url',
			'user_registered',
			'user_activation_key',
			'user_status',
			'display_name',
		);
		if ( is_multisite() ) {
			$allowed_fields[] = 'spam';
			$allowed_fields[] = 'deleted';
		}

		if ( is_array( $qv['fields'] ) ) {
			$qv['fields'] = array_map( 'strtolower', $qv['fields'] );
			$qv['fields'] = array_intersect( array_unique( $qv['fields'] ), $allowed_fields );

			if ( empty( $qv['fields'] ) ) {
				$qv['fields'] = array( 'id' );
			}

			$this->query_fields = array();
			foreach ( $qv['fields'] as $field ) {
				$field                = 'id' === $field ? 'ID' : sanitize_key( $field );
				$this->query_fields[] = "$wpdb->users.$field";
			}
			$this->query_fields = implode( ',', $this->query_fields );
		} elseif ( 'all_with_meta' === $qv['fields'] || 'all' === $qv['fields'] || ! in_array( $qv['fields'], $allowed_fields, true ) ) {
			$this->query_fields = "$wpdb->users.ID";
		} else {
			$field              = 'id' === strtolower( $qv['fields'] ) ? 'ID' : sanitize_key( $qv['fields'] );
			$this->query_fields = "$wpdb->users.$field";
		}

		if ( isset( $qv['count_total'] ) && $qv['count_total'] ) {
			$this->query_fields = 'SQL_CALC_FOUND_ROWS ' . $this->query_fields;
		}

		$this->query_from  = "FROM $wpdb->users";
		$this->query_where = 'WHERE 1=1';

		// Parse and sanitize 'include', for use by 'orderby' as well as 'include' below.
		if ( ! empty( $qv['include'] ) ) {
			$include = wp_parse_id_list( $qv['include'] );
		} else {
			$include = false;
		}

		$blog_id = 0;
		if ( isset( $qv['blog_id'] ) ) {
			$blog_id = absint( $qv['blog_id'] );
		}

		if ( $qv['has_published_posts'] && $blog_id ) {
			if ( true === $qv['has_published_posts'] ) {
				$post_types = get_post_types( array( 'public' => true ) );
			} else {
				$post_types = (array) $qv['has_published_posts'];
			}

			foreach ( $post_types as &$post_type ) {
				$post_type = $wpdb->prepare( '%s', $post_type );
			}

			$posts_table        = $wpdb->get_blog_prefix( $blog_id ) . 'posts';
			$this->query_where .= " AND $wpdb->users.ID IN ( SELECT DISTINCT $posts_table.post_author FROM $posts_table WHERE $posts_table.post_status = 'publish' AND $posts_table.post_type IN ( " . implode( ', ', $post_types ) . ' ) )';
		}

		// nicename
		if ( '' !== $qv['nicename'] ) {
			$this->query_where .= $wpdb->prepare( ' AND user_nicename = %s', $qv['nicename'] );
		}

		if ( ! empty( $qv['nicename__in'] ) ) {
			$sanitized_nicename__in = array_map( 'esc_sql', $qv['nicename__in'] );
			$nicename__in           = implode( "','", $sanitized_nicename__in );
			$this->query_where     .= " AND user_nicename IN ( '$nicename__in' )";
		}

		if ( ! empty( $qv['nicename__not_in'] ) ) {
			$sanitized_nicename__not_in = array_map( 'esc_sql', $qv['nicename__not_in'] );
			$nicename__not_in           = implode( "','", $sanitized_nicename__not_in );
			$this->query_where         .= " AND user_nicename NOT IN ( '$nicename__not_in' )";
		}

		// login
		if ( '' !== $qv['login'] ) {
			$this->query_where .= $wpdb->prepare( ' AND user_login = %s', $qv['login'] );
		}

		if ( ! empty( $qv['login__in'] ) ) {
			$sanitized_login__in = array_map( 'esc_sql', $qv['login__in'] );
			$login__in           = implode( "','", $sanitized_login__in );
			$this->query_where  .= " AND user_login IN ( '$login__in' )";
		}

		if ( ! empty( $qv['login__not_in'] ) ) {
			$sanitized_login__not_in = array_map( 'esc_sql', $qv['login__not_in'] );
			$login__not_in           = implode( "','", $sanitized_login__not_in );
			$this->query_where      .= " AND user_login NOT IN ( '$login__not_in' )";
		}

		// Meta query.
		$this->meta_query = new WP_Meta_Query();
		$this->meta_query->parse_query_vars( $qv );

		if ( isset( $qv['who'] ) && 'authors' === $qv['who'] && $blog_id ) {
			_deprecated_argument(
				'WP_User_Query',
				'5.9.0',
				sprintf(
					/* translators: 1: who, 2: capability */
					__( '%1$s is deprecated. Use %2$s instead.' ),
					'<code>who</code>',
					'<code>capability</code>'
				)
			);

			$who_query = array(
				'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'user_level',
				'value'   => 0,
				'compare' => '!=',
			);

			// Prevent extra meta query.
			$qv['blog_id'] = 0;
			$blog_id       = 0;

			if ( empty( $this->meta_query->queries ) ) {
				$this->meta_query->queries = array( $who_query );
			} else {
				// Append the cap query to the original queries and reparse the query.
				$this->meta_query->queries = array(
					'relation' => 'AND',
					array( $this->meta_query->queries, $who_query ),
				);
			}

			$this->meta_query->parse_query_vars( $this->meta_query->queries );
		}

		// Roles.
		$roles = array();
		if ( isset( $qv['role'] ) ) {
			if ( is_array( $qv['role'] ) ) {
				$roles = $qv['role'];
			} elseif ( is_string( $qv['role'] ) && ! empty( $qv['role'] ) ) {
				$roles = array_map( 'trim', explode( ',', $qv['role'] ) );
			}
		}

		$role__in = array();
		if ( isset( $qv['role__in'] ) ) {
			$role__in = (array) $qv['role__in'];
		}

		$role__not_in = array();
		if ( isset( $qv['role__not_in'] ) ) {
			$role__not_in = (array) $qv['role__not_in'];
		}

		// Capabilities.
		$available_roles = array();

		if ( ! empty( $qv['capability'] ) || ! empty( $qv['capability__in'] ) || ! empty( $qv['capability__not_in'] ) ) {
			$wp_roles->for_site( $blog_id );
			$available_roles = $wp_roles->roles;
		}

		$capabilities = array();
		if ( ! empty( $qv['capability'] ) ) {
			if ( is_array( $qv['capability'] ) ) {
				$capabilities = $qv['capability'];
			} elseif ( is_string( $qv['capability'] ) ) {
				$capabilities = array_map( 'trim', explode( ',', $qv['capability'] ) );
			}
		}

		$capability__in = array();
		if ( ! empty( $qv['capability__in'] ) ) {
			$capability__in = (array) $qv['capability__in'];
		}

		$capability__not_in = array();
		if ( ! empty( $qv['capability__not_in'] ) ) {
			$capability__not_in = (array) $qv['capability__not_in'];
		}

		// Keep track of all capabilities and the roles they're added on.
		$caps_with_roles = array();

		foreach ( $available_roles as $role => $role_data ) {
			$role_caps = array_keys( array_filter( $role_data['capabilities'] ) );

			foreach ( $capabilities as $cap ) {
				if ( in_array( $cap, $role_caps, true ) ) {
					$caps_with_roles[ $cap ][] = $role;
					break;
				}
			}

			foreach ( $capability__in as $cap ) {
				if ( in_array( $cap, $role_caps, true ) ) {
					$role__in[] = $role;
					break;
				}
			}

			foreach ( $capability__not_in as $cap ) {
				if ( in_array( $cap, $role_caps, true ) ) {
					$role__not_in[] = $role;
					break;
				}
			}
		}

		$role__in     = array_merge( $role__in, $capability__in );
		$role__not_in = array_merge( $role__not_in, $capability__not_in );

		$roles        = array_unique( $roles );
		$role__in     = array_unique( $role__in );
		$role__not_in = array_unique( $role__not_in );

		// Support querying by capabilities added directly to users.
		if ( $blog_id && ! empty( $capabilities ) ) {
			$capabilities_clauses = array( 'relation' => 'AND' );

			foreach ( $capabilities as $cap ) {
				$clause = array( 'relation' => 'OR' );

				$clause[] = array(
					'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
					'value'   => '"' . $cap . '"',
					'compare' => 'LIKE',
				);

				if ( ! empty( $caps_with_roles[ $cap ] ) ) {
					foreach ( $caps_with_roles[ $cap ] as $role ) {
						$clause[] = array(
							'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
							'value'   => '"' . $role . '"',
							'compare' => 'LIKE',
						);
					}
				}

				$capabilities_clauses[] = $clause;
			}

			$role_queries[] = $capabilities_clauses;

			if ( empty( $this->meta_query->queries ) ) {
				$this->meta_query->queries[] = $capabilities_clauses;
			} else {
				// Append the cap query to the original queries and reparse the query.
				$this->meta_query->queries = array(
					'relation' => 'AND',
					array( $this->meta_query->queries, array( $capabilities_clauses ) ),
				);
			}

			$this->meta_query->parse_query_vars( $this->meta_query->queries );
		}

		if ( $blog_id && ( ! empty( $roles ) || ! empty( $role__in ) || ! empty( $role__not_in ) || is_multisite() ) ) {
			$role_queries = array();

			$roles_clauses = array( 'relation' => 'AND' );
			if ( ! empty( $roles ) ) {
				foreach ( $roles as $role ) {
					$roles_clauses[] = array(
						'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
						'value'   => '"' . $role . '"',
						'compare' => 'LIKE',
					);
				}

				$role_queries[] = $roles_clauses;
			}

			$role__in_clauses = array( 'relation' => 'OR' );
			if ( ! empty( $role__in ) ) {
				foreach ( $role__in as $role ) {
					$role__in_clauses[] = array(
						'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
						'value'   => '"' . $role . '"',
						'compare' => 'LIKE',
					);
				}

				$role_queries[] = $role__in_clauses;
			}

			$role__not_in_clauses = array( 'relation' => 'AND' );
			if ( ! empty( $role__not_in ) ) {
				foreach ( $role__not_in as $role ) {
					$role__not_in_clauses[] = array(
						'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
						'value'   => '"' . $role . '"',
						'compare' => 'NOT LIKE',
					);
				}

				$role_queries[] = $role__not_in_clauses;
			}

			// If there are no specific roles named, make sure the user is a member of the site.
			if ( empty( $role_queries ) ) {
				$role_queries[] = array(
					'key'     => $wpdb->get_blog_prefix( $blog_id ) . 'capabilities',
					'compare' => 'EXISTS',
				);
			}

			// Specify that role queries should be joined with AND.
			$role_queries['relation'] = 'AND';

			if ( empty( $this->meta_query->queries ) ) {
				$this->meta_query->queries = $role_queries;
			} else {
				// Append the cap query to the original queries and reparse the query.
				$this->meta_query->queries = array(
					'relation' => 'AND',
					array( $this->meta_query->queries, $role_queries ),
				);
			}

			$this->meta_query->parse_query_vars( $this->meta_query->queries );
		}

		if ( ! empty( $this->meta_query->queries ) ) {
			$clauses            = $this->meta_query->get_sql( 'user', $wpdb->users, 'ID', $this );
			$this->query_from  .= $clauses['join'];
			$this->query_where .= $clauses['where'];

			if ( $this->meta_query->has_or_relation() ) {
				$this->query_fields = 'DISTINCT ' . $this->query_fields;
			}
		}

		// Sorting.
		$qv['order'] = isset( $qv['order'] ) ? strtoupper( $qv['order'] ) : '';
		$order       = $this->parse_order( $qv['order'] );

		if ( empty( $qv['orderby'] ) ) {
			// Default order is by 'user_login'.
			$ordersby = array( 'user_login' => $order );
		} elseif ( is_array( $qv['orderby'] ) ) {
			$ordersby = $qv['orderby'];
		} else {
			// 'orderby' values may be a comma- or space-separated list.
			$ordersby = preg_split( '/[,\s]+/', $qv['orderby'] );
		}

		$orderby_array = array();
		foreach ( $ordersby as $_key => $_value ) {
			if ( ! $_value ) {
				continue;
			}

			if ( is_int( $_key ) ) {
				// Integer key means this is a flat array of 'orderby' fields.
				$_orderby = $_value;
				$_order   = $order;
			} else {
				// Non-integer key means this the key is the field and the value is ASC/DESC.
				$_orderby = $_key;
				$_order   = $_value;
			}

			$parsed = $this->parse_orderby( $_orderby );

			if ( ! $parsed ) {
				continue;
			}

			if ( 'nicename__in' === $_orderby || 'login__in' === $_orderby ) {
				$orderby_array[] = $parsed;
			} else {
				$orderby_array[] = $parsed . ' ' . $this->parse_order( $_order );
			}
		}

		// If no valid clauses were found, order by user_login.
		if ( empty( $orderby_array ) ) {
			$orderby_array[] = "user_login $order";
		}

		$this->query_orderby = 'ORDER BY ' . implode( ', ', $orderby_array );

		// Limit.
		if ( isset( $qv['number'] ) && $qv['number'] > 0 ) {
			if ( $qv['offset'] ) {
				$this->query_limit = $wpdb->prepare( 'LIMIT %d, %d', $qv['offset'], $qv['number'] );
			} else {
				$this->query_limit = $wpdb->prepare( 'LIMIT %d, %d', $qv['number'] * ( $qv['paged'] - 1 ), $qv['number'] );
			}
		}

		$search = '';
		if ( isset( $qv['search'] ) ) {
			$search = trim( $qv['search'] );
		}

		if ( $search ) {
			$leading_wild  = ( ltrim( $search, '*' ) !== $search );
			$trailing_wild = ( rtrim( $search, '*' ) !== $search );
			if ( $leading_wild && $trailing_wild ) {
				$wild = 'both';
			} elseif ( $leading_wild ) {
				$wild = 'leading';
			} elseif ( $trailing_wild ) {
				$wild = 'trailing';
			} else {
				$wild = false;
			}
			if ( $wild ) {
				$search = trim( $search, '*' );
			}

			$search_columns = array();
			if ( $qv['search_columns'] ) {
				$search_columns = array_intersect( $qv['search_columns'], array( 'ID', 'user_login', 'user_email', 'user_url', 'user_nicename', 'display_name' ) );
			}
			if ( ! $search_columns ) {
				if ( str_contains( $search, '@' ) ) {
					$search_columns = array( 'user_email' );
				} elseif ( is_numeric( $search ) ) {
					$search_columns = array( 'user_login', 'ID' );
				} elseif ( preg_match( '|^https?://|', $search ) && ! ( is_multisite() && wp_is_large_network( 'users' ) ) ) {
					$search_columns = array( 'user_url' );
				} else {
					$search_columns = array( 'user_login', 'user_url', 'user_email', 'user_nicename', 'display_name' );
				}
			}

			/**
			 * Filters the columns to search in a WP_User_Query search.
			 *
			 * The default columns depend on the search term, and include 'ID', 'user_login',
			 * 'user_email', 'user_url', 'user_nicename', and 'display_name'.
			 *
			 * @since 3.6.0
			 *
			 * @param string[]      $search_columns Array of column names to be searched.
			 * @param string        $search         Text being searched.
			 * @param WP_User_Query $query          The current WP_User_Query instance.
			 */
			$search_columns = apply_filters( 'user_search_columns', $search_columns, $search, $this );

			$this->query_where .= $this->get_search_sql( $search, $search_columns, $wild );
		}

		if ( ! empty( $include ) ) {
			// Sanitized earlier.
			$ids                = implode( ',', $include );
			$this->query_where .= " AND $wpdb->users.ID IN ($ids)";
		} elseif ( ! empty( $qv['exclude'] ) ) {
			$ids                = implode( ',', wp_parse_id_list( $qv['exclude'] ) );
			$this->query_where .= " AND $wpdb->users.ID NOT IN ($ids)";
		}

		// Date queries are allowed for the user_registered field.
		if ( ! empty( $qv['date_query'] ) && is_array( $qv['date_query'] ) ) {
			$date_query         = new WP_Date_Query( $qv['date_query'], 'user_registered' );
			$this->query_where .= $date_query->get_sql();
		}

		/**
		 * Fires after the WP_User_Query has been parsed, and before
		 * the query is executed.
		 *
		 * The passed WP_User_Query object contains SQL parts formed
		 * from parsing the given query.
		 *
		 * @since 3.1.0
		 *
		 * @param WP_User_Query $query Current instance of WP_User_Query (passed by reference).
		 */
		do_action_ref_array( 'pre_user_query', array( &$this ) );
	}

	/**
	 * Executes the query, with the current variables.
	 *
	 * @since 3.1.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 */
	public function query() {
		global $wpdb;

		if ( ! did_action( 'plugins_loaded' ) ) {
			_doing_it_wrong(
				'WP_User_Query::query',
				sprintf(
				/* translators: %s: plugins_loaded */
					__( 'User queries should not be run before the %s hook.' ),
					'<code>plugins_loaded</code>'
				),
				'6.1.1'
			);
		}

		$qv =& $this->query_vars;

		// Do not cache results if more than 3 fields are requested.
		if ( is_array( $qv['fields'] ) && count( $qv['fields'] ) > 3 ) {
			$qv['cache_results'] = false;
		}

		/**
		 * Filters the users array before the query takes place.
		 *
		 * Return a non-null value to bypass WordPress' default user queries.
		 *
		 * Filtering functions that require pagination information are encouraged to set
		 * the `total_users` property of the WP_User_Query object, passed to the filter
		 * by reference. If WP_User_Query does not perform a database query, it will not
		 * have enough information to generate these values itself.
		 *
		 * @since 5.1.0
		 *
		 * @param array|null    $results Return an array of user data to short-circuit WP's user query
		 *                               or null to allow WP to run its normal queries.
		 * @param WP_User_Query $query   The WP_User_Query instance (passed by reference).
		 */
		$this->results = apply_filters_ref_array( 'users_pre_query', array( null, &$this ) );

		if ( null === $this->results ) {
			// Beginning of the string is on a new line to prevent leading whitespace. See https://core.trac.wordpress.org/ticket/56841.
			$this->request =
				"SELECT {$this->query_fields}
				 {$this->query_from}
				 {$this->query_where}
				 {$this->query_orderby}
				 {$this->query_limit}";
			$cache_value   = false;
			$cache_key     = $this->generate_cache_key( $qv, $this->request );
			$cache_group   = 'user-queries';
			if ( $qv['cache_results'] ) {
				$cache_value = wp_cache_get( $cache_key, $cache_group );
			}
			if ( false !== $cache_value ) {
				$this->results     = $cache_value['user_data'];
				$this->total_users = $cache_value['total_users'];
			} else {

				if ( is_array( $qv['fields'] ) ) {
					$this->results = $wpdb->get_results( $this->request );
				} else {
					$this->results = $wpdb->get_col( $this->request );
				}

				if ( isset( $qv['count_total'] ) && $qv['count_total'] ) {
					/**
					 * Filters SELECT FOUND_ROWS() query for the current WP_User_Query instance.
					 *
					 * @since 3.2.0
					 * @since 5.1.0 Added the `$this` parameter.
					 *
					 * @global wpdb $wpdb WordPress database abstraction object.
					 *
					 * @param string        $sql   The SELECT FOUND_ROWS() query for the current WP_User_Query.
					 * @param WP_User_Query $query The current WP_User_Query instance.
					 */
					$found_users_query = apply_filters( 'found_users_query', 'SELECT FOUND_ROWS()', $this );

					$this->total_users = (int) $wpdb->get_var( $found_users_query );
				}

				if ( $qv['cache_results'] ) {
					$cache_value = array(
						'user_data'   => $this->results,
						'total_users' => $this->total_users,
					);
					wp_cache_add( $cache_key, $cache_value, $cache_group );
				}
			}
		}

		if ( ! $this->results ) {
			return;
		}
		if (
			is_array( $qv['fields'] ) &&
			isset( $this->results[0]->ID )
		) {
			foreach ( $this->results as $result ) {
				$result->id = $result->ID;
			}
		} elseif ( 'all_with_meta' === $qv['fields'] || 'all' === $qv['fields'] ) {
			if ( function_exists( 'cache_users' ) ) {
				cache_users( $this->results );
			}

			$r = array();
			foreach ( $this->results as $userid ) {
				if ( 'all_with_meta' === $qv['fields'] ) {
					$r[ $userid ] = new WP_User( $userid, '', $qv['blog_id'] );
				} else {
					$r[] = new WP_User( $userid, '', $qv['blog_id'] );
				}
			}

			$this->results = $r;
		}
	}

	/**
	 * Retrieves query variable.
	 *
	 * @since 3.5.0
	 *
	 * @param string $query_var Query variable key.
	 * @return mixed
	 */
	public function get( $query_var ) {
		if ( isset( $this->query_vars[ $query_var ] ) ) {
			return $this->query_vars[ $query_var ];
		}

		return null;
	}

	/**
	 * Sets query variable.
	 *
	 * @since 3.5.0
	 *
	 * @param string $query_var Query variable key.
	 * @param mixed  $value     Query variable value.
	 */
	public function set( $query_var, $value ) {
		$this->query_vars[ $query_var ] = $value;
	}

	/**
	 * Used internally to generate an SQL string for searching across multiple columns.
	 *
	 * @since 3.1.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param string   $search  Search string.
	 * @param string[] $columns Array of columns to search.
	 * @param bool     $wild    Whether to allow wildcard searches. Default is false for Network Admin, true for single site.
	 *                          Single site allows leading and trailing wildcards, Network Admin only trailing.
	 * @return string
	 */
	protected function get_search_sql( $search, $columns, $wild = false ) {
		global $wpdb;

		$searches      = array();
		$leading_wild  = ( 'leading' === $wild || 'both' === $wild ) ? '%' : '';
		$trailing_wild = ( 'trailing' === $wild || 'both' === $wild ) ? '%' : '';
		$like          = $leading_wild . $wpdb->esc_like( $search ) . $trailing_wild;

		foreach ( $columns as $column ) {
			if ( 'ID' === $column ) {
				$searches[] = $wpdb->prepare( "$column = %s", $search );
			} else {
				$searches[] = $wpdb->prepare( "$column LIKE %s", $like );
			}
		}

		return ' AND (' . implode( ' OR ', $searches ) . ')';
	}

	/**
	 * Returns the list of users.
	 *
	 * @since 3.1.0
	 *
	 * @return array Array of results.
	 */
	public function get_results() {
		return $this->results;
	}

	/**
	 * Returns the total number of users for the current query.
	 *
	 * @since 3.1.0
	 *
	 * @return int Number of total users.
	 */
	public function get_total() {
		return $this->total_users;
	}

	/**
	 * Parses and sanitizes 'orderby' keys passed to the user query.
	 *
	 * @since 4.2.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param string $orderby Alias for the field to order by.
	 * @return string Value to used in the ORDER clause, if `$orderby` is valid.
	 */
	protected function parse_orderby( $orderby ) {
		global $wpdb;

		$meta_query_clauses = $this->meta_query->get_clauses();

		$_orderby = '';
		if ( in_array( $orderby, array( 'login', 'nicename', 'email', 'url', 'registered' ), true ) ) {
			$_orderby = 'user_' . $orderby;
		} elseif ( in_array( $orderby, array( 'user_login', 'user_nicename', 'user_email', 'user_url', 'user_registered' ), true ) ) {
			$_orderby = $orderby;
		} elseif ( 'name' === $orderby || 'display_name' === $orderby ) {
			$_orderby = 'display_name';
		} elseif ( 'post_count' === $orderby ) {
			// @todo Avoid the JOIN.
			$where             = get_posts_by_author_sql( 'post' );
			$this->query_from .= " LEFT OUTER JOIN (
				SELECT post_author, COUNT(*) as post_count
				FROM $wpdb->posts
				$where
				GROUP BY post_author
			) p ON ({$wpdb->users}.ID = p.post_author)";
			$_orderby          = 'post_count';
		} elseif ( 'ID' === $orderby || 'id' === $orderby ) {
			$_orderby = 'ID';
		} elseif ( 'meta_value' === $orderby || $this->get( 'meta_key' ) === $orderby ) {
			$_orderby = "$wpdb->usermeta.meta_value";
		} elseif ( 'meta_value_num' === $orderby ) {
			$_orderby = "$wpdb->usermeta.meta_value+0";
		} elseif ( 'include' === $orderby && ! empty( $this->query_vars['include'] ) ) {
			$include     = wp_parse_id_list( $this->query_vars['include'] );
			$include_sql = implode( ',', $include );
			$_orderby    = "FIELD( $wpdb->users.ID, $include_sql )";
		} elseif ( 'nicename__in' === $orderby ) {
			$sanitized_nicename__in = array_map( 'esc_sql', $this->query_vars['nicename__in'] );
			$nicename__in           = implode( "','", $sanitized_nicename__in );
			$_orderby               = "FIELD( user_nicename, '$nicename__in' )";
		} elseif ( 'login__in' === $orderby ) {
			$sanitized_login__in = array_map( 'esc_sql', $this->query_vars['login__in'] );
			$login__in           = implode( "','", $sanitized_login__in );
			$_orderby            = "FIELD( user_login, '$login__in' )";
		} elseif ( isset( $meta_query_clauses[ $orderby ] ) ) {
			$meta_clause = $meta_query_clauses[ $orderby ];
			$_orderby    = sprintf( 'CAST(%s.meta_value AS %s)', esc_sql( $meta_clause['alias'] ), esc_sql( $meta_clause['cast'] ) );
		}

		return $_orderby;
	}

	/**
	 * Generate cache key.
	 *
	 * @since 6.3.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param array  $args Query arguments.
	 * @param string $sql  SQL statement.
	 * @return string Cache key.
	 */
	protected function generate_cache_key( array $args, $sql ) {
		global $wpdb;

		// Replace wpdb placeholder in the SQL statement used by the cache key.
		$sql = $wpdb->remove_placeholder_escape( $sql );

		$key          = md5( $sql );
		$last_changed = wp_cache_get_last_changed( 'users' );

		if ( empty( $args['orderby'] ) ) {
			// Default order is by 'user_login'.
			$ordersby = array( 'user_login' => '' );
		} elseif ( is_array( $args['orderby'] ) ) {
			$ordersby = $args['orderby'];
		} else {
			// 'orderby' values may be a comma- or space-separated list.
			$ordersby = preg_split( '/[,\s]+/', $args['orderby'] );
		}

		$blog_id = 0;
		if ( isset( $args['blog_id'] ) ) {
			$blog_id = absint( $args['blog_id'] );
		}

		if ( $args['has_published_posts'] || in_array( 'post_count', $ordersby, true ) ) {
			$switch = $blog_id && get_current_blog_id() !== $blog_id;
			if ( $switch ) {
				switch_to_blog( $blog_id );
			}

			$last_changed .= wp_cache_get_last_changed( 'posts' );

			if ( $switch ) {
				restore_current_blog();
			}
		}

		return "get_users:$key:$last_changed";
	}

	/**
	 * Parses an 'order' query variable and casts it to ASC or DESC as necessary.
	 *
	 * @since 4.2.0
	 *
	 * @param string $order The 'order' query variable.
	 * @return string The sanitized 'order' query variable.
	 */
	protected function parse_order( $order ) {
		if ( ! is_string( $order ) || empty( $order ) ) {
			return 'DESC';
		}

		if ( 'ASC' === strtoupper( $order ) ) {
			return 'ASC';
		} else {
			return 'DESC';
		}
	}

	/**
	 * Makes private properties readable for backward compatibility.
	 *
	 * @since 4.0.0
	 * @since 6.4.0 Getting a dynamic property is deprecated.
	 *
	 * @param string $name Property to get.
	 * @return mixed Property.
	 */
	public function __get( $name ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			return $this->$name;
		}

		wp_trigger_error(
			__METHOD__,
			"The property `{$name}` is not declared. Getting a dynamic property is " .
			'deprecated since version 6.4.0! Instead, declare the property on the class.',
			E_USER_DEPRECATED
		);
		return null;
	}

	/**
	 * Makes private properties settable for backward compatibility.
	 *
	 * @since 4.0.0
	 * @since 6.4.0 Setting a dynamic property is deprecated.
	 *
	 * @param string $name  Property to check if set.
	 * @param mixed  $value Property value.
	 */
	public function __set( $name, $value ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			$this->$name = $value;
			return;
		}

		wp_trigger_error(
			__METHOD__,
			"The property `{$name}` is not declared. Setting a dynamic property is " .
			'deprecated since version 6.4.0! Instead, declare the property on the class.',
			E_USER_DEPRECATED
		);
	}

	/**
	 * Makes private properties checkable for backward compatibility.
	 *
	 * @since 4.0.0
	 * @since 6.4.0 Checking a dynamic property is deprecated.
	 *
	 * @param string $name Property to check if set.
	 * @return bool Whether the property is set.
	 */
	public function __isset( $name ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			return isset( $this->$name );
		}

		wp_trigger_error(
			__METHOD__,
			"The property `{$name}` is not declared. Checking `isset()` on a dynamic property " .
			'is deprecated since version 6.4.0! Instead, declare the property on the class.',
			E_USER_DEPRECATED
		);
		return false;
	}

	/**
	 * Makes private properties un-settable for backward compatibility.
	 *
	 * @since 4.0.0
	 * @since 6.4.0 Unsetting a dynamic property is deprecated.
	 *
	 * @param string $name Property to unset.
	 */
	public function __unset( $name ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			unset( $this->$name );
			return;
		}

		wp_trigger_error(
			__METHOD__,
			"A property `{$name}` is not declared. Unsetting a dynamic property is " .
			'deprecated since version 6.4.0! Instead, declare the property on the class.',
			E_USER_DEPRECATED
		);
	}

	/**
	 * Makes private/protected methods readable for backward compatibility.
	 *
	 * @since 4.0.0
	 *
	 * @param string $name      Method to call.
	 * @param array  $arguments Arguments to pass when calling.
	 * @return mixed Return value of the callback, false otherwise.
	 */
	public function __call( $name, $arguments ) {
		if ( 'get_search_sql' === $name ) {
			return $this->get_search_sql( ...$arguments );
		}
		return false;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-user-query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-user-query.php#L18) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-user-query.php#L18-L1219)

## [Changelog](https://developer.wordpress.org/reference/classes/wp_user_query/\#changelog)

| Version | Description |
| --- | --- |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_user_query/\#user-contributed-notes)

1. [Skip to note 9 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-1714)



WordPress [WP\_User\_Query](https://developer.wordpress.org/reference/classes/wp_user_query/) Generator:



[https://GenerateWP.com/wp\_user\_query/](https://generatewp.com/wp_user_query/)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D1714%23feedback-editor-1714)

2. [Skip to note 10 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-2008)



**If you want to search a user by first\_name / last\_name / description and the default search\_columns.**





`wp-includes/class-wp-user-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_user_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
// The search term
$search_term = 'Ross';

// WP_User_Query arguments
$args = array (
       'role' => 'reporter',
       'order' => 'ASC',
       'orderby' => 'display_name',
       'search' => '*'.esc_attr( $search_term ).'*',
       'meta_query' => array(
           'relation' => 'OR',
           array(
               'key'     => 'first_name',
               'value'   => $search_term,
               'compare' => 'LIKE'
           ),
           array(
               'key'     => 'last_name',
               'value'   => $search_term,
               'compare' => 'LIKE'
           ),
           array(
               'key' => 'description',
               'value' => $search_term ,
               'compare' => 'LIKE'
           )
       )
);

// Create the WP_User_Query object
$wp_user_query = new WP_User_Query($args);

// Get the results
$authors = $wp_user_query->get_results();

// Check for results
if (!empty($authors)) {
       echo '<ul>';
       // loop through each author
       foreach ($authors as $author)
       {
           // get all the user's data
           $author_info = get_userdata($author->ID);
           echo '<li>' . $author_info->first_name . ' ' . $author_info->last_name . '</li>';
       }
       echo '</ul>';
} else {
       echo 'No authors found';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D2008%23feedback-editor-2008)

3. [Skip to note 11 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-5851)



In addition to Dave answer above, while dealing with custom roles


1\. We must use “slug”, but not “name” (only if you have space(” “) in your role name like “Wholesale Customer”





`wp-includes/class-wp-user-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
<? // this will not work as it has two words and space between them
$role_query = new WP_User_Query( array( 'role' => array( 'Wholesale Customers ) ) );

// this will work using slug
$role_query = new WP_User_Query( array( 'role' => array( 'wholesale_customers ) ) );

// this will work even though it is custom role, it has one word, no need to use slug
$role_query = new WP_User_Query( array( 'role' => array( 'Affiliate ) ) );
```





2\. If you want to query in more roles esp. custom ones e.g teacher, student “role” will not work, instead use “role\_\_in”





`wp-includes/class-wp-user-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
// this will not work
$role_query = new WP_User_Query( array( 'role' => array( 'teacher','student' ) ) );

// this works
$role_query = new WP_User_Query( array( 'role__in' => array( 'teacher','student' ) ) );

// finally to get results
$role_results = $role_query->get_results();
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D5851%23feedback-editor-5851)

4. [Skip to note 12 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-3001)



If you need all network users use \`’blog\_id’ => 0,\`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D3001%23feedback-editor-3001)

5. [Skip to note 13 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-3459)



Also note that users with no roles have also no wp\_capabilities, so querying with following args will not match any of them:





`wp-includes/class-wp-user-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```js
role
role__not_in
role__in
```





The workaround to get theses users, is to use the builtin method : **[wp\_get\_users\_with\_no\_role()](https://developer.wordpress.org/reference/classes/wp_user_query/wp_get_users_with_no_role)**





[Show feedback (1)](https://developer.wordpress.org/reference/classes/wp_user_query/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D3459%23feedback-editor-3459)



- Link returns a 404. Might be looking for: [https://developer.wordpress.org/reference/functions/wp\_get\_users\_with\_no\_role/](https://developer.wordpress.org/reference/functions/wp_get_users_with_no_role/)



[sproutchris](https://profiles.wordpress.org/sproutchris/) [6 years ago](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-3519)


6. [Skip to note 14 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-5713)



Important note when working with custom roles: you need to query by slug, not name as the docs claim.





`wp-includes/class-wp-user-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
// This returns zero users, even though the admin area shows this as the Role name
$user_query = new WP_User_Query( array( 'role' => 'Wholesale Customer' ) );

// This query correctly returns >3400 users
$user_query = new WP_User_Query( array( 'role' => 'wholesale_customer' ) );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D5713%23feedback-editor-5713)

7. [Skip to note 15 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-6166)



To do a search for multiple values of the same key – i.e. “country” is equal to “Israel”, “USA”, or “United Kingdom” – you may be tempted to try using a `'relation' => 'OR'`. This will not work.



You should use an array of your values, then use the `'compare' => 'IN'` parameter.



Please note: the “type” default value is “CHAR”, so you may need to include that parameter if you are not evaluating string values.





`wp-includes/class-wp-user-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_user_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
// This will not work
$args = array(
   	'meta_query' => array(
   		'relation' => 'OR',
   		array(
   			'key'     => 'country',
   			'value'   => 'Israel',
   	 		'compare' => '='
   		),
   		array(
   			'key'     => 'country',
   			'value'   => 'USA',
   	 		'compare' => '='
   		),
   		array(
   			'key'     => 'country',
   			'value'   => 'United Kingdom',
   	 		'compare' => '='
   		)
   	)
    );
$user_query = new WP_User_Query( $args );
```







`wp-includes/class-wp-user-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
// This will work
$args = array(
   	'meta_query' => array(
   		array(
   			'key'     => 'country',
   			'value'   => array('Israel', 'USA', 'United Kingdom'),
   	 		'compare' => 'IN'
   		)
   	)
    );
$user_query = new WP_User_Query( $args );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D6166%23feedback-editor-6166)

8. [Skip to note 16 content](https://developer.wordpress.org/reference/classes/wp_user_query/#comment-content-6406)



Use this in your `functions.php` file to modify the parameter `AND` in `wp_user_query->query_where` before it fetches the result.



The reason is that when you combine `meta_query` with a search for a keyword in `WP_User_Query`, the query will return users which match both the search query AND the result of the meta query even if you’re using `relation => OR` in `meta_query`.



Note: this workaround works when using `search`, `search_columns`, and `meta_query` as the only `WP_User_Query` args!





`wp-includes/class-wp-user-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_user_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_user_query/#)




```php
function wpdocs_pre_user_query_modify_AND( $query ) {
       if ( is_admin() ) {
           return;
       }

       if ( ! is_search() ) {
           return;
       }

       /**
        * Modify "AND" in "query_where" by "OR"
        */

       if ( isset( $query->query_vars['search_columns'][0] )
          && isset( $query->query_vars['meta_query'] )
          && is_array( $query->query_vars['meta_query'] )
          && isset( $query->query_vars['meta_query']['relation'] )
          && count( $query->query_vars['meta_query'] ) > 1
       ) {
           $first_search_column = $query->query_vars['search_columns'][0];

           $where = str_replace(
               ") AND ({$first_search_column} LIKE",
               ") OR ({$first_search_column} LIKE",
               $query->query_where
           );

           $query->query_where = $where;
       }

}
add_action( 'pre_user_query', 'wpdocs_pre_user_query_modify_AND' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F%3Freplytocom%3D6406%23feedback-editor-6406)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_user_query%2F) before being able to contribute a note or feedback.

Notifications