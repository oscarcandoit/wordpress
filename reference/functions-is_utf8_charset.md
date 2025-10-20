---
url: https://developer.wordpress.org/reference/functions/is_utf8_charset
scraped_at: 2025-10-20T03:19:53.761Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_utf8_charset/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_utf8\_charset()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_utf8\_charset()

Search

# is\_utf8\_charset( string\|null$blog\_charset = null ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/is_utf8_charset/#description)
  - [See also](https://developer.wordpress.org/reference/functions/is_utf8_charset/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/is_utf8_charset/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/is_utf8_charset/#return)
- [Source](https://developer.wordpress.org/reference/functions/is_utf8_charset/#source)
- [Related](https://developer.wordpress.org/reference/functions/is_utf8_charset/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_utf8_charset/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_utf8_charset/#wp--skip-link--target)

Indicates if a given slug for a character set represents the UTF-8 text encoding. If not provided, examines the current blog’s charset.

## [Description](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#description)

A charset is considered to represent UTF-8 if it is a case-insensitive match of "UTF-8" with or without the hyphen.

Example:

`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/is_utf8_charset/#)

```php
true  === is_utf8_charset( 'UTF-8' );
true  === is_utf8_charset( 'utf8' );
false === is_utf8_charset( 'latin1' );
false === is_utf8_charset( 'UTF 8' );

// Only strings match.
false === is_utf8_charset( [ 'charset' => 'utf-8' ] );

// Without a given charset, it depends on the site option "blog_charset".
$is_utf8 = is_utf8_charset();
```

### [See also](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#see-also)

- [\_is\_utf8\_charset](https://developer.wordpress.org/reference/functions/_is_utf8_charset)

## [Parameters](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#parameters)

`$blog_charset` string\|nulloptional

Slug representing a text character encoding, or "charset".

E.g. "UTF-8", "Windows-1252", "ISO-8859-1", "SJIS".

Default value is to infer from "blog\_charset" option.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#return)

bool Whether the slug represents the UTF-8 encoding.

## [Source](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#source)

`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/is_utf8_charset/#)

```php
function is_utf8_charset( $blog_charset = null ) {
	return _is_utf8_charset( $blog_charset ?? get_option( 'blog_charset' ) );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L7568) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L7568-L7570)

## [Related](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#related)

| Uses | Description |
| --- | --- |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

| Used by | Description |
| --- | --- |
| [WP\_Script\_Modules::print\_script\_module\_data()](https://developer.wordpress.org/reference/classes/wp_script_modules/print_script_module_data/) `wp-includes/class-wp-script-modules.php` | Print data associated with Script Modules. |
| [wp\_check\_invalid\_utf8()](https://developer.wordpress.org/reference/functions/wp_check_invalid_utf8/) `wp-includes/formatting.php` | Checks for invalid UTF8 in a string. |
| [\_canonical\_charset()](https://developer.wordpress.org/reference/functions/_canonical_charset/) `wp-includes/functions.php` | Retrieves a canonical form of the provided charset appropriate for passing to PHP functions such as htmlspecialchars() and charset HTML attributes. |

## [Changelog](https://developer.wordpress.org/reference/functions/is_utf8_charset/\#changelog)

| Version | Description |
| --- | --- |
| [6.6.1](https://developer.wordpress.org/reference/since/6.6.1/) | A wrapper for \_is\_utf8\_charset |
| [6.6.0](https://developer.wordpress.org/reference/since/6.6.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_utf8_charset%2F) before being able to contribute a note or feedback.

Notifications