---
url: https://developer.wordpress.org/reference/functions/sanitize_text_field
scraped_at: 2025-10-20T03:15:54.654Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

sanitize\_text\_field()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)sanitize\_text\_field()

Search

# sanitize\_text\_field( string$str ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/sanitize_text_field/#description)
  - [See also](https://developer.wordpress.org/reference/functions/sanitize_text_field/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/sanitize_text_field/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/sanitize_text_field/#return)
- [More Information](https://developer.wordpress.org/reference/functions/sanitize_text_field/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/sanitize_text_field/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/sanitize_text_field/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/sanitize_text_field/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/sanitize_text_field/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_text_field/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/sanitize_text_field/#wp--skip-link--target)

Sanitizes a string from user input or from the database.

## [Description](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#description)

- Checks for invalid UTF-8,
- Converts single `<` characters to entities
- Strips all tags
- Removes line breaks, tabs, and extra whitespace
- Strips percent-encoded characters

### [See also](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#see-also)

- [sanitize\_textarea\_field()](https://developer.wordpress.org/reference/functions/sanitize_textarea_field)
- [wp\_check\_invalid\_utf8()](https://developer.wordpress.org/reference/functions/wp_check_invalid_utf8)
- [wp\_strip\_all\_tags()](https://developer.wordpress.org/reference/functions/wp_strip_all_tags)

## [Parameters](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#parameters)

`$str` stringrequired

String to sanitize.

## [Return](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#return)

string Sanitized string.

## [More Information](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#more-information)

**Basic Usage**

`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)

```php
<?php sanitize_text_field( $str ) ?>
```

## [Source](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#source)

`wp-includes/formatting.php`
[Expand code](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)

[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)

```php
function sanitize_text_field( $str ) {
	$filtered = _sanitize_text_fields( $str, false );

	/**
	 * Filters a sanitized text field string.
	 *
	 * @since 2.9.0
	 *
	 * @param string $filtered The sanitized string.
	 * @param string $str      The string prior to being sanitized.
	 */
	return apply_filters( 'sanitize_text_field', $filtered, $str );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/formatting.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/formatting.php#L5564) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/formatting.php#L5564-L5576)

## [Hooks](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#hooks)

[apply\_filters( ‘sanitize\_text\_field’, string$filtered, string$str )](https://developer.wordpress.org/reference/hooks/sanitize_text_field/)

Filters a sanitized text field string.

## [Related](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#related)

| Uses | Description |
| --- | --- |
| [\_sanitize\_text\_fields()](https://developer.wordpress.org/reference/functions/_sanitize_text_fields/) `wp-includes/formatting.php` | Internal helper function to sanitize a string from user input or from the database. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [WP\_Font\_Utils::sanitize\_font\_family()](https://developer.wordpress.org/reference/classes/wp_font_utils/sanitize_font_family/) `wp-includes/fonts/class-wp-font-utils.php` | Sanitizes and formats font family names. |
| [WP\_Font\_Utils::get\_font\_face\_slug()](https://developer.wordpress.org/reference/classes/wp_font_utils/get_font_face_slug/) `wp-includes/fonts/class-wp-font-utils.php` | Generates a slug from font face properties, e.g. `open sans;normal;400;100%;U+0-10FFFF` |
| [WP\_Font\_Collection::get\_sanitization\_schema()](https://developer.wordpress.org/reference/classes/wp_font_collection/get_sanitization_schema/) `wp-includes/fonts/class-wp-font-collection.php` | Retrieves the font collection sanitization schema. |
| [WP\_REST\_Templates\_Controller::get\_wp\_templates\_author\_text\_field()](https://developer.wordpress.org/reference/classes/wp_rest_templates_controller/get_wp_templates_author_text_field/) `wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php` | Returns a human readable text for the author of the template. |
| [wp\_get\_theme\_preview\_path()](https://developer.wordpress.org/reference/functions/wp_get_theme_preview_path/) `wp-includes/theme-previews.php` | Filters the blog option to return the path for the previewed theme. |
| [wp\_attach\_theme\_preview\_middleware()](https://developer.wordpress.org/reference/functions/wp_attach_theme_preview_middleware/) `wp-includes/theme-previews.php` | Adds a middleware to `apiFetch` to set the theme for the preview. |
| [WP\_REST\_Pattern\_Directory\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_pattern_directory_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-pattern-directory-controller.php` | Prepare a raw block pattern before it gets output in a REST API response. |
| [WP\_REST\_Site\_Health\_Controller::get\_directory\_sizes()](https://developer.wordpress.org/reference/classes/wp_rest_site_health_controller/get_directory_sizes/) `wp-includes/rest-api/endpoints/class-wp-rest-site-health-controller.php` | Gets the current directory sizes for this install. |
| [WP\_Application\_Passwords::create\_new\_application\_password()](https://developer.wordpress.org/reference/classes/wp_application_passwords/create_new_application_password/) `wp-includes/class-wp-application-passwords.php` | Creates a new application password. |
| [WP\_Application\_Passwords::update\_application\_password()](https://developer.wordpress.org/reference/classes/wp_application_passwords/update_application_password/) `wp-includes/class-wp-application-passwords.php` | Updates an application password. |
| [WP\_REST\_Plugins\_Controller::sanitize\_plugin\_param()](https://developer.wordpress.org/reference/classes/wp_rest_plugins_controller/sanitize_plugin_param/) `wp-includes/rest-api/endpoints/class-wp-rest-plugins-controller.php` | Sanitizes the “plugin” parameter to be a proper plugin file with “.php” appended. |
| [WP\_Sitemaps::render\_sitemaps()](https://developer.wordpress.org/reference/classes/wp_sitemaps/render_sitemaps/) `wp-includes/sitemaps/class-wp-sitemaps.php` | Renders sitemap templates based on rewrite rules. |
| [wp\_ajax\_toggle\_auto\_updates()](https://developer.wordpress.org/reference/functions/wp_ajax_toggle_auto_updates/) `wp-admin/includes/ajax-actions.php` | Handles enabling or disable plugin and theme auto-updates via AJAX. |
| [wp\_ajax\_health\_check\_get\_sizes()](https://developer.wordpress.org/reference/functions/wp_ajax_health_check_get_sizes/) `wp-admin/includes/ajax-actions.php` | Handles site health check to get directories and database sizes via AJAX. |
| [WP\_Privacy\_Requests\_Table::get\_views()](https://developer.wordpress.org/reference/classes/wp_privacy_requests_table/get_views/) `wp-admin/includes/class-wp-privacy-requests-table.php` | Gets an associative array ( id => link ) with the list of views available on this table. |
| [WP\_Privacy\_Requests\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_privacy_requests_table/prepare_items/) `wp-admin/includes/class-wp-privacy-requests-table.php` | Prepares items to output. |
| [\_wp\_personal\_data\_handle\_actions()](https://developer.wordpress.org/reference/functions/_wp_personal_data_handle_actions/) `wp-admin/includes/privacy-tools.php` | Handle list table actions. |
| [WP\_Customize\_Manager::handle\_load\_themes\_request()](https://developer.wordpress.org/reference/classes/wp_customize_manager/handle_load_themes_request/) `wp-includes/class-wp-customize-manager.php` | Loads themes into the theme browsing/installation UI. |
| [WP\_Widget\_Custom\_HTML::update()](https://developer.wordpress.org/reference/classes/wp_widget_custom_html/update/) `wp-includes/widgets/class-wp-widget-custom-html.php` | Handles updating settings for the current Custom HTML widget instance. |
| [rest\_sanitize\_value\_from\_schema()](https://developer.wordpress.org/reference/functions/rest_sanitize_value_from_schema/) `wp-includes/rest-api.php` | Sanitize a value based on a schema. |
| [WP\_REST\_Attachments\_Controller::create\_item()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/create_item/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Creates a single attachment. |
| [wp\_ajax\_delete\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_plugin/) `wp-admin/includes/ajax-actions.php` | Handles deleting a plugin via AJAX. |
| [WP\_Customize\_Nav\_Menu\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_setting/sanitize/) `wp-includes/customize/class-wp-customize-nav-menu-setting.php` | Sanitize an input. |
| [WP\_Customize\_Nav\_Menu\_Item\_Setting::sanitize()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menu_item_setting/sanitize/) `wp-includes/customize/class-wp-customize-nav-menu-item-setting.php` | Sanitize an input. |
| [WP\_Customize\_Nav\_Menus::ajax\_search\_available\_items()](https://developer.wordpress.org/reference/classes/wp_customize_nav_menus/ajax_search_available_items/) `wp-includes/class-wp-customize-nav-menus.php` | Ajax handler for searching available menu items. |
| [wp\_ajax\_update\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_update_plugin/) `wp-admin/includes/ajax-actions.php` | Handles updating a plugin via AJAX. |
| [validate\_another\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_another_blog_signup/) `wp-signup.php` | Validates a new site sign-up for an existing user. |
| [validate\_blog\_signup()](https://developer.wordpress.org/reference/functions/validate_blog_signup/) `wp-signup.php` | Validates new site signup. |
| [WP\_Plugins\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/prepare_items/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [WP\_Links\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_links_list_table/prepare_items/) `wp-admin/includes/class-wp-links-list-table.php` |  |
| [WP\_MS\_Themes\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-themes-list-table.php` |  |
| [WP\_Theme\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_theme_install_list_table/prepare_items/) `wp-admin/includes/class-wp-theme-install-list-table.php` |  |
| [edit\_user()](https://developer.wordpress.org/reference/functions/edit_user/) `wp-admin/includes/user.php` | Edit user settings based on contents of $\_POST |
| [WP\_Plugin\_Install\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/prepare_items/) `wp-admin/includes/class-wp-plugin-install-list-table.php` |  |
| [media\_handle\_upload()](https://developer.wordpress.org/reference/functions/media_handle_upload/) `wp-admin/includes/media.php` | Saves a file submitted from a POST request and create an attachment post for it. |
| [edit\_post()](https://developer.wordpress.org/reference/functions/edit_post/) `wp-admin/includes/post.php` | Updates an existing post with values provided in `$_POST`. |
| [wp\_ajax\_save\_attachment()](https://developer.wordpress.org/reference/functions/wp_ajax_save_attachment/) `wp-admin/includes/ajax-actions.php` | Handles updating attachment attributes via AJAX. |
| [WP\_Customize\_Manager::save()](https://developer.wordpress.org/reference/classes/wp_customize_manager/save/) `wp-includes/class-wp-customize-manager.php` | Handles customize\_save WP Ajax request to save/update a changeset. |
| [WP\_Nav\_Menu\_Widget::update()](https://developer.wordpress.org/reference/classes/wp_nav_menu_widget/update/) `wp-includes/widgets/class-wp-nav-menu-widget.php` | Handles updating settings for the current Navigation Menu widget instance. |
| [WP\_Widget\_Tag\_Cloud::update()](https://developer.wordpress.org/reference/classes/wp_widget_tag_cloud/update/) `wp-includes/widgets/class-wp-widget-tag-cloud.php` | Handles updating settings for the current Tag Cloud widget instance. |
| [WP\_Widget\_Recent\_Comments::update()](https://developer.wordpress.org/reference/classes/wp_widget_recent_comments/update/) `wp-includes/widgets/class-wp-widget-recent-comments.php` | Handles updating settings for the current Recent Comments widget instance. |
| [WP\_Widget\_Recent\_Posts::update()](https://developer.wordpress.org/reference/classes/wp_widget_recent_posts/update/) `wp-includes/widgets/class-wp-widget-recent-posts.php` | Handles updating the settings for the current Recent Posts widget instance. |
| [WP\_Widget\_Categories::update()](https://developer.wordpress.org/reference/classes/wp_widget_categories/update/) `wp-includes/widgets/class-wp-widget-categories.php` | Handles updating settings for the current Categories widget instance. |
| [WP\_Widget\_Calendar::update()](https://developer.wordpress.org/reference/classes/wp_widget_calendar/update/) `wp-includes/widgets/class-wp-widget-calendar.php` | Handles updating settings for the current Calendar widget instance. |
| [WP\_Widget\_Text::update()](https://developer.wordpress.org/reference/classes/wp_widget_text/update/) `wp-includes/widgets/class-wp-widget-text.php` | Handles updating settings for the current Text widget instance. |
| [WP\_Widget\_Archives::update()](https://developer.wordpress.org/reference/classes/wp_widget_archives/update/) `wp-includes/widgets/class-wp-widget-archives.php` | Handles updating settings for the current Archives widget instance. |
| [WP\_Widget\_Meta::update()](https://developer.wordpress.org/reference/classes/wp_widget_meta/update/) `wp-includes/widgets/class-wp-widget-meta.php` | Handles updating settings for the current Meta widget instance. |
| [WP\_Widget\_Search::update()](https://developer.wordpress.org/reference/classes/wp_widget_search/update/) `wp-includes/widgets/class-wp-widget-search.php` | Handles updating settings for the current Search widget instance. |
| [WP\_Widget\_Pages::update()](https://developer.wordpress.org/reference/classes/wp_widget_pages/update/) `wp-includes/widgets/class-wp-widget-pages.php` | Handles updating settings for the current Pages widget instance. |
| [register\_new\_user()](https://developer.wordpress.org/reference/functions/register_new_user/) `wp-includes/user.php` | Handles registering a new user. |
| [wp\_page\_menu()](https://developer.wordpress.org/reference/functions/wp_page_menu/) `wp-includes/post-template.php` | Displays or retrieves a list of pages with an optional home link. |

[Show 46 more](https://developer.wordpress.org/reference/functions/sanitize_text_field/#) [Show less](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)

## [Changelog](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#changelog)

| Version | Description |
| --- | --- |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/sanitize_text_field/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-content-5204)



This function is not for protecting against SQL injection, so please don’t use it in your database queries. In most cases using [https://developer.wordpress.org/reference/classes/wpdb/prepare/](https://developer.wordpress.org/reference/classes/wpdb/prepare/) with placeholders is best for database queries.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F%3Freplytocom%3D5204%23feedback-editor-5204)

2. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-content-5504)



Sanitize an array





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)




```php
map_deep( $form_data, 'sanitize_text_field' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F%3Freplytocom%3D5504%23feedback-editor-5504)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-content-4353)



Check whether the string is a valid UTF-8 character, and remove all HTML tags.





`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)




```php
$str = "<h2>Title</h2>";
sanitize_text_field( $str ); // it will return "title" without any HTML tags!
```







[Show feedback (1)](https://developer.wordpress.org/reference/functions/sanitize_text_field/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F%3Freplytocom%3D4353%23feedback-editor-4353)



- This will not convert text string to lower case as stated in your comment ” it will return ‘title’ without any HTML tags!” make it “it will return ‘Title’ without any HTML tags!’



[bharatthapa](https://profiles.wordpress.org/bharatthapa/) [4 years ago](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-5297)


4. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-content-4419)



I ran across an issue with one of my plugins, as it was going through the initial security review, where I had an array that wasn’t passing a security check. The [sanitize\_text\_field()](https://developer.wordpress.org/reference/functions/sanitize_text_field/) function only works on a string, not an array’d item.



I located this nice little tidbit of code to sanitize an array, properly.





`wp-includes/formatting.php`
[Expand code](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)

[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)




```php
/***
    * To ensure arrays are properly sanitized to WordPress Codex standards,
    * they encourage usage of sanitize_text_field(). That only works with a single
    * variable (string). This function allows for a full blown array to get sanitized
    * properly, while sanitizing each individual value in a key -> value pair.
    *
    * Source: https://wordpress.stackexchange.com/questions/24736/wordpress-sanitize-array
    * Author: Broshi, answered Feb 5 '17 at 9:14
    */
function wporg_recursive_sanitize_text_field( $array ) {
   	foreach ( $array as $key => &$value ) {
   		if ( is_array( $value ) ) {
   			$value = wporg_recursive_sanitize_text_field( $value );
   		} else {
   			$value = sanitize_text_field( $value );
   		}
   	}
   	return $array;
}
```





IMHO, this needs to become a core feature of WordPress’ sanitation functions. Lior Broshi is the gentleman that came up with this creative solution (I have obtained his permission to share this).





[Show feedback (2)](https://developer.wordpress.org/reference/functions/sanitize_text_field/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F%3Freplytocom%3D4419%23feedback-editor-4419)



- Sanitize an array







`wp-includes/formatting.php`
[Copy](https://developer.wordpress.org/reference/functions/sanitize_text_field/#)




```php
map_deep( $form_data, 'sanitize_text_field' );
```







[bhvreddy](https://profiles.wordpress.org/bhvreddy/) [4 years ago](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-5503)

- We handle this by using the array\_map, it gets a bit tricky if the array contains various field types (text fields, emails etc) but it can be done using: `$sanitized_array = array_map( 'sanitize_text_field', $array );`



[Andrew Lima](https://profiles.wordpress.org/andrewza/) [12 months ago](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-7200)


5. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/sanitize_text_field/#comment-content-7360)



`
$unsafe_input = 'alert("XSS")hello';
$safe_input = sanitize_text_field($unsafe_input);
echo $safe_input; // Output: hello
`



Use [sanitize\_text\_field()](https://developer.wordpress.org/reference/functions/sanitize_text_field/) when:


(1) You’re handling free-form user input from forms, URLs, or APIs.


(2) The value will be stored in the database, output in HTML, or used in queries.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F%3Freplytocom%3D7360%23feedback-editor-7360)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fsanitize_text_field%2F) before being able to contribute a note or feedback.

Notifications