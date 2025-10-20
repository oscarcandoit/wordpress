---
url: https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker
scraped_at: 2025-10-20T03:18:50.159Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_localize\_jquery\_ui\_datepicker()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_localize\_jquery\_ui\_datepicker()

Search

# wp\_localize\_jquery\_ui\_datepicker()

## In this article

Table of Contents

- [Source](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#wp--skip-link--target)

Localizes the jQuery UI datepicker.

## [Source](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/\#source)

`wp-includes/script-loader.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#)

```php
function wp_localize_jquery_ui_datepicker() {
	global $wp_locale;

	if ( ! wp_script_is( 'jquery-ui-datepicker', 'enqueued' ) ) {
		return;
	}

	// Convert the PHP date format into jQuery UI's format.
	$datepicker_date_format = str_replace(
		array(
			'd',
			'j',
			'l',
			'z', // Day.
			'F',
			'M',
			'n',
			'm', // Month.
			'Y',
			'y', // Year.
		),
		array(
			'dd',
			'd',
			'DD',
			'o',
			'MM',
			'M',
			'm',
			'mm',
			'yy',
			'y',
		),
		get_option( 'date_format' )
	);

	$datepicker_defaults = wp_json_encode(
		array(
			'closeText'       => __( 'Close' ),
			'currentText'     => __( 'Today' ),
			'monthNames'      => array_values( $wp_locale->month ),
			'monthNamesShort' => array_values( $wp_locale->month_abbrev ),
			'nextText'        => __( 'Next' ),
			'prevText'        => __( 'Previous' ),
			'dayNames'        => array_values( $wp_locale->weekday ),
			'dayNamesShort'   => array_values( $wp_locale->weekday_abbrev ),
			'dayNamesMin'     => array_values( $wp_locale->weekday_initial ),
			'dateFormat'      => $datepicker_date_format,
			'firstDay'        => absint( get_option( 'start_of_week' ) ),
			'isRTL'           => $wp_locale->is_rtl(),
		)
	);

	wp_add_inline_script( 'jquery-ui-datepicker', "jQuery(function(jQuery){jQuery.datepicker.setDefaults({$datepicker_defaults});});" );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/script-loader.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/script-loader.php#L1960) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/script-loader.php#L1960-L2014)

## [Related](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/\#related)

| Uses | Description |
| --- | --- |
| [wp\_add\_inline\_script()](https://developer.wordpress.org/reference/functions/wp_add_inline_script/) `wp-includes/functions.wp-scripts.php` | Adds extra code to a registered script. |
| [wp\_script\_is()](https://developer.wordpress.org/reference/functions/wp_script_is/) `wp-includes/functions.wp-scripts.php` | Determines whether a script has been added to the queue. |
| [WP\_Locale::is\_rtl()](https://developer.wordpress.org/reference/classes/wp_locale/is_rtl/) `wp-includes/class-wp-locale.php` | Checks if current locale is RTL. |
| [wp\_json\_encode()](https://developer.wordpress.org/reference/functions/wp_json_encode/) `wp-includes/functions.php` | Encodes a variable into JSON, with some confidence checks. |
| [absint()](https://developer.wordpress.org/reference/functions/absint/) `wp-includes/load.php` | Converts a value to non-negative integer. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

[Show 3 more](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#) [Show less](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_localize_jquery_ui_datepicker/\#changelog)

| Version | Description |
| --- | --- |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_localize_jquery_ui_datepicker%2F) before being able to contribute a note or feedback.

Notifications