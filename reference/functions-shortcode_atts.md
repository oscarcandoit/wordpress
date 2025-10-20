---
url: https://developer.wordpress.org/reference/functions/shortcode_atts
scraped_at: 2025-10-20T03:45:45.334Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/shortcode_atts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

shortcode\_atts()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)shortcode\_atts()

Search

# shortcode\_atts( array$pairs, array$atts, string$shortcode = '' ): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/shortcode_atts/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/shortcode_atts/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/shortcode_atts/#return)
- [Source](https://developer.wordpress.org/reference/functions/shortcode_atts/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/shortcode_atts/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/shortcode_atts/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/shortcode_atts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/shortcode_atts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/shortcode_atts/#wp--skip-link--target)

Combines user attributes with known attributes and fill in defaults when needed.

## [Description](https://developer.wordpress.org/reference/functions/shortcode_atts/\#description)

The pairs should be considered to be all of the attributes which are supported by the caller and given as a list. The returned attributes will only contain the attributes in the $pairs list.

If the $atts list has unsupported attributes, then they will be ignored and removed from the final returned list.

## [Parameters](https://developer.wordpress.org/reference/functions/shortcode_atts/\#parameters)

`$pairs` arrayrequired

Entire list of supported attributes and their defaults.

`$atts` arrayrequired

User defined attributes in shortcode tag.

`$shortcode` stringoptional

The name of the shortcode, provided for context to enable filtering

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/shortcode_atts/\#return)

array Combined and filtered attribute list.

## [Source](https://developer.wordpress.org/reference/functions/shortcode_atts/\#source)

`wp-includes/shortcodes.php`
[Expand code](https://developer.wordpress.org/reference/functions/shortcode_atts/#)

[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)

```php
function shortcode_atts( $pairs, $atts, $shortcode = '' ) {
	$atts = (array) $atts;
	$out  = array();
	foreach ( $pairs as $name => $default ) {
		if ( array_key_exists( $name, $atts ) ) {
			$out[ $name ] = $atts[ $name ];
		} else {
			$out[ $name ] = $default;
		}
	}

	if ( $shortcode ) {
		/**
		 * Filters shortcode attributes.
		 *
		 * If the third parameter of the shortcode_atts() function is present then this filter is available.
		 * The third parameter, $shortcode, is the name of the shortcode.
		 *
		 * @since 3.6.0
		 * @since 4.4.0 Added the `$shortcode` parameter.
		 *
		 * @param array  $out       The output array of shortcode attributes.
		 * @param array  $pairs     The supported attributes and their defaults.
		 * @param array  $atts      The user defined shortcode attributes.
		 * @param string $shortcode The shortcode name.
		 */
		$out = apply_filters( "shortcode_atts_{$shortcode}", $out, $pairs, $atts, $shortcode );
	}

	return $out;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/shortcodes.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/shortcodes.php#L664) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/shortcodes.php#L664-L694)

## [Hooks](https://developer.wordpress.org/reference/functions/shortcode_atts/\#hooks)

[apply\_filters( “shortcode\_atts\_{$shortcode}”, array$out, array$pairs, array$atts, string$shortcode )](https://developer.wordpress.org/reference/hooks/shortcode_atts_shortcode/)

Filters shortcode attributes.

## [Related](https://developer.wordpress.org/reference/functions/shortcode_atts/\#related)

| Uses | Description |
| --- | --- |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/shortcode_atts/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/shortcode_atts/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-content-3820)



It might be **really** useful to note that attribute _names_ must be all lowercase…



If your shortcode looks like this:

`[shortcode attOne="foo" attTwo="bar"]`


The array passed to the callback function will look like this:

`Array( attone => "foo", atttwo => "bar" )`



So, I guess you could use camelCase in the shortcode, just remember to expect those camelCase to be all lowercase in your `shortcode_atts`…





[Show feedback (2)](https://developer.wordpress.org/reference/functions/shortcode_atts/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F%3Freplytocom%3D3820%23feedback-editor-3820)



- This is not true, but can seem true: see [explanation](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3826).



[crstauf](https://profiles.wordpress.org/crstauf/) [5 years ago](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3827)

- To clear up any confusion: [Aaron’s post](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3820) is correct, while the the [explanation](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3826) by crstauf is _technically_ correct. It is true that `shortcode_atts()` makes a case-sensitive comparison between the first argument (array of supported attributes and their defaults) and the second argument (array of user-defined attributes in shortcode tag). But the user-defined attributes are normalized to lowercase by WordPress before being passed to the shortcode callback function (see [`shortcode_parse_atts()`](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/)). So the case-sensitivity of `shortcode_atts()` only becomes an issue if you define supported attributes using uppercase characters.



[Bart Kuijper](https://profiles.wordpress.org/spartelfant/) [5 years ago](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-4713)


2. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-content-805)



**Example**





`wp-includes/shortcodes.php`
[Expand code](https://developer.wordpress.org/reference/functions/shortcode_atts/#)

[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
/**
    * Callback to register a bartag shortcode.
    *
    * @param array $atts Shortcode attributes.
    * @return string Shortcode output.
function wpdocs_bartag_func( $atts ) {
   	$atts = shortcode_atts(
   		array(
   			'foo' => 'no foo',
   			'bar' => 'default bar',
   		), $atts, 'bartag' );

   	return 'bartag: ' . esc_html( $atts['foo'] ) . ' ' . esc_html( $atts['bar'] );
}
add_shortcode( 'bartag', 'wpdocs_bartag_func' );
```





\[bartag foo=”koala” bar=”bears”\] outputs the following:


bartag: koala bears



\[bartag foo=”koala”\] outputs the following:


bartag: koala default bar



This creates a “ `[bartag]`” shortcode that supports two attributes: `[bartag foo="something" bar="something else"]`. Both attributes are optional and will take on default options if they are not provided.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F%3Freplytocom%3D805%23feedback-editor-805)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-content-3826)



Clarification on [Aaron’s note](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3820):



The case of the keys on the `$pairs` must match the keys on the `$atts`, or the value will be discarded.



See these examples:





`wp-includes/shortcodes.php`
[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
print_r( shortcode_atts( array(
   	'CAPITAL' => '1',
   	'fooBar' => '2',
), array(
   	'CAPITAL' => '3',
   	'fooBar' => '4',
) ) );
// Output: Array ( [CAPITAL] => 3 [fooBar] => 4 )
```







`wp-includes/shortcodes.php`
[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
print_r( shortcode_atts( array(
   	'CAPITAL' => '1',
   	'fooBar' => '2',
), array(
   	'capital' => '3',
   	'fooBar' => '4',
) ) );
// Output: Array ( [CAPITAL] => 1 [fooBar] => 4 )
```







`wp-includes/shortcodes.php`
[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
print_r( shortcode_atts( array(
   	'CAPITAL' => '1',
   	'fooBar' => '2',
), array(
   	'capital' => '3',
   	'foobar' => '4',
) ) );
// Output: Array ( [CAPITAL] => 1 [fooBar] => 2 )
```







`wp-includes/shortcodes.php`
[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
print_r( shortcode_atts( array(
   	'capital' => '1',
   	'fooBar' => '2',
), array(
   	'capital' => '3',
   	'foobar' => '4',
) ) );
// Output: Array ( [capital] => 3 [fooBar] => 2 )
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F%3Freplytocom%3D3826%23feedback-editor-3826)

4. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-content-5604)



To ensure this function works and allow for case insensitive attributes, I use `array_change_key_case` in a one-liner like this





`wp-includes/shortcodes.php`
[Expand code](https://developer.wordpress.org/reference/functions/shortcode_atts/#)

[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
/**
    * My Custom Shortcode
    *
    * @param array $atts Optional. An associative array of key/value attributes. Default is empty array.
    * @param string $content Optional. The content between the opening and closing shortcode tags. Default is an empty string.
    * @param string $tag Optional. The name of the shortcode, provided for context to enable filtering. Default is an empty string.
    *
    * @return string shortcode output
    */
function tw_custom_shortcode($atts = array(), $content = '', $tag = '')
{
       $atts = shortcode_atts(array(), array_change_key_case((array)$atts, CASE_LOWER), $tag);

       //Do stuff, probably sanitize inputs

       $output = '';
       return $output;
}
add_shortcode('tw_custom', 'tw_custom_shortcode');
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F%3Freplytocom%3D5604%23feedback-editor-5604)

5. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-content-1748)



I had to hunt around to find all the pieces, I hope others find this helpful.



So, building on a previous example:





`wp-includes/shortcodes.php`
[Expand code](https://developer.wordpress.org/reference/functions/shortcode_atts/#)

[Copy](https://developer.wordpress.org/reference/functions/shortcode_atts/#)




```php
/**
    * How to use shortcode callback parms with shortcode_atts to make
    * callback code flexible and re-useable.
    *
    * This allows filters to be applied to a callback depending on which
    * shortcode called it.
    *
    * @param array  $atts    Shortcode attributes.
    * @param string $content Shortcode content.
    * @param string $tag     The shortcode which invoked the callback
    * @return string Shortcode output.
    */
function my_callback_func( $atts, $content, $tag ) {
       $atts = shortcode_atts(
           array(
               'foo' => '',
               'bar' => '',
           ), $atts, $tag );

    //do something here(trivial example)
   	if ( !empty($zoo) ) {
   		return $zoo;  //where did $zoo come from? see below
   	}
   	else return $foo;

}

add_shortcode( 'myshortcode1', 'my_callback_func' );
add_shortcode( 'myshortcode2', 'my_callback_func' );

/* now make a filter that's applied ONLY when my_callback_func is invoked by myshortcode1 -
this example adds param 'zoo' to myshortcode1  */

add_filter ('shortcode_atts_myshortcode1', 'add_zoo', 10, 3);
function add_zoo ($out, $pairs, $atts ) {
   	$out['zoo'] = '';
   	return $out;
}
// Now we can use [myshortcode1 foo='myfoo' zoo='myzoo']  output: myzoo
// and [myshortcode2 foo='myfoo' zoo='myzoo']  output: myfoo
```







[Show feedback (1)](https://developer.wordpress.org/reference/functions/shortcode_atts/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F%3Freplytocom%3D1748%23feedback-editor-1748)



- The example function \`my\_callback\_func\` gets the attributes into an array, but uses the individual attribute names as variables. No \`extract\` was done. Also, the filter \`add\_zoo\` only sets it to ”, not the value the user entered.



[Joy](https://profiles.wordpress.org/joyously/) [6 years ago](https://developer.wordpress.org/reference/functions/shortcode_atts/#comment-3549)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fshortcode_atts%2F) before being able to contribute a note or feedback.

Notifications