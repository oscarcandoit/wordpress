---
url: https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts
scraped_at: 2025-10-20T03:22:26.628Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_tinymce\_inline\_scripts()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_tinymce\_inline\_scripts()

Search

# wp\_tinymce\_inline\_scripts()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#description)
- [Source](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#wp--skip-link--target)

Adds inline scripts required for the TinyMCE in the block editor.

## [Description](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/\#description)

These TinyMCE init settings are used to extend and override the default settings from `_WP_Editors::default_settings()` for the Classic block.

## [Source](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/\#source)

`wp-includes/script-loader.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#)

```php
function wp_tinymce_inline_scripts() {
	global $wp_scripts;

	/** This filter is documented in wp-includes/class-wp-editor.php */
	$editor_settings = apply_filters( 'wp_editor_settings', array( 'tinymce' => true ), 'classic-block' );

	$tinymce_plugins = array(
		'charmap',
		'colorpicker',
		'hr',
		'lists',
		'media',
		'paste',
		'tabfocus',
		'textcolor',
		'fullscreen',
		'wordpress',
		'wpautoresize',
		'wpeditimage',
		'wpemoji',
		'wpgallery',
		'wplink',
		'wpdialogs',
		'wptextpattern',
		'wpview',
	);

	/** This filter is documented in wp-includes/class-wp-editor.php */
	$tinymce_plugins = apply_filters( 'tiny_mce_plugins', $tinymce_plugins, 'classic-block' );
	$tinymce_plugins = array_unique( $tinymce_plugins );

	$disable_captions = false;
	// Runs after `tiny_mce_plugins` but before `mce_buttons`.
	/** This filter is documented in wp-admin/includes/media.php */
	if ( apply_filters( 'disable_captions', '' ) ) {
		$disable_captions = true;
	}

	$toolbar1 = array(
		'formatselect',
		'bold',
		'italic',
		'bullist',
		'numlist',
		'blockquote',
		'alignleft',
		'aligncenter',
		'alignright',
		'link',
		'unlink',
		'wp_more',
		'spellchecker',
		'wp_add_media',
		'wp_adv',
	);

	/** This filter is documented in wp-includes/class-wp-editor.php */
	$toolbar1 = apply_filters( 'mce_buttons', $toolbar1, 'classic-block' );

	$toolbar2 = array(
		'strikethrough',
		'hr',
		'forecolor',
		'pastetext',
		'removeformat',
		'charmap',
		'outdent',
		'indent',
		'undo',
		'redo',
		'wp_help',
	);

	/** This filter is documented in wp-includes/class-wp-editor.php */
	$toolbar2 = apply_filters( 'mce_buttons_2', $toolbar2, 'classic-block' );
	/** This filter is documented in wp-includes/class-wp-editor.php */
	$toolbar3 = apply_filters( 'mce_buttons_3', array(), 'classic-block' );
	/** This filter is documented in wp-includes/class-wp-editor.php */
	$toolbar4 = apply_filters( 'mce_buttons_4', array(), 'classic-block' );
	/** This filter is documented in wp-includes/class-wp-editor.php */
	$external_plugins = apply_filters( 'mce_external_plugins', array(), 'classic-block' );

	$tinymce_settings = array(
		'plugins'              => implode( ',', $tinymce_plugins ),
		'toolbar1'             => implode( ',', $toolbar1 ),
		'toolbar2'             => implode( ',', $toolbar2 ),
		'toolbar3'             => implode( ',', $toolbar3 ),
		'toolbar4'             => implode( ',', $toolbar4 ),
		'external_plugins'     => wp_json_encode( $external_plugins ),
		'classic_block_editor' => true,
	);

	if ( $disable_captions ) {
		$tinymce_settings['wpeditimage_disable_captions'] = true;
	}

	if ( ! empty( $editor_settings['tinymce'] ) && is_array( $editor_settings['tinymce'] ) ) {
		$tinymce_settings = array_merge( $tinymce_settings, $editor_settings['tinymce'] );
	}

	/** This filter is documented in wp-includes/class-wp-editor.php */
	$tinymce_settings = apply_filters( 'tiny_mce_before_init', $tinymce_settings, 'classic-block' );

	/*
	 * Do "by hand" translation from PHP array to js object.
	 * Prevents breakage in some custom settings.
	 */
	$init_obj = '';
	foreach ( $tinymce_settings as $key => $value ) {
		if ( is_bool( $value ) ) {
			$val       = $value ? 'true' : 'false';
			$init_obj .= $key . ':' . $val . ',';
			continue;
		} elseif ( ! empty( $value ) && is_string( $value ) && (
			( '{' === $value[0] && '}' === $value[ strlen( $value ) - 1 ] ) ||
			( '[' === $value[0] && ']' === $value[ strlen( $value ) - 1 ] ) ||
			preg_match( '/^\(?function ?\(/', $value ) ) ) {
			$init_obj .= $key . ':' . $value . ',';
			continue;
		}
		$init_obj .= $key . ':"' . $value . '",';
	}

	$init_obj = '{' . trim( $init_obj, ' ,' ) . '}';

	$script = 'window.wpEditorL10n = {
		tinymce: {
			baseURL: ' . wp_json_encode( includes_url( 'js/tinymce' ) ) . ',
			suffix: ' . ( SCRIPT_DEBUG ? '""' : '".min"' ) . ',
			settings: ' . $init_obj . ',
		}
	}';

	$wp_scripts->add_inline_script( 'wp-block-library', $script, 'before' );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/script-loader.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/script-loader.php#L516) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/script-loader.php#L516-L650)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/\#hooks)

[apply\_filters( ‘disable\_captions’, bool$bool )](https://developer.wordpress.org/reference/hooks/disable_captions/)

Filters whether to disable captions.

[apply\_filters( ‘mce\_buttons’, array$mce\_buttons, string$editor\_id )](https://developer.wordpress.org/reference/hooks/mce_buttons/)

Filters the first-row list of TinyMCE buttons (Visual tab).

[apply\_filters( ‘mce\_buttons\_2’, array$mce\_buttons\_2, string$editor\_id )](https://developer.wordpress.org/reference/hooks/mce_buttons_2/)

Filters the second-row list of TinyMCE buttons (Visual tab).

[apply\_filters( ‘mce\_buttons\_3’, array$mce\_buttons\_3, string$editor\_id )](https://developer.wordpress.org/reference/hooks/mce_buttons_3/)

Filters the third-row list of TinyMCE buttons (Visual tab).

[apply\_filters( ‘mce\_buttons\_4’, array$mce\_buttons\_4, string$editor\_id )](https://developer.wordpress.org/reference/hooks/mce_buttons_4/)

Filters the fourth-row list of TinyMCE buttons (Visual tab).

[apply\_filters( ‘mce\_external\_plugins’, array$external\_plugins, string$editor\_id )](https://developer.wordpress.org/reference/hooks/mce_external_plugins/)

Filters the list of TinyMCE external plugins.

[apply\_filters( ‘tiny\_mce\_before\_init’, array$mce\_init, string$editor\_id )](https://developer.wordpress.org/reference/hooks/tiny_mce_before_init/)

Filters the TinyMCE config before init.

[apply\_filters( ‘tiny\_mce\_plugins’, array$plugins, string$editor\_id )](https://developer.wordpress.org/reference/hooks/tiny_mce_plugins/)

Filters the list of default TinyMCE plugins.

[apply\_filters( ‘wp\_editor\_settings’, array$settings, string$editor\_id )](https://developer.wordpress.org/reference/hooks/wp_editor_settings/)

Filters the [wp\_editor()](https://developer.wordpress.org/reference/functions/wp_editor/) settings.

## [Related](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Scripts::add\_inline\_script()](https://developer.wordpress.org/reference/classes/wp_scripts/add_inline_script/) `wp-includes/class-wp-scripts.php` | Adds extra code to a registered script. |
| [includes\_url()](https://developer.wordpress.org/reference/functions/includes_url/) `wp-includes/link-template.php` | Retrieves the URL to the includes directory. |
| [wp\_json\_encode()](https://developer.wordpress.org/reference/functions/wp_json_encode/) `wp-includes/functions.php` | Encodes a variable into JSON, with some confidence checks. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#) [Show less](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_tinymce_inline_scripts/\#changelog)

| Version | Description |
| --- | --- |
| [5.0.0](https://developer.wordpress.org/reference/since/5.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_tinymce_inline_scripts%2F) before being able to contribute a note or feedback.

Notifications