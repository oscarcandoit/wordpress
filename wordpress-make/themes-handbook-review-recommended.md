---
url: https://make.wordpress.org/themes/handbook/review/recommended/
scraped_at: 2025-10-20T03:00:56.135Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fthemes%2Fhandbook%2Freview%2Frecommended%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/themes/handbook/review/recommended/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Themes](https://make.wordpress.org/themes)

Recommended

[Home](https://make.wordpress.org/themes)[Handbook](https://make.wordpress.org/themes/handbook/)[Review Process](https://make.wordpress.org/themes/handbook/review/)Recommended

Search

# Recommended

## In this article

Table of Contents

- [Comments](https://make.wordpress.org/themes/handbook/review/recommended/#comments)
- [Theme support](https://make.wordpress.org/themes/handbook/review/recommended/#theme-support)
- [Editor style](https://make.wordpress.org/themes/handbook/review/recommended/#editor-style)
- [Block patterns and block styles](https://make.wordpress.org/themes/handbook/review/recommended/#block-patterns-and-block-styles)
- [Post navigation](https://make.wordpress.org/themes/handbook/review/recommended/#post-navigation)
- [Recommended styles](https://make.wordpress.org/themes/handbook/review/recommended/#recommended-styles)
- [Avatars](https://make.wordpress.org/themes/handbook/review/recommended/#avatars)
- [Post formats](https://make.wordpress.org/themes/handbook/review/recommended/#post-formats)
- [Widget areas and widgets](https://make.wordpress.org/themes/handbook/review/recommended/#widget-areas-and-widgets)
- [Favicons and Site Icons should not be included](https://make.wordpress.org/themes/handbook/review/recommended/#favicons-and-site-icons-should-not-be-included)
- [WP\_title should not be used](https://make.wordpress.org/themes/handbook/review/recommended/#wp_title-should-not-be-used)
- [Document <title> tag should not be used](https://make.wordpress.org/themes/handbook/review/recommended/#document-title-tag-should-not-be-used)

[↑ Back to top](https://make.wordpress.org/themes/handbook/review/recommended/#wp--skip-link--target)

## [Comments](https://make.wordpress.org/themes/handbook/review/recommended/\#comments)

Themes are recommended to support comments, including nested comments and comment navigation.

If comments are not supported, the team recommends that this is documented as a limitation, in the theme readme file.

## [Theme support](https://make.wordpress.org/themes/handbook/review/recommended/\#theme-support)

The following theme support is recommended for classic themes

- `add_theme_support( "custom-header", $args )`
- `add_theme_support( "custom-background", $args )`
- `add_theme_support( "custom-logo", $args )`
- `add_theme_support( "html5", $args )`
- `add_theme_support( "responsive-embeds" )`
- `add_theme_support( "align-wide" )`
- `add_theme_support( "wp-block-styles" )`
- `add_theme_support( "post-thumbnails" )`

[Read more about theme support.](https://developer.wordpress.org/reference/functions/add_theme_support/)

## [Editor style](https://make.wordpress.org/themes/handbook/review/recommended/\#editor-style)

For a good user experience, it is recommended to include an editor style and that the editors and the front match.

## [Block patterns and block styles](https://make.wordpress.org/themes/handbook/review/recommended/\#block-patterns-and-block-styles)

Themes are recommended to include [block patterns](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-patterns/) and [custom block styles](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-styles/).

## [Post navigation](https://make.wordpress.org/themes/handbook/review/recommended/\#post-navigation)

Themes are recommended to support post navigation using either:

- [posts\_nav\_link()](https://developer.wordpress.org/reference/functions/posts_nav_link/)
- [paginate\_links()](https://developer.wordpress.org/reference/functions/paginate_links/)
- [the\_posts\_pagination()](https://developer.wordpress.org/reference/functions/the_posts_pagination/)
- [the\_posts\_navigation()](https://developer.wordpress.org/reference/functions/the_posts_navigation/)

## [Recommended styles](https://make.wordpress.org/themes/handbook/review/recommended/\#recommended-styles)

For classic themes, WordPress outputs the following CSS classes that themes are recommended to style:

- .sticky
- .bypostauthor
- .alignleft
- .alignright
- .aligncenter
- .wp-caption
- .wp-caption-text
- .gallery-caption
- .screen-reader-text

## [Avatars](https://make.wordpress.org/themes/handbook/review/recommended/\#avatars)

Include support for the standard avatar functions, [get\_avatar()](https://developer.wordpress.org/reference/functions/get_avatar/) or [wp\_list\_comments()](https://developer.wordpress.org/reference/functions/wp_list_comments/)

## [Post formats](https://make.wordpress.org/themes/handbook/review/recommended/\#post-formats)

If post formats are included, it is recommended to style these in a way that distinguishes them from standard post and page content.

## [Widget areas and widgets](https://make.wordpress.org/themes/handbook/review/recommended/\#widget-areas-and-widgets)

Classic themes are recommended to support widgets.

Sidebars need to be registered in a custom function hooked to the `widgets_init ` action. See: [register\_sidebar()](https://developer.wordpress.org/reference/functions/register_sidebar).

* * *

## [Favicons and Site Icons should not be included](https://make.wordpress.org/themes/handbook/review/recommended/\#favicons-and-site-icons-should-not-be-included)

Themes are recommended to **not** include their own favicon or site icon.

Favicons are handled by the Site Icon setting in the customizer since WordPress version 4.3.

## [WP\_title should not be used](https://make.wordpress.org/themes/handbook/review/recommended/\#wp_title-should-not-be-used)

wp\_title() was historically used for the document `<title>` tag and was never intended for other purposes.

Use ` add_theme_support( "title-tag" )` instead.

## [Document <title> tag should not be used](https://make.wordpress.org/themes/handbook/review/recommended/\#document-title-tag-should-not-be-used)

Document titles must not be hard coded, use `add_theme_support( "title-tag" )` instead.

First published

November 4, 2014

Last updated

August 11, 2021

[PreviousTheme Unit TestPrevious: Theme Unit Test](https://make.wordpress.org/themes/handbook/review/theme-unit-test/)

[NextResourcesNext: Resources](https://make.wordpress.org/themes/handbook/review/resources/)

[WordPress.org](https://wordpress.org/)[WordPress.org](https://wordpress.org/)

- [Visit our X (formerly Twitter) account](https://www.x.com/WordPress)
- [Visit our Bluesky account](https://bsky.app/profile/wordpress.org)
- [Visit our Mastodon account](https://mastodon.world/@WordPress)
- [Visit our Threads account](https://www.threads.net/@wordpress)
- [Visit our Facebook page](https://www.facebook.com/WordPress/)
- [Visit our Instagram account](https://www.instagram.com/wordpress/)
- [Visit our LinkedIn account](https://www.linkedin.com/company/wordpress)
- [Visit our TikTok account](https://www.tiktok.com/@wordpress)
- [Visit our YouTube channel](https://www.youtube.com/wordpress)
- [Visit our Tumblr account](https://wordpress.tumblr.com/)

![Code is Poetry](https://s.w.org/style/images/code-is-poetry-for-dark-bg.svg)

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment