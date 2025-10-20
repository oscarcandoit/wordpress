---
url: https://developer.wordpress.org/reference/functions/__checked_selected_helper
scraped_at: 2025-10-20T03:15:44.248Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_\_checked\_selected\_helper()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_\_checked\_selected\_helper()

Search

# \_\_checked\_selected\_helper( mixed$helper, mixed$current, bool$display, string$type ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#return)
- [Source](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#source)
- [Related](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Private helper function for checked, selected, disabled and readonly.

## [Description](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#description)

Compares the first two arguments and if identical marks as `$type`.

## [Parameters](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#parameters)

`$helper` mixedrequired

One of the values to compare.

`$current` mixedrequired

The other value to compare if not just true.

`$display` boolrequired

Whether to echo or just return the string.

`$type` stringrequired

The type of `checked|selected|disabled|readonly` we are doing.

## [Return](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#return)

string HTML attribute or empty string.

## [Source](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#)

[Copy](https://developer.wordpress.org/reference/functions/__checked_selected_helper/#)

```php
function __checked_selected_helper( $helper, $current, $display, $type ) { // phpcs:ignore WordPress.NamingConventions.ValidFunctionName.FunctionDoubleUnderscore,PHPCompatibility.FunctionNameRestrictions.ReservedFunctionNames.FunctionDoubleUnderscore
	if ( (string) $helper === (string) $current ) {
		$result = " $type='$type'";
	} else {
		$result = '';
	}

	if ( $display ) {
		echo $result;
	}

	return $result;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L5310) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L5310-L5322)

## [Related](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#related)

| Used by | Description |
| --- | --- |
| [wp\_readonly()](https://developer.wordpress.org/reference/functions/wp_readonly/) `wp-includes/general-template.php` | Outputs the HTML readonly attribute. |
| [checked()](https://developer.wordpress.org/reference/functions/checked/) `wp-includes/general-template.php` | Outputs the HTML checked attribute. |
| [selected()](https://developer.wordpress.org/reference/functions/selected/) `wp-includes/general-template.php` | Outputs the HTML selected attribute. |
| [disabled()](https://developer.wordpress.org/reference/functions/disabled/) `wp-includes/general-template.php` | Outputs the HTML disabled attribute. |

## [Changelog](https://developer.wordpress.org/reference/functions/__checked_selected_helper/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F__checked_selected_helper%2F) before being able to contribute a note or feedback.

Notifications