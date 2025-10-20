---
url: https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters
scraped_at: 2025-10-20T03:16:52.408Z
---

[Skip to content](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Shortcodes with Parameters


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Shortcodes](https://developer.wordpress.org/plugins/shortcodes/)Shortcodes with Parameters

Search

# Shortcodes with Parameters

## In this article

Table of Contents

- [Parsing Attributes](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#parsing-attributes)
- [Complete Example](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#complete-example)

[↑ Back to top](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#wp--skip-link--target)

Now that we know how to create a [basic shortcode](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/) and how to use it as [self-closing and enclosing](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/), we will look at using parameters in shortcode `[$tag]` and handler function.

Shortcode `[$tag]` can accept parameters, known as attributes:

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#)

```php
[wporg title="WordPress.org"]
Having fun with WordPress.org shortcodes.
[/wporg]
```

Shortcode handler function can accept 3 parameters:

- `$atts` – array – \[$tag\] attributes
- `$content` – string – The content inside your shortcode. In the example above, it will be “Having fun with WordPress.org shortcodes.”
- `$tag` – string – the name of the \[$tag\] (i.e. the name of the shortcode)

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#)

```php
function wporg_shortcode( $atts = array(), $content = null, $tag = '' ) {}
```

## [Parsing Attributes](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/\#parsing-attributes)

For the user, shortcodes are just strings with square brackets inside the post content. The user have no idea which attributes are available and what happens behind the scenes.

For plugin developers, there is no way to enforce a policy on the use of attributes. The user may include one attribute, two or none at all.

To gain control of how the shortcodes are used:

- Declare default parameters for the handler function
- Performing normalization of the key case for the attributes array with [array\_change\_key\_case()](http://php.net/manual/en/function.array-change-key-case.php)
- Parse attributes using [shortcode\_atts()](https://developer.wordpress.org/reference/functions/shortcode_atts/) providing default values array and user `$atts`
- [Secure the output](https://developer.wordpress.org/plugins/security/securing-output/) before returning it

## [Complete Example](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/\#complete-example)

Complete example using a basic shortcode structure, taking care of self-closing and enclosing scenarios and securing output.

A `[wporg]` shortcode that will accept a title and will display a box that we can style with CSS.

``
[Expand code](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#)

[Copy](https://developer.wordpress.org/plugins/shortcodes/shortcodes-with-parameters/#)

```php
/**
 * The [wporg] shortcode.
 *
 * Accepts a title and will display a box.
 *
 * @param array  $atts    Shortcode attributes. Default empty.
 * @param string $content Shortcode content. Default null.
 * @param string $tag     Shortcode tag (name). Default empty.
 * @return string Shortcode output.
 */
function wporg_shortcode( $atts = [], $content = null, $tag = '' ) {
	// normalize attribute keys, lowercase
	$atts = array_change_key_case( (array) $atts, CASE_LOWER );

	// override default attributes with user attributes
	$wporg_atts = shortcode_atts(
		array(
			'title' => 'WordPress.org',
		), $atts, $tag
	);

	// start box
	$o = '<div class="wporg-box">';

	// title
	$o .= '<h2>' . esc_html( $wporg_atts['title'] ) . '</h2>';

	// enclosing tags
	if ( ! is_null( $content ) ) {
		// $content here holds everything in between the opening and the closing tags of your shortcode. eg.g [my-shortcode]content[/my-shortcode].
        // Depending on what your shortcode supports, you will parse and append the content to your output in different ways.
		// In this example, we just secure output by executing the_content filter hook on $content.
		$o .= apply_filters( 'the_content', $content );
	}

	// end box
	$o .= '</div>';

	// return output
	return $o;
}

/**
 * Central location to create all shortcodes.
 */
function wporg_shortcodes_init() {
	add_shortcode( 'wporg', 'wporg_shortcode' );
}

add_action( 'init', 'wporg_shortcodes_init' );
```

First published

September 18, 2014

Last updated

March 27, 2024

[PreviousEnclosing ShortcodesPrevious: Enclosing Shortcodes](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/)

[NextTinyMCE Enhanced ShortcodesNext: TinyMCE Enhanced Shortcodes](https://developer.wordpress.org/plugins/shortcodes/tinymce-enhanced-shortcodes/)

Notifications