---
url: https://developer.wordpress.org/reference/functions/capital_p_dangit
scraped_at: 2025-10-20T03:25:36.099Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/capital_p_dangit/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

capital\_P\_dangit()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)capital\_P\_dangit()

Search

# capital\_P\_dangit( string$text ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/capital_p_dangit/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/capital_p_dangit/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/capital_p_dangit/#return)
- [Source](https://developer.wordpress.org/reference/functions/capital_p_dangit/#source)
- [Related](https://developer.wordpress.org/reference/functions/capital_p_dangit/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/capital_p_dangit/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/capital_p_dangit/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/capital_p_dangit/#wp--skip-link--target)

Forever eliminate “Wordpress” from the planet (or at least the little bit we can influence).

## [Description](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#description)

Violating our coding standards for a good function name.

## [Parameters](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#parameters)

`$text` stringrequired

The text to be modified.

## [Return](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#return)

string The modified text.

## [Source](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#source)

`wp-includes/formatting.php`
[Expand code](https://developer.wordpress.org/reference/functions/capital_p_dangit/#)

[Copy](https://developer.wordpress.org/reference/functions/capital_p_dangit/#)

```php
function capital_P_dangit( $text ) {
	// Simple replacement for titles.
	$current_filter = current_filter();
	if ( 'the_title' === $current_filter || 'wp_title' === $current_filter ) {
		return str_replace( 'Wordpress', 'WordPress', $text );
	}
	// Still here? Use the more judicious replacement.
	static $dblq = false;
	if ( false === $dblq ) {
		$dblq = _x( '&#8220;', 'opening curly double quote' );
	}
	return str_replace(
		array( ' WordPress', '&#8216;Wordpress', $dblq . 'Wordpress', '>Wordpress', '(WordPress' ),
		array( ' WordPress', '&#8216;WordPress', $dblq . 'WordPress', '>WordPress', '(WordPress' ),
		$text
	);
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L5681) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L5681-L5697)

## [Related](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#related)

| Uses | Description |
| --- | --- |
| [current\_filter()](https://developer.wordpress.org/reference/functions/current_filter/) `wp-includes/plugin.php` | Retrieves the name of the current filter hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/capital_p_dangit/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/capital_p_dangit/#comment-content-1402)



**Example**



If you prefer not to use these filters, here’s how you can remove them:





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/capital_p_dangit/#)




```php
remove_filter( 'the_title', 'capital_P_dangit', 11 );
remove_filter( 'the_content', 'capital_P_dangit', 11 );
remove_filter( 'comment_text', 'capital_P_dangit', 31 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcapital_p_dangit%2F%3Freplytocom%3D1402%23feedback-editor-1402)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcapital_p_dangit%2F) before being able to contribute a note or feedback.

Notifications