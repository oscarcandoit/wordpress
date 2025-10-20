---
url: https://developer.wordpress.org/reference/functions/has_action
scraped_at: 2025-10-20T03:27:00.058Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/has_action/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

has\_action()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)has\_action()

Search

# has\_action( string$hook\_name, callable\|string\|array\|false$callback = false ): bool\|int

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/has_action/#description)
  - [See also](https://developer.wordpress.org/reference/functions/has_action/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/has_action/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/has_action/#return)
- [More Information](https://developer.wordpress.org/reference/functions/has_action/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/has_action/#source)
- [Related](https://developer.wordpress.org/reference/functions/has_action/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/has_action/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/has_action/#wp--skip-link--target)

Checks if any action has been registered for a hook.

## [Description](https://developer.wordpress.org/reference/functions/has_action/\#description)

When using the `$callback` argument, this function may return a non-boolean value that evaluates to false (e.g. 0), so use the `===` operator for testing the return value.

### [See also](https://developer.wordpress.org/reference/functions/has_action/\#see-also)

- [has\_filter()](https://developer.wordpress.org/reference/functions/has_filter): This function is an alias of [has\_filter()](https://developer.wordpress.org/reference/functions/has_filter/) .

## [Parameters](https://developer.wordpress.org/reference/functions/has_action/\#parameters)

`$hook_name` stringrequired

The name of the action hook.

`$callback` callable\|string\|array\|falseoptional

The callback to check for.

This function can be called unconditionally to speculatively check a callback that may or may not exist.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/has_action/\#return)

bool\|int If `$callback` is omitted, returns boolean for whether the hook has anything registered. When checking a specific function, the priority of that hook is returned, or false if the function is not attached.

## [More Information](https://developer.wordpress.org/reference/functions/has_action/\#more-information)

Since this action is an alias of [has\_filter()](https://developer.wordpress.org/reference/functions/has_filter/) , it also uses the global array $wp\_filter that stores all of the filters / actions.

## [Source](https://developer.wordpress.org/reference/functions/has_action/\#source)

`wp-includes/plugin.php`
[Copy](https://developer.wordpress.org/reference/functions/has_action/#)

```php
function has_action( $hook_name, $callback = false ) {
	return has_filter( $hook_name, $callback );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/plugin.php#L588) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/plugin.php#L588-L590)

## [Related](https://developer.wordpress.org/reference/functions/has_action/\#related)

| Uses | Description |
| --- | --- |
| [has\_filter()](https://developer.wordpress.org/reference/functions/has_filter/) `wp-includes/plugin.php` | Checks if any filter has been registered for a hook. |

| Used by | Description |
| --- | --- |
| [wp\_enqueue\_emoji\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_emoji_styles/) `wp-includes/formatting.php` | Enqueues the important emoji-related styles. |
| [wp\_enqueue\_admin\_bar\_bump\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_admin_bar_bump_styles/) `wp-includes/admin-bar.php` | Enqueues inline bump styles to make room for the admin bar. |
| [wp\_enqueue\_admin\_bar\_header\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_admin_bar_header_styles/) `wp-includes/admin-bar.php` | Enqueues inline style to hide the admin bar when printing. |
| [wp\_enqueue\_embed\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_embed_styles/) `wp-includes/embed.php` | Enqueues the CSS in the embed iframe header. |
| [wp\_enqueue\_block\_template\_skip\_link()](https://developer.wordpress.org/reference/functions/wp_enqueue_block_template_skip_link/) `wp-includes/theme-templates.php` | Enqueues the skip-link script & styles. |
| [wp\_save\_post\_revision\_on\_insert()](https://developer.wordpress.org/reference/functions/wp_save_post_revision_on_insert/) `wp-includes/revision.php` | Saves revisions for a post after all changes have been made. |
| [\_wp\_get\_iframed\_editor\_assets()](https://developer.wordpress.org/reference/functions/_wp_get_iframed_editor_assets/) `wp-includes/block-editor.php` | Collect the block editor assets that need to be loaded into the editor’s iframe. |
| [wp\_maybe\_enqueue\_oembed\_host\_js()](https://developer.wordpress.org/reference/functions/wp_maybe_enqueue_oembed_host_js/) `wp-includes/embed.php` | Enqueue the wp-embed script if the provided oEmbed HTML contains a post embed. |
| [wp\_is\_local\_html\_output()](https://developer.wordpress.org/reference/functions/wp_is_local_html_output/) `wp-includes/https-detection.php` | Checks whether a given HTML string is likely an output from this WordPress site. |
| [wp\_insert\_site()](https://developer.wordpress.org/reference/functions/wp_insert_site/) `wp-includes/ms-site.php` | Inserts a new site into the database. |
| [WP\_Customize\_Manager::save\_changeset\_post()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save_changeset_post/) `wp-includes/class-wp-customize-manager.php` | Saves the post for the loaded changeset. |
| [do\_action\_deprecated()](https://developer.wordpress.org/reference/functions/do_action_deprecated/) `wp-includes/plugin.php` | Fires functions attached to a deprecated action hook. |
| [WP\_Screen::render\_meta\_boxes\_preferences()](https://developer.wordpress.org/reference/classes/wp_screen/render_meta_boxes_preferences/) `wp-admin/includes/class-wp-screen.php` | Renders the meta boxes preferences. |
| [wp\_admin\_bar\_customize\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_customize_menu/) `wp-includes/admin-bar.php` | Adds the “Customize” link to the Toolbar. |
| [display\_setup\_form()](https://developer.wordpress.org/reference/functions/display_setup_form/) `wp-admin/install.php` | Displays installer setup form. |
| [get\_plugin\_page\_hook()](https://developer.wordpress.org/reference/functions/get_plugin_page_hook/) `wp-admin/includes/plugin.php` | Gets the hook attached to the administrative page of a plugin. |
| [do\_feed()](https://developer.wordpress.org/reference/functions/do_feed/) `wp-includes/functions.php` | Loads the feed template from the use of an action hook. |
| [WP\_Customize\_Setting::preview()](https://developer.wordpress.org/reference/classes/wp_customize_setting/preview/) `wp-includes/class-wp-customize-setting.php` | Add filters to supply the setting’s value when accessed. |
| [WP\_Customize\_Setting::update()](https://developer.wordpress.org/reference/classes/wp_customize_setting/update/) `wp-includes/class-wp-customize-setting.php` | Save the value of the setting, using the related API. |
| [wp\_save\_post\_revision()](https://developer.wordpress.org/reference/functions/wp_save_post_revision/) `wp-includes/revision.php` | Creates a revision for the current version of a post. |
| [comment\_form()](https://developer.wordpress.org/reference/functions/comment_form/) `wp-includes/comment-template.php` | Outputs a complete commenting form for use within a template. |

[Show 16 more](https://developer.wordpress.org/reference/functions/has_action/#) [Show less](https://developer.wordpress.org/reference/functions/has_action/#)

## [Changelog](https://developer.wordpress.org/reference/functions/has_action/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fhas_action%2F) before being able to contribute a note or feedback.

Notifications