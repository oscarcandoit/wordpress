---
url: https://developer.wordpress.org/reference/functions/wp_comment_reply
scraped_at: 2025-10-20T03:13:32.653Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_comment_reply/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_comment\_reply()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_comment\_reply()

Search

# wp\_comment\_reply( int$position = 1, bool$checkbox = false, string$mode = 'single', bool$table\_row = true )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_comment_reply/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_comment_reply/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_comment_reply/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_comment_reply/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_comment_reply/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_comment_reply/#wp--skip-link--target)

Outputs the in-line comment reply-to form in the Comments list table.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_comment_reply/\#parameters)

`$position` intoptional

The value of the `'position'` input field.

Default: `1`

`$checkbox` booloptional

The value of the `'checkbox'` input field.

Default: `false`

`$mode` stringoptional

If set to `'single'`, will use [WP\_Post\_Comments\_List\_Table](https://developer.wordpress.org/reference/classes/wp_post_comments_list_table/), otherwise [WP\_Comments\_List\_Table](https://developer.wordpress.org/reference/classes/wp_comments_list_table/). Default `'single'`.

Default: `'single'`

`$table_row` booloptional

Whether to use a table instead of a div element.

Default: `true`

## [Source](https://developer.wordpress.org/reference/functions/wp_comment_reply/\#source)

`wp-admin/includes/template.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_comment_reply/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_comment_reply/#)

```php
function wp_comment_reply( $position = 1, $checkbox = false, $mode = 'single', $table_row = true ) {
	global $wp_list_table;
	/**
	 * Filters the in-line comment reply-to form output in the Comments
	 * list table.
	 *
	 * Returning a non-empty value here will short-circuit display
	 * of the in-line comment-reply form in the Comments list table,
	 * echoing the returned value instead.
	 *
	 * @since 2.7.0
	 *
	 * @see wp_comment_reply()
	 *
	 * @param string $content The reply-to form content.
	 * @param array  $args    An array of default args.
	 */
	$content = apply_filters(
		'wp_comment_reply',
		'',
		array(
			'position' => $position,
			'checkbox' => $checkbox,
			'mode'     => $mode,
		)
	);

	if ( ! empty( $content ) ) {
		echo $content;
		return;
	}

	if ( ! $wp_list_table ) {
		if ( 'single' === $mode ) {
			$wp_list_table = _get_list_table( 'WP_Post_Comments_List_Table' );
		} else {
			$wp_list_table = _get_list_table( 'WP_Comments_List_Table' );
		}
	}

	?>
<form method="get">
	<?php if ( $table_row ) : ?>
<table style="display:none;"><tbody id="com-reply"><tr id="replyrow" class="inline-edit-row" style="display:none;"><td colspan="<?php echo $wp_list_table->get_column_count(); ?>" class="colspanchange">
<?php else : ?>
<div id="com-reply" style="display:none;"><div id="replyrow" style="display:none;">
<?php endif; ?>
	<fieldset class="comment-reply">
	<legend>
		<span class="hidden" id="editlegend"><?php _e( 'Edit Comment' ); ?></span>
		<span class="hidden" id="replyhead"><?php _e( 'Reply to Comment' ); ?></span>
		<span class="hidden" id="addhead"><?php _e( 'Add Comment' ); ?></span>
	</legend>

	<div id="replycontainer">
	<label for="replycontent" class="screen-reader-text">
		<?php
		/* translators: Hidden accessibility text. */
		_e( 'Comment' );
		?>
	</label>
	<?php
	$quicktags_settings = array( 'buttons' => 'strong,em,link,block,del,ins,img,ul,ol,li,code,close' );
	wp_editor(
		'',
		'replycontent',
		array(
			'media_buttons' => false,
			'tinymce'       => false,
			'quicktags'     => $quicktags_settings,
		)
	);
	?>
	</div>

	<div id="edithead" style="display:none;">
		<div class="inside">
		<label for="author-name"><?php _e( 'Name' ); ?></label>
		<input type="text" name="newcomment_author" size="50" value="" id="author-name" />
		</div>

		<div class="inside">
		<label for="author-email"><?php _e( 'Email' ); ?></label>
		<input type="text" name="newcomment_author_email" size="50" value="" id="author-email" />
		</div>

		<div class="inside">
		<label for="author-url"><?php _e( 'URL' ); ?></label>
		<input type="text" id="author-url" name="newcomment_author_url" class="code" size="103" value="" />
		</div>
	</div>

	<div id="replysubmit" class="submit">
		<p class="reply-submit-buttons">
			<button type="button" class="save button button-primary">
				<span id="addbtn" style="display: none;"><?php _e( 'Add Comment' ); ?></span>
				<span id="savebtn" style="display: none;"><?php _e( 'Update Comment' ); ?></span>
				<span id="replybtn" style="display: none;"><?php _e( 'Submit Reply' ); ?></span>
			</button>
			<button type="button" class="cancel button"><?php _e( 'Cancel' ); ?></button>
			<span class="waiting spinner"></span>
		</p>
		<?php
		wp_admin_notice(
			'<p class="error"></p>',
			array(
				'type'               => 'error',
				'additional_classes' => array( 'notice-alt', 'inline', 'hidden' ),
				'paragraph_wrap'     => false,
			)
		);
		?>
	</div>

	<input type="hidden" name="action" id="action" value="" />
	<input type="hidden" name="comment_ID" id="comment_ID" value="" />
	<input type="hidden" name="comment_post_ID" id="comment_post_ID" value="" />
	<input type="hidden" name="status" id="status" value="" />
	<input type="hidden" name="position" id="position" value="<?php echo $position; ?>" />
	<input type="hidden" name="checkbox" id="checkbox" value="<?php echo $checkbox ? 1 : 0; ?>" />
	<input type="hidden" name="mode" id="mode" value="<?php echo esc_attr( $mode ); ?>" />
	<?php
		wp_nonce_field( 'replyto-comment', '_ajax_nonce-replyto-comment', false );
	if ( current_user_can( 'unfiltered_html' ) ) {
		wp_nonce_field( 'unfiltered-html-comment', '_wp_unfiltered_html_comment', false );
	}
	?>
	</fieldset>
	<?php if ( $table_row ) : ?>
</td></tr></tbody></table>
	<?php else : ?>
</div></div>
	<?php endif; ?>
</form>
	<?php
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/template.php#L413) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/template.php#L413-L548)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_comment_reply/\#hooks)

[apply\_filters( ‘wp\_comment\_reply’, string$content, array$args )](https://developer.wordpress.org/reference/hooks/wp_comment_reply/)

Filters the in-line comment reply-to form output in the Comments list table.

## [Related](https://developer.wordpress.org/reference/functions/wp_comment_reply/\#related)

| Uses | Description |
| --- | --- |
| [wp\_admin\_notice()](https://developer.wordpress.org/reference/functions/wp_admin_notice/) `wp-includes/functions.php` | Outputs an admin notice. |
| [WP\_List\_Table::get\_column\_count()](https://developer.wordpress.org/reference/classes/wp_list_table/get_column_count/) `wp-admin/includes/class-wp-list-table.php` | Returns the number of visible columns. |
| [\_get\_list\_table()](https://developer.wordpress.org/reference/functions/_get_list_table/) `wp-admin/includes/list-table.php` | Fetches an instance of a [WP\_List\_Table](https://developer.wordpress.org/reference/classes/wp_list_table/) class. |
| [wp\_editor()](https://developer.wordpress.org/reference/functions/wp_editor/) `wp-includes/general-template.php` | Renders an editor. |
| [wp\_nonce\_field()](https://developer.wordpress.org/reference/functions/wp_nonce_field/) `wp-includes/functions.php` | Retrieves or display nonce hidden field for forms. |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 3 more](https://developer.wordpress.org/reference/functions/wp_comment_reply/#) [Show less](https://developer.wordpress.org/reference/functions/wp_comment_reply/#)

| Used by | Description |
| --- | --- |
| [wp\_dashboard\_recent\_comments()](https://developer.wordpress.org/reference/functions/wp_dashboard_recent_comments/) `wp-admin/includes/dashboard.php` | Show Comments section. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_comment_reply/\#changelog)

| Version | Description |
| --- | --- |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_comment_reply%2F) before being able to contribute a note or feedback.

Notifications