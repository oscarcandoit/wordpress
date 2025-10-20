---
url: https://developer.wordpress.org/apis/quicktags
scraped_at: 2025-10-20T04:06:21.811Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/quicktags/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Quicktags


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Quicktags

Search

# Quicktags

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/apis/quicktags/#description)
- [History](https://developer.wordpress.org/apis/quicktags/#history)
- [Usage](https://developer.wordpress.org/apis/quicktags/#usage)
- [Parameters](https://developer.wordpress.org/apis/quicktags/#parameters)
- [Return Values](https://developer.wordpress.org/apis/quicktags/#return-values)
- [Examples](https://developer.wordpress.org/apis/quicktags/#examples)
  - [Modern example](https://developer.wordpress.org/apis/quicktags/#modern-example)
  - [Another modern example](https://developer.wordpress.org/apis/quicktags/#another-modern-example)
  - [Traditional example](https://developer.wordpress.org/apis/quicktags/#traditional-example)
- [Default Quicktags](https://developer.wordpress.org/apis/quicktags/#default-quicktags)
- [Source File](https://developer.wordpress.org/apis/quicktags/#source-file)

[↑ Back to top](https://developer.wordpress.org/apis/quicktags/#wp--skip-link--target)

## [Description](https://developer.wordpress.org/apis/quicktags/\#description)

The Quicktags API allows you to include additional buttons in the Text (HTML) mode of the WordPress Classic editor.

![](https://i0.wp.com/developer.wordpress.org/files/2019/08/quicktags-editor.png?resize=550%2C90&ssl=1)

## [History](https://developer.wordpress.org/apis/quicktags/\#history)

This API was introduced in [WordPress 3.3](https://developer.wordpress.org/support/wordpress-version/version-3-3).

## [Usage](https://developer.wordpress.org/apis/quicktags/\#usage)

``
[Copy](https://developer.wordpress.org/apis/quicktags/#)

```js
QTags.addButton( id, display, arg1, arg2, access_key, title, priority, instance, object );
```

## [Parameters](https://developer.wordpress.org/apis/quicktags/\#parameters)

- `id` **(** _**string**_ **) (** _**required**_ **):** The html id for the button. Default: _None_
- `display` **(** _**string**_ **) (** _**required**_ **):** The html value for the button. Default: _None_
- `arg1` **(** _**string**_ **) (** _**required**_ **):** Either a starting tag to be inserted like “<span>” or a callback that is executed when the button is clicked. Default: _None_
- `arg2` **(** _**string**_ **) (** _**optional**_ **):** Ending tag like “</span>”. Leave empty if tag doesn’t need to be closed (i.e. “<hr />”). Default: _None_
- `access_key` **(** _**string**_ **) (** _**optional**_ **):** **Deprecated and Not used.** Shortcut access key for the button. Default: _None_
- `title` **(** _**string**_ **) (** _**optional**_ **):** The html title value for the button. Default: _None_
- `priority` **(** _**int**_ **) (** _**optional**_ **):** A number representing the desired position of the button in the toolbar. 1 – 9 = first, 11 – 19 = second, 21 – 29 = third, etc. Default: _None_
- `instance` **(** _**string**_ **) (** _**optional**_ **):** Limit the button to a specific instance of Quicktags, add to all instances if not present. Default: _None_
- `object` **(** _**attr**_ **) (** _**optional**_ **):** Used to pass additional attributes. Currently supports `ariaLabel` and `ariaLabelClose` (for “close tag” state)

## [Return Values](https://developer.wordpress.org/apis/quicktags/\#return-values)

( _mixed_) Null or the button object that is needed for back-compat.

## [Examples](https://developer.wordpress.org/apis/quicktags/\#examples)

Below examples would add HTML buttons to the default Quicktags in the Text editor.

### [Modern example](https://developer.wordpress.org/apis/quicktags/\#modern-example)

This example uses the inline JS API to add the JavaScript when quicktags are enqueued.

``
[Copy](https://developer.wordpress.org/apis/quicktags/#)

```php
/**
 * Add a paragraph tag button to the quicktags toolbar
 *
 * @return void
 */
function wporg_add_quicktag_paragraph() {
	wp_add_inline_script(
		'quicktags',
		"QTags.addButton( 'eg_paragraph_v2', 'p_v2', '<p>', '</p>', '', 'Paragraph tag v2', 2, '', { ariaLabel: 'Paragraph', ariaLabelClose: 'Close Paragraph tag' });"
	);
}
add_action( 'admin_enqueue_scripts', 'wporg_add_quicktag_paragraph' );
```

### [Another modern example](https://developer.wordpress.org/apis/quicktags/\#another-modern-example)

In this example,

1. Enqueue a script using the proper WordPress function [`wp_enqueue_script`](https://developer.wordpress.org/reference/functions/wp_enqueue_script).
2. Call any JavaScript that you want to fire when or after the QuickTag was clicked inside the QuickTag call-back.

#### [Enqueue the script](https://developer.wordpress.org/apis/quicktags/\#enqueue-the-script)

Put below codes into active theme’s `functions.php`.

``
[Copy](https://developer.wordpress.org/apis/quicktags/#)

```php
function enqueue_quicktag_script(){
	wp_enqueue_script( 'your-handle', get_template_directory_uri() . '/editor-script.js', array( 'jquery', 'quicktags' ), '1.0.0', true );
}
add_action( 'admin_enqueue_scripts', 'enqueue_quicktag_script' );
```

#### [The JavaScript itself](https://developer.wordpress.org/apis/quicktags/\#the-javascript-itself)

Create new file `editor-script` and save under the active theme directory.

``
[Copy](https://developer.wordpress.org/apis/quicktags/#)

```javascript
QTags.addButton( 'eg_paragraph_v3', 'p_v3', my_callback, '', '', 'Prompted Paragraph tag', 3, '', { ariaLabel: 'Prompted Paragraph' } );

function my_callback(){
  var my_stuff = prompt( 'Enter Some Stuff:', '' );
  if ( my_stuff ) {
    QTags.insertContent( '<p>' + my_stuff + '</p>' );
  }
}
```

### [Traditional example](https://developer.wordpress.org/apis/quicktags/\#traditional-example)

This example manually add hardcoded JavaScript with `wp_script_is` on the admin footer hook. You should consider to use modern example. See above.

``
[Expand code](https://developer.wordpress.org/apis/quicktags/#)

[Copy](https://developer.wordpress.org/apis/quicktags/#)

```php
/**
 * Add more buttons to the quicktags HTML editor
 *
 * @return void
 */
function wporg_traditional_add_quicktags() {
	if ( ! wp_script_is( 'quicktags' ) ) {
		return;
	}

	?>
	<script type="text/javascript">
		QTags.addButton( 'eg_paragraph', 'p', '<p>', '</p>', '', 'Paragraph tag', 1, '', { ariaLabel: 'Paragraph', ariaLabelClose: 'Close Paragraph tag' } );
		QTags.addButton( 'eg_hr', 'hr', '<hr />', '', '', 'Horizontal rule line', 201, '', { ariaLabel: 'Horizontal' } );
		QTags.addButton( 'eg_pre', 'pre', '<pre lang="php">', '</pre>', '', 'Preformatted text tag', 111, '', { ariaLabel: 'Pre', ariaLabelClose: 'Close Pre tag' } );
	</script>
	<?php
}

add_action( 'admin_print_footer_scripts', 'wporg_traditional_add_quicktags', 11 );
```

Note:

- To avoid a Reference Error we check to see whether or not the ‘quicktags’ script is in use.
- Since WordPress 6.0, the script loading order was changed and the error “QTags is not defined” occurs without 3rd parameter of `add_action()`. Also, you have to specfy the larger number than 10 (ex.11).

The “p” button HTML would be:

``
[Copy](https://developer.wordpress.org/apis/quicktags/#)

```markup
<input type="button" id="qt_content_eg_paragraph" class="ed_button button button-small" title="Paragraph tag" aria-label="Paragraph" value="p">
```

The ID value for each button is automatically prepended with the string qt\_content\_.

Here is a dump of the docblock from `quicktags.js`, it’s pretty useful on it’s own.

``
[Expand code](https://developer.wordpress.org/apis/quicktags/#)

[Copy](https://developer.wordpress.org/apis/quicktags/#)

```php
/**
 * Main API function for adding a button to Quicktags
 *
 * Adds qt.Button or qt.TagButton depending on the args. The first three args are always required.
 * To be able to add button(s) to Quicktags, your script should be enqueued as dependent
 * on "quicktags" and outputted in the footer. If you are echoing JS directly from PHP,
 * use add_action( 'admin_print_footer_scripts', 'output_my_js', 100 ) or add_action( 'wp_footer', 'output_my_js', 100 )
 *
 * Minimum required to add a button that calls an external function:
 *     QTags.addButton( 'my_id', 'my button', my_callback );
 *     function my_callback() { alert('yeah!'); }
 *
 * Minimum required to add a button that inserts a tag:
 *     QTags.addButton( 'my_id', 'my button', '<span>', '</span>' );
 *     QTags.addButton( 'my_id2', 'my button', '<br />' );
 */
```

## [Default Quicktags](https://developer.wordpress.org/apis/quicktags/\#default-quicktags)

Here are the values of the default Quicktags added by WordPress to the Text editor. ID must be unique. When adding your own buttons, do not use these values:

| **ID** | **Value** | **Tag Start** | **Tag End** |
| --- | --- | --- | --- |
| link | link | <a href=”‘ + URL + ‘”> | </a> |
| strong | b | <strong> | </strong> |
| code | code | <code> | </code> |
| del | del | <del datetime=”‘ + \_datetime + ‘”> | </del> |
| fullscreen | fullscreen |  |  |
| em | i | <em> | </em> |
| li | li | t<li> | </li>n |
| img | img | <img src=”‘ + src + ‘” alt=”‘ + alt + ‘” /> |  |
| ol | ol | <ol>n | </ol>nn |
| block | b-quote | nn<blockquote> | </blockquote>nn |
| ins | ins | <ins datetime=”‘ + \_datetime + ‘”> | </ins> |
| more | more | <!–more–> |  |
| ul | ul | <ul>n | </ul>nn |
| spell | lookup |  |  |
| close | close |  |

Some tag values above use variables, such as URL and `_datetime`, passed from functions.

## [Source File](https://developer.wordpress.org/apis/quicktags/\#source-file)

qt.addButton() source is located in `[js/\_enqueues/lib/quicktags.js](https://core.trac.wordpress.org/browser/tags/5.2.1/src/js/_enqueues/lib/quicktags.js#L0)`, during build it’s output in `wp-incudes/js/quicktags.js` and `wp-includes/js/quicktags.min.js`.

First published

August 12, 2019

Last updated

February 27, 2023

[PreviousAuthenticationPrevious: Authentication](https://developer.wordpress.org/apis/making-http-requests/authentication/)

[NextRESTNext: REST](https://developer.wordpress.org/apis/rest/)

Notifications