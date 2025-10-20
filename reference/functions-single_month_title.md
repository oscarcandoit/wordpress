---
url: https://developer.wordpress.org/reference/functions/single_month_title
scraped_at: 2025-10-20T03:17:44.472Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/single_month_title/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

single\_month\_title()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)single\_month\_title()

Search

# single\_month\_title( string$prefix = '', bool$display = true ): string\|false\|void

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/single_month_title/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/single_month_title/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/single_month_title/#return)
- [More Information](https://developer.wordpress.org/reference/functions/single_month_title/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/single_month_title/#source)
- [Related](https://developer.wordpress.org/reference/functions/single_month_title/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/single_month_title/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/single_month_title/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/single_month_title/#wp--skip-link--target)

Displays or retrieves page title for post archive based on date.

## [Description](https://developer.wordpress.org/reference/functions/single_month_title/\#description)

Useful for when the template only needs to display the month and year, if either are available. The prefix does not automatically place a space between the prefix, so if there should be a space, the parameter value will need to have it at the end.

## [Parameters](https://developer.wordpress.org/reference/functions/single_month_title/\#parameters)

`$prefix` stringoptional

What to display before the title.

Default: `''`

`$display` booloptional

Whether to display or retrieve title.

Default: `true`

## [Return](https://developer.wordpress.org/reference/functions/single_month_title/\#return)

string\|false\|void False if there’s no valid title for the month. Title when retrieving.

## [More Information](https://developer.wordpress.org/reference/functions/single_month_title/\#more-information)

- This tag only works when the `m` or archive month argument has been passed by WordPress to the current page (this occurs when viewing a monthly archive page).
- This tag works only on date archive pages, not on category templates or others.
- It does not support placing the separator after the title, but by leaving the prefix parameter empty, you can set the title separator manually.

## [Source](https://developer.wordpress.org/reference/functions/single_month_title/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/single_month_title/#)

[Copy](https://developer.wordpress.org/reference/functions/single_month_title/#)

```php
function single_month_title( $prefix = '', $display = true ) {
	global $wp_locale;

	$m        = get_query_var( 'm' );
	$year     = get_query_var( 'year' );
	$monthnum = get_query_var( 'monthnum' );

	if ( ! empty( $monthnum ) && ! empty( $year ) ) {
		$my_year  = $year;
		$my_month = $wp_locale->get_month( $monthnum );
	} elseif ( ! empty( $m ) ) {
		$my_year  = substr( $m, 0, 4 );
		$my_month = $wp_locale->get_month( substr( $m, 4, 2 ) );
	}

	if ( empty( $my_month ) ) {
		return false;
	}

	$result = $prefix . $my_month . $prefix . $my_year;

	if ( ! $display ) {
		return $result;
	}
	echo $result;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L1660) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L1660-L1685)

## [Related](https://developer.wordpress.org/reference/functions/single_month_title/\#related)

| Uses | Description |
| --- | --- |
| [get\_query\_var()](https://developer.wordpress.org/reference/functions/get_query_var/) `wp-includes/query.php` | Retrieves the value of a query variable in the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) class. |
| [WP\_Locale::get\_month()](https://developer.wordpress.org/reference/classes/wp_locale/get_month/) `wp-includes/class-wp-locale.php` | Retrieves the full translated month by month number. |

## [Changelog](https://developer.wordpress.org/reference/functions/single_month_title/\#changelog)

| Version | Description |
| --- | --- |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/single_month_title/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/single_month_title/#comment-content-1075)



**Month and Year on New Lines**



Displays the title, placing month and year on new lines.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/single_month_title/#)




```php
<p><?php single_month_title('<br />') ?></p>
```





Output is following 2 lines.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/single_month_title/#)




```php
December
2004
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsingle_month_title%2F%3Freplytocom%3D1075%23feedback-editor-1075)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsingle_month_title%2F) before being able to contribute a note or feedback.

Notifications