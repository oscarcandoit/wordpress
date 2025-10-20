---
url: https://wordpress.org/documentation/wordpress-version/version-6-8
scraped_at: 2025-10-20T02:01:48.938Z
---

[Skip to content](https://wordpress.org/documentation/wordpress-version/version-6-8/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Version 6.8

[Home](https://wordpress.org/documentation)Version 6.8

Search documentation

# Version 6.8

## In this article

Table of Contents

- [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-8/#installation-update-information)
- [Learn more about WordPress 6.8](https://wordpress.org/documentation/wordpress-version/version-6-8/#learn-more-about-wordpress-6-6)
- [The 6.8 release squad](https://wordpress.org/documentation/wordpress-version/version-6-8/#the-6-6-release-squad)
- [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-8/#changelog)
  - [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-8/#updated-packages)
  - [List of files revised](https://wordpress.org/documentation/wordpress-version/version-6-8/#list-of-files-revised)

[↑ Back to top](https://wordpress.org/documentation/wordpress-version/version-6-8/#wp--skip-link--target)

On April 15, 2025, WordPress 6.8 “Cecil” was released to the public. For more information on this release, read the [WordPress 6.8 announcement](https://wordpress.org/news/2025/04/cecil).

For Version 6.8, the database version ( **db\_version** in **wp\_options**) was `58975` and Trac revision was `60168`.

A [full list of tickets included in 6.8](https://core.trac.wordpress.org/milestone/6.8) can be found on [Trac](https://core.trac.wordpress.org/).

## [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-8/\#installation-update-information)

To download WordPress 6.8, update automatically from the Dashboard > Updates menu in your site’s admin area or visit the [release archive](https://wordpress.org/download/release-archive/).

For step-by-step instructions on installing and updating WordPress:

- [Updating WordPress](https://wordpress.org/documentation/article/updating-wordpress/)

If you are new to WordPress, we recommend that you begin with the following:

- [New To WordPress – Where to Start](https://wordpress.org/support/article/new_to_wordpress_-_where_to_start/)
- [First Steps with WordPress (Classic Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-classic/) or [First Steps with WordPress (Block Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-block-editor/)
- [Upgrading WordPress Extended](https://wordpress.org/documentation/article/upgrading-wordpress-extended-instructions/)

## [Learn more about WordPress 6.8](https://wordpress.org/documentation/wordpress-version/version-6-8/\#learn-more-about-wordpress-6-6)

[Learn WordPress](https://learn.wordpress.org/) is a free resource for new and experienced WordPress users. Learn is stocked with how-to videos on using various features in WordPress, [interactive workshops](https://learn.wordpress.org/online-workshops/) for exploring topics in-depth, and lesson plans for diving deep into specific areas of WordPress.

Explore the [WordPress 6.8 Field Guide](https://make.wordpress.org/core/2025/03/28/wordpress-6-8-field-guide/). Learn about the changes in this release with detailed developer notes to help you build with WordPress.

Read the WordPress 6.8 Release Notes for information on installation, enhancements, fixed issues, release contributors, learning resources, and the list of file changes. Review the list of [performance improvements](https://make.wordpress.org/core/2025/04/16/wordpress-6-8-performance-improvements/).

Visit the [feature showcase](https://wordpress.org/download/releases/6-8/) for a full overview of all the new features and enhancements in WordPress 6.8.

## [The 6.8 release squad](https://wordpress.org/documentation/wordpress-version/version-6-8/\#the-6-6-release-squad)

Every release comes to you from a dedicated team of enthusiastic contributors who help keep things on track and moving smoothly. The team that has led 6.8 is a cross-functional group of contributors who are always ready to champion ideas, remove blockers, and resolve issues.

- Release Lead – [Matt Mullenweg](https://profiles.wordpress.org/matt/)
- Coordination – [Jeffrey Paul](https://profiles.wordpress.org/jeffpaul/) & [Michelle Frechette](https://profiles.wordpress.org/michelleames/)
- Tech Leads – [Joe McGill](https://profiles.wordpress.org/joemcgill/), [Jonathan Desrosiers](https://profiles.wordpress.org/desrosj/), [George Mamadashvili](https://profiles.wordpress.org/mamaduka/)
- Triage Lead – [Jb Audras](https://profiles.wordpress.org/audrasjb/)
- Design Lead – [Tammie Lister](https://profiles.wordpress.org/karmatosed/)
- Performance Lead – [Felix Arntz](https://profiles.wordpress.org/flixos90/)
- Test Lead – [Krupa Nanda](https://profiles.wordpress.org/krupajnanda/)

## [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-8/\#changelog)

### [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-8/\#updated-packages)

```
@wordpress/a11y – 4.19.1
@wordpress/annotations – 3.19.1
@wordpress/api-fetch – 7.19.1
@wordpress/autop – 4.19.1
@wordpress/blob – 4.19.1
@wordpress/block-directory – 5.19.5
@wordpress/block-editor – 14.14.4
@wordpress/block-library – 9.19.4
@wordpress/block-serialization-default-parser – 5.19.1
@wordpress/blocks – 14.8.1
@wordpress/commands – 1.19.2
@wordpress/components – 29.5.2
@wordpress/compose – 7.19.1
@wordpress/core-commands – 1.19.4
@wordpress/core-data – 7.19.4
@wordpress/customize-widgets – 5.19.4
@wordpress/data – 10.19.1
@wordpress/data-controls – 4.19.1
@wordpress/dataviews – 4.15.2
@wordpress/date – 5.19.1
@wordpress/deprecated – 4.19.1
@wordpress/dom – 4.19.1
@wordpress/dom-ready – 4.19.1
@wordpress/edit-post – 8.19.5
@wordpress/edit-site – 6.19.5
@wordpress/edit-widgets – 6.19.4
@wordpress/editor – 14.19.5
@wordpress/element – 6.19.1
@wordpress/escape-html – 3.19.1
@wordpress/fields – 0.11.4
@wordpress/format-library – 5.19.4
@wordpress/hooks – 4.19.1
@wordpress/html-entities – 4.19.1
@wordpress/i18n – 5.19.1
@wordpress/icons – 10.19.1
@wordpress/interactivity – 6.19.1
@wordpress/interactivity-router – 2.19.1
@wordpress/interface – 9.4.2
@wordpress/is-shallow-equal – 5.19.1
@wordpress/keyboard-shortcuts – 5.19.1
@wordpress/keycodes – 4.19.1
@wordpress/list-reusable-blocks – 5.19.2
@wordpress/media-utils – 5.19.1
@wordpress/notices – 5.19.1
@wordpress/nux – 9.19.2
@wordpress/patterns – 2.19.4
@wordpress/plugins – 7.19.2
@wordpress/preferences – 4.19.2
@wordpress/preferences-persistence – 2.19.1
@wordpress/primitives – 4.19.1
@wordpress/priority-queue – 3.19.1
@wordpress/private-apis – 1.19.1
@wordpress/redux-routine – 5.19.1
@wordpress/reusable-blocks – 5.19.4
@wordpress/rich-text – 7.19.1
@wordpress/router – 1.19.1
@wordpress/server-side-render – 5.19.2
@wordpress/shortcode – 4.19.1
@wordpress/style-engine – 2.19.1
@wordpress/sync – 1.19.1
@wordpress/token-list – 3.19.1
@wordpress/undo-manager – 1.19.1
@wordpress/upload-media – 0.4.2
@wordpress/url – 4.19.1
@wordpress/viewport – 6.19.1
@wordpress/warning – 3.19.1
@wordpress/widgets – 4.19.4
@wordpress/wordcount – 4.19.1
json2php – 0.0.12
@playwright/test – 1.50.1
@wordpress/babel-preset-default – 8.19.1
@wordpress/dependency-extraction-webpack-plugin – 6.19.1
@wordpress/e2e-test-utils – 11.19.1
@wordpress/e2e-test-utils-playwright – 1.19.1
@wordpress/prettier-config – 4.19.1
@wordpress/scripts – 30.12.1
chalk – 5.4.1
copy-webpack-plugin – 13.0.0
dotenv – 16.4.7
dotenv-expand – 12.0.1
grunt-sass – ~4.0.0
postcss – 8.5.3
prettier – npm:wp-prettier@3.0.3
qunit – ~2.23.1
sass – 1.85.1
terser-webpack-plugin – 5.3.12
uglify-js – ^3.19.3
uuid – 11.1.0
wait-on – 8.0.2
webpack – 5.98.0
```

### [List of files revised](https://wordpress.org/documentation/wordpress-version/version-6-8/\#list-of-files-revised)

```
Modified files:
license.txt
readme.html
wp-admin/about.php
wp-admin/admin-functions.php
wp-admin/admin-header.php
wp-admin/admin-post.php
wp-admin/admin.php
wp-admin/async-upload.php
wp-admin/credits.php
wp-admin/css/about-rtl.css
wp-admin/css/about-rtl.min.css
wp-admin/css/about.css
wp-admin/css/about.min.css
wp-admin/css/admin-menu-rtl.css
wp-admin/css/admin-menu-rtl.min.css
wp-admin/css/admin-menu.css
wp-admin/css/admin-menu.min.css
wp-admin/css/colors/_admin.scss
wp-admin/css/colors/_mixins.scss
wp-admin/css/colors/_variables.scss
wp-admin/css/colors/blue/colors.scss
wp-admin/css/colors/coffee/colors.scss
wp-admin/css/colors/ectoplasm/colors.scss
wp-admin/css/colors/light/colors.scss
wp-admin/css/colors/midnight/colors.scss
wp-admin/css/colors/modern/colors-rtl.css
wp-admin/css/colors/modern/colors-rtl.min.css
wp-admin/css/colors/modern/colors.css
wp-admin/css/colors/modern/colors.min.css
wp-admin/css/colors/modern/colors.scss
wp-admin/css/colors/ocean/colors.scss
wp-admin/css/colors/sunrise/colors.scss
wp-admin/css/common-rtl.css
wp-admin/css/common-rtl.min.css
wp-admin/css/common.css
wp-admin/css/common.min.css
wp-admin/css/customize-controls-rtl.css
wp-admin/css/customize-controls-rtl.min.css
wp-admin/css/customize-controls.css
wp-admin/css/customize-controls.min.css
wp-admin/css/customize-nav-menus-rtl.css
wp-admin/css/customize-nav-menus-rtl.min.css
wp-admin/css/customize-nav-menus.css
wp-admin/css/customize-nav-menus.min.css
wp-admin/css/customize-widgets-rtl.css
wp-admin/css/customize-widgets-rtl.min.css
wp-admin/css/customize-widgets.css
wp-admin/css/customize-widgets.min.css
wp-admin/css/install-rtl.css
wp-admin/css/install-rtl.min.css
wp-admin/css/install.css
wp-admin/css/install.min.css
wp-admin/css/login-rtl.css
wp-admin/css/login-rtl.min.css
wp-admin/css/login.css
wp-admin/css/login.min.css
wp-admin/css/media-rtl.css
wp-admin/css/media-rtl.min.css
wp-admin/css/media.css
wp-admin/css/media.min.css
wp-admin/css/nav-menus-rtl.css
wp-admin/css/nav-menus-rtl.min.css
wp-admin/css/nav-menus.css
wp-admin/css/nav-menus.min.css
wp-admin/css/site-health-rtl.css
wp-admin/css/site-health-rtl.min.css
wp-admin/css/site-health.css
wp-admin/css/site-health.min.css
wp-admin/css/themes-rtl.css
wp-admin/css/themes-rtl.min.css
wp-admin/css/themes.css
wp-admin/css/themes.min.css
wp-admin/custom-background.php
wp-admin/custom-header.php
wp-admin/customize.php
wp-admin/edit-form-advanced.php
wp-admin/edit-form-blocks.php
wp-admin/edit-form-comment.php
wp-admin/edit-link-form.php
wp-admin/edit-tag-form.php
wp-admin/freedoms.php
wp-admin/images/about-release-badge.svg
wp-admin/import.php
wp-admin/includes/admin-filters.php
wp-admin/includes/ajax-actions.php
wp-admin/includes/bookmark.php
wp-admin/includes/class-custom-background.php
wp-admin/includes/class-custom-image-header.php
wp-admin/includes/class-ftp.php
wp-admin/includes/class-pclzip.php
wp-admin/includes/class-theme-installer-skin.php
wp-admin/includes/class-wp-automatic-updater.php
wp-admin/includes/class-wp-comments-list-table.php
wp-admin/includes/class-wp-debug-data.php
wp-admin/includes/class-wp-importer.php
wp-admin/includes/class-wp-list-table.php
wp-admin/includes/class-wp-media-list-table.php
wp-admin/includes/class-wp-ms-sites-list-table.php
wp-admin/includes/class-wp-ms-themes-list-table.php
wp-admin/includes/class-wp-ms-users-list-table.php
wp-admin/includes/class-wp-posts-list-table.php
wp-admin/includes/class-wp-privacy-policy-content.php
wp-admin/includes/class-wp-privacy-requests-table.php
wp-admin/includes/class-wp-site-health-auto-updates.php
wp-admin/includes/class-wp-site-health.php
wp-admin/includes/class-wp-theme-install-list-table.php
wp-admin/includes/class-wp-themes-list-table.php
wp-admin/includes/class-wp-upgrader.php
wp-admin/includes/credits.php
wp-admin/includes/file.php
wp-admin/includes/image-edit.php
wp-admin/includes/image.php
wp-admin/includes/media.php
wp-admin/includes/meta-boxes.php
wp-admin/includes/misc.php
wp-admin/includes/ms.php
wp-admin/includes/nav-menu.php
wp-admin/includes/network.php
wp-admin/includes/post.php
wp-admin/includes/revision.php
wp-admin/includes/schema.php
wp-admin/includes/template.php
wp-admin/includes/update-core.php
wp-admin/includes/update.php
wp-admin/includes/upgrade.php
wp-admin/includes/user.php
wp-admin/install.php
wp-admin/js/common.js
wp-admin/js/common.min.js
wp-admin/js/customize-controls.min.js
wp-admin/js/customize-nav-menus.js
wp-admin/js/customize-nav-menus.min.js
wp-admin/js/customize-widgets.min.js
wp-admin/js/dashboard.js
wp-admin/js/dashboard.min.js
wp-admin/js/edit-comments.js
wp-admin/js/edit-comments.min.js
wp-admin/js/editor.js
wp-admin/js/editor.min.js
wp-admin/js/nav-menu.js
wp-admin/js/nav-menu.min.js
wp-admin/js/postbox.js
wp-admin/js/postbox.min.js
wp-admin/js/tags.js
wp-admin/js/tags.min.js
wp-admin/js/theme-plugin-editor.js
wp-admin/js/theme-plugin-editor.min.js
wp-admin/js/theme.js
wp-admin/js/theme.min.js
wp-admin/js/updates.js
wp-admin/js/updates.min.js
wp-admin/link-add.php
wp-admin/link-manager.php
wp-admin/media-upload.php
wp-admin/menu-header.php
wp-admin/menu.php
wp-admin/nav-menus.php
wp-admin/network/menu.php
wp-admin/network/settings.php
wp-admin/network/site-new.php
wp-admin/network/site-users.php
wp-admin/network/sites.php
wp-admin/network/themes.php
wp-admin/network/user-new.php
wp-admin/network/users.php
wp-admin/options-discussion.php
wp-admin/options-general.php
wp-admin/options-head.php
wp-admin/options-media.php
wp-admin/options-privacy.php
wp-admin/plugin-editor.php
wp-admin/plugins.php
wp-admin/privacy.php
wp-admin/setup-config.php
wp-admin/site-editor.php
wp-admin/site-health-info.php
wp-admin/theme-editor.php
wp-admin/theme-install.php
wp-admin/themes.php
wp-admin/upgrade.php
wp-admin/upload.php
wp-admin/user-edit.php
wp-admin/user-new.php
wp-admin/user/menu.php
wp-admin/users.php
wp-content/plugins/akismet/akismet.php
wp-content/plugins/akismet/class.akismet.php
wp-content/plugins/akismet/readme.txt
wp-content/plugins/hello.php
wp-content/themes/twentytwentyfive/patterns/banner-intro-image.php
wp-content/themes/twentytwentyfive/patterns/header-centered.php
wp-content/themes/twentytwentyfive/patterns/header-columns.php
wp-content/themes/twentytwentyfive/patterns/header-large-title.php
wp-content/themes/twentytwentyfive/patterns/header.php
wp-content/themes/twentytwentyfive/patterns/hero-full-width-image.php
wp-content/themes/twentytwentyfive/patterns/template-404-vertical-header-blog.php
wp-content/themes/twentytwentyfive/patterns/template-archive-text-blog.php
wp-content/themes/twentytwentyfive/patterns/template-archive-vertical-header-blog.php
wp-content/themes/twentytwentyfive/patterns/template-home-text-blog.php
wp-content/themes/twentytwentyfive/patterns/template-home-vertical-header-blog.php
wp-content/themes/twentytwentyfive/patterns/template-page-vertical-header-blog.php
wp-content/themes/twentytwentyfive/patterns/template-query-loop-text-blog.php
wp-content/themes/twentytwentyfive/patterns/template-query-loop-vertical-header-blog.php
wp-content/themes/twentytwentyfive/patterns/template-search-text-blog.php
wp-content/themes/twentytwentyfive/patterns/template-single-text-blog.php
wp-content/themes/twentytwentyfive/patterns/vertical-header.php
wp-content/themes/twentytwentyfive/readme.txt
wp-content/themes/twentytwentyfive/style.css
wp-content/themes/twentytwentyfive/theme.json
wp-content/themes/twentytwentyfour/readme.txt
wp-content/themes/twentytwentyfour/style.css
wp-content/themes/twentytwentythree/readme.txt
wp-content/themes/twentytwentythree/style.css
wp-includes/PHPMailer/PHPMailer.php
wp-includes/PHPMailer/SMTP.php
wp-includes/admin-bar.php
wp-includes/assets/script-loader-packages.min.php
wp-includes/assets/script-loader-packages.php
wp-includes/assets/script-loader-react-refresh-entry.min.php
wp-includes/assets/script-loader-react-refresh-entry.php
wp-includes/assets/script-modules-packages.min.php
wp-includes/assets/script-modules-packages.php
wp-includes/block-editor.php
wp-includes/block-patterns.php
wp-includes/block-supports/block-style-variations.php
wp-includes/block-supports/layout.php
wp-includes/block-template-utils.php
wp-includes/block-template.php
wp-includes/blocks.php
wp-includes/blocks/archives/block.json
wp-includes/blocks/archives/editor-rtl.css
wp-includes/blocks/archives/editor-rtl.min.css
wp-includes/blocks/archives/editor.css
wp-includes/blocks/archives/editor.min.css
wp-includes/blocks/block.php
wp-includes/blocks/blocks-json.php
wp-includes/blocks/button/block.json
wp-includes/blocks/button/style-rtl.css
wp-includes/blocks/button/style-rtl.min.css
wp-includes/blocks/button/style.css
wp-includes/blocks/button/style.min.css
wp-includes/blocks/buttons/style-rtl.css
wp-includes/blocks/buttons/style-rtl.min.css
wp-includes/blocks/buttons/style.css
wp-includes/blocks/buttons/style.min.css
wp-includes/blocks/categories/block.json
wp-includes/blocks/code/style-rtl.css
wp-includes/blocks/code/style-rtl.min.css
wp-includes/blocks/code/style.css
wp-includes/blocks/code/style.min.css
wp-includes/blocks/comment-template/style-rtl.css
wp-includes/blocks/comment-template/style-rtl.min.css
wp-includes/blocks/comment-template/style.css
wp-includes/blocks/comment-template/style.min.css
wp-includes/blocks/comments-pagination/block.json
wp-includes/blocks/comments-pagination/editor-rtl.css
wp-includes/blocks/comments-pagination/editor-rtl.min.css
wp-includes/blocks/comments-pagination/editor.css
wp-includes/blocks/comments-pagination/editor.min.css
wp-includes/blocks/comments-pagination/style-rtl.css
wp-includes/blocks/comments-pagination/style-rtl.min.css
wp-includes/blocks/comments-pagination/style.css
wp-includes/blocks/comments-pagination/style.min.css
wp-includes/blocks/comments/block.json
wp-includes/blocks/comments/editor-rtl.css
wp-includes/blocks/comments/editor-rtl.min.css
wp-includes/blocks/comments/editor.css
wp-includes/blocks/comments/editor.min.css
wp-includes/blocks/comments/style-rtl.css
wp-includes/blocks/comments/style-rtl.min.css
wp-includes/blocks/comments/style.css
wp-includes/blocks/comments/style.min.css
wp-includes/blocks/cover.php
wp-includes/blocks/cover/block.json
wp-includes/blocks/cover/editor-rtl.css
wp-includes/blocks/cover/editor-rtl.min.css
wp-includes/blocks/cover/editor.css
wp-includes/blocks/cover/editor.min.css
wp-includes/blocks/cover/style-rtl.css
wp-includes/blocks/cover/style-rtl.min.css
wp-includes/blocks/cover/style.css
wp-includes/blocks/cover/style.min.css
wp-includes/blocks/details/block.json
wp-includes/blocks/file/block.json
wp-includes/blocks/file/view.js
wp-includes/blocks/freeform/editor-rtl.css
wp-includes/blocks/freeform/editor-rtl.min.css
wp-includes/blocks/freeform/editor.css
wp-includes/blocks/freeform/editor.min.css
wp-includes/blocks/gallery/editor-rtl.css
wp-includes/blocks/gallery/editor-rtl.min.css
wp-includes/blocks/gallery/editor.css
wp-includes/blocks/gallery/editor.min.css
wp-includes/blocks/heading/block.json
wp-includes/blocks/home-link.php
wp-includes/blocks/image.php
wp-includes/blocks/image/block.json
wp-includes/blocks/image/editor-rtl.css
wp-includes/blocks/image/editor-rtl.min.css
wp-includes/blocks/image/editor.css
wp-includes/blocks/image/editor.min.css
wp-includes/blocks/image/style-rtl.css
wp-includes/blocks/image/style-rtl.min.css
wp-includes/blocks/image/style.css
wp-includes/blocks/image/style.min.css
wp-includes/blocks/image/view.js
wp-includes/blocks/image/view.min.js
wp-includes/blocks/latest-posts/block.json
wp-includes/blocks/latest-posts/style-rtl.css
wp-includes/blocks/latest-posts/style-rtl.min.css
wp-includes/blocks/latest-posts/style.css
wp-includes/blocks/latest-posts/style.min.css
wp-includes/blocks/list-item/block.json
wp-includes/blocks/media-text/style-rtl.css
wp-includes/blocks/media-text/style-rtl.min.css
wp-includes/blocks/media-text/style.css
wp-includes/blocks/media-text/style.min.css
wp-includes/blocks/navigation-link.php
wp-includes/blocks/navigation-link/editor-rtl.css
wp-includes/blocks/navigation-link/editor-rtl.min.css
wp-includes/blocks/navigation-link/editor.css
wp-includes/blocks/navigation-link/editor.min.css
wp-includes/blocks/navigation-submenu.php
wp-includes/blocks/navigation.php
wp-includes/blocks/navigation/style-rtl.css
wp-includes/blocks/navigation/style-rtl.min.css
wp-includes/blocks/navigation/style.css
wp-includes/blocks/navigation/style.min.css
wp-includes/blocks/navigation/view.js
wp-includes/blocks/navigation/view.min.js
wp-includes/blocks/page-list/block.json
wp-includes/blocks/page-list/style-rtl.css
wp-includes/blocks/page-list/style-rtl.min.css
wp-includes/blocks/page-list/style.css
wp-includes/blocks/page-list/style.min.css
wp-includes/blocks/paragraph/editor-rtl.css
wp-includes/blocks/paragraph/editor-rtl.min.css
wp-includes/blocks/paragraph/editor.css
wp-includes/blocks/paragraph/editor.min.css
wp-includes/blocks/pattern.php
wp-includes/blocks/pattern/block.json
wp-includes/blocks/post-author-name.php
wp-includes/blocks/post-author-name/block.json
wp-includes/blocks/post-author.php
wp-includes/blocks/post-author/block.json
wp-includes/blocks/post-comments-form/block.json
wp-includes/blocks/post-comments-form/style-rtl.css
wp-includes/blocks/post-comments-form/style-rtl.min.css
wp-includes/blocks/post-comments-form/style.css
wp-includes/blocks/post-comments-form/style.min.css
wp-includes/blocks/post-content/block.json
wp-includes/blocks/post-date/block.json
wp-includes/blocks/post-featured-image/block.json
wp-includes/blocks/post-featured-image/editor-rtl.css
wp-includes/blocks/post-featured-image/editor-rtl.min.css
wp-includes/blocks/post-featured-image/editor.css
wp-includes/blocks/post-featured-image/editor.min.css
wp-includes/blocks/post-template/block.json
wp-includes/blocks/post-template/style-rtl.css
wp-includes/blocks/post-template/style-rtl.min.css
wp-includes/blocks/post-template/style.css
wp-includes/blocks/post-template/style.min.css
wp-includes/blocks/post-terms.php
wp-includes/blocks/post-title/block.json
wp-includes/blocks/pullquote/style-rtl.css
wp-includes/blocks/pullquote/style-rtl.min.css
wp-includes/blocks/pullquote/style.css
wp-includes/blocks/pullquote/style.min.css
wp-includes/blocks/query-no-results/block.json
wp-includes/blocks/query-pagination-previous.php
wp-includes/blocks/query-title/block.json
wp-includes/blocks/query.php
wp-includes/blocks/query/block.json
wp-includes/blocks/query/editor-rtl.css
wp-includes/blocks/query/editor-rtl.min.css
wp-includes/blocks/query/editor.css
wp-includes/blocks/query/editor.min.css
wp-includes/blocks/query/view.js
wp-includes/blocks/query/view.min.js
wp-includes/blocks/read-more/style-rtl.css
wp-includes/blocks/read-more/style-rtl.min.css
wp-includes/blocks/read-more/style.css
wp-includes/blocks/read-more/style.min.css
wp-includes/blocks/require-dynamic-blocks.php
wp-includes/blocks/rss.php
wp-includes/blocks/rss/block.json
wp-includes/blocks/rss/editor-rtl.css
wp-includes/blocks/rss/editor-rtl.min.css
wp-includes/blocks/rss/editor.css
wp-includes/blocks/rss/editor.min.css
wp-includes/blocks/rss/style-rtl.css
wp-includes/blocks/rss/style-rtl.min.css
wp-includes/blocks/rss/style.css
wp-includes/blocks/rss/style.min.css
wp-includes/blocks/search.php
wp-includes/blocks/search/style-rtl.css
wp-includes/blocks/search/style-rtl.min.css
wp-includes/blocks/search/style.css
wp-includes/blocks/search/style.min.css
wp-includes/blocks/search/view.js
wp-includes/blocks/search/view.min.js
wp-includes/blocks/separator/block.json
wp-includes/blocks/site-logo/block.json
wp-includes/blocks/site-logo/editor-rtl.css
wp-includes/blocks/site-logo/editor-rtl.min.css
wp-includes/blocks/site-logo/editor.css
wp-includes/blocks/site-logo/editor.min.css
wp-includes/blocks/site-title.php
wp-includes/blocks/site-title/block.json
wp-includes/blocks/social-link.php
wp-includes/blocks/social-link/block.json
wp-includes/blocks/social-link/editor-rtl.css
wp-includes/blocks/social-link/editor-rtl.min.css
wp-includes/blocks/social-link/editor.css
wp-includes/blocks/social-link/editor.min.css
wp-includes/blocks/social-links/editor-rtl.css
wp-includes/blocks/social-links/editor-rtl.min.css
wp-includes/blocks/social-links/editor.css
wp-includes/blocks/social-links/editor.min.css
wp-includes/blocks/social-links/style-rtl.css
wp-includes/blocks/social-links/style-rtl.min.css
wp-includes/blocks/social-links/style.css
wp-includes/blocks/social-links/style.min.css
wp-includes/blocks/table/block.json
wp-includes/blocks/tag-cloud/editor-rtl.css
wp-includes/blocks/tag-cloud/editor-rtl.min.css
wp-includes/blocks/tag-cloud/editor.css
wp-includes/blocks/tag-cloud/editor.min.css
wp-includes/blocks/template-part.php
wp-includes/blocks/text-columns/style-rtl.css
wp-includes/blocks/text-columns/style-rtl.min.css
wp-includes/blocks/text-columns/style.css
wp-includes/blocks/text-columns/style.min.css
wp-includes/blocks/video/editor-rtl.css
wp-includes/blocks/video/editor-rtl.min.css
wp-includes/blocks/video/editor.css
wp-includes/blocks/video/editor.min.css
wp-includes/bookmark-template.php
wp-includes/category.php
wp-includes/certificates/ca-bundle.crt
wp-includes/class-IXR.php
wp-includes/class-pop3.php
wp-includes/class-walker-nav-menu.php
wp-includes/class-wp-application-passwords.php
wp-includes/class-wp-block-metadata-registry.php
wp-includes/class-wp-block-styles-registry.php
wp-includes/class-wp-block-supports.php
wp-includes/class-wp-block.php
wp-includes/class-wp-comment.php
wp-includes/class-wp-customize-control.php
wp-includes/class-wp-customize-manager.php
wp-includes/class-wp-customize-nav-menus.php
wp-includes/class-wp-customize-panel.php
wp-includes/class-wp-customize-setting.php
wp-includes/class-wp-customize-widgets.php
wp-includes/class-wp-date-query.php
wp-includes/class-wp-editor.php
wp-includes/class-wp-embed.php
wp-includes/class-wp-http.php
wp-includes/class-wp-image-editor-gd.php
wp-includes/class-wp-image-editor-imagick.php
wp-includes/class-wp-image-editor.php
wp-includes/class-wp-locale-switcher.php
wp-includes/class-wp-locale.php
wp-includes/class-wp-oembed.php
wp-includes/class-wp-plugin-dependencies.php
wp-includes/class-wp-post-type.php
wp-includes/class-wp-post.php
wp-includes/class-wp-query.php
wp-includes/class-wp-recovery-mode-key-service.php
wp-includes/class-wp-recovery-mode.php
wp-includes/class-wp-script-modules.php
wp-includes/class-wp-session-tokens.php
wp-includes/class-wp-simplepie-sanitize-kses.php
wp-includes/class-wp-taxonomy.php
wp-includes/class-wp-text-diff-renderer-table.php
wp-includes/class-wp-theme-json-resolver.php
wp-includes/class-wp-theme-json.php
wp-includes/class-wp-theme.php
wp-includes/class-wp-user-query.php
wp-includes/class-wp-user-request.php
wp-includes/class-wp-user.php
wp-includes/class-wp-widget.php
wp-includes/class-wp-xmlrpc-server.php
wp-includes/class-wp.php
wp-includes/class-wpdb.php
wp-includes/comment-template.php
wp-includes/comment.php
wp-includes/compat.php
wp-includes/cron.php
wp-includes/css/admin-bar-rtl.css
wp-includes/css/admin-bar-rtl.min.css
wp-includes/css/admin-bar.css
wp-includes/css/admin-bar.min.css
wp-includes/css/dist/block-directory/style-rtl.css
wp-includes/css/dist/block-directory/style-rtl.min.css
wp-includes/css/dist/block-directory/style.css
wp-includes/css/dist/block-directory/style.min.css
wp-includes/css/dist/block-editor/content-rtl.css
wp-includes/css/dist/block-editor/content-rtl.min.css
wp-includes/css/dist/block-editor/content.css
wp-includes/css/dist/block-editor/content.min.css
wp-includes/css/dist/block-editor/style-rtl.css
wp-includes/css/dist/block-editor/style-rtl.min.css
wp-includes/css/dist/block-editor/style.css
wp-includes/css/dist/block-editor/style.min.css
wp-includes/css/dist/block-library/common-rtl.css
wp-includes/css/dist/block-library/common-rtl.min.css
wp-includes/css/dist/block-library/common.css
wp-includes/css/dist/block-library/common.min.css
wp-includes/css/dist/block-library/editor-rtl.css
wp-includes/css/dist/block-library/editor-rtl.min.css
wp-includes/css/dist/block-library/editor.css
wp-includes/css/dist/block-library/editor.min.css
wp-includes/css/dist/block-library/style-rtl.css
wp-includes/css/dist/block-library/style-rtl.min.css
wp-includes/css/dist/block-library/style.css
wp-includes/css/dist/block-library/style.min.css
wp-includes/css/dist/components/style-rtl.css
wp-includes/css/dist/components/style-rtl.min.css
wp-includes/css/dist/components/style.css
wp-includes/css/dist/components/style.min.css
wp-includes/css/dist/customize-widgets/style-rtl.css
wp-includes/css/dist/customize-widgets/style-rtl.min.css
wp-includes/css/dist/customize-widgets/style.css
wp-includes/css/dist/customize-widgets/style.min.css
wp-includes/css/dist/edit-post/style-rtl.css
wp-includes/css/dist/edit-post/style-rtl.min.css
wp-includes/css/dist/edit-post/style.css
wp-includes/css/dist/edit-post/style.min.css
wp-includes/css/dist/edit-site/posts-rtl.css
wp-includes/css/dist/edit-site/posts-rtl.min.css
wp-includes/css/dist/edit-site/posts.css
wp-includes/css/dist/edit-site/posts.min.css
wp-includes/css/dist/edit-site/style-rtl.css
wp-includes/css/dist/edit-site/style-rtl.min.css
wp-includes/css/dist/edit-site/style.css
wp-includes/css/dist/edit-site/style.min.css
wp-includes/css/dist/edit-widgets/style-rtl.css
wp-includes/css/dist/edit-widgets/style-rtl.min.css
wp-includes/css/dist/edit-widgets/style.css
wp-includes/css/dist/edit-widgets/style.min.css
wp-includes/css/dist/editor/style-rtl.css
wp-includes/css/dist/editor/style-rtl.min.css
wp-includes/css/dist/editor/style.css
wp-includes/css/dist/editor/style.min.css
wp-includes/css/dist/format-library/style-rtl.css
wp-includes/css/dist/format-library/style-rtl.min.css
wp-includes/css/dist/format-library/style.css
wp-includes/css/dist/format-library/style.min.css
wp-includes/css/dist/nux/style-rtl.css
wp-includes/css/dist/nux/style-rtl.min.css
wp-includes/css/dist/nux/style.css
wp-includes/css/dist/nux/style.min.css
wp-includes/css/media-views-rtl.css
wp-includes/css/media-views-rtl.min.css
wp-includes/css/media-views.css
wp-includes/css/media-views.min.css
wp-includes/css/wp-embed-template.css
wp-includes/css/wp-embed-template.min.css
wp-includes/customize/class-wp-customize-date-time-control.php
wp-includes/customize/class-wp-customize-header-image-control.php
wp-includes/customize/class-wp-customize-themes-section.php
wp-includes/default-filters.php
wp-includes/default-widgets.php
wp-includes/deprecated.php
wp-includes/embed.php
wp-includes/feed-atom.php
wp-includes/formatting.php
wp-includes/functions.php
wp-includes/general-template.php
wp-includes/global-styles-and-settings.php
wp-includes/html-api/class-wp-html-processor-state.php
wp-includes/html-api/class-wp-html-processor.php
wp-includes/html-api/class-wp-html-tag-processor.php
wp-includes/https-detection.php
wp-includes/interactivity-api/class-wp-interactivity-api.php
wp-includes/js/autosave.js
wp-includes/js/backbone.min.js
wp-includes/js/colorpicker.min.js
wp-includes/js/customize-preview-nav-menus.min.js
wp-includes/js/customize-preview-widgets.min.js
wp-includes/js/customize-selective-refresh.min.js
wp-includes/js/dist/a11y.js
wp-includes/js/dist/annotations.js
wp-includes/js/dist/api-fetch.js
wp-includes/js/dist/api-fetch.min.js
wp-includes/js/dist/block-directory.js
wp-includes/js/dist/block-directory.min.js
wp-includes/js/dist/block-editor.js
wp-includes/js/dist/block-editor.min.js
wp-includes/js/dist/block-library.js
wp-includes/js/dist/block-library.min.js
wp-includes/js/dist/blocks.js
wp-includes/js/dist/blocks.min.js
wp-includes/js/dist/commands.js
wp-includes/js/dist/commands.min.js
wp-includes/js/dist/components.js
wp-includes/js/dist/components.min.js
wp-includes/js/dist/compose.js
wp-includes/js/dist/compose.min.js
wp-includes/js/dist/core-commands.js
wp-includes/js/dist/core-commands.min.js
wp-includes/js/dist/core-data.js
wp-includes/js/dist/core-data.min.js
wp-includes/js/dist/customize-widgets.js
wp-includes/js/dist/customize-widgets.min.js
wp-includes/js/dist/data-controls.js
wp-includes/js/dist/data.js
wp-includes/js/dist/data.min.js
wp-includes/js/dist/date.js
wp-includes/js/dist/date.min.js
wp-includes/js/dist/deprecated.js
wp-includes/js/dist/development/react-refresh-entry.js
wp-includes/js/dist/development/react-refresh-entry.min.js
wp-includes/js/dist/dom.js
wp-includes/js/dist/dom.min.js
wp-includes/js/dist/edit-post.js
wp-includes/js/dist/edit-post.min.js
wp-includes/js/dist/edit-site.js
wp-includes/js/dist/edit-site.min.js
wp-includes/js/dist/edit-widgets.js
wp-includes/js/dist/edit-widgets.min.js
wp-includes/js/dist/editor.js
wp-includes/js/dist/editor.min.js
wp-includes/js/dist/element.js
wp-includes/js/dist/element.min.js
wp-includes/js/dist/escape-html.js
wp-includes/js/dist/format-library.js
wp-includes/js/dist/format-library.min.js
wp-includes/js/dist/hooks.js
wp-includes/js/dist/i18n.js
wp-includes/js/dist/is-shallow-equal.js
wp-includes/js/dist/keyboard-shortcuts.js
wp-includes/js/dist/keycodes.js
wp-includes/js/dist/list-reusable-blocks.js
wp-includes/js/dist/list-reusable-blocks.min.js
wp-includes/js/dist/media-utils.js
wp-includes/js/dist/media-utils.min.js
wp-includes/js/dist/notices.js
wp-includes/js/dist/nux.js
wp-includes/js/dist/patterns.js
wp-includes/js/dist/patterns.min.js
wp-includes/js/dist/plugins.js
wp-includes/js/dist/plugins.min.js
wp-includes/js/dist/preferences-persistence.js
wp-includes/js/dist/preferences.js
wp-includes/js/dist/preferences.min.js
wp-includes/js/dist/primitives.js
wp-includes/js/dist/priority-queue.js
wp-includes/js/dist/private-apis.js
wp-includes/js/dist/private-apis.min.js
wp-includes/js/dist/redux-routine.js
wp-includes/js/dist/redux-routine.min.js
wp-includes/js/dist/reusable-blocks.js
wp-includes/js/dist/rich-text.js
wp-includes/js/dist/rich-text.min.js
wp-includes/js/dist/router.js
wp-includes/js/dist/router.min.js
wp-includes/js/dist/script-modules/a11y/index.js
wp-includes/js/dist/script-modules/block-library/file/view.js
wp-includes/js/dist/script-modules/block-library/image/view.js
wp-includes/js/dist/script-modules/block-library/image/view.min.js
wp-includes/js/dist/script-modules/block-library/navigation/view.js
wp-includes/js/dist/script-modules/block-library/navigation/view.min.js
wp-includes/js/dist/script-modules/block-library/query/view.js
wp-includes/js/dist/script-modules/block-library/query/view.min.js
wp-includes/js/dist/script-modules/block-library/search/view.js
wp-includes/js/dist/script-modules/block-library/search/view.min.js
wp-includes/js/dist/script-modules/interactivity-router/index.js
wp-includes/js/dist/script-modules/interactivity-router/index.min.js
wp-includes/js/dist/script-modules/interactivity/debug.js
wp-includes/js/dist/script-modules/interactivity/debug.min.js
wp-includes/js/dist/script-modules/interactivity/index.js
wp-includes/js/dist/script-modules/interactivity/index.min.js
wp-includes/js/dist/server-side-render.js
wp-includes/js/dist/server-side-render.min.js
wp-includes/js/dist/shortcode.js
wp-includes/js/dist/style-engine.js
wp-includes/js/dist/url.js
wp-includes/js/dist/url.min.js
wp-includes/js/dist/vendor/lodash.min.js
wp-includes/js/dist/vendor/moment.min.js
wp-includes/js/dist/vendor/react-dom.min.js
wp-includes/js/dist/vendor/react-jsx-runtime.min.js
wp-includes/js/dist/vendor/regenerator-runtime.min.js
wp-includes/js/dist/vendor/wp-polyfill-dom-rect.min.js
wp-includes/js/dist/vendor/wp-polyfill-element-closest.min.js
wp-includes/js/dist/vendor/wp-polyfill-fetch.min.js
wp-includes/js/dist/vendor/wp-polyfill-node-contains.min.js
wp-includes/js/dist/vendor/wp-polyfill.js
wp-includes/js/dist/vendor/wp-polyfill.min.js
wp-includes/js/dist/viewport.js
wp-includes/js/dist/warning.js
wp-includes/js/dist/widgets.js
wp-includes/js/dist/widgets.min.js
wp-includes/js/dist/wordcount.js
wp-includes/js/jquery/ui/core.min.js
wp-includes/js/jquery/ui/datepicker.min.js
wp-includes/js/jquery/ui/selectable.min.js
wp-includes/js/media-audiovideo.js
wp-includes/js/media-audiovideo.min.js
wp-includes/js/media-grid.js
wp-includes/js/media-grid.min.js
wp-includes/js/media-models.js
wp-includes/js/media-models.min.js
wp-includes/js/media-views.js
wp-includes/js/media-views.min.js
wp-includes/js/plupload/handlers.js
wp-includes/js/plupload/handlers.min.js
wp-includes/js/plupload/moxie.js
wp-includes/js/tinymce/plugins/wordpress/plugin.js
wp-includes/js/tinymce/plugins/wordpress/plugin.min.js
wp-includes/js/tinymce/plugins/wpeditimage/plugin.min.js
wp-includes/js/tinymce/skins/wordpress/wp-content.css
wp-includes/js/tinymce/wp-tinymce.js
wp-includes/js/twemoji.js
wp-includes/js/twemoji.min.js
wp-includes/js/underscore.min.js
wp-includes/js/wp-ajax-response.js
wp-includes/js/wp-ajax-response.min.js
wp-includes/js/wp-emoji-loader.js
wp-includes/js/wp-emoji-loader.min.js
wp-includes/js/wp-emoji-release.min.js
wp-includes/js/wp-sanitize.js
wp-includes/js/wplink.js
wp-includes/kses.php
wp-includes/l10n.php
wp-includes/link-template.php
wp-includes/load.php
wp-includes/media-template.php
wp-includes/media.php
wp-includes/meta.php
wp-includes/ms-blogs.php
wp-includes/ms-files.php
wp-includes/ms-functions.php
wp-includes/ms-settings.php
wp-includes/ms-site.php
wp-includes/nav-menu-template.php
wp-includes/option.php
wp-includes/pluggable-deprecated.php
wp-includes/pluggable.php
wp-includes/post-template.php
wp-includes/post-thumbnail-template.php
wp-includes/post.php
wp-includes/rest-api.php
wp-includes/rest-api/class-wp-rest-request.php
wp-includes/rest-api/class-wp-rest-server.php
wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-autosaves-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-block-directory-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-block-pattern-categories-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-block-types-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-edit-site-export-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-font-collections-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-global-styles-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-menu-items-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-menu-locations-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-menus-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-pattern-directory-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-post-types-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-search-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-sidebars-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-taxonomies-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-template-autosaves-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-template-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-themes-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-widget-types-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-widgets-controller.php
wp-includes/revision.php
wp-includes/script-loader.php
wp-includes/sitemaps/providers/class-wp-sitemaps-taxonomies.php
wp-includes/style-engine/class-wp-style-engine.php
wp-includes/taxonomy.php
wp-includes/theme-i18n.json
wp-includes/theme-templates.php
wp-includes/theme.php
wp-includes/update.php
wp-includes/user.php
wp-includes/vars.php
wp-includes/version.php
wp-includes/widgets.php
wp-includes/widgets/class-wp-widget-text.php
wp-includes/wp-diff.php
wp-login.php
wp-mail.php
wp-settings.php
wp-signup.php
xmlrpc.php

Deleted files:
wp-includes/blocks/post-content/editor-rtl.css
wp-includes/blocks/post-content/editor-rtl.min.css
wp-includes/blocks/post-content/editor.css
wp-includes/blocks/post-content/editor.min.css
wp-includes/blocks/post-template/editor-rtl.css
wp-includes/blocks/post-template/editor-rtl.min.css
wp-includes/blocks/post-template/editor.css
wp-includes/blocks/post-template/editor.min.css
wp-includes/js/dist/fields.js
wp-includes/js/dist/fields.min.js
wp-includes/js/dist/undo-manager.js
wp-includes/js/dist/undo-manager.min.js

New files:
wp-includes/block-supports/aria-label.php
wp-includes/blocks/query-total.php
wp-includes/blocks/query-total/
wp-includes/class-wp-phpmailer.php
wp-includes/class-wp-speculation-rules.php
wp-includes/class-wp-url-pattern-prefixer.php
wp-includes/css/wp-empty-template-alert.css
wp-includes/css/wp-empty-template-alert.min.css
wp-includes/js/dist/script-modules/block-library/form/
wp-includes/js/tinymce/skins/wordpress/images/script.svg
wp-includes/js/tinymce/skins/wordpress/images/style.svg
wp-includes/speculative-loading.php
```

First published

April 15, 2025

Last updated

April 22, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.