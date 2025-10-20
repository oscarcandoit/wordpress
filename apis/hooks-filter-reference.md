---
url: https://developer.wordpress.org/apis/hooks/filter-reference
scraped_at: 2025-10-20T04:10:38.604Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/hooks/filter-reference/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Filter Reference


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Hooks](https://developer.wordpress.org/apis/hooks/)Filter Reference

Search

# Filter Reference

## In this article

Table of Contents

- [Post, Page, and Attachment (Upload) Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#post-page-and-attachment-upload-filters)
  - [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/#database-reads)
  - [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/#database-writes)
- [Comment, Trackback, and Ping Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#comment-trackback-and-ping-filters)
  - [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/#database-reads-2)
  - [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/#database-writes-2)
- [Category and Term Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#category-and-term-filters)
  - [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/#database-reads-3)
  - [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/#database-writes-3)
- [Link Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#link-filters)
- [Date and Time Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#date-and-time-filters)
- [Author and User Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#author-and-user-filters)
  - [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/#database-reads-4)
  - [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/#database-writes-4)
- [Blogroll Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#blogroll-filters)
- [Blog Information and Option Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#blog-information-and-option-filters)
- [General Text Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#general-text-filters)
- [Administrative Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#administrative-filters)
- [Rich Text Editor Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#rich-text-editor-filters)
- [Template Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#template-filters)
  - [Kubrick Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#kubrick-filters)
- [Registration & Login Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#registration-login-filters)
- [Redirect/Rewrite Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#redirect-rewrite-filters)
- [WP\_Query Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#wp_query-filters)
- [Media Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#media-filters)
- [Advanced WordPress Filters](https://developer.wordpress.org/apis/hooks/filter-reference/#advanced-wordpress-filters)
- [Widgets](https://developer.wordpress.org/apis/hooks/filter-reference/#widgets)
- [Admin Bar](https://developer.wordpress.org/apis/hooks/filter-reference/#admin-bar)
- [Further Reading](https://developer.wordpress.org/apis/hooks/filter-reference/#further-reading)

[↑ Back to top](https://developer.wordpress.org/apis/hooks/filter-reference/#wp--skip-link--target)

This article contains an extensive (but not 100% comprehensive) list of the filter hooks available for use in plugin development in Version 2.1 and above of WordPress. For more information:

- To learn more about what filter and action hooks are, see [Plugin API](https://developer.wordpress.org/themes/advanced-topics/plugin-api-hooks/).
- To learn about writing plugins in general, see [Writing a Plugin](https://developer.wordpress.org/plugins/intro/).
- For a reference list of action hooks, see [Plugin API/Action Reference](https://developer.wordpress.org/apis/hooks/action-reference/).
- For an automatically-generated list of _all_ WordPress hooks, see the [WordPress Hooks Database](https://developer.wordpress.org/reference/hooks/)

Note: If you want to add to or clarify this documentation, please follow the style of the existing entries. Describe what data the filter is applied to, and if the filter function takes additional arguments, describe the argument list.

## [Post, Page, and Attachment (Upload) Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#post-page-and-attachment-upload-filters)

See also [#Category and Term Filters](https://developer.wordpress.org/#Category_and_Term_Filters), [#Author and User Filters](https://developer.wordpress.org/#Author_and_User_Filters), [#Link Filters](https://developer.wordpress.org/#Link_Filters), [#Date and Time Filters](https://developer.wordpress.org/#Date_and_Time_Filters), and [#Administrative Filters](https://developer.wordpress.org/#Administrative_Filters) below.

### [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-reads)

Filters in this section are applied to information read from the

database, prior to displaying on a page or editing screen.

[attachment\_fields\_to\_edit](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/) : applied to the form fields to be displayed when editing an attachment. Called in the `get_attachment_fields_to_edit` function. Filter function arguments: an array of form fields, the post object.

[attachment\_icon](https://developer.wordpress.org/reference/hooks/attachment_icon/) : applied to the icon for an attachment in the `get_attachment_icon` function. Filter function arguments: icon file as an HTML IMG tag, attachment ID.

[attachment\_innerHTML](https://developer.wordpress.org/reference/hooks/attachment_innerHTML/) : applied to the title to be used for an attachment if there is no icon, in the `get_attachment_innerHTML` function. Filter function arguments: inner HTML (defaults to the title), attachment ID.

[author\_edit\_pre](https://developer.wordpress.org/reference/hooks/author_edit_pre/) : applied to post author prior to display for editing.

[body\_class](https://developer.wordpress.org/reference/hooks/body_class/) : applied to the classes for the HTML

[content\_edit\_pre](https://developer.wordpress.org/reference/hooks/content_edit_pre/) : applied to post content prior to display for editing.

[content\_filtered\_edit\_pre](https://developer.wordpress.org/reference/hooks/content_filtered_edit_pre/) : applied to post content filtered prior to display for editing.

[excerpt\_edit\_pre](https://developer.wordpress.org/reference/hooks/excerpt_edit_pre/) : applied to post excerpt prior to display for editing.

[date\_edit\_pre](https://developer.wordpress.org/reference/hooks/date_edit_pre/) : applied to post date prior to display for editing.

[date\_gmt\_edit\_pre](https://developer.wordpress.org/reference/hooks/date_gmt_edit_pre/) : applied to post date prior to display for editing.

[get\_attached\_file](https://developer.wordpress.org/reference/hooks/get_attached_file/) : applied to the attached file information retrieved by the `get_attached_file` function. Filter function arguments: file information, attachment ID.

[get\_enclosed](https://developer.wordpress.org/reference/hooks/get_enclosed/) : applied to the enclosures list for a post by the `get_enclosed` function.

[get\_pages](https://developer.wordpress.org/reference/hooks/get_pages/) : applied to the list of pages returned by the [`get_pages` function](https://developer.wordpress.org/reference/functions/get_pages/). Filter function arguments: list of pages (each item of which contains a page data array), `get_pages` function argument list (telling which pages were requested).

[get\_pung](https://developer.wordpress.org/reference/hooks/get_pung/) : applied to the list of pinged URLs for a post by the `get_pung` function.

[get\_the\_archive\_title](https://developer.wordpress.org/reference/hooks/get_the_archive_title/) : applied to the archive’s title in the `get_the_archive_title` function.

[get\_the\_excerpt](https://developer.wordpress.org/reference/hooks/get_the_excerpt/) : applied to the post’s excerpt in the `get_the_excerpt` function.

[get\_the\_guid](https://developer.wordpress.org/reference/hooks/get_the_guid/) : applied to the post’s GUID in the `get_the_guid` function.

[get\_to\_ping](https://developer.wordpress.org/reference/hooks/get_to_ping/) : applied to the list of URLs to ping for a post by the `get_to_ping` function.

[icon\_dir](https://developer.wordpress.org/reference/hooks/icon_dir/) : applied to the template’s image directory in several functions. Basically allows a plugin to specify that icons for MIME types should come from a different location.

[icon\_dir\_uri](https://developer.wordpress.org/reference/hooks/icon_dir_uri/) : applied to the template’s image directory URI in several functions. Basically allows a plugin to specify that icons for MIME types should come from a different location.

[image\_size\_names\_choose](https://developer.wordpress.org/reference/hooks/image_size_names_choose/) : applied to the list of image sizes selectable in the Media Library. Commonly used to make [custom image sizes](https://developer.wordpress.org/reference/functions/add_image_size/) selectable.

[mime\_type\_edit\_pre](https://developer.wordpress.org/reference/hooks/mime_type_edit_pre/) : applied to post mime type prior to display for editing.

[modified\_edit\_pre](https://developer.wordpress.org/reference/hooks/modified_edit_pre/) : applied to post modification date prior to display for editing.

[modified\_gmt\_edit\_pre](https://developer.wordpress.org/reference/hooks/modified_gmt_edit_pre/) : applied to post modification gmt date prior to display for editing.

[no\_texturize\_shortcodes](https://developer.wordpress.org/reference/hooks/no_texturize_shortcodes/) : applied to registered shortcodes. Can be used to exempt shortcodes from the automatic texturize function.

[parent\_edit\_pre](https://developer.wordpress.org/reference/hooks/parent_edit_pre/) : applied to post parent id prior to display for editing.

[password\_edit\_pre](https://developer.wordpress.org/reference/hooks/password_edit_pre/) : applied to post password prior to display for editing.

[post\_class](https://developer.wordpress.org/reference/hooks/post_class/) : applied to the classes of the outermost HTML element for a post. Called in the [`get_post_class`](https://developer.wordpress.org/reference/functions/get_post_class/) function. Filter function arguments: an array of class names, an array of additional class names that were added to the first array, and the post ID.

[pre\_kses](https://developer.wordpress.org/reference/hooks/pre_kses/) : applied to various content prior to being processed/sanitized by KSES. This hook allows developers to customize what types of scripts/tags should either be allowed in content or stripped.

[prepend\_attachment](https://developer.wordpress.org/reference/hooks/prepend_attachment/) : applied to the HTML to be prepended by the `prepend_attachment` function.

[protected\_title\_format](https://developer.wordpress.org/reference/hooks/protected_title_format/) : Used to the change or manipulate the post title when the post is password protected.

[private\_title\_format](https://developer.wordpress.org/reference/hooks/private_title_format/) : Used to the change or manipulate the post title when its status is private.

[sanitize\_title](https://developer.wordpress.org/reference/hooks/sanitize_title/) : applied to a post title by the `sanitize_title` function, after stripping out HTML tags.

[single\_post\_title](https://developer.wordpress.org/reference/hooks/single_post_title/) : applied to the post title when used to create a blog page title by the `wp_title` and `single_post_title` functions.

[status\_edit\_pre](https://developer.wordpress.org/reference/hooks/status_edit_pre/) : applied to post status prior to display for editing.

[the\_content](https://developer.wordpress.org/reference/hooks/the_content/) : applied to the post content retrieved from the database, prior to printing on the screen (also used in some other operations, such as trackbacks).

[the\_content\_rss](https://developer.wordpress.org/reference/hooks/the_content_rss/) : applied to the post content prior to including in an RSS feed. (Deprecated)

[the\_content\_feed](https://developer.wordpress.org/reference/hooks/the_content_feed/) : applied to the post content prior to including in an RSS feed.

[the\_editor\_content](https://developer.wordpress.org/reference/hooks/the_editor_content/) : applied to post content before putting it into a rich editor window.

[the\_excerpt](https://developer.wordpress.org/reference/hooks/the_excerpt/) : applied to the post excerpt (or post content, if there is no excerpt) retrieved from the database, prior to printing on the screen (also used in some other operations, such as trackbacks).

[the\_excerpt\_rss](https://developer.wordpress.org/reference/hooks/the_excerpt_rss/) : applied to the post excerpt prior to including in an RSS feed.

[the\_password\_form](https://developer.wordpress.org/reference/hooks/the_password_form/) : applied to the password form for protected posts.

[the\_tags](https://developer.wordpress.org/reference/hooks/the_tags/) : applied to the tags retrieved from the database, prior to printing on the screen.

[the\_title](https://developer.wordpress.org/reference/hooks/the_title/) : applied to the post title retrieved from the database, prior to printing on the screen (also used in some other operations, such as trackbacks).

[the\_title\_rss](https://developer.wordpress.org/reference/hooks/the_title_rss/) : applied to the post title before including in an RSS feed (after first filtering with `the_title`.

[title\_edit\_pre](https://developer.wordpress.org/reference/hooks/title_edit_pre/) : applied to post title prior to display for editing.

[type\_edit\_pre](https://developer.wordpress.org/reference/hooks/type_edit_pre/) : applied to post type prior to display for editing.

[wp\_dropdown\_pages](https://developer.wordpress.org/reference/hooks/wp_dropdown_pages/) : applied to the HTML dropdown list of WordPress pages generated by the `wp_dropdown_pages` function.

[wp\_list\_pages](https://developer.wordpress.org/reference/hooks/wp_list_pages/) : applied to the HTML list generated by the `wp_list_pages` function.

[wp\_list\_pages\_excludes](https://developer.wordpress.org/reference/hooks/wp_list_pages_excludes/) : applied to the list of excluded pages (an array of page IDs) in the `wp_list_pages` function.

[wp\_get\_attachment\_metadata](https://developer.wordpress.org/reference/hooks/wp_get_attachment_metadata/) : applied to the attachment metadata retrieved by the `wp_get_attachment_metadata` function. Filter function arguments: meta data, attachment ID.

[wp\_get\_attachment\_thumb\_file](https://developer.wordpress.org/reference/hooks/wp_get_attachment_thumb_file/) : applied to the attachment thumbnail file retrieved by the `wp_get_attachment_thumb_file` function. Filter function arguments: thumbnail file, attachment ID.

[wp\_get\_attachment\_thumb\_url](https://developer.wordpress.org/reference/hooks/wp_get_attachment_thumb_url/) : applied to the attachment thumbnail URL retrieved by the `wp_get_attachment_thumb_URL` function. Filter function arguments: thumbnail URL, attachment ID.

[wp\_get\_attachment\_url](https://developer.wordpress.org/reference/hooks/wp_get_attachment_url/) : applied to the attachment URL retrieved by the `wp_get_attachment_url` function. Filter function arguments: URL, attachment ID.

[wp\_mime\_type\_icon](https://developer.wordpress.org/reference/hooks/wp_mime_type_icon/) : applied to the MIME type icon for an attachment calculated by the `wp_mime_type_icon` function. Filter function arguments: icon URI calculated, MIME type, post ID.

[wp\_title](https://developer.wordpress.org/reference/hooks/wp_title/) : applied to the blog page title before sending to the browser in the `wp_title` function.

### [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-writes)

Filters in this section are applied to information prior to saving to

the database.

[add\_ping](https://developer.wordpress.org/reference/hooks/add_ping/) : applied to the new value of the pinged field on a post when a ping is added, prior to saving the new information in the database.

[attachment\_fields\_to\_save](https://developer.wordpress.org/reference/hooks/attachment_fields_to_save/) : applied to fields associated with an attachment prior to saving them in the database. Called in the `media_upload_form_handler` function. Filter function arguments: an array of post attributes, an array of attachment fields including the changes submitted from the form.

[attachment\_max\_dims](https://developer.wordpress.org/reference/hooks/attachment_max_dims/) : applied to the maximum image dimensions before reducing an image size. Filter function input (and return value) is either false (if no maximum dimensions have been specified) or a two-item list (width, height).

[category\_save\_pre](https://developer.wordpress.org/reference/hooks/category_save_pre/) : applied to post category comma-separated list prior to saving it in the database (also used for attachments).

[comment\_status\_pre](https://developer.wordpress.org/reference/hooks/comment_status_pre/) : applied to post comment status prior to saving it in the database (also used for attachments).

[content\_filtered\_save\_pre](https://developer.wordpress.org/reference/hooks/content_filtered_save_pre/) : applied to filtered post content prior to saving it in the database (also used for attachments).

[content\_save\_pre](https://developer.wordpress.org/reference/hooks/content_save_pre/) : applied to post content prior to saving it in the database (also used for attachments).

[excerpt\_save\_pre](https://developer.wordpress.org/reference/hooks/excerpt_save_pre/) : applied to post excerpt prior to saving it in the database (also used for attachments).

[image\_save\_pre](https://developer.wordpress.org/reference/hooks/image_save_pre/) (deprecated) : use [`image_editor_save_pre`](https://developer.wordpress.org/reference/hooks/image_editor_sav_pre/) instead.

[jpeg\_quality](https://developer.wordpress.org/reference/hooks/jpeg_quality/) (deprecated) : use [`wp_editor_set_quality`](https://developer.wordpress.org/reference/hooks/wp_editor_set_quality/) or `WP_Image_Editor::set_quality()` instead.

[name\_save\_pre](https://developer.wordpress.org/reference/hooks/name_save_pre/) (Deprecated): applied to post name prior to saving it in the database (also used for attachments).

[phone\_content](https://developer.wordpress.org/reference/hooks/phone_content/) : applied to the content of a post submitted by email, before saving.

[ping\_status\_pre](https://developer.wordpress.org/reference/hooks/ping_status_pre/) : applied to post ping status prior to saving it in the database (also used for attachments).

[post\_mime\_type\_pre](https://developer.wordpress.org/reference/hooks/post_mime_type_pre/) : applied to the MIME type for an attachment prior to saving it in the database.

[status\_save\_pre](https://developer.wordpress.org/reference/hooks/status_save_pre/) : applied to post status prior to saving it in the database.

[thumbnail\_filename](https://developer.wordpress.org/reference/hooks/thumbnail_filename/) : applied to the file name for the thumbnail when uploading an image.

[title\_save\_pre](https://developer.wordpress.org/reference/hooks/title_save_pre/) : applied to post title prior to saving it in the database (also used for attachments).

[update\_attached\_file](https://developer.wordpress.org/reference/hooks/update_attached_file/) : applied to the attachment information prior to saving in post metadata in the `update_attached_file` function. Filter function arguments: attachment information, attachment ID.

[wp\_create\_thumbnail](https://developer.wordpress.org/reference/hooks/wp_create_thumbnail/) (deprecated)

[wp\_delete\_file](https://developer.wordpress.org/reference/hooks/wp_delete_file/) : applied to an attachment file name just before deleting.

[wp\_generate\_attachment\_metadata](https://developer.wordpress.org/reference/hooks/wp_generate_attachment_metadata/) : applied to the attachment metadata array before saving in the database.

[wp\_save\_image\_file](https://developer.wordpress.org/reference/hooks/wp_save_image_file/) (deprecated) : use [`wp_save_image_editor_file`](https://developer.wordpress.org/reference/hooks/wp_save_image_editor_file/) instead.

[wp\_thumbnail\_creation\_size\_limit](https://developer.wordpress.org/reference/hooks/wp_thumbnail_creation_size_limit/) : applied to the size of the thumbnail when uploading an image. Filter function arguments: max file size, attachment ID, attachment file name.

[wp\_thumbnail\_max\_side\_length](https://developer.wordpress.org/reference/hooks/wp_thumbnail_max_side_length/) : applied to the size of the thumbnail when uploading an image. Filter function arguments: image side max size, attachment ID, attachment file name.

[wp\_update\_attachment\_metadata](https://developer.wordpress.org/reference/hooks/wp_update_attachment_metadata/) : applied to the attachment metadata just before saving in the `wp_update_attachment_metadata` function. Filter function arguments: meta data, attachment ID.

## [Comment, Trackback, and Ping Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#comment-trackback-and-ping-filters)

See also [#Author and User Filters](https://developer.wordpress.org/#Author_and_User_Filters), [#Link Filters](https://developer.wordpress.org/#Link_Filters), [#Date and Time Filters](https://developer.wordpress.org/#Date_and_Time_Filters), and [#Administrative Filters](https://developer.wordpress.org/#Administrative_Filters) below.

### [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-reads-2)

Filters in this section are applied to information read from the

database, prior to displaying on a page or editing screen.

[comment\_excerpt](https://developer.wordpress.org/reference/hooks/comment_excerpt/) : applied to the comment excerpt by the `comment_excerpt` function. See also `get_comment_excerpt`.

[comment\_flood\_filter](https://developer.wordpress.org/reference/hooks/comment_flood_filter/) : applied when someone appears to be flooding your blog with comments. Filter function arguments: already blocked (true/false, whether a previous filtering plugin has already blocked it; set to true and return true to block this comment in a plugin), time of previous comment, time of current comment.

[comment\_post\_redirect](https://developer.wordpress.org/reference/hooks/comment_post_redirect/) : applied to the redirect location after someone adds a comment. Filter function arguments: redirect location, comment info array.

[comment\_text](https://developer.wordpress.org/reference/hooks/comment_text/) : applied to the comment text before displaying on the screen by the `comment_text` function, and in the admin menus.

[comment\_text\_rss](https://developer.wordpress.org/reference/hooks/comment_text_rss/) : applied to the comment text prior to including in an RSS feed.

[comments\_array](https://developer.wordpress.org/reference/hooks/comments_array/) : applied to the array of comments for a post in the `comments_template` function. Filter function arguments: array of comment information structures, post ID.

[comments\_number](https://developer.wordpress.org/reference/hooks/comments_number/) : applied to the formatted text giving the number of comments generated by the `comments_number` function. See also `get_comments_number`.

[get\_comment\_excerpt](https://developer.wordpress.org/reference/hooks/get_comment_excerpt/) : applied to the comment excerpt read from the database by the `get_comment_excerpt` function (which is also called by `comment_excerpt`. See also `comment_excerpt`.

[get\_comment\_ID](https://developer.wordpress.org/reference/hooks/get_comment_ID/) : applied to the comment ID read from the global `$comments` variable by the `get_comment_ID` function.

[get\_comment\_text](https://developer.wordpress.org/reference/hooks/get_comment_text/) : applied to the comment text of the current comment in the `get_comment_text` function, which is also called by the `comment_text` function.

[get\_comment\_type](https://developer.wordpress.org/reference/hooks/get_comment_type/) : applied to the comment type (“comment”, “trackback”, or “pingback”) by the `get_comment_type` function (which is also called by `comment_type`).

[get\_comments\_number](https://developer.wordpress.org/reference/hooks/get_comments_number/) : applied to the comment count read from the `$post` global variable by the `get_comments_number` function (which is also called by the `comments_number` function; see also `comments_number` filter).

[post\_comments\_feed\_link](https://developer.wordpress.org/reference/hooks/post_comments_feed_link/) : applied to the feed URL generated for the comments feed by the `comments_rss` function.

### [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-writes-2)

Filters in this section are applied to information prior to saving to

the database.

[comment\_save\_pre](https://developer.wordpress.org/reference/hooks/comment_save_pre/) : applied to the comment data just prior to updating/editing comment data. Function arguments: comment data array, with indices “comment\_post\_ID”, “comment\_author”, “comment\_author\_email”, “comment\_author\_url”, “comment\_content”, “comment\_type”, and “user\_ID”.

[pre\_comment\_approved](https://developer.wordpress.org/reference/hooks/pre_comment_approved/) : applied to the current comment’s approval status (true/false) to allow a plugin to override. Return true/false and set first argument to true/false to approve/disapprove the comment, and use global variables such as `$comment_ID` to access information about this comment.

[pre\_comment\_content](https://developer.wordpress.org/reference/hooks/pre_comment_content/) : applied to the content of a comment prior to saving the comment in the database.

[preprocess\_comment](https://developer.wordpress.org/reference/hooks/preprocess_comment/) : applied to the comment data prior to any other processing, when saving a new comment in the database. Function arguments: comment data array, with indices “comment\_post\_ID”, “comment\_author”, “comment\_author\_email”, “comment\_author\_url”, “comment\_content”, “comment\_type”, and “user\_ID”.

[wp\_insert\_post\_data](https://developer.wordpress.org/reference/hooks/wp_insert_post_data/) : applied to modified and unmodified post data in [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) prior to update or insertion of post into database. Function arguments: modified and extended post array and sanitized post array.

## [Category and Term Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#category-and-term-filters)

See also [#Administrative Filters](https://developer.wordpress.org/#Administrative_Filters)

below.

### [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-reads-3)

Filters in this section are applied to information read from the

database, prior to displaying on a page or editing screen.

[category\_description](https://developer.wordpress.org/reference/hooks/category_description/) : applied to the “description” field categories by the `category_description` and [`wp_list_categories`](https://developer.wordpress.org/reference/functions/wp_list_categories/) functions. Filter function arguments: description, category ID when called from `category_description`; description, category information array (all fields from the category table for that particular category) when called from [`wp_list_categories`](https://developer.wordpress.org/reference/functions/wp_list_categories/).

[category\_feed\_link](https://developer.wordpress.org/reference/hooks/category_feed_link/) : applied to the feed URL generated for the category feed by the [`get_category_feed_link`](https://developer.wordpress.org/reference/functions/get_category_feed_link/) function.

[category\_link](https://developer.wordpress.org/reference/hooks/category_link/) : applied to the URL created for a category by the [`get_category_link`](https://developer.wordpress.org/reference/functions/get_category_link/) function. Filter function arguments: link URL, category ID.

[get\_ancestors](https://developer.wordpress.org/reference/hooks/get_ancestors/) : applied to the list of ancestor IDs returned by the [`get_ancestors`](https://developer.wordpress.org/reference/functions/get_ancestors/) function (which is in turn used by many other functions). Filter function arguments: ancestor IDs array, given object ID, given object type.

[get\_categories](https://developer.wordpress.org/reference/hooks/get_categories/) : applied to the category list generated by the [`get_categories`](https://developer.wordpress.org/reference/functions/get_categories/) function (which is in turn used by many other functions). Filter function arguments: category list, [`get_categories`](https://developer.wordpress.org/reference/functions/get_categories/) options list.

[get\_category](https://developer.wordpress.org/reference/hooks/get_category/) : applied to the category information that the [`get_category`](https://developer.wordpress.org/reference/functions/get_category/) function looks up, which is basically an array of all the fields in WordPress’s category table for a particular category ID.

[list\_cats](https://developer.wordpress.org/reference/hooks/list_cats/) : called for two different purposes:

1. the

[`wp_dropdown_categories`](https://developer.wordpress.org/reference/functions/wp_dropdown_categories/)

function uses it to filter the `show_option_all` and

`show_option_none` arguments (which are used to put options “All”

and “None” in category drop-down lists). No additional filter

function arguments.
2. the

[`wp_list_categories`](https://developer.wordpress.org/reference/functions/wp_list_categories/)

function applies it to the category names. Filter function

arguments: category name, category information list (all fields from

the category table for that particular category).

[list\_cats\_exclusions](https://developer.wordpress.org/reference/hooks/list_cats_exclusions/) : applied to the SQL WHERE statement giving the categories to be excluded by the [`get_categories`](https://developer.wordpress.org/reference/functions/get_categories/) function. Typically, a plugin would add to this list, in order to exclude certain categories or groups of categories from category lists. Filter function arguments: excluded category WHERE clause, [`get_categories`](https://developer.wordpress.org/reference/functions/get_categories/) options list.

[single\_cat\_title](https://developer.wordpress.org/reference/hooks/single_cat_title/) : applied to the category name when used to create a blog page title by the [`wp_title`](https://developer.wordpress.org/reference/functions/wp_title/) and [`single_cat_title`](https://developer.wordpress.org/reference/functions/single_cat_title/) functions.

[the\_category](https://developer.wordpress.org/reference/hooks/the_category/) : applied to the list of categories (an HTML list with links) created by the `get_the_category_list` function. Filter function arguments: generated HTML text, list separator being used (empty string means it is a default LI list), `parents` argument to `get_the_category_list`.

[the\_category\_rss](https://developer.wordpress.org/reference/hooks/the_category_rss/) : applied to the category list (a list of category XML elements) for a post by the [`get_the_category_rss`](https://developer.wordpress.org/reference/functions/get_the_category_rss/) function, before including in an RSS feed. Filter function arguments are the list text and the type (“rdf” or “rss” generally).

[wp\_dropdown\_cats](https://developer.wordpress.org/reference/hooks/wp_dropdown_cats/) : applied to the drop-down category list (a text string containing HTML option elements) generated by the [`wp_dropdown_categories`](https://developer.wordpress.org/reference/functions/wp_dropdown_categories/) function.

[wp\_list\_categories](https://developer.wordpress.org/reference/hooks/wp_list_categories/) : applied to the category list (an HTML list) generated by the [`wp_list_categories`](https://developer.wordpress.org/reference/functions/wp_list_categories/) function.

[wp\_get\_object\_terms](https://developer.wordpress.org/reference/functions/wp_get_object_terms/) : applied to the list of terms (an array of objects) generated by the [`wp_get_object_terms`](https://developer.wordpress.org/reference/functions/wp_get_object_terms/) function, which is called by a number of category/term related functions, such as [`get_the_terms`](https://developer.wordpress.org/reference/functions/get_the_terms/) and [`get_the_category`](https://developer.wordpress.org/reference/functions/get_the_category/).

### [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-writes-3)

Filters in this section are applied to information prior to saving to

the database.

[pre\_category\_description](https://developer.wordpress.org/reference/hooks/pre_category_description/) : applied to the category desription prior to saving in the database.

[wp\_update\_term\_parent](https://developer.wordpress.org/reference/hooks/wp_update_term_parent/) : filter term parent before update to term is applied, hook to this filter to see if it will cause a hierarchy loop.

[edit\_terms](https://developer.wordpress.org/reference/hooks/edit_terms/) : (actually an action, but often used like a filter) hooked in prior to saving taxonomy/category change in the database

[pre\_category\_name](https://developer.wordpress.org/reference/hooks/pre_category_name/) : applied to the category name prior to saving in the database.

[pre\_category\_nicename](https://developer.wordpress.org/reference/hooks/pre_category_nicename/) : applied to the category nice name prior to saving in the database.

## [Link Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#link-filters)

Note: This section contains filters related to links to posts, pages,

archives, feeds, etc. For blogroll links, see the [#Blogroll Filters](https://developer.wordpress.org/#Blogroll_Filters) section below.

[attachment\_link](https://developer.wordpress.org/reference/hooks/attachment_link/) : applied to the calculated attachment permalink by the `get_attachment_link` function. Filter function arguments: link URL, attachment ID.

[author\_feed\_link](https://developer.wordpress.org/reference/hooks/author_feed_link/) : applied to the feed URL generated for the author feed by the `get_author_rss_link` function.

[author\_link](https://developer.wordpress.org/reference/hooks/author_link/) : applied to the author’s archive permalink created by the `get_author_posts_url` function. Filter function arguments: link URL, author ID, author’s “nice” name. Note that `get_author_posts_url` is called within functions `wp_list_authors` and `the_author_posts_link`.

[comment\_reply\_link](https://developer.wordpress.org/reference/hooks/comment_reply_link/) : applied to the link generated for replying to a specific comment by the `get_comment_reply_link` function which is called within function `comments_template`. Filter function arguments: link (string), custom options (array), current comment (object), current post (object).

[day\_link](https://developer.wordpress.org/reference/hooks/day_link/) : applied to the link URL for a daily archive by the `get_day_link` function. Filter function arguments: URL, year, month number, day number.

[feed\_link](https://developer.wordpress.org/reference/hooks/feed_link/) : applied to the link URL for a feed by the `get_feed_link` function. Filter function arguments: URL, type of feed (e.g. “rss2”, “atom”, etc.).

[get\_comment\_author\_link](https://developer.wordpress.org/reference/hooks/get_comment_author_link/) : applied to the HTML generated for the author’s link on a comment, in the `get_comment_author_link` function (which is also called by `comment_author_link`. Action function arguments: user name

[get\_comment\_author\_url\_link](https://developer.wordpress.org/reference/hooks/get_comment_author_url_link/) : applied to the HTML generated for the author’s link on a comment, in the `get_comment_author_url_link` function (which is also called by `comment_author_link`).

[month\_link](https://developer.wordpress.org/reference/hooks/month_link/) : applied to the link URL for a monthly archive by the `get_month_link` function. Filter function arguments: URL, year, month number.

[page\_link](https://developer.wordpress.org/reference/hooks/page_link/) : applied to the calculated page URL by the `get_page_link` function. Filter function arguments: URL, page ID. Note that there is also an internal filter called `_get_page_link` that can be used to filter the URLS of pages that are not designated as the blog’s home page (same arguments). Note that this only applies to WordPress pages, not posts, custom post types, or attachments.

[post\_link](https://developer.wordpress.org/reference/hooks/post_link/) : applied to the calculated post permalink by the `get_permalink` function, which is also called by the `the_permalink`, `post_permalink`, `previous_post_link`, and `next_post_link` functions. Filter function arguments: permalink URL, post data list. Note that this only applies to WordPress default posts, and not custom post types (nor pages or attachments).

[post\_type\_link](https://developer.wordpress.org/reference/hooks/post_type_link/) : applied to the calculated custom post type permalink by the `get_post_permalink` function.

[the\_permalink](https://developer.wordpress.org/reference/hooks/the_permalink/) : applied to the permalink URL for a post prior to printing by function `the_permalink`.

[year\_link](https://developer.wordpress.org/reference/hooks/year_link/) : applied to the link URL for a yearly archive by the `get_year_link` function. Filter function arguments: URL, year.

[tag\_link](https://developer.wordpress.org/reference/hooks/tag_link/) : applied to the URL created for a tag by the get\_tag\_link function. Filter function arguments: link URL, tag ID.

[term\_link](https://developer.wordpress.org/reference/hooks/term_link/) : applied to the URL created for a term by the get\_term\_link function. Filter function arguments: term link URL, term object and taxonomy slug.

## [Date and Time Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#date-and-time-filters)

See also [#Link Filters](https://developer.wordpress.org/#Link_Filters) above.

[get\_comment\_date](https://developer.wordpress.org/reference/hooks/get_comment_date/) : applied to the formatted comment date generated by the `get_comment_date` function (which is also called by `comment_date`).

[get\_comment\_time](https://developer.wordpress.org/reference/hooks/get_comment_time/) : applied to the formatted comment time in the `get_comment_time` function (which is also called by `comment_time`).

[get\_the\_modified\_date](https://developer.wordpress.org/reference/hooks/get_the_modified_date/) : applied to the formatted post modification date generated by the `get_the_modified_date` function (which is also called by the `the_modified_date` function).

[get\_the\_modified\_time](https://developer.wordpress.org/reference/hooks/get_the_modified_time/) : applied to the formatted post modification time generated by the `get_the_modified_time` and `get_post_modified_time` functions (which are also called by the `the_modified_time` function).

[get\_the\_time](https://developer.wordpress.org/reference/hooks/get_the_time/) : applied to the formatted post time generated by the `get_the_time` and `get_post_time` functions (which are also called by the `the_time` function).

[the\_date](https://developer.wordpress.org/reference/hooks/the_date/) : applied to the formatted post date generated by the `the_date` function.

[the\_modified\_date](https://developer.wordpress.org/reference/hooks/the_modified_date/) : applied to the formatted post modification date generated by the `the_modified_date` function.

[the\_modified\_time](https://developer.wordpress.org/reference/hooks/the_modified_time/) : applied to the formatted post modification time generated by the `the_modified_time` function.

[the\_time](https://developer.wordpress.org/reference/hooks/the_time/) : applied to the formatted post time generated by the `the_time` function.

[the\_weekday](https://developer.wordpress.org/reference/hooks/the_weekday/) : applied to the post date weekday name generated by the `the_weekday` function.

[the\_weekday\_date](https://developer.wordpress.org/reference/hooks/the_weekday_date/) : applied to the post date weekday name generated by the `the_weekday_date` function. Function arguments are the weekday name, before text, and after text (before text and after text are added to the weekday name if the current post’s weekday is different from the previous post’s weekday).

## [Author and User Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#author-and-user-filters)

See also [#Link Filters](https://developer.wordpress.org/#Link_Filters) and [#Administrative Filters](https://developer.wordpress.org/#Administrative_Filters) sections.

[login\_body\_class](https://developer.wordpress.org/reference/hooks/login_body_class/) : Allows filtering of the body class applied to the login screen in [`login_header()`](https://developer.wordpress.org/reference/functions/login_header/).

[login\_redirect](https://developer.wordpress.org/reference/hooks/login_redirect/) : applied to the `redirect_to` post/get variable during the user login process.

[user\_contactmethods](https://developer.wordpress.org/reference/hooks/user_contactmethods/) : applied to the contact methods fields on the user profile page. (old page is here: [contactmethods](https://developer.wordpress.org/reference/hooks/contactmethods/))

[update\_(meta\_type)\_metadata](https://developer.wordpress.org/reference/hooks/update_(meta_type)_metadata/) : applied before a (user) metadata gets updated.

### [Database Reads](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-reads-4)

Filters in this section are applied to information read from the

database, prior to displaying on a page or editing screen.

[author\_email](https://developer.wordpress.org/reference/hooks/author_email/) : applied to the comment author’s email address retrieved from the database by the `comment_author_email` function. See also `get_comment_author_email`.

[comment\_author](https://developer.wordpress.org/reference/hooks/comment_author/) : applied to the comment author’s name retrieved from the database by the `comment_author` function. See also `get_comment_author`.

[comment\_author\_rss](https://developer.wordpress.org/reference/hooks/comment_author_rss/) : applied to the comment author’s name prior to including in an RSS feed.

[comment\_email](https://developer.wordpress.org/reference/hooks/comment_email/) : applied to the comment author’s email address retrieved from the database by the `comment_author_email_link` function.

[comment\_url](https://developer.wordpress.org/reference/hooks/comment_url/) : applied to the comment author’s URL retrieved from the database by the `comment_author_url` function (see also `get_comment_author_url`).

[get\_comment\_author](https://developer.wordpress.org/reference/hooks/get_comment_author/) : applied to the comment author’s name retrieved from the database by `get_comment_author`, which is also called by `comment_author`. See also `comment_author`.

[get\_comment\_author\_email](https://developer.wordpress.org/reference/hooks/get_comment_author_email/) : applied to the comment author’s email address retrieved from the database by `get_comment_author_email`, which is also called by `comment_author_email`. See also `author_email`.

[get\_comment\_author\_IP](https://developer.wordpress.org/reference/hooks/get_comment_author_IP/) : applied to the comment author’s IP address retrieved from the database by the `get_comment_author_IP` function, which is also called by `comment_author_IP`.

[get\_comment\_author\_url](https://developer.wordpress.org/reference/hooks/get_comment_author_url/) : applied to the comment author’s URL retrieved from the database by the `get_comment_author_url` function, which is also called by `comment_author_url`. See also `comment_url`.

[login\_errors](https://developer.wordpress.org/reference/hooks/login_errors/) : applied to the login error message printed on the login screen.

[login\_headertitle](https://developer.wordpress.org/reference/hooks/login_headertitle/) : applied to the title for the login header URL (Powered by WordPress by default) printed on the login screen.

[login\_headerurl](https://developer.wordpress.org/reference/hooks/login_headerurl/) : applied to the login header URL (points to wordpress.org by default) printed on the login screen.

[login\_message](https://developer.wordpress.org/reference/hooks/login_message/) : applied to the login message printed on the login screen.

[role\_has\_cap](https://developer.wordpress.org/reference/hooks/role_has_cap/) : applied to a role’s capabilities list in the `WP_Role->has_cap` function. Filter function arguments are the capabilities list to be filtered, the capability being questioned, and the role’s name.

[sanitize\_user](https://developer.wordpress.org/reference/hooks/sanitize_user/) : applied to a user name by the `sanitize_user` function. Filter function arguments: user name (after some cleaning up), raw user name, strict (true or false to use strict ASCII or not).

[the\_author](https://developer.wordpress.org/reference/hooks/the_author/) : applied to a post author’s displayed name by the `get_the_author` function, which is also called by the `the_author` function.

[the\_author\_email](https://developer.wordpress.org/reference/hooks/the_author_email/) : applied to a post author’s email address by the `the_author_email` function.

[user\_search\_columns](https://developer.wordpress.org/reference/hooks/user_search_columns/) : applied to the list of columns in the wp\_users table to include in the `WHERE` clause inside [WP\_User\_Query](https://developer.wordpress.org/reference/classes/wp_user_query/).

### [Database Writes](https://developer.wordpress.org/apis/hooks/filter-reference/\#database-writes-4)

Filters in this section are applied to information prior to saving to

the database.

[pre\_comment\_author\_email](https://developer.wordpress.org/reference/hooks/pre_comment_author_email/) : applied to a comment author’s email address prior to saving the comment in the database.

[pre\_comment\_author\_name](https://developer.wordpress.org/reference/hooks/pre_comment_author_name/) : applied to a comment author’s user name prior to saving the comment in the database.

[pre\_comment\_author\_url](https://developer.wordpress.org/reference/hooks/pre_comment_author_url/) : applied to a comment author’s URL prior to saving the comment in the database.

[pre\_comment\_user\_agent](https://developer.wordpress.org/reference/hooks/pre_comment_user_agent/) : applied to the comment author’s user agent prior to saving the comment in the database.

[pre\_comment\_user\_ip](https://developer.wordpress.org/reference/hooks/pre_comment_user_ip/) : applied to the comment author’s IP address prior to saving the comment in the database.

[pre\_user\_id](https://developer.wordpress.org/reference/hooks/pre_user_id/) : applied to the comment author’s user ID prior to saving the comment in the database.

[pre\_user\_description](https://developer.wordpress.org/reference/hooks/pre_user_description/) : applied to the user’s description prior to saving in the database.

[pre\_user\_display\_name](https://developer.wordpress.org/reference/hooks/pre_user_display_name/) : applied to the user’s displayed name prior to saving in the database.

[pre\_user\_email](https://developer.wordpress.org/reference/hooks/pre_user_email/) : applied to the user’s email address prior to saving in the database.

[pre\_user\_first\_name](https://developer.wordpress.org/reference/hooks/pre_user_first_name/) : applied to the user’s first name prior to saving in the database.

[pre\_user\_last\_name](https://developer.wordpress.org/reference/hooks/pre_user_last_name/) : applied to the user’s last name prior to saving in the database.

[pre\_user\_login](https://developer.wordpress.org/reference/hooks/pre_user_login/) : applied to the user’s login name prior to saving in the database.

[pre\_user\_nicename](https://developer.wordpress.org/reference/hooks/pre_user_nicename/) : applied to the user’s “nice name” prior to saving in the database.

[pre\_user\_nickname](https://developer.wordpress.org/reference/hooks/pre_user_nickname/) : applied to the user’s nickname prior to saving in the database.

[pre\_user\_url](https://developer.wordpress.org/reference/hooks/pre_user_url/) : applied to the user’s URL prior to saving in the database.

[registration\_errors](https://developer.wordpress.org/reference/hooks/registration_errors/) : applied to the list of registration errors generated while registering a user for a new account.

[user\_registration\_email](https://developer.wordpress.org/reference/hooks/user_registration_email/) : applied to the user’s email address read from the registration page, prior to trying to register the person as a new user.

[validate\_username](https://developer.wordpress.org/reference/hooks/validate_username/) : applied to the validation result on a new user name. Filter function arguments: valid (true/false), user name being validated.

## [Blogroll Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#blogroll-filters)

Note: This section contains filters related to blogroll links. For

filters related to links to posts, pages, categories, etc., see section

[#Link Filters](https://developer.wordpress.org/#Link_Filters) above.

[get\_bookmarks](https://developer.wordpress.org/reference/hooks/get_bookmarks/) : applied to link/blogroll database query results by the `get_bookmarks` function. Filter function arguments: database query results list, `get_bookmarks` arguments list.

[link\_category](https://developer.wordpress.org/reference/hooks/link_category/) : applied to the link category by the `get_links_list` and `wp_list_bookmarks` functions (as of WordPress 2.2).

[link\_description](https://developer.wordpress.org/reference/hooks/link_description/) : applied to the link description by the `get_links` and `wp_list_bookmarks` functions (as of WordPress 2.2).

[link\_rating](https://developer.wordpress.org/reference/hooks/link_rating/) : applied to the link rating number by the `get_linkrating` function.

[link\_title](https://developer.wordpress.org/reference/hooks/link_title/) : applied to the link title by the `get_links` and `wp_list_bookmarks` functions (as of WordPress 2.2)

[pre\_link\_description](https://developer.wordpress.org/reference/hooks/pre_link_description/) : applied to the link description prior to saving in the database.

[pre\_link\_image](https://developer.wordpress.org/reference/hooks/pre_link_image/) : applied to the link image prior to saving in the database.

[pre\_link\_name](https://developer.wordpress.org/reference/hooks/pre_link_name/) : applied to the link name prior to saving in the database.

[pre\_link\_notes](https://developer.wordpress.org/reference/hooks/pre_link_notes/) : applied to the link notes prior to saving in the database.

[pre\_link\_rel](https://developer.wordpress.org/reference/hooks/pre_link_rel/) : applied to the link relation information prior to saving in the database.

[pre\_link\_rss](https://developer.wordpress.org/reference/hooks/pre_link_rss/) : applied to the link RSS URL prior to saving in the database.

[pre\_link\_target](https://developer.wordpress.org/reference/hooks/pre_link_target/) : applied to the link target information prior to saving in the database.

[pre\_link\_url](https://developer.wordpress.org/reference/hooks/pre_link_url/) : applied to the link URL prior to saving in the database.

## [Blog Information and Option Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#blog-information-and-option-filters)

[all\_options](https://developer.wordpress.org/reference/hooks/all_options/) : applied to the option list retrieved from the database by the `get_alloptions` function.

[all\_plugins](https://developer.wordpress.org/reference/hooks/all_plugins/) : applied to the list of plugins retrieved for display in the plugins list table.

[bloginfo](https://developer.wordpress.org/reference/hooks/bloginfo/) : applied to the blog option information retrieved from the database by the `bloginfo` function, after first retrieving the information with the `get_bloginfo` function. A second argument `$show` gives the name of the bloginfo option that was requested. Note that `bloginfo("url")`, `bloginfo("directory")` and `bloginfo("home")` do _not_ use this filtering function (see `bloginfo_url`).

[bloginfo\_rss](https://developer.wordpress.org/reference/hooks/bloginfo_rss/) : applied to the blog option information by function `get_bloginfo_rss` (which is also called from `bloginfo_rss`), after first retrieving the information with the `get_bloginfo` function, stripping out HTML tags, and converting characters appropriately. A second argument `$show` gives the name of the bloginfo option that was requested.

[bloginfo\_url](https://developer.wordpress.org/reference/hooks/bloginfo_url/) : applied to the the output of `bloginfo("url")`, `bloginfo("directory")` and `bloginfo("home")` before returning the information.

[loginout](https://developer.wordpress.org/reference/hooks/loginout/) : applied to the HTML link for logging in and out (generally placed in the sidebar) generated by the `wp_loginout` function.

[lostpassword\_url](https://developer.wordpress.org/reference/hooks/lostpassword_url/) : applied to the URL that allows users to reset their passwords.

[option\_(option name)](https://developer.wordpress.org/reference/hooks/option_(option_name)/) : applied to the option value retrieved from the database by the `get_option` function, after unserializing (which decodes array-based options). To use this filter, you will need to add filters for specific options names, such as “option\_foo” to filter the output of `get_option("foo")`.

[pre\_get\_space\_used](https://developer.wordpress.org/reference/hooks/pre_get_space_used/): applied to the [`get_space_used()`](https://developer.wordpress.org/reference/functions/get_space_used/) function to provide an alternative way of displaying storage space used. Returning false from this filter will revert to default display behavior (used [wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) directory space in megabytes).

[pre\_option\_(option name)](https://developer.wordpress.org/reference/hooks/pre_option_(option_name)/) : applied to the option value retrieved from the database by the `get_alloptions` function, after unserializing (which decodes array-based options). To use this filter, you will need to add filters for specific options names, such as “pre\_option\_foo” to filter the option “foo”.

[pre\_update\_option\_(option name)](https://developer.wordpress.org/reference/hooks/pre_update_option_(option_name)/) : applied the option value before being saving to the database to allow overriding the value to be stored. To use this filter, you will need to add filters for specific options names, such as “pre\_update\_option\_foo” to filter the option “foo”.

[register](https://developer.wordpress.org/reference/hooks/register/) : applied to the sidebar link created for the user to register (if allowed) or visit the admin panels (if already logged in) by the `wp_register` function.

[upload\_dir](https://developer.wordpress.org/reference/hooks/upload_dir/) : applied to the directory to be used for uploads calculated by the `wp_upload_dir` function. Filter function argument is an array with components “dir” (the upload directory path), “url” (the URL of the upload directory), and “error” (which you can set to true if you want to generate an error).

[upload\_mimes](https://developer.wordpress.org/reference/hooks/upload_mimes/) : allows a filter function to return a list of MIME types for uploads, if there is no MIME list input to the `wp_check_filetype` function. Filter function argument is an associated list of MIME types whose component names are file extensions (separated by vertical bars) and values are the corresponding MIME types.

## [General Text Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#general-text-filters)

[attribute\_escape](https://developer.wordpress.org/reference/hooks/attribute_escape/) : applied to post text and other content by the `attribute_escape` function, which is called in many places in WordPress to change certain characters into HTML attributes before sending to the browser.

[js\_escape](https://developer.wordpress.org/reference/hooks/js_escape/) : applied to JavaScript code before sending to the browser in the `js_escape` function.

[sanitize\_key](https://developer.wordpress.org/reference/hooks/sanitize_key/) : applied to key before using it for your settings, field, or other needs, generated by `sanitize_key` function

## [Administrative Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#administrative-filters)

The filters in this section are related to the administration screens of

WordPress, including content editing screens.

[admin\_user\_info\_links](https://developer.wordpress.org/reference/hooks/admin_user_info_links/) : applied to the user profile and info links in the WordPress admin quick menu.

[autosave\_interval](https://developer.wordpress.org/reference/hooks/autosave_interval/) : applied to the interval for auto-saving posts.

[bulk\_actions](https://developer.wordpress.org/reference/hooks/bulk_actions/) : applied to an array of bulk items in admin bulk action dropdowns.

[bulk\_post\_updated\_messages](https://developer.wordpress.org/reference/hooks/bulk_post_updated_messages/) : applied to an array of bulk action updated messages.

[cat\_rows](https://developer.wordpress.org/reference/hooks/cat_rows/) : applied to the category rows HTML generated for managing categories in the admin menus.

[comment\_edit\_pre](https://developer.wordpress.org/reference/hooks/comment_edit_pre/) : applied to comment content prior to display in the editing screen.

[comment\_edit\_redirect](https://developer.wordpress.org/reference/hooks/comment_edit_redirect/) : applied to the redirect location after someone edits a comment in the admin menus. Filter function arguments: redirect location, comment ID.

[comment\_moderation\_subject](https://developer.wordpress.org/reference/hooks/comment_moderation_subject/) : applied to the mail subject before sending email notifying the administrator of the need to moderate a new comment. Filter function arguments: mail subject, comment ID..

[comment\_moderation\_text](https://developer.wordpress.org/reference/hooks/comment_moderation_text/) : applied to the body of the mail message before sending email notifying the administrator of the need to moderate a new comment. Filter function arguments: mail body text, comment ID.

[comment\_notification\_headers](https://developer.wordpress.org/reference/hooks/comment_notification_headers/) : applied to the mail headers before sending email notifying the post author of a new comment. Filter function arguments: mail header text, comment ID.

[comment\_notification\_subject](https://developer.wordpress.org/reference/hooks/comment_notification_subject/) : applied to the mail subject before sending email notifying the post author of a new comment. Filter function arguments: mail subject, comment ID.

[comment\_notification\_text](https://developer.wordpress.org/reference/hooks/comment_notification_text/) : applied to the body of the mail message before sending email notifying the post author of a new comment. Filter function arguments: mail body text, comment ID.

[comment\_row\_actions](https://developer.wordpress.org/reference/hooks/comment_row_actions/) : applied to the list of action links under each comment row (like Reply, Quick Edit, Edit).

[cron\_request](https://developer.wordpress.org/reference/hooks/cron_request/) : Allows filtering of the URL, key and arguments passed to [wp\_remote\_post()](https://developer.wordpress.org/reference/functions/wp_remote_post/) in [spawn\_cron()](https://developer.wordpress.org/reference/functions/spawn_cron/).

[cron\_schedules](https://developer.wordpress.org/reference/hooks/cron_schedules/) : applied to an empty array to allow a plugin to generate cron schedules in the `wp_get_schedules` function.

[custom\_menu\_order](https://developer.wordpress.org/reference/hooks/custom_menu_order/) : used to activate the ‘menu\_order’ filter.

[default\_content](https://developer.wordpress.org/reference/hooks/default_content/) : applied to the default post content prior to opening the editor for a new post.

[default\_excerpt](https://developer.wordpress.org/reference/hooks/default_excerpt/) : applied to the default post excerpt prior to opening the editor for a new post.

[default\_title](https://developer.wordpress.org/reference/hooks/default_title/) : applied to the default post title prior to opening the editor for a new post.

[editable\_slug](https://developer.wordpress.org/reference/hooks/editable_slug/) : applied to the post, page, tag or category slug by the `get_sample_permalink` function.

[format\_to\_edit](https://developer.wordpress.org/reference/hooks/format_to_edit/) : applied to post content, excerpt, title, and password by the `format_to_edit` function, which is called by the admin menus to set up a post for editing. Also applied to when editing comments in the admin menus.

[format\_to\_post](https://developer.wordpress.org/reference/hooks/format_to_post/) : applied to post content by the `format_to_post` function, which is not used in WordPress by default.

[manage\_edit-${post\_type}\_columns](https://developer.wordpress.org/reference/hooks/manage_edit-post_type_columns/) : applied to the list of columns to print on the manage posts screen for a custom post type. Filter function argument/return value is an associative array where the element key is the name of the column, and the value is the header text for that column. See also action [`manage_${post_type}_posts_custom_column`](https://developer.wordpress.org/reference/hooks/manage_post_type_posts_custom_column/), which puts the column information into the edit screen.

[manage\_link-manager\_columns](https://developer.wordpress.org/reference/hooks/manage_link-manager_columns/) : was `manage_link_columns` until wordpress 2.7. applied to the list of columns to print on the blogroll management screen. Filter function argument/return value is an associative list where the element key is the name of the column, and the value is the header text for that column. See also action [`manage_link_custom_column`](https://developer.wordpress.org/reference/hooks/manage_posts_custom_column/), which puts the column information into the edit screen.

[manage\_posts\_columns](https://developer.wordpress.org/reference/hooks/manage_posts_columns/) : applied to the list of columns to print on the manage posts screen. Filter function argument/return value is an associative array where the element key is the name of the column, and the value is the header text for that column. See also action [`manage_posts_custom_column`](https://developer.wordpress.org/reference/hooks/manage_posts_custom_column/), which puts the column information into the edit screen. (see [Scompt’s tutorial](http://scompt.com/archives/2007/10/20/adding-custom-columns-to-the-wordpress-manage-posts-screen) for examples and use.)

[manage\_pages\_columns](https://developer.wordpress.org/reference/hooks/manage_pages_columns/) : applied to the list of columns to print on the manage pages screen. Filter function argument/return value is an associative array where the element key is the name of the column, and the value is the header text for that column. See also action `manage_pages_custom_column`, which puts the column information into the edit screen.

[manage\_users\_columns](https://developer.wordpress.org/reference/hooks/manage_users_columns/)

[manage\_users\_custom\_column](https://developer.wordpress.org/reference/hooks/manage_users_custom_column/)

[manage\_users\_sortable\_columns](https://developer.wordpress.org/reference/hooks/manage_users_sortable_columns/)

[media\_row\_actions](https://developer.wordpress.org/reference/hooks/media_row_actions/) : applied to the list of action links under each file in the Media Library (like View, Edit).

[menu\_order](https://developer.wordpress.org/reference/hooks/menu_order/) : applied to the array for the admin menu order. Must be activated with the ‘custom\_menu\_order’ filter before.

[nonce\_life](https://developer.wordpress.org/reference/hooks/nonce_life/) : applied to the lifespan of a [nonce](https://developer.wordpress.org/Glossary#Nonce) to generate or verify the nonce. Can be used to generate nonces which expire earlier. The value returned by the filter should be in seconds.

[nonce\_user\_logged\_out](https://developer.wordpress.org/reference/hooks/nonce_user_logged_out/) : applied to the current user ID used to generate or verify a [nonce](https://developer.wordpress.org/Glossary#Nonce) when the user is logged out.

[plugin\_row\_meta](https://developer.wordpress.org/reference/hooks/plugin_row_meta/) : add additional links below each plugin on the plugins page.

[postmeta\_form\_limit](https://developer.wordpress.org/reference/hooks/postmeta_form_limit/) : applied to the number of post-meta information items shown on the post edit screen.

[post\_row\_actions](https://developer.wordpress.org/reference/hooks/post_row_actions/) : applied to the list of action links (like Quick Edit, Edit, View, Preview) under each post in the Posts > All Posts section.

[post\_updated\_messages](https://developer.wordpress.org/reference/hooks/post_updated_messages/) : applied to the array storing user-visible administrative messages when working with posts, pages and custom post types. This filter is used to change the text of said messages, not to trigger them. See “customizing the messages” in the [register\_post\_type](https://developer.wordpress.org/reference/functions/register_post_type#Example/) documentation.

[pre\_upload\_error](https://developer.wordpress.org/reference/hooks/pre_upload_error/) : applied to allow a plugin to create an XMLRPC error for uploading files.

[preview\_page\_link](https://developer.wordpress.org/reference/hooks/preview_page_link/) : applied to the link on the page editing screen that shows the page preview at the bottom of the screen.

[preview\_post\_link](https://developer.wordpress.org/reference/hooks/preview_post_link/) : applied to the link on the post editing screen that shows the post preview at the bottom of the screen.

[richedit\_pre](https://developer.wordpress.org/reference/hooks/richedit_pre/) : applied to post content by the `wp_richedit_pre` function, before displaying in the rich text editor.

[schedule\_event](https://developer.wordpress.org/reference/hooks/schedule_event/) : applied to each recurring and single event as it is added to the cron schedule.

[set-screen-option](https://developer.wordpress.org/reference/hooks/set-screen-option/) : Filter a screen option value before it is set.

[show\_password\_fields](https://developer.wordpress.org/reference/hooks/show_password_fields/) : applied to the true/false variable that controls whether the user is presented with the opportunity to change their password on the user profile screen (true means to show password changing fields; false means don’t).

[terms\_to\_edit](https://developer.wordpress.org/reference/hooks/terms_to_edit/) : applied to the CSV of terms (for each taxonomy) that is used to show which terms are attached to the post.

[the\_editor](https://developer.wordpress.org/reference/hooks/the_editor/) : applied to the HTML DIV created to house the rich text editor, prior to printing it on the screen. Filter function argument/return value is a string.

[user\_can\_richedit](https://developer.wordpress.org/reference/hooks/user_can_richedit/) : applied to the calculation of whether the user’s browser has rich editing capabilities, and whether the user wants to use the rich editor, in the `user_can_richedit` function. Filter function argument and return value is true/false if the current user can/cannot use the rich editor.

[user\_has\_cap](https://developer.wordpress.org/reference/hooks/user_has_cap/) : applied to a user’s capabilities list in the `WP_User->has_cap` function (which is called by the `current_user_can` function). Filter function arguments are the capabilities list to be filtered, the capability being questioned, and the argument list (which has things such as the post ID if the capability is to edit posts, etc.)

[wp\_handle\_upload\_prefilter](https://developer.wordpress.org/reference/hooks/wp_handle_upload_prefilter/) : applied to the upload information when uploading a file. Filter function argument: array which represents a single element of $\_FILES.

[wp\_handle\_upload](https://developer.wordpress.org/reference/hooks/wp_handle_upload/) : applied to the upload information when uploading a file. Filter function argument: array with elements “file” (file name), “url”, “type”.

[wp\_revisions\_to\_keep](https://developer.wordpress.org/reference/hooks/wp_revisions_to_keep/) : alters how many revisions are kept for a given post. Filter function arguments: number representing desired revisions saved (default is unlimited revisions), the post object.

[wp\_terms\_checklist\_args](https://developer.wordpress.org/reference/hooks/wp_terms_checklist_args/) : applied to arguments of the [wp\_terms\_checklist()](https://developer.wordpress.org/reference/functions/wp_terms_checklist/) function. Filter function argument: array of checklist arguments, post ID.

[wp\_upload\_tabs](https://developer.wordpress.org/reference/hooks/wp_upload_tabs/) : applied to the list of custom tabs to display on the upload management admin screen. Use action `upload_files_(tab)` to display a page for your custom tab.

[media\_upload\_tabs](https://developer.wordpress.org/reference/hooks/media_upload_tabs/) : applied to the list of custom tabs to display on the upload management admin screen. Use action `upload_files_(tab)` to display a page for your custom tab.

[plugin\_action\_links\_(plugin file name)](https://developer.wordpress.org/reference/hooks/plugin_action_links_(plugin_file_name)/) : applied to the list of links to display on the plugins page (beside the activate/deactivate links).

[views\_edit-post](https://developer.wordpress.org/reference/hooks/views_edit-post/) : applied to the list posts eg All (30) \| Published (22) \| Draft (5) \| Pending (2) \| Trash (1)

## [Rich Text Editor Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#rich-text-editor-filters)

These filters modify the configuration of the rich text editor, TinyMCE.

[mce\_spellchecker\_languages](https://developer.wordpress.org/reference/hooks/mce_spellchecker_languages/) : applied to the language selection available in the spell checker.

[mce\_buttons, mce\_buttons\_2, mce\_buttons\_3, mce\_buttons\_4](https://developer.wordpress.org/reference/hooks/mce_buttons,_mce_buttons_2,_mce_buttons_3,_mce_buttons_4/) : applied to the rows of buttons for the rich editor toolbar (each is an array of button names).

[mce\_css](https://developer.wordpress.org/reference/hooks/mce_css/) : applied to the CSS file URL for the rich text editor.

[mce\_external\_plugins](https://developer.wordpress.org/reference/hooks/mce_external_plugins/) : applied to the array of external plugins to be loaded by the rich text editor.

[mce\_external\_languages](https://developer.wordpress.org/reference/hooks/mce_external_languages/) : applied to the array of language files loaded by external plugins, allowing them to use the standard translation method (see tinymce/langs/wp-langs.php for reference).

[tiny\_mce\_before\_init](https://developer.wordpress.org/reference/hooks/tiny_mce_before_init/) : applied to the whole init array for the editor.

## [Template Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#template-filters)

This section contains links related to themes, templates, and style

files.

[locale\_stylesheet\_uri](https://developer.wordpress.org/reference/hooks/locale_stylesheet_uri/) : applied to the locale-specific stylesheet URI returned by the `get_locale_stylesheet_uri` function. Filter function arguments: URI, stylesheet directory URI.

[stylesheet](https://developer.wordpress.org/reference/hooks/stylesheet/) : applied to the stylesheet returned by the `get_stylesheet` function.

[stylesheet\_directory](https://developer.wordpress.org/reference/hooks/stylesheet_directory/) : applied to the stylesheet directory returned by the `get_stylesheet_directory` function. Filter function arguments: stylesheet directory, stylesheet.

[stylesheet\_directory\_uri](https://developer.wordpress.org/reference/hooks/stylesheet_directory_uri/) : applied to the stylesheet directory URI returned by the `get_stylesheet_directory_uri` function. Filter function arguments: stylesheet directory URI, stylesheet.

[stylesheet\_uri](https://developer.wordpress.org/reference/hooks/stylesheet_uri/) : applied to the stylesheet URI returned by the `get_stylesheet_uri` function. Filter function arguments: stylesheet URI, stylesheet.

[template](https://developer.wordpress.org/reference/hooks/template/) : applied to the template returned by the `get_template` function.

[template\_directory](https://developer.wordpress.org/reference/hooks/template_directory/) : applied to the template directory returned by the `get_template_directory` function. Filter function arguments: template directory, template.

[template\_directory\_uri](https://developer.wordpress.org/reference/hooks/template_directory_uri/) : applied to the template directory URI returned by the `get_template_directory_uri` function. Filter function arguments: template directory URI, template.

[theme\_root](https://developer.wordpress.org/reference/hooks/theme_root/) : applied to the theme root directory (normally wp-content/themes) returned by the `get_theme_root` function.

[theme\_root\_uri](https://developer.wordpress.org/reference/hooks/theme_root_uri/) : applied to the theme root directory URI returned by the `get_theme_root_uri` function. Filter function arguments: URI, site URL.

You can also replace individual template files from your theme, by using

the following filter hooks. See also the

[`template_redirect`](https://developer.wordpress.org/reference/hooks/template_redirect/)

action hook. Each of these filters takes as input the path to the

corresponding template file in the current theme. A plugin can modify

the file to be used by returning a new path to a template file.

[404\_template](https://developer.wordpress.org/reference/hooks/404_template/) :

[archive\_template](https://developer.wordpress.org/reference/hooks/archive_template/) : You can use this for example to enforce a specific template for a custom post type archive. This way you can keep all the code in a plugin.

[attachment\_template](https://developer.wordpress.org/reference/hooks/attachment_template/) :

[author\_template](https://developer.wordpress.org/reference/hooks/author_template/) :

[category\_template](https://developer.wordpress.org/reference/hooks/category_template/) :

[comments\_popup\_template](https://developer.wordpress.org/reference/hooks/comments_popup_template/) :

[comments\_template](https://developer.wordpress.org/reference/hooks/comments_template/) : The “comments\_template” filter can be used to load a custom template form a plugin which replace the themes default comment template.

[date\_template](https://developer.wordpress.org/reference/hooks/date_template/) :

[home\_template](https://developer.wordpress.org/reference/hooks/home_template/) :

[page\_template](https://developer.wordpress.org/reference/hooks/page_template/) :

[paged\_template](https://developer.wordpress.org/reference/hooks/paged_template/) :

[search\_template](https://developer.wordpress.org/reference/hooks/search_template/) :

[single\_template](https://developer.wordpress.org/reference/hooks/single_template/) : You can use this for example to enforce a specific template for a custom post type. This way you can keep all the code in a plugin.

[shortcut\_link](https://developer.wordpress.org/reference/hooks/shortcut_link/) : applied to the “Press This” bookmarklet link.

[template\_include](https://developer.wordpress.org/reference/hooks/template_include/) :

[wp\_nav\_menu\_args](https://developer.wordpress.org/reference/hooks/wp_nav_menu_args/) : applied to the arguments of the `wp_nav_menu` function.

[wp\_nav\_menu\_items](https://developer.wordpress.org/reference/hooks/wp_nav_menu_items/) : Filter the HTML list content for navigation menus.

### [Kubrick Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#kubrick-filters)

These filters were present in the pre-3.0 default theme kubrick.

[kubrick\_header\_color](https://developer.wordpress.org/reference/hooks/kubrick_header_color/) : applied to the color for the header of the kubrick theme.

[kubrick\_header\_display](https://developer.wordpress.org/reference/hooks/kubrick_header_display/) : applied to the display option for the header of the kubrick theme.

[kubrick\_header\_image](https://developer.wordpress.org/reference/hooks/kubrick_header_image/) : applied to the header image file for the kubrick theme.

## [Registration & Login Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#registration-login-filters)

[authenticate](https://developer.wordpress.org/reference/hooks/authenticate/) : allows basic authentication to be performed on login based on username and password.

[registration\_errors](https://developer.wordpress.org/reference/hooks/registration_errors/) : applied to the list of registration errors generated while registering a user for a new account.

[user\_registration\_email](https://developer.wordpress.org/reference/hooks/user_registration_email/) : applied to the user’s email address read from the registration page, prior to trying to register the person as a new user.

[validate\_username](https://developer.wordpress.org/reference/hooks/validate_username/) : applied to the validation result on a new user name. Filter function arguments: valid (true/false), user name being validated.

[wp\_authenticate\_user](https://developer.wordpress.org/reference/hooks/wp_authenticate_user/) : applied when a user attempted to log in, after WordPress validates username and password, but before validation errors are checked.

## [Redirect/Rewrite Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#redirect-rewrite-filters)

These advanced filters relate to WordPress’s handling of rewrite rules.

[allowed\_redirect\_hosts](https://developer.wordpress.org/reference/hooks/allowed_redirect_hosts/) : applied to the list of host names deemed safe for redirection. wp-login.php uses this to defend against a dangerous ‘redirect\_to’ request parameter

[author\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/author_rewrite_rules/) : applied to the author-related rewrite rules after they are generated.

[category\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/category_rewrite_rules/) : applied to the category-related rewrite rules after they are generated.

[comments\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/comments_rewrite_rules/) : applied to the comment-related rewrite rules after they are generated.

[date\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/date_rewrite_rules/) : applied to the date-related rewrite rules after they are generated.

[mod\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/) : applied to the list of rewrite rules given to the user to put into their .htaccess file when they change their permalink structure. (Note: replaces deprecated filter `rewrite_rules`.)

[page\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/page_rewrite_rules/) : applied to the page-related rewrite rules after they are generated.

[post\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/post_rewrite_rules/) : applied to the post-related rewrite rules after they are generated.

[redirect\_canonical](https://developer.wordpress.org/reference/hooks/redirect_canonical/) : Can be used to cancel a “canonical” URL redirect. Accepts 2 parameters: `$redirect_url`, `$requested_url`. To cancel the redirect return **`FALSE`**, to allow the redirect return `$redirect_url`

[rewrite\_rules\_array](https://developer.wordpress.org/reference/hooks/rewrite_rules_array/) : applied to the entire rewrite rules array after it is generated.

[root\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/root_rewrite_rules/) : applied to the root-level rewrite rules after they are generated.

[search\_rewrite\_rules](https://developer.wordpress.org/reference/hooks/search_rewrite_rules/) : applied to the search-related rewrite rules after they are generated.

[wp\_redirect](https://developer.wordpress.org/reference/hooks/wp_redirect/) : applied to a redirect URL by the default `wp_redirect` function. Filter function arguments: URL, HTTP status code.

[wp\_redirect\_status](https://developer.wordpress.org/reference/hooks/wp_redirect_status/) : applied to the HTTP status code when redirecting by the default `wp_redirect` function. Filter function arguments: HTTP status code, URL.

## [WP\_Query Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#wp_query-filters)

These are filters run by the [WP\_Query object](https://developer.wordpress.org/reference/classes/wp_query/) in the course of building

and executing a query to retrieve posts. See also [#Advanced WordPress Filters](https://developer.wordpress.org/#Advanced_WordPress_Filters) for queries relating

to users, meta values, and more generic queries.

[found\_posts](https://developer.wordpress.org/reference/hooks/found_posts/) : applied to the list of posts, just after querying from the database.

[found\_posts\_query](https://developer.wordpress.org/reference/hooks/found_posts_query/) : after the list of posts to display is queried from the database, WordPress selects rows in the query results. This filter allows you to do something other than `SELECT FOUND_ROWS()` at that step.

[post\_limits](https://developer.wordpress.org/reference/hooks/post_limits/) : applied to the `LIMIT` clause of the query that returns the post array.

[posts\_clauses](https://developer.wordpress.org/reference/hooks/posts_clauses/) : applied to the entire SQL query, divided into a keyed array for each clause type, that returns the post array. Can be easier to work with than `posts_request`.

[posts\_distinct](https://developer.wordpress.org/reference/hooks/posts_distinct/) : allows a plugin to add a `DISTINCTROW` clause to the query that returns the post array.

[posts\_fields](https://developer.wordpress.org/reference/hooks/posts_fields/) : applied to the field list for the query that returns the post array.

[posts\_groupby](https://developer.wordpress.org/reference/hooks/posts_groupby/) : applied to the `GROUP BY` clause of the query that returns the post array (normally empty).

[posts\_join](https://developer.wordpress.org/reference/hooks/posts_join/) : applied to the `JOIN` clause of the query that returns the post array. This is typically used to add a table to the `JOIN`, in combination with the `posts_where` filter.

[posts\_join\_paged](https://developer.wordpress.org/reference/hooks/posts_join_paged/) : applied to the `JOIN` clause of the query that returns the post array, after the paging is calculated (though paging does not affect the JOIN, so this is actually equivalent to `posts_join`).

[posts\_orderby](https://developer.wordpress.org/reference/hooks/posts_orderby/) : applied to the `ORDER BY` clause of the query that returns the post array.

[posts\_request](https://developer.wordpress.org/reference/hooks/posts_request/) : applied to the entire SQL query that returns the post array, just prior to running the query.

[posts\_results](https://developer.wordpress.org/reference/hooks/posts_results/) : allows you to manipulate the resulting array returned from the query.

[posts\_search](https://developer.wordpress.org/reference/hooks/posts_search/) : applied to the search SQL that is used in the `WHERE` clause of [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/).

[posts\_where](https://developer.wordpress.org/reference/hooks/posts_where/) : applied to the `WHERE` clause of the query that returns the post array.

[posts\_where\_paged](https://developer.wordpress.org/reference/hooks/posts_where_paged/) : applied to the `WHERE` clause of the query that returns the post array, after the paging is calculated (though paging does not affect the WHERE, so this is actually equivalent to `posts_where`).

[the\_posts](https://developer.wordpress.org/reference/hooks/the_posts/) : applied to the list of posts queried from the database after minimal processing for permissions and draft status on single-post pages.

## [Media Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#media-filters)

This section contains media filters that are used to integrated

different types of media.

[editor\_max\_image\_size](https://developer.wordpress.org/reference/hooks/editor_max_image_size/) :

[image\_downsize](https://developer.wordpress.org/reference/hooks/image_downsize/) :

[get\_image\_tag\_class](https://developer.wordpress.org/reference/hooks/get_image_tag_class/) :

[get\_image\_tag](https://developer.wordpress.org/reference/hooks/get_image_tag/) :

[image\_resize\_dimensions](https://developer.wordpress.org/reference/hooks/image_resize_dimensions/) :

[intermediate\_image\_sizes](https://developer.wordpress.org/reference/hooks/intermediate_image_sizes/) :

[icon\_dir](https://developer.wordpress.org/reference/hooks/icon_dir/) :

[wp\_get\_attachment\_image\_attributes](https://developer.wordpress.org/reference/hooks/wp_get_attachment_image_attributes/) :

[img\_caption\_shortcode](https://developer.wordpress.org/reference/hooks/img_caption_shortcode/) :

[post\_gallery](https://developer.wordpress.org/reference/hooks/post_gallery/) :

[use\_default\_gallery\_style](https://developer.wordpress.org/reference/hooks/use_default_gallery_style/) :

[gallery\_style](https://developer.wordpress.org/reference/hooks/gallery_style/) :

[(adjacent)\_image\_link](https://developer.wordpress.org/reference/hooks/(adjacent)_image_link/) :

[embed\_defaults](https://developer.wordpress.org/reference/hooks/embed_defaults/) :

[load\_default\_embeds](https://developer.wordpress.org/reference/hooks/load_default_embeds/) :

[embed\_oembed\_html](https://developer.wordpress.org/reference/hooks/embed_oembed_html/) :

[embed\_googlevideo](https://developer.wordpress.org/reference/hooks/embed_googlevideo/) :

[oembed\_result](https://developer.wordpress.org/reference/hooks/oembed_result/) :

[upload\_size\_limit](https://developer.wordpress.org/reference/hooks/upload_size_limit/) :

[wp\_image\_editors](https://developer.wordpress.org/reference/hooks/wp_image_editors/) :

[plupload\_default\_settings](https://developer.wordpress.org/reference/hooks/plupload_default_settings/) :

[plupload\_default\_params](https://developer.wordpress.org/reference/hooks/plupload_default_params/) :

[image\_size\_names\_choose](https://developer.wordpress.org/reference/hooks/image_size_names_choose/) :

[wp\_prepare\_attachment\_for\_js](https://developer.wordpress.org/reference/hooks/wp_prepare_attachment_for_js/) :

[media\_upload\_tabs](https://developer.wordpress.org/reference/hooks/media_upload_tabs/) :

[disable\_captions](https://developer.wordpress.org/reference/hooks/disable_captions/) :

[media\_view\_settings](https://developer.wordpress.org/reference/hooks/media_view_settings/) :

[media\_view\_strings](https://developer.wordpress.org/reference/hooks/media_view_strings/) :

[wp\_handle\_upload\_prefilter](https://developer.wordpress.org/reference/hooks/wp_handle_upload_prefilter/) :

## [Advanced WordPress Filters](https://developer.wordpress.org/apis/hooks/filter-reference/\#advanced-wordpress-filters)

This section contains advanced filters related to internationalization,

miscellaneous queries, and other fundamental WordPress functions.

[create\_user\_query](https://developer.wordpress.org/reference/hooks/create_user_query/) : applied to the query used to save a new user’s information to the database, just prior to running the query.

[get\_editable\_authors](https://developer.wordpress.org/reference/hooks/get_editable_authors/) : applied to the list of post authors that the current user is authorized to edit in the `get_editable_authors` function.

[get\_next\_post\_join](https://developer.wordpress.org/reference/hooks/get_next_post_join/) : in function `get_next_post` (which finds the post after the currently-displayed post), applied to the SQL JOIN clause (which normally joins to the category table if user is viewing a category archive). Filter function arguments: JOIN clause, stay in same category (true/false), list of excluded categories.

[get\_next\_post\_sort](https://developer.wordpress.org/reference/hooks/get_next_post_sort/) : in function `get_next_post` (which finds the post after the currently-displayed post), applied to the SQL ORDER BY clause (which normally orders by post date in ascending order with a limit of 1 post). Filter function arguments: ORDER BY clause.

[get\_next\_post\_where](https://developer.wordpress.org/reference/hooks/get_next_post_where/) : in function `get_next_post` (which finds the post after the currently-displayed post), applied to the SQL WHERE clause (which normally looks for the next dated published post). Filter function arguments: WHERE clause, stay in same category (true/false), list of excluded categories.

[get\_previous\_post\_join](https://developer.wordpress.org/reference/hooks/get_previous_post_join/) : in function `get_previous_post` (which finds the post before the currently-displayed post), applied to the SQL JOIN clause (which normally joins to the category table if user is viewing a category archive). Filter function arguments: join clause, stay in same category (true/false), list of excluded categories.

[get\_previous\_post\_sort](https://developer.wordpress.org/reference/hooks/get_previous_post_sort/) : in function `get_previous_post` (which finds the post before the currently-displayed post), applied to the SQL ORDER BY clause (which normally orders by post date in descending order with a limit of 1 post). Filter function arguments: ORDER BY clause.

[get\_previous\_post\_where](https://developer.wordpress.org/reference/hooks/get_previous_post_where/) : in function `get_previous_post` (which finds the post before the currently-displayed post), applied to the SQL WHERE clause (which normally looks for the previous dated published post). Filter function arguments: WHERE clause, stay in same category (true/false), list of excluded categories.

[gettext](https://developer.wordpress.org/reference/hooks/gettext/) : applied to the translated text by the [`translation()`](https://developer.wordpress.org/reference/functions/translation/) function (which is called by functions like the [`__()`](https://developer.wordpress.org/reference/functions/_2/) and [`_e()`](https://developer.wordpress.org/reference/functions/_e/) internationalization functions ). Filter function arguments: translated text, untranslated text and the text domain. Gets applied even if internationalization is not in effect or if the text domain has not been loaded.

[override\_load\_textdomain](https://developer.wordpress.org/reference/hooks/override_load_textdomain/)

[get\_meta\_sql](https://developer.wordpress.org/reference/hooks/get_meta_sql/) : in function `WP_Meta_Query::get_sql` (which generates SQL clauses to be appended to a main query for advanced meta queries.), applied to the SQL JOIN and WHERE clause generated by the advanced meta query. Filter function arguments: array( compact( ‘join’, ‘where’ ), $this->queries, $type, $primary\_table, $primary\_id\_column, $context )

[get\_others\_drafts](https://developer.wordpress.org/reference/hooks/get_others_drafts/) : applied to the query that selects the other users’ drafts for display in the admin menus.

[get\_users\_drafts](https://developer.wordpress.org/reference/hooks/get_users_drafts/) : applied to the query that selects the users’ drafts for display in the admin menus.

[locale](https://developer.wordpress.org/reference/hooks/locale/) : applied to the locale by the `get_locale` function.

[query](https://developer.wordpress.org/reference/hooks/query/) : applied to all queries (at least all queries run after plugins are loaded).

[query\_string](https://developer.wordpress.org/reference/hooks/query_string/) : deprecated – use `query_vars` or `request` instead.

[query\_vars](https://developer.wordpress.org/reference/hooks/query_vars/) : applied to the list of public WordPress query variables before the SQL query is formed. Useful for removing extra permalink information the plugin has dealt with in some other manner.

[request](https://developer.wordpress.org/reference/hooks/request/) : like `query_vars`, but applied after “extra” and private query variables have been added.

[excerpt\_length](https://developer.wordpress.org/reference/hooks/excerpt_length/) : Defines the length of a single-post excerpt.

[excerpt\_more](https://developer.wordpress.org/reference/hooks/excerpt_more/) : Defines the more string at the end of the excerpt.

[post\_edit\_form\_tag](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/) : Allows you to append code to the form tag in the default post/page editor.

[update\_user\_query](https://developer.wordpress.org/reference/hooks/update_user_query/) : applied to the update query used to update user information, prior to running the query.

[uploading\_iframe\_src](https://developer.wordpress.org/reference/hooks/uploading_iframe_src/) (removed since WP 2.5): applied to the HTML src tag for the uploading iframe on the post and page editing screens.

[xmlrpc\_methods](https://developer.wordpress.org/reference/hooks/xmlrpc_methods/) : applied to list of defined XMLRPC methods for the XMLRPC server.

[wp\_mail\_from](https://developer.wordpress.org/reference/hooks/wp_mail_from/) : applied before any mail is sent by the wp\_mail function. Supplied value is the calculated from address which is wordpress at the current hostname (set by $\_SERVER\[‘SERVER\_NAME’\]). The filter should return an email address or name/email combo in the form “user@example.com” or “Name \\<user@example.com>” (without the quotes!).

[wp\_mail\_from\_name](https://developer.wordpress.org/reference/hooks/wp_mail_from_name/) : applied before any mail is sent by the wp\_mail function. The filter should return a name string to be used as the email from name.

[update\_(meta\_type)\_metadata](https://developer.wordpress.org/reference/hooks/update_(meta_type)_metadata/) : applied before a metadata gets updated. For example if a user metadata gets updated the hook would be ‘update\_user\_metadata’

## [Widgets](https://developer.wordpress.org/apis/hooks/filter-reference/\#widgets)

This section contains filters added by widgets present in WordPress

core.

[dynamic\_sidebar\_params](https://developer.wordpress.org/reference/hooks/dynamic_sidebar_params/) : applied to the arguments passed to the widgets\_init function in the WordPress widgets.

[widget\_archives\_dropdown\_args](https://developer.wordpress.org/reference/hooks/widget_archives_dropdown_args/) : applied to the arguments passed to the [`wp_get_archives()`](https://developer.wordpress.org/reference/functions/wp_get_archives/) function in the WordPress Archives widget.

[widget\_categories\_args](https://developer.wordpress.org/reference/hooks/widget_categories_args/) : applied to the arguments passed to the [`wp_list_categories()`](https://developer.wordpress.org/reference/functions/wp_list_categories/) function in the WordPress Categories widget.

[widget\_links\_args](https://developer.wordpress.org/reference/hooks/widget_links_args/) : applied to the arguments passed to the [`wp_list_bookmarks()`](https://developer.wordpress.org/reference/functions/wp_list_bookmarks/) function in the WordPress Links widget.

[widget\_nav\_menu\_args](https://developer.wordpress.org/reference/hooks/widget_nav_menu_args/) : applied to the arguments passed to the [`wp_nav_menu()`](https://developer.wordpress.org/reference/functions/wp_nav_menu/) function in the WordPress Custom Menu widget.

[widget\_pages\_args](https://developer.wordpress.org/reference/hooks/widget_pages_args/) : applied to the arguments passed to the [`wp_list_pages()`](https://developer.wordpress.org/reference/functions/wp_list_pages/) function in the WordPress Pages widget.

[widget\_tag\_cloud\_args](https://developer.wordpress.org/reference/hooks/widget_tag_cloud_args/) : applied to the arguments passed to the [`wp_tag_cloud()`](https://developer.wordpress.org/reference/functions/wp_tag_cloud/) function in the WordPress Pages widget.

[widget\_text](https://developer.wordpress.org/reference/hooks/widget_text/) : applied to the widget text of the WordPress Text widget. May also apply to some third party widgets as well.

[widget\_title](https://developer.wordpress.org/reference/hooks/widget_title/) : applied to the widget title of any user editable WordPress Widget. May also apply to some third party widgets as well.

## [Admin Bar](https://developer.wordpress.org/apis/hooks/filter-reference/\#admin-bar)

This section contains filters added by the Admin Bar added in WordPress

3.1.0.

[wp\_admin\_bar\_class](https://developer.wordpress.org/reference/hooks/wp_admin_bar_class/) : allows changing the default ‘ [WP\_Admin\_Bar](https://developer.wordpress.org/reference/classes/wp_admin_bar/)’ class in the [`_wp_admin_bar_init()`](https://developer.wordpress.org/reference/functions/_wp_admin_bar_init/) function in .

## [Further Reading](https://developer.wordpress.org/apis/hooks/filter-reference/\#further-reading)

- [Hooks Database](https://developer.wordpress.org/reference/hooks/) – documentation for all hooks in the official WordPress Code

Reference.

First published

January 29, 2024

Last updated

May 31, 2025

[PreviousAction ReferencePrevious: Action Reference](https://developer.wordpress.org/apis/hooks/action-reference/)

[NextResponsive ImagesNext: Responsive Images](https://developer.wordpress.org/apis/responsive-images/)

Notifications