---
url: https://developer.wordpress.org/reference/classes/wp_styles
scraped_at: 2025-10-20T03:25:54.324Z
---

[Skip to content](https://developer.wordpress.org/reference/classes/wp_styles/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

WP\_Styles


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Classes](https://developer.wordpress.org/reference/classes/)WP\_Styles

Search

# class WP\_Styles {}

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/classes/wp_styles/#description)
  - [See also](https://developer.wordpress.org/reference/classes/wp_styles/#see-also)
- [More Information](https://developer.wordpress.org/reference/classes/wp_styles/#more-information)
  - [Text direction](https://developer.wordpress.org/reference/classes/wp_styles/#text-direction)
  - [Concatenation vs Printing](https://developer.wordpress.org/reference/classes/wp_styles/#concatenation-vs-printing)
  - [Media](https://developer.wordpress.org/reference/classes/wp_styles/#media)
- [Properties and Hooks](https://developer.wordpress.org/reference/classes/wp_styles/#properties-and-hooks)
  - [Properties](https://developer.wordpress.org/reference/classes/wp_styles/#properties)
- [Hooks](https://developer.wordpress.org/reference/classes/wp_styles/#hooks)
  - [Actions](https://developer.wordpress.org/reference/classes/wp_styles/#actions)
  - [Filters](https://developer.wordpress.org/reference/classes/wp_styles/#filters)
- [Methods](https://developer.wordpress.org/reference/classes/wp_styles/#methods)
- [Source](https://developer.wordpress.org/reference/classes/wp_styles/#source)
- [Related](https://developer.wordpress.org/reference/classes/wp_styles/#related)
- [Changelog](https://developer.wordpress.org/reference/classes/wp_styles/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_styles/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/classes/wp_styles/#wp--skip-link--target)

Core class used to register styles.

## [Description](https://developer.wordpress.org/reference/classes/wp_styles/\#description)

### [See also](https://developer.wordpress.org/reference/classes/wp_styles/\#see-also)

- [WP\_Dependencies](https://developer.wordpress.org/reference/classes/wp_dependencies)

## [More Information](https://developer.wordpress.org/reference/classes/wp_styles/\#more-information)

`WP_Styles` is a class that helps developers interact with a theme. It ensures registered stylesheets are output in the proper order, with dependent stylesheets coming after their dependencies. While more than one instance can be created, typically the global $wp\_styles is used to enqueue stylesheets, which are then output by `wp_print_styles` during the `[wp\_head](https://developer.wordpress.org/reference/hooks/wp_head/ "Plugin API/Action Reference/wp head")` action. `WP_Styles` extends `[WP\_Dependencies](https://developer.wordpress.org/reference/classes/wp_dependencies/ "Class Reference/WP Dependencies")`.

`WP_Styles` handles both external and embedded stylesheets (though the latter must be associated with one of the former), outputting a <link> or <style> element as appropriate.

### [Text direction](https://developer.wordpress.org/reference/classes/wp_styles/\#text-direction)

For any stylesheet, an additional stylesheet can be loaded for right-to-left text (triggered by setting $wp\_styles->text\_direction to ‘rtl’). The URL for this stylesheet is built by inserting ‘-rtl’ into the URL of the left-to-right stylesheet. Normally, ‘-rtl’ is inserted before the ‘.css’ extension. If ‘suffix’ is set in the stylesheet’s extra data (using `WP_Dependencies::add_data()` or `_WP_Dependency::add_data()`), ‘-rtl’ will be inserted before the suffix and ‘.css’ extension ( `"${suffix}.css"`).

### [Concatenation vs Printing](https://developer.wordpress.org/reference/classes/wp_styles/\#concatenation-vs-printing)

When it comes time to output enqueued stylesheets, `WP_Styles` can print them, or accumulate them in instance variables ($print\_html for external and $print\_code for embedded). This behaviour is controlled by the boolean instance variable $do\_concat. If true, output is concatenated to the appropriate instance variable; if false, it’s printed.

Any [unconditional](http://msdn.microsoft.com/en-us/library/ms537512.aspx), non- [alternate](http://www.w3.org/Style/Examples/007/alternatives.en.html) stylesheet in a default directory (as determined by `WP_Styles::in_default_dir()`) isn’t accumulated when $do\_concat is true.

### [Media](https://developer.wordpress.org/reference/classes/wp_styles/\#media)

The media for a stylesheet is passed via the $args argument to `[WP\_Dependencies](https://developer.wordpress.org/reference/classes/wp_dependencies/ "Class Reference/WP Dependencies")::add()`.

## [Properties and Hooks](https://developer.wordpress.org/reference/classes/wp_styles/\#properties-and-hooks)

Note: Refer source code for the complete list of properties and hooks.

### [Properties](https://developer.wordpress.org/reference/classes/wp_styles/\#properties)

$base\_urlThe base URL for the site, it gets prepended to the URL for an enqueued sheet in most cases (see $content\_url for an exception). Set to the site URL (as determined by `[site\_url()](https://developer.wordpress.org/reference/functions/site_url/ "Function Reference/site url")` or `wp_guess_url()`) by default.$content\_urlThe URL for the wp-content directory. Set to `WP_CONTENT_URL` by default. If a stylesheet URL begins with the content URL, the base URL isn’t prepended.$default\_versionDefault value used when a version isn’t specified in a call to [wp\_enqueue\_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_style/ "Function Reference/wp enqueue style") or [wp\_register\_style()](https://developer.wordpress.org/reference/functions/wp_register_style/ "Function Reference/wp register style").$text\_direction = ‘ltr’If ‘rtl’, an addtional stylesheet will be loaded, allowing custom styling targeting right-to-left.$do\_concat = falseIf true, concatenate output to $print\_html and $print\_code member variables rather than printing it.$print\_html = “”holds accumulated HTML (<link> elements and conditional comments).$print\_code = “”holds accumulated embedded style rules.$concat = “”list of item handles that were accumulated, separated by commas.$concat\_version = “”list of item handles & versions that were accumulated.$default\_dirsPath or array of paths. Used by `WP_Styles::in_default_dir()`. Compared directly to $src property of a stylesheet.

## [Hooks](https://developer.wordpress.org/reference/classes/wp_styles/\#hooks)

Note: Refer source code for the complete list of hooks.

### [Actions](https://developer.wordpress.org/reference/classes/wp_styles/\#actions)

- wp\_default\_styles – Invoked when a [WP\_Styles](https://developer.wordpress.org/reference/classes/wp_styles/) is created. The instance is passed to action hooks.

### [Filters](https://developer.wordpress.org/reference/classes/wp_styles/\#filters)

- print\_styles\_array – Filters list of stylesheets to be output. Called from `WP_Styles::all_deps()`.
- style\_loader\_src – Filter a stylesheet URL in preparation for output. Happens after $base\_url has been prepended (if warranted).
- style\_loader\_tag – Filter the <link> element for a stylesheet.

## [Methods](https://developer.wordpress.org/reference/classes/wp_styles/\#methods)

| Name | Description |
| --- | --- |
| [WP\_Styles::\_\_construct](https://developer.wordpress.org/reference/classes/wp_styles/__construct/) | Constructor. |
| [WP\_Styles::\_css\_href](https://developer.wordpress.org/reference/classes/wp_styles/_css_href/) | Generates an enqueued style’s fully-qualified URL. |
| [WP\_Styles::add\_inline\_style](https://developer.wordpress.org/reference/classes/wp_styles/add_inline_style/) | Adds extra CSS styles to a registered stylesheet. |
| [WP\_Styles::all\_deps](https://developer.wordpress.org/reference/classes/wp_styles/all_deps/) | Determines style dependencies. |
| [WP\_Styles::do\_footer\_items](https://developer.wordpress.org/reference/classes/wp_styles/do_footer_items/) | Processes items and dependencies for the footer group. |
| [WP\_Styles::do\_item](https://developer.wordpress.org/reference/classes/wp_styles/do_item/) | Processes a style dependency. |
| [WP\_Styles::in\_default\_dir](https://developer.wordpress.org/reference/classes/wp_styles/in_default_dir/) | Whether a handle’s source is in a default directory. |
| [WP\_Styles::print\_inline\_style](https://developer.wordpress.org/reference/classes/wp_styles/print_inline_style/) | Prints extra CSS styles of a registered stylesheet. |
| [WP\_Styles::reset](https://developer.wordpress.org/reference/classes/wp_styles/reset/) | Resets class properties. |

## [Source](https://developer.wordpress.org/reference/classes/wp_styles/\#source)

`wp-includes/class-wp-styles.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_styles/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)

```php
class WP_Styles extends WP_Dependencies {
	/**
	 * Base URL for styles.
	 *
	 * Full URL with trailing slash.
	 *
	 * @since 2.6.0
	 * @var string
	 */
	public $base_url;

	/**
	 * URL of the content directory.
	 *
	 * @since 2.8.0
	 * @var string
	 */
	public $content_url;

	/**
	 * Default version string for stylesheets.
	 *
	 * @since 2.6.0
	 * @var string
	 */
	public $default_version;

	/**
	 * The current text direction.
	 *
	 * @since 2.6.0
	 * @var string
	 */
	public $text_direction = 'ltr';

	/**
	 * Holds a list of style handles which will be concatenated.
	 *
	 * @since 2.8.0
	 * @var string
	 */
	public $concat = '';

	/**
	 * Holds a string which contains style handles and their version.
	 *
	 * @since 2.8.0
	 * @deprecated 3.4.0
	 * @var string
	 */
	public $concat_version = '';

	/**
	 * Whether to perform concatenation.
	 *
	 * @since 2.8.0
	 * @var bool
	 */
	public $do_concat = false;

	/**
	 * Holds HTML markup of styles and additional data if concatenation
	 * is enabled.
	 *
	 * @since 2.8.0
	 * @var string
	 */
	public $print_html = '';

	/**
	 * Holds inline styles if concatenation is enabled.
	 *
	 * @since 3.3.0
	 * @var string
	 */
	public $print_code = '';

	/**
	 * List of default directories.
	 *
	 * @since 2.8.0
	 * @var array
	 */
	public $default_dirs;

	/**
	 * Holds a string which contains the type attribute for style tag.
	 *
	 * If the active theme does not declare HTML5 support for 'style',
	 * then it initializes as `type='text/css'`.
	 *
	 * @since 5.3.0
	 * @var string
	 */
	private $type_attr = '';

	/**
	 * Constructor.
	 *
	 * @since 2.6.0
	 */
	public function __construct() {
		if (
			function_exists( 'is_admin' ) && ! is_admin()
		&&
			function_exists( 'current_theme_supports' ) && ! current_theme_supports( 'html5', 'style' )
		) {
			$this->type_attr = " type='text/css'";
		}

		/**
		 * Fires when the WP_Styles instance is initialized.
		 *
		 * @since 2.6.0
		 *
		 * @param WP_Styles $wp_styles WP_Styles instance (passed by reference).
		 */
		do_action_ref_array( 'wp_default_styles', array( &$this ) );
	}

	/**
	 * Processes a style dependency.
	 *
	 * @since 2.6.0
	 * @since 5.5.0 Added the `$group` parameter.
	 *
	 * @see WP_Dependencies::do_item()
	 *
	 * @param string    $handle The style's registered handle.
	 * @param int|false $group  Optional. Group level: level (int), no groups (false).
	 *                          Default false.
	 * @return bool True on success, false on failure.
	 */
	public function do_item( $handle, $group = false ) {
		if ( ! parent::do_item( $handle ) ) {
			return false;
		}

		$obj = $this->registered[ $handle ];

		if ( null === $obj->ver ) {
			$ver = '';
		} else {
			$ver = $obj->ver ? $obj->ver : $this->default_version;
		}

		if ( isset( $this->args[ $handle ] ) ) {
			$ver = $ver ? $ver . '&amp;' . $this->args[ $handle ] : $this->args[ $handle ];
		}

		$src                   = $obj->src;
		$ie_conditional_prefix = '';
		$ie_conditional_suffix = '';
		$conditional           = isset( $obj->extra['conditional'] ) ? $obj->extra['conditional'] : '';

		if ( $conditional ) {
			$ie_conditional_prefix = "<!--[if {$conditional}]>\n";
			$ie_conditional_suffix = "<![endif]-->\n";
		}

		$inline_style = $this->print_inline_style( $handle, false );

		if ( $inline_style ) {
			$inline_style_tag = sprintf(
				"<style id='%s-inline-css'%s>\n%s\n</style>\n",
				esc_attr( $handle ),
				$this->type_attr,
				$inline_style
			);
		} else {
			$inline_style_tag = '';
		}

		if ( $this->do_concat ) {
			if ( $this->in_default_dir( $src ) && ! $conditional && ! isset( $obj->extra['alt'] ) ) {
				$this->concat         .= "$handle,";
				$this->concat_version .= "$handle$ver";

				$this->print_code .= $inline_style;

				return true;
			}
		}

		if ( isset( $obj->args ) ) {
			$media = esc_attr( $obj->args );
		} else {
			$media = 'all';
		}

		// A single item may alias a set of items, by having dependencies, but no source.
		if ( ! $src ) {
			if ( $inline_style_tag ) {
				if ( $this->do_concat ) {
					$this->print_html .= $inline_style_tag;
				} else {
					echo $inline_style_tag;
				}
			}

			return true;
		}

		$href = $this->_css_href( $src, $ver, $handle );
		if ( ! $href ) {
			return true;
		}

		$rel   = isset( $obj->extra['alt'] ) && $obj->extra['alt'] ? 'alternate stylesheet' : 'stylesheet';
		$title = isset( $obj->extra['title'] ) ? sprintf( " title='%s'", esc_attr( $obj->extra['title'] ) ) : '';

		$tag = sprintf(
			"<link rel='%s' id='%s-css'%s href='%s'%s media='%s' />\n",
			$rel,
			$handle,
			$title,
			$href,
			$this->type_attr,
			$media
		);

		/**
		 * Filters the HTML link tag of an enqueued style.
		 *
		 * @since 2.6.0
		 * @since 4.3.0 Introduced the `$href` parameter.
		 * @since 4.5.0 Introduced the `$media` parameter.
		 *
		 * @param string $tag    The link tag for the enqueued style.
		 * @param string $handle The style's registered handle.
		 * @param string $href   The stylesheet's source URL.
		 * @param string $media  The stylesheet's media attribute.
		 */
		$tag = apply_filters( 'style_loader_tag', $tag, $handle, $href, $media );

		if ( 'rtl' === $this->text_direction && isset( $obj->extra['rtl'] ) && $obj->extra['rtl'] ) {
			if ( is_bool( $obj->extra['rtl'] ) || 'replace' === $obj->extra['rtl'] ) {
				$suffix   = isset( $obj->extra['suffix'] ) ? $obj->extra['suffix'] : '';
				$rtl_href = str_replace( "{$suffix}.css", "-rtl{$suffix}.css", $this->_css_href( $src, $ver, "$handle-rtl" ) );
			} else {
				$rtl_href = $this->_css_href( $obj->extra['rtl'], $ver, "$handle-rtl" );
			}

			$rtl_tag = sprintf(
				"<link rel='%s' id='%s-rtl-css'%s href='%s'%s media='%s' />\n",
				$rel,
				$handle,
				$title,
				$rtl_href,
				$this->type_attr,
				$media
			);

			/** This filter is documented in wp-includes/class-wp-styles.php */
			$rtl_tag = apply_filters( 'style_loader_tag', $rtl_tag, $handle, $rtl_href, $media );

			if ( 'replace' === $obj->extra['rtl'] ) {
				$tag = $rtl_tag;
			} else {
				$tag .= $rtl_tag;
			}
		}

		if ( $this->do_concat ) {
			$this->print_html .= $ie_conditional_prefix;
			$this->print_html .= $tag;
			if ( $inline_style_tag ) {
				$this->print_html .= $inline_style_tag;
			}
			$this->print_html .= $ie_conditional_suffix;
		} else {
			echo $ie_conditional_prefix;
			echo $tag;
			$this->print_inline_style( $handle );
			echo $ie_conditional_suffix;
		}

		return true;
	}

	/**
	 * Adds extra CSS styles to a registered stylesheet.
	 *
	 * @since 3.3.0
	 *
	 * @param string $handle The style's registered handle.
	 * @param string $code   String containing the CSS styles to be added.
	 * @return bool True on success, false on failure.
	 */
	public function add_inline_style( $handle, $code ) {
		if ( ! $code ) {
			return false;
		}

		$after = $this->get_data( $handle, 'after' );
		if ( ! $after ) {
			$after = array();
		}

		$after[] = $code;

		return $this->add_data( $handle, 'after', $after );
	}

	/**
	 * Prints extra CSS styles of a registered stylesheet.
	 *
	 * @since 3.3.0
	 *
	 * @param string $handle  The style's registered handle.
	 * @param bool   $display Optional. Whether to print the inline style
	 *                        instead of just returning it. Default true.
	 * @return string|bool False if no data exists, inline styles if `$display` is true,
	 *                     true otherwise.
	 */
	public function print_inline_style( $handle, $display = true ) {
		$output = $this->get_data( $handle, 'after' );

		if ( empty( $output ) ) {
			return false;
		}

		$output = implode( "\n", $output );

		if ( ! $display ) {
			return $output;
		}

		printf(
			"<style id='%s-inline-css'%s>\n%s\n</style>\n",
			esc_attr( $handle ),
			$this->type_attr,
			$output
		);

		return true;
	}

	/**
	 * Determines style dependencies.
	 *
	 * @since 2.6.0
	 *
	 * @see WP_Dependencies::all_deps()
	 *
	 * @param string|string[] $handles   Item handle (string) or item handles (array of strings).
	 * @param bool            $recursion Optional. Internal flag that function is calling itself.
	 *                                   Default false.
	 * @param int|false       $group     Optional. Group level: level (int), no groups (false).
	 *                                   Default false.
	 * @return bool True on success, false on failure.
	 */
	public function all_deps( $handles, $recursion = false, $group = false ) {
		$result = parent::all_deps( $handles, $recursion, $group );
		if ( ! $recursion ) {
			/**
			 * Filters the array of enqueued styles before processing for output.
			 *
			 * @since 2.6.0
			 *
			 * @param string[] $to_do The list of enqueued style handles about to be processed.
			 */
			$this->to_do = apply_filters( 'print_styles_array', $this->to_do );
		}
		return $result;
	}

	/**
	 * Generates an enqueued style's fully-qualified URL.
	 *
	 * @since 2.6.0
	 *
	 * @param string $src    The source of the enqueued style.
	 * @param string $ver    The version of the enqueued style.
	 * @param string $handle The style's registered handle.
	 * @return string Style's fully-qualified URL.
	 */
	public function _css_href( $src, $ver, $handle ) {
		if ( ! is_bool( $src ) && ! preg_match( '|^(https?:)?//|', $src ) && ! ( $this->content_url && str_starts_with( $src, $this->content_url ) ) ) {
			$src = $this->base_url . $src;
		}

		if ( ! empty( $ver ) ) {
			$src = add_query_arg( 'ver', $ver, $src );
		}

		/**
		 * Filters an enqueued style's fully-qualified URL.
		 *
		 * @since 2.6.0
		 *
		 * @param string $src    The source URL of the enqueued style.
		 * @param string $handle The style's registered handle.
		 */
		$src = apply_filters( 'style_loader_src', $src, $handle );
		return esc_url( $src );
	}

	/**
	 * Whether a handle's source is in a default directory.
	 *
	 * @since 2.8.0
	 *
	 * @param string $src The source of the enqueued style.
	 * @return bool True if found, false if not.
	 */
	public function in_default_dir( $src ) {
		if ( ! $this->default_dirs ) {
			return true;
		}

		foreach ( (array) $this->default_dirs as $test ) {
			if ( str_starts_with( $src, $test ) ) {
				return true;
			}
		}
		return false;
	}

	/**
	 * Processes items and dependencies for the footer group.
	 *
	 * HTML 5 allows styles in the body, grab late enqueued items and output them in the footer.
	 *
	 * @since 3.3.0
	 *
	 * @see WP_Dependencies::do_items()
	 *
	 * @return string[] Handles of items that have been processed.
	 */
	public function do_footer_items() {
		$this->do_items( false, 1 );
		return $this->done;
	}

	/**
	 * Resets class properties.
	 *
	 * @since 3.3.0
	 */
	public function reset() {
		$this->do_concat      = false;
		$this->concat         = '';
		$this->concat_version = '';
		$this->print_html     = '';
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes_class-wp-styles-php-2/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-styles.php#L18) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-styles.php#L18-L464)

## [Related](https://developer.wordpress.org/reference/classes/wp_styles/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Dependencies](https://developer.wordpress.org/reference/classes/wp_dependencies/) `wp-includes/class-wp-dependencies.php` | Core base class extended to register items. |

## [Changelog](https://developer.wordpress.org/reference/classes/wp_styles/\#changelog)

| Version | Description |
| --- | --- |
| [2.6.0](https://developer.wordpress.org/reference/since/2.6.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_styles/\#user-contributed-notes)

1. [Skip to note 7 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1994)



**Adding a Right-to-Left Stylesheet**


To specify a stylesheet to add, set ‘rtl’ to the URL:





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example', '/themes/example/example.css');
      $wp_styles->add_data('rtl', '/themes/example/rtl.css');
      $wp_styles->enqueue(array('example'));
?>
```





To have WordPress create the URL for the rtl stylesheet, set ‘rtl’ to TRUE and (optionally) set a suffix for the stylesheet in the extra data:





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example', '/themes/example/example-new.css');
      $wp_styles->add_data('rtl', TRUE);
      # URL for rtl stylesheet will be '/themes/example/example-rtl-new.css'
      $wp_styles->add_data('suffix', '-new');
      $wp_styles->enqueue(array('example'));
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1994%23feedback-editor-1994)

2. [Skip to note 8 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1993)



**Examples**



**Dependent Stylesheet**





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example', '/themes/example/example.css');
      $wp_styles->add('example_ie7-', '/themes/example/ie7-.css', array('example'));
      $wp_styles->enqueue(array('example', 'example_ie7-'));
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1993%23feedback-editor-1993)

3. [Skip to note 9 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1995)



**Embedded Style**


An embedded stylesheet can be added to an external one, but sparingly:





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example', '/themes/example/example.css');
      $wp_styles->add_inline_style('example', '* {margin: 0}');
      $wp_styles->enqueue(array('example'));
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1995%23feedback-editor-1995)

4. [Skip to note 10 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1996)



**Conditional Styles**


Conditional comments can be added around the to a stylesheet by setting ‘conditional’ in a stylesheet’s extra data:





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example_ie7-', '/themes/example/ie7-.css');
      $wp_styles->add_data('example_ie7-', 'conditional', 'lte IE 7');
      $wp_styles->enqueue(array('example_ie7-'));
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1996%23feedback-editor-1996)

5. [Skip to note 11 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1997)



**Other Attributes**


Other attributes include the stylesheet title, and wether it’s an alternate stylesheet:





`wp-includes/class-wp-styles.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      global $wp_styles;
      $wp_styles->add('example-alt', '/themes/example/example-alt.css');
      $wp_styles->add_data('example-alt', 'title', 'Example Alternate Stylesheet');
      $wp_styles->add_data('example-alt', 'alt', TRUE);
      $wp_styles->enqueue(array('example-alt'));
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1997%23feedback-editor-1997)

6. [Skip to note 12 content](https://developer.wordpress.org/reference/classes/wp_styles/#comment-content-1998)



**Accumulation**


Instead of printing style sheet elements, they can be gathered for other purposes:





`wp-includes/class-wp-styles.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_styles/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_styles/#)




```php
<?php
      /* Create  */
      $my_styles = new WP_Styles;
      $my_styles->do_concat = TRUE;

      /* Add styles */
      $my_styles->add('example', '/themes/example/example.css');
      $my_styles->add('example_ie7-', '/themes/example/ie7-.css', array('example'));
      $my_styles->add_data('example_ie7-', 'conditional', 'lte IE 7');
      #...
      $wp_styles->enqueue(array('example', 'example_ie7-', ...));

      /* Output styles */
      $my_styles->do_items();

      /* */
      # 'example,example_ie7-,...'
      $my_styles->concat;
      # accumulated elements
      $my_styles->print_html;
      #...
      /* Clear  */
      $my_styles->reset();
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F%3Freplytocom%3D1998%23feedback-editor-1998)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_styles%2F) before being able to contribute a note or feedback.

Notifications