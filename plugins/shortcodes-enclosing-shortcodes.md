---
url: https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes
scraped_at: 2025-10-20T04:48:30.182Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Enclosing Shortcodes


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Shortcodes](https://developer.wordpress.org/plugins/shortcodes/)Enclosing Shortcodes

Search

# Enclosing Shortcodes

## In this article

Table of Contents

- [Enclosing Content](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#enclosing-content)
- [Processing Enclosed Content](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#processing-enclosed-content)
- [Shortcode-ception](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#shortcode-ception)
- [Limitations](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#limitations)

[↑ Back to top](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#wp--skip-link--target)

The are two scenarios for using shortcodes:

- The shortcode is a self-closing tag like we seen in the [Basic Shortcodes](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/) section.
- The shortcode is enclosing content.

## [Enclosing Content](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/\#enclosing-content)

Enclosing content with a shortcode allows manipulations on the enclosed content.

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#)

```php
[wporg]content to manipulate[/wporg]
```

As seen above, all you need to do in order to enclose a section of content is add a beginning `[$tag]` and an end `[/$tag]`, similar to HTML.

## [Processing Enclosed Content](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/\#processing-enclosed-content)

Lets get back to our original \[wporg\] shortcode code:

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#)

```php
function wporg_shortcode( $atts = array(), $content = null ) {
    // do something to $content
    // always return
    return $content;
}
add_shortcode( 'wporg', 'wporg_shortcode' );
```

Looking at the callback function we see that we chose to accept two parameters, `$atts` and `$content`. The `$content` parameter is going to hold our enclosed content. We will talk about `$atts` later.

The default value of `$content` is set to `null` so we can differentiate between a self-closing tag and enclosing tags by using PHP function [is\_null()](http://php.net/is_null).

The shortcode `[$tag]`, including its content and the end `[/$tag]` will be replaced with the **return value** of the handler function.

It is the responsibility of the handler function to [secure the output](https://developer.wordpress.org/plugins/security/securing-output/).

## [Shortcode-ception](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/\#shortcode-ception)

The shortcode parser performs a **single pass** on the content of the post.

This means that if the `$content` parameter of a shortcode handler contains another shortcode, it won’t be parsed. In this example, `[shortcode]` will not be processed:

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#)

```php
[wporg]another [shortcode] is included[/wporg]
```

Using shortcodes inside other shortcodes is possible by calling `do_shortcode()` on the **final return value** of the handler function.

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#)

```php
function wporg_shortcode( $atts = array(), $content = null ) {
	// do something to $content
	// run shortcode parser recursively
	$content = do_shortcode( $content );
	// always return
	return $content;
}
add_shortcode( 'wporg', 'wporg_shortcode' );
```

## [Limitations](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/\#limitations)

The shortcode parser is unable to handle mixing of enclosing and non-enclosing forms of the same `[$tag]`.

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/#)

```php
[wporg] non-enclosed content [wporg]enclosed content[/wporg]
```

Instead of being treated as two shortcodes separated by the text “ `non-enclosed content`“, the parser treats this as a single shortcode enclosing “ `non-enclosed content [wporg]enclosed content`“.

First published

September 18, 2014

Last updated

November 17, 2022

[PreviousBasic ShortcodesPrevious: Basic Shortcodes](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/)

[NextShortcodes with ParametersNext: Shortcodes with Parameters](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/)

Notifications