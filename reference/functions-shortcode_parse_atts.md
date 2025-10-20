---
url: https://developer.wordpress.org/reference/functions/shortcode_parse_atts
scraped_at: 2025-10-20T03:24:34.498Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

shortcode\_parse\_atts()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)shortcode\_parse\_atts()

Search

# shortcode\_parse\_atts( string$text ): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#return)
- [Source](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#source)
- [Related](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#wp--skip-link--target)

Retrieves all attributes from the shortcodes tag.

## [Description](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#description)

The attributes list has the attribute name as the key and the value of the attribute as the value in the key/value pair. This allows for easier retrieval of the attributes, since all attributes have to be known.

## [Parameters](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#parameters)

`$text` stringrequired

Shortcode arguments list.

## [Return](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#return)

array Array of attribute values keyed by attribute name.

Returns empty array if there are no attributes or if the original arguments string cannot be parsed.

## [Source](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#source)

`wp-includes/shortcodes.php`
[Expand code](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#)

[Copy](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#)

```php
function shortcode_parse_atts( $text ) {
	$atts    = array();
	$pattern = get_shortcode_atts_regex();
	$text    = preg_replace( "/[\x{00a0}\x{200b}]+/u", ' ', $text );
	if ( preg_match_all( $pattern, $text, $match, PREG_SET_ORDER ) ) {
		foreach ( $match as $m ) {
			if ( ! empty( $m[1] ) ) {
				$atts[ strtolower( $m[1] ) ] = stripcslashes( $m[2] );
			} elseif ( ! empty( $m[3] ) ) {
				$atts[ strtolower( $m[3] ) ] = stripcslashes( $m[4] );
			} elseif ( ! empty( $m[5] ) ) {
				$atts[ strtolower( $m[5] ) ] = stripcslashes( $m[6] );
			} elseif ( isset( $m[7] ) && strlen( $m[7] ) ) {
				$atts[] = stripcslashes( $m[7] );
			} elseif ( isset( $m[8] ) && strlen( $m[8] ) ) {
				$atts[] = stripcslashes( $m[8] );
			} elseif ( isset( $m[9] ) ) {
				$atts[] = stripcslashes( $m[9] );
			}
		}

		// Reject any unclosed HTML elements.
		foreach ( $atts as &$value ) {
			if ( str_contains( $value, '<' ) ) {
				if ( 1 !== preg_match( '/^[^<]*+(?:<[^>]*+>[^<]*+)*+$/', $value ) ) {
					$value = '';
				}
			}
		}
	}

	return $atts;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/shortcodes.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/shortcodes.php#L613) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/shortcodes.php#L613-L645)

## [Related](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#related)

| Uses | Description |
| --- | --- |
| [get\_shortcode\_atts\_regex()](https://developer.wordpress.org/reference/functions/get_shortcode_atts_regex/) `wp-includes/shortcodes.php` | Retrieves the shortcode attributes regex. |

| Used by | Description |
| --- | --- |
| [wp\_ajax\_parse\_embed()](https://developer.wordpress.org/reference/functions/wp_ajax_parse_embed/) `wp-admin/includes/ajax-actions.php` | Applies Ajax handlers to a string. |
| [do\_shortcode\_tag()](https://developer.wordpress.org/reference/functions/do_shortcode_tag/) `wp-includes/shortcodes.php` | Regular Expression callable for [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) for calling shortcode hook. |
| [WP\_oEmbed::discover()](https://developer.wordpress.org/reference/classes/wp_oembed/discover/) `wp-includes/class-wp-oembed.php` | Attempts to discover link tags at the given URL for an oEmbed provider. |

## [Changelog](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#changelog)

| Version | Description |
| --- | --- |
| [6.5.0](https://developer.wordpress.org/reference/since/6.5.0/) | The function now always returns an array, even if the original arguments string cannot be parsed or is empty. |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#comment-content-3867)



To get the shortcode attribute value:





`wp-includes/shortcodes.php`
[Copy](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/#)




```php
$atts = shortcode_parse_atts(
       ''
);
echo $atts['url']; // echo just the URL
```





from [here](https://wordpress.stackexchange.com/questions/107278/how-to-parse-this-shortcode)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_parse_atts%2F%3Freplytocom%3D3867%23feedback-editor-3867)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_parse_atts%2F) before being able to contribute a note or feedback.

Notifications