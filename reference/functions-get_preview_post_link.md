---
url: https://developer.wordpress.org/reference/functions/get_preview_post_link
scraped_at: 2025-10-20T03:17:24.767Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_preview_post_link/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_preview\_post\_link()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_preview\_post\_link()

Search

# get\_preview\_post\_link( int\|WP\_Post$post = null, array$query\_args = array(), string$preview\_link = '' ): string\|null

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_preview_post_link/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_preview_post_link/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_preview_post_link/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_preview_post_link/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_preview_post_link/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_preview_post_link/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_preview_post_link/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_preview_post_link/#wp--skip-link--target)

Retrieves the URL used for the post preview.

## [Description](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#description)

Allows additional query args to be appended.

## [Parameters](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Post ID or `WP_Post` object. Defaults to global `$post`.

Default: `null`

`$query_args` arrayoptional

Array of additional query args to be appended to the link.

Default: `array()`

`$preview_link` stringoptional

Base preview link to be used if it should differ from the post permalink.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#return)

string\|null URL used for the post preview, or null if the post does not exist.

## [Source](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#source)

`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_preview_post_link/#)

[Copy](https://developer.wordpress.org/reference/functions/get_preview_post_link/#)

```php
function get_preview_post_link( $post = null, $query_args = array(), $preview_link = '' ) {
	$post = get_post( $post );

	if ( ! $post ) {
		return;
	}

	$post_type_object = get_post_type_object( $post->post_type );
	if ( is_post_type_viewable( $post_type_object ) ) {
		if ( ! $preview_link ) {
			$preview_link = set_url_scheme( get_permalink( $post ) );
		}

		$query_args['preview'] = 'true';
		$preview_link          = add_query_arg( $query_args, $preview_link );
	}

	/**
	 * Filters the URL used for a post preview.
	 *
	 * @since 2.0.5
	 * @since 4.0.0 Added the `$post` parameter.
	 *
	 * @param string  $preview_link URL used for the post preview.
	 * @param WP_Post $post         Post object.
	 */
	return apply_filters( 'preview_post_link', $preview_link, $post );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L1409) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L1409-L1436)

## [Hooks](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#hooks)

[apply\_filters( ‘preview\_post\_link’, string$preview\_link, WP\_Post$post )](https://developer.wordpress.org/reference/hooks/preview_post_link/)

Filters the URL used for a post preview.

## [Related](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#related)

| Uses | Description |
| --- | --- |
| [is\_post\_type\_viewable()](https://developer.wordpress.org/reference/functions/is_post_type_viewable/) `wp-includes/post.php` | Determines whether a post type is considered “viewable”. |
| [set\_url\_scheme()](https://developer.wordpress.org/reference/functions/set_url_scheme/) `wp-includes/link-template.php` | Sets the scheme for a URL. |
| [add\_query\_arg()](https://developer.wordpress.org/reference/functions/add_query_arg/) `wp-includes/functions.php` | Retrieves a modified URL query string. |
| [get\_permalink()](https://developer.wordpress.org/reference/functions/get_permalink/) `wp-includes/link-template.php` | Retrieves the full permalink for the current post or post ID. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |
| [get\_post\_type\_object()](https://developer.wordpress.org/reference/functions/get_post_type_object/) `wp-includes/post.php` | Retrieves a post type object by name. |

[Show 5 more](https://developer.wordpress.org/reference/functions/get_preview_post_link/#) [Show less](https://developer.wordpress.org/reference/functions/get_preview_post_link/#)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Autosaves\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_autosaves_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-autosaves-controller.php` | Prepares the revision for the REST response. |
| [WP\_Posts\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_posts_list_table/handle_row_actions/) `wp-admin/includes/class-wp-posts-list-table.php` | Generates and displays row action links. |
| [get\_sample\_permalink\_html()](https://developer.wordpress.org/reference/functions/get_sample_permalink_html/) `wp-admin/includes/post.php` | Returns the HTML of the sample permalink slug editor. |
| [\_admin\_notice\_post\_locked()](https://developer.wordpress.org/reference/functions/_admin_notice_post_locked/) `wp-admin/includes/post.php` | Outputs the HTML for the notice to say that someone else is editing or has taken over editing of this post. |
| [post\_preview()](https://developer.wordpress.org/reference/functions/post_preview/) `wp-admin/includes/post.php` | Saves a draft or manually autosaves for the purpose of showing a post preview. |
| [wp\_ajax\_get\_permalink()](https://developer.wordpress.org/reference/functions/wp_ajax_get_permalink/) `wp-admin/includes/ajax-actions.php` | Handles retrieving a permalink via AJAX. |
| [post\_submit\_meta\_box()](https://developer.wordpress.org/reference/functions/post_submit_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays post submit form fields. |
| [wp\_admin\_bar\_edit\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_edit_menu/) `wp-includes/admin-bar.php` | Provides an edit link for posts and terms. |
| [\_wp\_link\_page()](https://developer.wordpress.org/reference/functions/_wp_link_page/) `wp-includes/post-template.php` | Helper function for [wp\_link\_pages()](https://developer.wordpress.org/reference/functions/wp_link_pages/) . |

[Show 4 more](https://developer.wordpress.org/reference/functions/get_preview_post_link/#) [Show less](https://developer.wordpress.org/reference/functions/get_preview_post_link/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_preview_post_link/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_preview_post_link%2F) before being able to contribute a note or feedback.

Notifications