---
url: https://developer.wordpress.org/reference/functions/sanitize_sql_orderby
scraped_at: 2025-10-20T03:26:45.210Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

sanitize\_sql\_orderby()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)sanitize\_sql\_orderby()

Search

# sanitize\_sql\_orderby( string$orderby ): string\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#return)
- [Source](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#wp--skip-link--target)

Ensures a string is a valid SQL ‘order by’ clause.

## [Description](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#description)

Accepts one or more columns, with or without a sort order (ASC / DESC).

e.g. ‘column\_1’, ‘column\_1, column\_2’, ‘column\_1 ASC, column\_2 DESC’ etc.

Also accepts ‘RAND()’.

## [Parameters](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#parameters)

`$orderby` stringrequired

Order by clause to be validated.

## [Return](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#return)

string\|false Returns $orderby if valid, false otherwise.

## [Source](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#source)

`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#)

```php
function sanitize_sql_orderby( $orderby ) {
	if ( preg_match( '/^\s*(([a-z0-9_]+|`[a-z0-9_]+`)(\s+(ASC|DESC))?\s*(,\s*(?=[a-z0-9_`])|$))+$/i', $orderby ) || preg_match( '/^\s*RAND\(\s*\)\s*$/i', $orderby ) ) {
		return $orderby;
	}
	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L2395) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L2395-L2400)

## [Changelog](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.1](https://developer.wordpress.org/reference/since/2.5.1/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#comment-content-5925)





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/#)




```php
<?php
//code copied from Woocommerce code base shows a perfect use of this function.
$orderby           = in_array( $args['orderby'], $allowed_orders, true ) ? $args['orderby'] : 'download_log_id';
$order             = 'DESC' === strtoupper( $args['order'] ) ? 'DESC' : 'ASC';
$orderby_sql       = sanitize_sql_orderby( "{$orderby} {$order}" );
$query[]           = "ORDER BY {$orderby_sql}";
$raw_download_logs = $wpdb->get_results( implode( ' ', $query ) );
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_sql_orderby%2F%3Freplytocom%3D5925%23feedback-editor-5925)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_sql_orderby%2F) before being able to contribute a note or feedback.

Notifications