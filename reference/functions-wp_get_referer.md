---
url: https://developer.wordpress.org/reference/functions/wp_get_referer
scraped_at: 2025-10-20T03:22:52.579Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_referer/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_referer()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_referer()

Search

# wp\_get\_referer(): string\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_get_referer/#description)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_referer/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_get_referer/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_referer/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_referer/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_referer/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_referer/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_referer/#wp--skip-link--target)

Retrieves referer from ‘\_wp\_http\_referer’ or HTTP referer.

## [Description](https://developer.wordpress.org/reference/functions/wp_get_referer/\#description)

If it’s the same as the current request URL, will return false.

## [Return](https://developer.wordpress.org/reference/functions/wp_get_referer/\#return)

string\|false Referer URL on success, false on failure.

## [More Information](https://developer.wordpress.org/reference/functions/wp_get_referer/\#more-information)

`HTTP referer` is a server variable. ‘referer’ is deliberately misspelled.

If page “refered” (form posted) to itself, returns false (because $\_SERVER\[‘HTTP\_REFERER’\] == $\_REQUEST\[‘\_wp\_http\_referer’\])

## [Source](https://developer.wordpress.org/reference/functions/wp_get_referer/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_referer/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_referer/#)

```php
function wp_get_referer() {
	// Return early if called before wp_validate_redirect() is defined.
	if ( ! function_exists( 'wp_validate_redirect' ) ) {
		return false;
	}

	$ref = wp_get_raw_referer();

	if ( $ref && wp_unslash( $_SERVER['REQUEST_URI'] ) !== $ref
		&& home_url() . wp_unslash( $_SERVER['REQUEST_URI'] ) !== $ref
	) {
		return wp_validate_redirect( $ref, false );
	}

	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L1974) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L1974-L1989)

## [Related](https://developer.wordpress.org/reference/functions/wp_get_referer/\#related)

| Uses | Description |
| --- | --- |
| [wp\_get\_raw\_referer()](https://developer.wordpress.org/reference/functions/wp_get_raw_referer/) `wp-includes/functions.php` | Retrieves unvalidated referer from the ‘\_wp\_http\_referer’ URL query variable or the HTTP referer. |
| [wp\_validate\_redirect()](https://developer.wordpress.org/reference/functions/wp_validate_redirect/) `wp-includes/pluggable.php` | Validates a URL for use in a redirect. |
| [wp\_unslash()](https://developer.wordpress.org/reference/functions/wp_unslash/) `wp-includes/formatting.php` | Removes slashes from a string or recursively removes slashes from strings within an array. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_get_referer/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_referer/#)

| Used by | Description |
| --- | --- |
| [WP\_Recovery\_Mode::handle\_exit\_recovery\_mode()](https://developer.wordpress.org/reference/classes/wp_recovery_mode/handle_exit_recovery_mode/) `wp-includes/class-wp-recovery-mode.php` | Handles a request to exit Recovery Mode. |
| [the\_block\_editor\_meta\_box\_post\_form\_hidden\_fields()](https://developer.wordpress.org/reference/functions/the_block_editor_meta_box_post_form_hidden_fields/) `wp-admin/includes/post.php` | Renders the hidden form required for the meta boxes form. |
| [WP\_Customize\_Manager::get\_return\_url()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_return_url/) `wp-includes/class-wp-customize-manager.php` | Gets URL to link the user to when closing the Customizer. |
| [WP\_Terms\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/handle_row_actions/) `wp-admin/includes/class-wp-terms-list-table.php` | Generates and displays row action links. |
| [wp\_media\_attach\_action()](https://developer.wordpress.org/reference/functions/wp_media_attach_action/) `wp-admin/includes/media.php` | Encapsulates the logic for Attach/Detach actions. |
| [set\_screen\_options()](https://developer.wordpress.org/reference/functions/set_screen_options/) `wp-admin/includes/misc.php` | Saves option for number of rows when listing posts, pages, comments, etc. |
| [\_admin\_notice\_post\_locked()](https://developer.wordpress.org/reference/functions/_admin_notice_post_locked/) `wp-admin/includes/post.php` | Outputs the HTML for the notice to say that someone else is editing or has taken over editing of this post. |
| [WP\_Terms\_List\_Table::column\_name()](https://developer.wordpress.org/reference/classes/wp_terms_list_table/column_name/) `wp-admin/includes/class-wp-terms-list-table.php` |  |
| [redirect\_post()](https://developer.wordpress.org/reference/functions/redirect_post/) `wp-admin/includes/post.php` | Redirects to previous page. |
| [auth\_redirect()](https://developer.wordpress.org/reference/functions/auth_redirect/) `wp-includes/pluggable.php` | Checks if a user is logged in, if not it redirects them to the login page. |
| [check\_admin\_referer()](https://developer.wordpress.org/reference/functions/check_admin_referer/) `wp-includes/pluggable.php` | Ensures intent by verifying that a user was referred from another admin page with the correct security nonce. |
| [wp\_nonce\_ays()](https://developer.wordpress.org/reference/functions/wp_nonce_ays/) `wp-includes/functions.php` | Displays “Are You Sure” message to confirm the action being taken. |
| [wp\_original\_referer\_field()](https://developer.wordpress.org/reference/functions/wp_original_referer_field/) `wp-includes/functions.php` | Retrieves or displays original referer hidden field for forms. |

[Show 8 more](https://developer.wordpress.org/reference/functions/wp_get_referer/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_referer/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_referer/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.4](https://developer.wordpress.org/reference/since/2.0.4/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_referer/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_get_referer/#comment-content-749)



Example





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_referer/#)




```php
if ( wp_get_referer() ) {
   	wp_safe_redirect( wp_get_referer() );
} else {
   	wp_safe_redirect( get_home_url() );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_referer%2F%3Freplytocom%3D749%23feedback-editor-749)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_referer%2F) before being able to contribute a note or feedback.

Notifications