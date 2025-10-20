---
url: https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags
scraped_at: 2025-10-20T03:15:10.629Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

List of Conditional Tags


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[References](https://developer.wordpress.org/themes/classic-themes/references/)List of Conditional Tags

Search

# List of Conditional Tags

## In this article

Table of Contents

- [Complete List of Conditional Tags](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#complete-list-of-conditional-tags)
- [The Conditions For …](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#the-conditions-for)
  - [The Main Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#the-main-page)
  - [The Front Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#the-front-page)
  - [The Blog Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#the-blog-page)
  - [A Single Post Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-single-post-page)
  - [A PAGE Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-page-page)
  - [Has Post Thumbnail](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#has-post-thumbnail)
  - [A Single Page, a Single Post, an Attachment or Any Other Custom Post Type](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-single-page-a-single-post-an-attachment-or-any-other-custom-post-type)
  - [A Category Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-category-page)
  - [A Tag Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-tag-page)
  - [A Taxonomy Page (and related)](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-taxonomy-page-and-related)
  - [An Author Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#an-author-page)
  - [A Date Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-date-page)
  - [Any Archive Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#any-archive-page)
  - [A Search Result Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-search-result-page)
  - [A 404 Not Found Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-404-not-found-page)
  - [Is Dynamic SideBar](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-dynamic-sidebar)
  - [Is Sidebar Active](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-sidebar-active)
  - [Is Widget Active](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-widget-active)
  - [Is User Logged in](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-user-logged-in)
  - [Email Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#email-exists)
  - [Username Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#username-exists)
  - [A Paged Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-paged-page)
  - [Right To Left Reading](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#right-to-left-reading)
  - [An Attachment](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#an-attachment)
  - [Attachment Is Image](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#attachment-is-image)
  - [A Local Attachment](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-local-attachment)
  - [Post Type Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#post-type-exists)
  - [Is Main Query](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-main-query)
  - [A New Day](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-new-day)
  - [A Syndication](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-syndication)
  - [A Trackback](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-trackback)
  - [A Preview](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-preview)
  - [Has An Excerpt](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#has-an-excerpt)
  - [Has A Nav Menu Assigned](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#has-a-nav-menu-assigned)
  - [Is Blog Installed](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-blog-installed)
  - [Part of a Network (Multisite)](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#part-of-a-network-multisite)
  - [An Active Plugin](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#an-active-plugin)
  - [A Child Theme](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#a-child-theme)
  - [Theme supports a feature](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#theme-supports-a-feature)
  - [Is Previewed in the Customizer](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#is-previewed-in-the-customizer)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/#wp--skip-link--target)

Conditional Tags are a boolean data type that can be used in your Template Files to alter the display of content depending on the conditions that the current page matches. They tell WordPress what code to display under specific conditions. Conditional Tags usually work with PHP [if](http://php.net/manual/en/control-structures.if.php "PHP if conditional") / [else](http://php.net/manual/en/control-structures.else.php "PHP else conditional") Conditional Statements and have close relation with WOrdPress [Template Hierarchy](https://codex.wordpress.org/Template_Hierarchy "Template Hierarchy"). .

**Warning: You can only use conditional query tags after the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) is set up or  with [action hook](https://codex.wordpress.org/Plugin_API/Action_Reference#Actions_Run_During_a_Typical_Request "Plugin API/Action Reference").**

## [Complete List of Conditional Tags](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#complete-list-of-conditional-tags)

- `[is\_front\_page()](https://codex.wordpress.org/Function_Reference/is_front_page "Function Reference/is front page")`
- `[is\_home()](https://codex.wordpress.org/Function_Reference/is_home "Function Reference/is home")`
- `[is\_front\_page()](https://codex.wordpress.org/Function_Reference/is_front_page "Function Reference/is front page")`
- `[is\_home()](https://codex.wordpress.org/Function_Reference/is_home "Function Reference/is home")`
- [is\_admin()](https://codex.wordpress.org/Function_Reference/is_admin "Function Reference/is admin")
- [is\_network\_admin()](https://codex.wordpress.org/Function_Reference/is_network_admin "Function Reference/is network admin")
- `[is\_admin\_bar\_showing()](https://codex.wordpress.org/Function_Reference/is_admin_bar_showing "Function Reference/is admin bar showing")`
- `[is\_single()](https://codex.wordpress.org/Function_Reference/is_single "Function Reference/is single")`
- `[is\_sticky()](https://codex.wordpress.org/Function_Reference/is_sticky "Function Reference/is sticky")`
- `[is\_post\_type\_hierarchical( $post\_type )](https://codex.wordpress.org/Function_Reference/is_post_type_hierarchical "Function Reference/is post type hierarchical")`
- `[is\_post\_type\_archive()](https://codex.wordpress.org/Function_Reference/is_post_type_archive "Function Reference/is post type archive")`
- `[is\_comments\_popup()](https://codex.wordpress.org/Function_Reference/is_comments_popup "Function Reference/is comments popup")`
- [comments\_open()](https://codex.wordpress.org/Function_Reference/comments_open "Function Reference/comments open")
- [pings\_open()](https://codex.wordpress.org/Function_Reference/pings_open "Function Reference/pings open")
- `[is\_page()](https://codex.wordpress.org/Function_Reference/is_page "Function Reference/is page")`
- `[is\_page\_template()](https://codex.wordpress.org/Function_Reference/is_page_template "Function Reference/is page template")`
- `[is\_category( $category )](https://codex.wordpress.org/Function_Reference/is_category "Function Reference/is category")`
- `[is\_tag()](https://codex.wordpress.org/Function_Reference/is_tag "Function Reference/is tag")`
- `[is\_tax()](https://codex.wordpress.org/Function_Reference/is_tax "Function Reference/is tax")`
- `[has\_term()](https://codex.wordpress.org/Function_Reference/has_term "Function Reference/has term")`
- `[term\_exists( $term, $taxonomy, $parent )](https://codex.wordpress.org/Function_Reference/term_exists "Function Reference/term exists")`
- `[is\_taxonomy\_hierarchical( $taxonomy )](https://codex.wordpress.org/Function_Reference/is_taxonomy_hierarchical "Function Reference/is taxonomy hierarchical")`
- `[taxonomy\_exists( $taxonomy )](https://codex.wordpress.org/Function_Reference/taxonomy_exists "Function Reference/taxonomy exists")`
- `[is\_author()](https://codex.wordpress.org/Function_Reference/is_author "Function Reference/is author")`
- `[is\_date()](https://codex.wordpress.org/Function_Reference/is_date "Function Reference/is date")`
- `[is\_year()](https://codex.wordpress.org/Function_Reference/is_year "Function Reference/is year")`
- `[is\_month()](https://codex.wordpress.org/Function_Reference/is_month "Function Reference/is month")`
- `[is\_day()](https://codex.wordpress.org/Function_Reference/is_day "Function Reference/is day")`
- `[is\_time()](https://codex.wordpress.org/Function_Reference/is_time "Function Reference/is time")`
- `[is\_new\_day()](https://codex.wordpress.org/Function_Reference/is_new_day "Function Reference/is new day")`
- `[is\_archive()](https://codex.wordpress.org/Function_Reference/is_archive "Function Reference/is archive")`
- `[is\_search()](https://codex.wordpress.org/Function_Reference/is_search "Function Reference/is search")`
- `[is\_404()](https://codex.wordpress.org/Function_Reference/is_404 "Function Reference/is 404")`
- `[is\_paged()](https://codex.wordpress.org/Function_Reference/is_paged "Function Reference/is paged")`
- `[is\_attachment()](https://codex.wordpress.org/Function_Reference/is_attachment "Function Reference/is attachment")`
- `[wp\_attachment\_is\_image( $post\_id )](https://codex.wordpress.org/Function_Reference/wp_attachment_is_image "Function Reference/wp attachment is image")`
- `[is\_local\_attachment( $url )](https://codex.wordpress.org/Function_Reference/is_local_attachment "Function Reference/is local attachment")`
- `[is\_singular()](https://codex.wordpress.org/Function_Reference/is_singular "Function Reference/is singular")`
- `[post\_type\_exists( $post\_type )](https://codex.wordpress.org/Function_Reference/post_type_exists "Function Reference/post type exists")`
- [is\_main\_query()](https://codex.wordpress.org/Function_Reference/is_main_query "Function Reference/is main query")
- `[is\_new\_day()](https://codex.wordpress.org/Function_Reference/is_new_day "Function Reference/is new day")`
- `[is\_feed()](https://codex.wordpress.org/Function_Reference/is_feed "Function Reference/is feed")`
- `[is\_trackback()](https://codex.wordpress.org/Function_Reference/is_trackback "Function Reference/is trackback")`
- `[is\_preview()](https://codex.wordpress.org/Function_Reference/is_preview "Function Reference/is preview")`
- `[in\_the\_loop()](https://codex.wordpress.org/Function_Reference/in_the_loop "Function Reference/in the loop")`
- `[is\_dynamic\_sidebar()](https://codex.wordpress.org/Function_Reference/is_dynamic_sidebar "Function Reference/is dynamic sidebar")`
- `[is\_active\_sidebar()](https://codex.wordpress.org/Function_Reference/is_active_sidebar "Function Reference/is active sidebar")`
- `[is\_active\_widget( $widget\_callback, $widget\_id )](https://codex.wordpress.org/Function_Reference/is_active_widget "Function Reference/is active widget")`
- `[is\_blog\_installed()](https://codex.wordpress.org/Function_Reference/is_blog_installed "Function Reference/is blog installed")`
- `[is\_rtl()](https://codex.wordpress.org/Function_Reference/is_rtl "Function Reference/is rtl")`
- `[is\_multisite()](https://codex.wordpress.org/Function_Reference/is_multisite "Function Reference/is multisite")`
- `[is\_main\_site()](https://codex.wordpress.org/Function_Reference/is_main_site "Function Reference/is main site")`
- `[is\_super\_admin()](https://codex.wordpress.org/Function_Reference/is_super_admin "Function Reference/is super admin")`
- `[is\_user\_logged\_in()](https://codex.wordpress.org/Function_Reference/is_user_logged_in "Function Reference/is user logged in")`
- `[email\_exists( $email )](https://codex.wordpress.org/Function_Reference/email_exists "Function Reference/email exists")`
- `[username\_exists( $username )](https://codex.wordpress.org/Function_Reference/username_exists "Function Reference/username exists")`
- `[is\_plugin\_active( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_active "Function Reference/is plugin active")`
- `[is\_plugin\_inactive( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_inactive "Function Reference/is plugin inactive")`
- `[is\_plugin\_active\_for\_network( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_active_for_network "Function Reference/is plugin active for network")`
- `[is\_plugin\_page()](https://codex.wordpress.org/Function_Reference/is_plugin_page "Function Reference/is plugin page")`
- `[is\_child\_theme()](https://codex.wordpress.org/Function_Reference/is_child_theme "Function Reference/is child theme")`
- `[current\_theme\_supports()](https://codex.wordpress.org/Function_Reference/current_theme_supports "Function Reference/current theme supports")`
- `[has\_post\_thumbnail( $post\_id )](https://codex.wordpress.org/Function_Reference/has_post_thumbnail "Function Reference/has post thumbnail")`
- `[wp\_script\_is( $handle, $list )](https://codex.wordpress.org/Function_Reference/wp_script_is "Function Reference/wp script is")`

## [The Conditions For …](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#the-conditions-for)

All of the Conditional Tags test to see whether a certain condition is met, and then returns either TRUE or FALSE. The conditions under which various tags output TRUE is listed below. Those tags which can accept parameters are so noted.

### [The Main Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#the-main-page)

- `[is\_home()](https://codex.wordpress.org/Function_Reference/is_home "Function Reference/is home")`

### [The Front Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#the-front-page)

- `[is\_front\_page()](https://codex.wordpress.org/Function_Reference/is_front_page "Function Reference/is front page")`

### [The Blog Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#the-blog-page)

- [is\_front\_page()](https://codex.wordpress.org/Function_Reference/is_front_page "Function Reference/is front page")
- `[is\_home()](https://codex.wordpress.org/Function_Reference/is_home "Function Reference/is home")`

### [A Single Post Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-single-post-page)

- `[is\_single()](https://codex.wordpress.org/Function_Reference/is_single "Function Reference/is single")`

### [A PAGE Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-page-page)

- `[is\_page()](https://codex.wordpress.org/Function_Reference/is_page "Function Reference/is page")`
- `[is\_page\_template()](https://codex.wordpress.org/Function_Reference/is_page_template "Function Reference/is page template")`

### [Has Post Thumbnail](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#has-post-thumbnail)

- `[has\_post\_thumbnail( $post\_id )](https://codex.wordpress.org/Function_Reference/has_post_thumbnail "Function Reference/has post thumbnail")`

### [A Single Page, a Single Post, an Attachment or Any Other Custom Post Type](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-single-page-a-single-post-an-attachment-or-any-other-custom-post-type)

- `[is\_singular()](https://codex.wordpress.org/Function_Reference/is_singular "Function Reference/is singular")`

### [A Category Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-category-page)

- `[is\_category( $category )](https://codex.wordpress.org/Function_Reference/is_category "Function Reference/is category")`

### [A Tag Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-tag-page)

- `[is\_tag()](https://codex.wordpress.org/Function_Reference/is_tag "Function Reference/is tag")`
- `[has\_tag()](https://codex.wordpress.org/Function_Reference/has_tag "Function Reference/has tag")`

### [A Taxonomy Page (and related)](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-taxonomy-page-and-related)

- `[is\_tax()](https://codex.wordpress.org/Function_Reference/is_tax "Function Reference/is tax")`
- `[has\_term()](https://codex.wordpress.org/Function_Reference/has_term "Function Reference/has term")`
- `[term\_exists( $term, $taxonomy, $parent )](https://codex.wordpress.org/Function_Reference/term_exists "Function Reference/term exists")`
- `[is\_taxonomy\_hierarchical( $taxonomy )](https://codex.wordpress.org/Function_Reference/is_taxonomy_hierarchical "Function Reference/is taxonomy hierarchical")`
- `[taxonomy\_exists( $taxonomy )](https://codex.wordpress.org/Function_Reference/taxonomy_exists "Function Reference/taxonomy exists")`

### [An Author Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#an-author-page)

- `[is\_author()](https://codex.wordpress.org/Function_Reference/is_author "Function Reference/is author")`

### [A Date Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-date-page)

- `[is\_date()](https://codex.wordpress.org/Function_Reference/is_date "Function Reference/is date")`
- `[is\_year()](https://codex.wordpress.org/Function_Reference/is_year "Function Reference/is year")`
- `[is\_month()](https://codex.wordpress.org/Function_Reference/is_month "Function Reference/is month")`
- `[is\_day()](https://codex.wordpress.org/Function_Reference/is_day "Function Reference/is day")`
- `[is\_time()](https://codex.wordpress.org/Function_Reference/is_time "Function Reference/is time")`
- `[is\_new\_day()](https://codex.wordpress.org/Function_Reference/is_new_day "Function Reference/is new day")`

### [Any Archive Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#any-archive-page)

- `[is\_archive()](https://codex.wordpress.org/Function_Reference/is_archive "Function Reference/is archive")`

### [A Search Result Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-search-result-page)

- `[is\_search()](https://codex.wordpress.org/Function_Reference/is_search "Function Reference/is search")`

### [A 404 Not Found Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-404-not-found-page)

- `[is\_404()](https://codex.wordpress.org/Function_Reference/is_404 "Function Reference/is 404")`

### [Is Dynamic SideBar](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-dynamic-sidebar)

- `[is\_dynamic\_sidebar()](https://codex.wordpress.org/Function_Reference/is_dynamic_sidebar "Function Reference/is dynamic sidebar")`

### [Is Sidebar Active](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-sidebar-active)

- `[is\_active\_sidebar()](https://codex.wordpress.org/Function_Reference/is_active_sidebar "Function Reference/is active sidebar")`

### [Is Widget Active](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-widget-active)

- `[is\_active\_widget( $widget\_callback, $widget\_id )](https://codex.wordpress.org/Function_Reference/is_active_widget "Function Reference/is active widget")`

### [Is User Logged in](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-user-logged-in)

- `[is\_user\_logged\_in()](https://codex.wordpress.org/Function_Reference/is_user_logged_in "Function Reference/is user logged in")`

### [Email Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#email-exists)

- `[email\_exists( $email )](https://codex.wordpress.org/Function_Reference/email_exists "Function Reference/email exists")`

### [Username Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#username-exists)

- `[username\_exists( $username )](https://codex.wordpress.org/Function_Reference/username_exists "Function Reference/username exists")`

### [A Paged Page](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-paged-page)

- `[is\_paged()](https://codex.wordpress.org/Function_Reference/is_paged "Function Reference/is paged")`

### [Right To Left Reading](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#right-to-left-reading)

- `[is\_rtl()](https://codex.wordpress.org/Function_Reference/is_rtl "Function Reference/is rtl")`

### [An Attachment](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#an-attachment)

- `[is\_attachment()](https://codex.wordpress.org/Function_Reference/is_attachment "Function Reference/is attachment")`

### [Attachment Is Image](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#attachment-is-image)

- `[wp\_attachment\_is\_image( $post\_id )](https://codex.wordpress.org/Function_Reference/wp_attachment_is_image "Function Reference/wp attachment is image")`

### [A Local Attachment](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-local-attachment)

- `[is\_local\_attachment( $url )](https://codex.wordpress.org/Function_Reference/is_local_attachment "Function Reference/is local attachment")`

### [Post Type Exists](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#post-type-exists)

- `[post\_type\_exists( $post\_type )](https://codex.wordpress.org/Function_Reference/post_type_exists "Function Reference/post type exists")`

### [Is Main Query](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-main-query)

- [is\_main\_query()](https://codex.wordpress.org/Function_Reference/is_main_query "Function Reference/is main query")

### [A New Day](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-new-day)

- `[is\_new\_day()](https://codex.wordpress.org/Function_Reference/is_new_day "Function Reference/is new day")`

### [A Syndication](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-syndication)

- `[is\_feed()](https://codex.wordpress.org/Function_Reference/is_feed "Function Reference/is feed")`

### [A Trackback](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-trackback)

- `[is\_trackback()](https://codex.wordpress.org/Function_Reference/is_trackback "Function Reference/is trackback")`

### [A Preview](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-preview)

- `[is\_preview()](https://codex.wordpress.org/Function_Reference/is_preview "Function Reference/is preview")`

### [Has An Excerpt](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#has-an-excerpt)

- `[has\_excerpt()](https://codex.wordpress.org/Function_Reference/has_excerpt "Function Reference/has excerpt")`

### [Has A Nav Menu Assigned](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#has-a-nav-menu-assigned)

- `[has\_nav\_menu()](https://codex.wordpress.org/Function_Reference/has_nav_menu "Function Reference/has nav menu")`

### [Is Blog Installed](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-blog-installed)

- `[is\_blog\_installed()](https://codex.wordpress.org/Function_Reference/is_blog_installed "Function Reference/is blog installed")`

### [Part of a Network (Multisite)](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#part-of-a-network-multisite)

- `[is\_multisite()](https://codex.wordpress.org/Function_Reference/is_multisite "Function Reference/is multisite")`
- `[is\_main\_site()](https://codex.wordpress.org/Function_Reference/is_main_site "Function Reference/is main site")`
- `[is\_super\_admin()](https://codex.wordpress.org/Function_Reference/is_super_admin "Function Reference/is super admin")`

### [An Active Plugin](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#an-active-plugin)

- `[is\_plugin\_active( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_active "Function Reference/is plugin active")`
- `[is\_plugin\_inactive( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_inactive "Function Reference/is plugin inactive")`
- `[is\_plugin\_active\_for\_network( $path )](https://codex.wordpress.org/Function_Reference/is_plugin_active_for_network "Function Reference/is plugin active for network")`
- `[is\_plugin\_page()](https://codex.wordpress.org/Function_Reference/is_plugin_page "Function Reference/is plugin page")`

### [A Child Theme](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#a-child-theme)

- `[is\_child\_theme()](https://codex.wordpress.org/Function_Reference/is_child_theme "Function Reference/is child theme")`

### [Theme supports a feature](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#theme-supports-a-feature)

- `[current\_theme\_supports()](https://codex.wordpress.org/Function_Reference/current_theme_supports "Function Reference/current theme supports")`

### [Is Previewed in the Customizer](https://developer.wordpress.org/themes/classic-themes/references/list-of-conditional-tags/\#is-previewed-in-the-customizer)

- `[is\_customize\_preview()](https://codex.wordpress.org/Function_Reference/is_customize_preview "Function Reference/is customize preview")`

First published

January 12, 2017

Last updated

February 5, 2020

[PreviousList of Template TagsPrevious: List of Template Tags](https://developer.wordpress.org/themes/classic-themes/references/list-of-template-tags/)

[NextCreditsNext: Credits](https://developer.wordpress.org/themes/credits/)

Notifications