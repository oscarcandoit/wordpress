---
url: https://wordpress.org/documentation/wordpress-version/version-6-6
scraped_at: 2025-10-20T02:01:52.867Z
---

[Skip to content](https://wordpress.org/documentation/wordpress-version/version-6-6/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Version 6.6

[Home](https://wordpress.org/documentation)Version 6.6

Search documentation

# Version 6.6

## In this article

Table of Contents

- [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-6/#installation-update-information)
- [Highlights: What’s inside 6.6](https://wordpress.org/documentation/wordpress-version/version-6-6/#highlights)
  - [Color palettes & font sets](https://wordpress.org/documentation/wordpress-version/version-6-6/#color-palettes-font-sets)
  - [Quick previews for pages](https://wordpress.org/documentation/wordpress-version/version-6-6/#quick-previews-for-pages)
  - [Rollbacks for plugin auto-updates](https://wordpress.org/documentation/wordpress-version/version-6-6/#rollbacks-for-plugin-auto-updates)
  - [Overrides](https://wordpress.org/documentation/wordpress-version/version-6-6/#overrides)
  - [Performance updates](https://wordpress.org/documentation/wordpress-version/version-6-6/#performance-updates)
  - [Accessibility improvements](https://wordpress.org/documentation/wordpress-version/version-6-6/#accessibility-improvements)
- [Learn more about WordPress 6.6](https://wordpress.org/documentation/wordpress-version/version-6-6/#learn-more-about-wordpress-6-6)
- [The 6.6 release squad](https://wordpress.org/documentation/wordpress-version/version-6-6/#the-6-6-release-squad)
- [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-6/#changelog)
  - [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-6/#updated-packages)
  - [List of Files Revised](https://wordpress.org/documentation/wordpress-version/version-6-6/#list-of-files-revised)

[↑ Back to top](https://wordpress.org/documentation/wordpress-version/version-6-6/#wp--skip-link--target)

On July 16, 2024, WordPress 6.6 “Dorsey” was released to the public. For more information on this release, read the WordPress 6.6 announcement.

For Version 6.6, the database version ( **db\_version** in **wp\_options**) was `57155` and Trac revision was `58737`.

A [full list of tickets included in 6.6](https://core.trac.wordpress.org/milestone/6.6) can be found on [Trac](https://core.trac.wordpress.org/).

## [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-6/\#installation-update-information)

To download WordPress 6.6, update automatically from the Dashboard > Updates menu in your site’s admin area or visit the [release archive](https://wordpress.org/download/release-archive/).

For step-by-step instructions on installing and updating WordPress:

- [Updating WordPress](https://wordpress.org/documentation/article/updating-wordpress/)

If you are new to WordPress, we recommend that you begin with the following:

- [New To WordPress – Where to Start](https://wordpress.org/support/article/new_to_wordpress_-_where_to_start/)
- [First Steps with WordPress (Classic Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-classic/) or [First Steps with WordPress (Block Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-block-editor/)
- [Upgrading WordPress Extended](https://wordpress.org/documentation/article/upgrading-wordpress-extended-instructions/)

* * *

## [Highlights: What’s inside 6.6](https://wordpress.org/documentation/wordpress-version/version-6-6/\#highlights)

![](https://s.w.org/images/core/6.6/color-palettes.webp)

### [Color palettes & font sets](https://wordpress.org/documentation/wordpress-version/version-6-6/\#color-palettes-font-sets)

**Add more design options to any block theme.** Block theme authors can create unlimited individual color or font sets to offer more specific design options within the same theme. These sets provide more contained design possibilities, allowing for customization without changing the site’s broader styling, beyond color or typography settings.

![](https://s.w.org/images/core/6.6/page-previews.webp)

### [Quick previews for pages](https://wordpress.org/documentation/wordpress-version/version-6-6/\#quick-previews-for-pages)

**Simplify your workflow with a new layout built for pages.** See all of your pages and a preview of any selected page before you edit via a new side-by-side layout in the Site Editor.

![](https://s.w.org/images/core/6.6/feature-rollbacks.webp)

### [Rollbacks for plugin auto-updates](https://wordpress.org/documentation/wordpress-version/version-6-6/\#rollbacks-for-plugin-auto-updates)

**Auto-update your plugins with peace of mind.** Enjoy the ease of plugin auto-updates with the safety of rollbacks if anything goes wrong, improving your site’s security while minimizing potential downtime.

![](https://s.w.org/images/core/6.6/overrides.webp)

### [Overrides](https://wordpress.org/documentation/wordpress-version/version-6-6/\#overrides)

**Add the ability to customize content in synced patterns.** Allow specific pieces of content to be customized in each instance of a synced pattern while keeping a consistent style for all instances, simplifying future updates. Currently, you can set overrides for Heading, Paragraph, Button, and Image blocks.

### [Performance updates](https://wordpress.org/documentation/wordpress-version/version-6-6/\#performance-updates)

WordPress 6.6 includes important updates like removing redundant `WP_Theme_JSON` calls, disabling autoload for large options, eliminating unnecessary polyfill dependencies, lazy loading post embeds, introducing the `data-wp-on-async` directive, and a 33% reduction in template loading time in the editor.

### [Accessibility improvements](https://wordpress.org/documentation/wordpress-version/version-6-6/\#accessibility-improvements)

55+ accessibility fixes and enhancements focus on foundational aspects of the WordPress experience, particularly the data views component powering the new site editing experience and areas like the Inserter that provide a key way of interacting with blocks and patterns.

## [Learn more about WordPress 6.6](https://wordpress.org/documentation/wordpress-version/version-6-6/\#learn-more-about-wordpress-6-6)

[Learn WordPress](https://learn.wordpress.org/) is a free resource for new and experienced WordPress users. Learn is stocked with how-to videos on using various features in WordPress, [interactive workshops](https://learn.wordpress.org/online-workshops/) for exploring topics in-depth, and lesson plans for diving deep into specific areas of WordPress.

Explore the [WordPress 6.6 Field Guide](https://make.wordpress.org/core/wordpress-6-6-field-guide/). Learn about the changes in this release with detailed developer notes to help you build with WordPress.

[Read the WordPress 6.6 Release Notes](https://wordpress.org/documentation/wordpress-version/version-6-6/) for information on installation, enhancements, fixed issues, release contributors, learning resources, and the list of file changes.

Visit the [feature showcase](https://wordpress.org/download/releases/6-6/) for a full overview of all the new features and enhancements in WordPress 6.6.

## [The 6.6 release squad](https://wordpress.org/documentation/wordpress-version/version-6-6/\#the-6-6-release-squad)

Every release comes to you from a dedicated team of enthusiastic contributors who help keep things on track and moving smoothly. The team that has led 6.6 is a cross-functional group of contributors who are always ready to champion ideas, remove blockers, and resolve issues.

- Release Lead: [Matt Mullenweg](https://profiles.wordpress.org/matt/)
- Release Coordinator: [Meher Bala](https://profiles.wordpress.org/meher/)
- Core Tech Lead: [Jb Audras](https://profiles.wordpress.org/audrasjb/)
- Editor Tech Leads: [Ella van Durpe](https://profiles.wordpress.org/ellatrix/), [Vicente Canales](https://profiles.wordpress.org/vcanales/)
- Core Triage Leads: [Olga Gleckler](https://profiles.wordpress.org/oglekler/), [Nazmul Hasan Robin](https://profiles.wordpress.org/nhrrob/)
- Editor Triage Leads: [Fabian Kägy](https://profiles.wordpress.org/fabiankaegy/), [Damon Cook](https://profiles.wordpress.org/colorful-tones/)
- Documentation Leads: [JuanMa Garrido](https://profiles.wordpress.org/juanmaguitar/), [Jenny Dupuy](https://profiles.wordpress.org/jdy68/), [Josep Morán](https://profiles.wordpress.org/josepmoran/)
- Marketing & Communications Lead: [Mary Baum](https://profiles.wordpress.org/marybaum/)
- Test Lead: [Anne McCarthy](https://profiles.wordpress.org/annezazu/)
- Design Lead: [Rich Tabor](https://profiles.wordpress.org/richtabor/)
- Performance Lead: [Adam Silverstein](https://profiles.wordpress.org/adamsilverstein/)

## [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-6/\#changelog)

### [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-6/\#updated-packages)

```
@playwright/test - 1.45.0
@pmmmwh/react-refresh-webpack-plugin - 0.5.15
@wordpress/babel-preset-default - 8.0.1
@wordpress/dependency-extraction-webpack-plugin - 6.0.2
@wordpress/e2e-test-utils - 11.0.1
@wordpress/e2e-test-utils-playwright - 1.0.1
@wordpress/prettier-config - 4.0.1
@wordpress/scripts - 28.0.2
autoprefixer - 10.4.19
cssnano - 7.0.3
dotenv - 16.4.5
dotenv-expand - 11.0.6
grunt-contrib-qunit - ~10.0.0
postcss - 8.4.38
qunit - ~2.21.0
sass - 1.77.6
sinon-test - ~3.1.6
@wordpress/a11y - 4.0.1
@wordpress/annotations - 3.0.2
@wordpress/api-fetch - 7.0.1
@wordpress/autop - 4.0.1
@wordpress/blob - 4.0.1
@wordpress/block-directory - 5.0.7
@wordpress/block-editor - 13.0.5
@wordpress/block-library - 9.0.6
@wordpress/block-serialization-default-parser - 5.0.1
@wordpress/blocks - 13.0.3
@wordpress/commands - 1.0.3
@wordpress/components - 28.0.3
@wordpress/compose - 7.0.1
@wordpress/core-commands - 1.0.5
@wordpress/core-data - 7.0.5
@wordpress/customize-widgets - 5.0.6
@wordpress/data - 10.0.2
@wordpress/data-controls - 4.0.2
@wordpress/dataviews - 2.0.4
@wordpress/date - 5.0.1
@wordpress/deprecated - 4.0.1
@wordpress/dom - 4.0.1
@wordpress/dom-ready - 4.0.1
@wordpress/edit-post - 8.0.7
@wordpress/edit-site - 6.0.7
@wordpress/edit-widgets - 6.0.6
@wordpress/editor - 14.0.6
@wordpress/element - 6.0.1
@wordpress/escape-html - 3.0.1
@wordpress/format-library - 5.0.5
@wordpress/hooks - 4.0.1
@wordpress/html-entities - 4.0.1
@wordpress/i18n - 5.0.1
@wordpress/icons - 10.0.2
@wordpress/interactivity - 6.0.2
@wordpress/interactivity-router - 2.0.2
@wordpress/interface - 6.0.3
@wordpress/is-shallow-equal - 5.0.1
@wordpress/keyboard-shortcuts - 5.0.2
@wordpress/keycodes - 4.0.1
@wordpress/list-reusable-blocks - 5.0.3
@wordpress/media-utils - 5.0.1
@wordpress/notices - 5.0.2
@wordpress/nux - 9.0.3
@wordpress/patterns - 2.0.5
@wordpress/plugins - 7.0.3
@wordpress/preferences - 4.0.3
@wordpress/preferences-persistence - 2.0.1
@wordpress/primitives - 4.0.1
@wordpress/priority-queue - 3.0.1
@wordpress/private-apis - 1.0.2
@wordpress/redux-routine - 5.0.1
@wordpress/reusable-blocks - 5.0.5
@wordpress/rich-text - 7.0.2
@wordpress/router - 1.0.2
@wordpress/server-side-render - 5.0.3
@wordpress/shortcode - 4.0.1
@wordpress/style-engine - 2.0.2
@wordpress/sync - 1.0.1
@wordpress/token-list - 3.0.1
@wordpress/undo-manager - 1.0.1
@wordpress/url - 4.0.1
@wordpress/viewport - 6.0.2
@wordpress/warning - 3.0.1
@wordpress/widgets - 4.0.5
@wordpress/wordcount - 4.0.1
react - 18.3.1
react-dom - 18.3.1
react-is - 18.3.1
```

### [List of Files Revised](https://wordpress.org/documentation/wordpress-version/version-6-6/\#list-of-files-revised)

```
readme.html
wp-admin/about.php
wp-admin/admin-ajax.php
wp-admin/admin-header.php
wp-admin/admin-post.php
wp-admin/async-upload.php
wp-admin/comment.php
wp-admin/css/about-rtl.css
wp-admin/css/about-rtl.min.css
wp-admin/css/about.css
wp-admin/css/about.min.css
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
wp-admin/css/edit-rtl.css
wp-admin/css/edit-rtl.min.css
wp-admin/css/edit.css
wp-admin/css/edit.min.css
wp-admin/css/forms-rtl.css
wp-admin/css/forms-rtl.min.css
wp-admin/css/forms.css
wp-admin/css/forms.min.css
wp-admin/css/install-rtl.css
wp-admin/css/install-rtl.min.css
wp-admin/css/install.css
wp-admin/css/install.min.css
wp-admin/css/l10n-rtl.css
wp-admin/css/l10n-rtl.min.css
wp-admin/css/l10n.css
wp-admin/css/l10n.min.css
wp-admin/css/list-tables-rtl.css
wp-admin/css/list-tables-rtl.min.css
wp-admin/css/list-tables.css
wp-admin/css/list-tables.min.css
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
wp-admin/css/themes-rtl.css
wp-admin/css/themes-rtl.min.css
wp-admin/css/themes.css
wp-admin/css/themes.min.css
wp-admin/customize.php
wp-admin/edit-form-advanced.php
wp-admin/edit-form-blocks.php
wp-admin/edit-tag-form.php
wp-admin/edit-tags.php
wp-admin/edit.php
wp-admin/erase-personal-data.php
wp-admin/export-personal-data.php
wp-admin/export.php
wp-admin/images/about-release-badge.svg
wp-admin/includes/ajax-actions.php
wp-admin/includes/class-bulk-plugin-upgrader-skin.php
wp-admin/includes/class-bulk-theme-upgrader-skin.php
wp-admin/includes/class-bulk-upgrader-skin.php
wp-admin/includes/class-core-upgrader.php
wp-admin/includes/class-file-upload-upgrader.php
wp-admin/includes/class-language-pack-upgrader-skin.php
wp-admin/includes/class-language-pack-upgrader.php
wp-admin/includes/class-pclzip.php
wp-admin/includes/class-plugin-installer-skin.php
wp-admin/includes/class-theme-installer-skin.php
wp-admin/includes/class-wp-automatic-updater.php
wp-admin/includes/class-wp-comments-list-table.php
wp-admin/includes/class-wp-debug-data.php
wp-admin/includes/class-wp-links-list-table.php
wp-admin/includes/class-wp-list-table.php
wp-admin/includes/class-wp-ms-themes-list-table.php
wp-admin/includes/class-wp-plugin-install-list-table.php
wp-admin/includes/class-wp-plugins-list-table.php
wp-admin/includes/class-wp-posts-list-table.php
wp-admin/includes/class-wp-screen.php
wp-admin/includes/class-wp-site-health.php
wp-admin/includes/class-wp-terms-list-table.php
wp-admin/includes/class-wp-theme-install-list-table.php
wp-admin/includes/class-wp-upgrader-skin.php
wp-admin/includes/class-wp-upgrader.php
wp-admin/includes/export.php
wp-admin/includes/file.php
wp-admin/includes/image-edit.php
wp-admin/includes/media.php
wp-admin/includes/meta-boxes.php
wp-admin/includes/misc.php
wp-admin/includes/ms.php
wp-admin/includes/nav-menu.php
wp-admin/includes/network.php
wp-admin/includes/plugin-install.php
wp-admin/includes/plugin.php
wp-admin/includes/post.php
wp-admin/includes/schema.php
wp-admin/includes/screen.php
wp-admin/includes/template.php
wp-admin/includes/theme.php
wp-admin/includes/translation-install.php
wp-admin/includes/update.php
wp-admin/includes/upgrade.php
wp-admin/js/common.js
wp-admin/js/common.min.js
wp-admin/js/customize-controls.js
wp-admin/js/customize-controls.min.js
wp-admin/js/customize-nav-menus.js
wp-admin/js/customize-nav-menus.min.js
wp-admin/js/customize-widgets.js
wp-admin/js/customize-widgets.min.js
wp-admin/js/dashboard.js
wp-admin/js/editor-expand.js
wp-admin/js/editor.js
wp-admin/js/nav-menu.js
wp-admin/js/nav-menu.min.js
wp-admin/js/privacy-tools.js
wp-admin/js/privacy-tools.min.js
wp-admin/js/theme-plugin-editor.js
wp-admin/js/theme.js
wp-admin/js/theme.min.js
wp-admin/js/updates.js
wp-admin/js/updates.min.js
wp-admin/js/user-profile.js
wp-admin/js/user-profile.min.js
wp-admin/js/widgets/custom-html-widgets.js
wp-admin/js/widgets/custom-html-widgets.min.js
wp-admin/js/widgets/media-widgets.js
wp-admin/js/widgets/media-widgets.min.js
wp-admin/link-add.php
wp-admin/link-parse-opml.php
wp-admin/link.php
wp-admin/load-scripts.php
wp-admin/load-styles.php
wp-admin/media.php
wp-admin/menu-header.php
wp-admin/menu.php
wp-admin/ms-options.php
wp-admin/nav-menus.php
wp-admin/network.php
wp-admin/network/index.php
wp-admin/network/settings.php
wp-admin/network/site-info.php
wp-admin/network/site-new.php
wp-admin/network/site-themes.php
wp-admin/network/sites.php
wp-admin/network/themes.php
wp-admin/network/upgrade.php
wp-admin/options-general.php
wp-admin/options-head.php
wp-admin/options-permalink.php
wp-admin/options-reading.php
wp-admin/options-writing.php
wp-admin/options.php
wp-admin/plugin-editor.php
wp-admin/plugins.php
wp-admin/post-new.php
wp-admin/post.php
wp-admin/revision.php
wp-admin/setup-config.php
wp-admin/site-health-info.php
wp-admin/site-health.php
wp-admin/theme-editor.php
wp-admin/theme-install.php
wp-admin/themes.php
wp-admin/update-core.php
wp-admin/upload.php
wp-admin/user-edit.php
wp-admin/users.php
wp-admin/user/contribute.php
wp-config-sample.php
wp-content/plugins/akismet/akismet.php
wp-content/plugins/akismet/class.akismet-admin.php
wp-content/plugins/akismet/class.akismet.php
wp-content/plugins/akismet/readme.txt
wp-content/plugins/akismet/views/config.php
wp-content/plugins/akismet/views/notice.php
wp-content/plugins/akismet/views/setup.php
wp-content/themes/twentytwentyfour/patterns/banner-hero.php
wp-content/themes/twentytwentyfour/patterns/banner-project-description.php
wp-content/themes/twentytwentyfour/patterns/cta-content-image-on-right.php
wp-content/themes/twentytwentyfour/patterns/cta-pricing.php
wp-content/themes/twentytwentyfour/patterns/cta-rsvp.php
wp-content/themes/twentytwentyfour/patterns/cta-services-image-left.php
wp-content/themes/twentytwentyfour/patterns/cta-subscribe-centered.php
wp-content/themes/twentytwentyfour/patterns/footer-centered-logo-nav.php
wp-content/themes/twentytwentyfour/patterns/footer-colophon-3-col.php
wp-content/themes/twentytwentyfour/patterns/footer.php
wp-content/themes/twentytwentyfour/patterns/gallery-full-screen-image.php
wp-content/themes/twentytwentyfour/patterns/gallery-offset-images-grid-2-col.php
wp-content/themes/twentytwentyfour/patterns/gallery-offset-images-grid-3-col.php
wp-content/themes/twentytwentyfour/patterns/gallery-offset-images-grid-4-col.php
wp-content/themes/twentytwentyfour/patterns/gallery-project-layout.php
wp-content/themes/twentytwentyfour/patterns/page-about-business.php
wp-content/themes/twentytwentyfour/patterns/page-home-blogging.php
wp-content/themes/twentytwentyfour/patterns/page-home-business.php
wp-content/themes/twentytwentyfour/patterns/page-home-portfolio-gallery.php
wp-content/themes/twentytwentyfour/patterns/page-home-portfolio.php
wp-content/themes/twentytwentyfour/patterns/page-newsletter-landing.php
wp-content/themes/twentytwentyfour/patterns/page-portfolio-overview.php
wp-content/themes/twentytwentyfour/patterns/page-rsvp-landing.php
wp-content/themes/twentytwentyfour/patterns/posts-1-col.php
wp-content/themes/twentytwentyfour/patterns/posts-3-col.php
wp-content/themes/twentytwentyfour/patterns/posts-grid-2-col.php
wp-content/themes/twentytwentyfour/patterns/posts-images-only-3-col.php
wp-content/themes/twentytwentyfour/patterns/posts-images-only-offset-4-col.php
wp-content/themes/twentytwentyfour/patterns/posts-list.php
wp-content/themes/twentytwentyfour/patterns/team-4-col.php
wp-content/themes/twentytwentyfour/patterns/testimonial-centered.php
wp-content/themes/twentytwentyfour/patterns/text-alternating-images.php
wp-content/themes/twentytwentyfour/patterns/text-centered-statement-small.php
wp-content/themes/twentytwentyfour/patterns/text-centered-statement.php
wp-content/themes/twentytwentyfour/patterns/text-faq.php
wp-content/themes/twentytwentyfour/patterns/text-feature-grid-3-col.php
wp-content/themes/twentytwentyfour/patterns/text-project-details.php
wp-content/themes/twentytwentyfour/patterns/text-title-left-image-right.php
wp-content/themes/twentytwentyfour/readme.txt
wp-content/themes/twentytwentyfour/screenshot.png
wp-content/themes/twentytwentyfour/style.css
wp-content/themes/twentytwentyfour/templates/home.html
wp-content/themes/twentytwentyfour/theme.json
wp-content/themes/twentytwentythree/parts/header.html
wp-content/themes/twentytwentythree/patterns/call-to-action.php
wp-content/themes/twentytwentythree/patterns/footer-default.php
wp-content/themes/twentytwentythree/patterns/post-meta.php
wp-content/themes/twentytwentythree/readme.txt
wp-content/themes/twentytwentythree/screenshot.png
wp-content/themes/twentytwentythree/style.css
wp-content/themes/twentytwentythree/styles/aubergine.json
wp-content/themes/twentytwentythree/templates/archive.html
wp-content/themes/twentytwentythree/templates/home.html
wp-content/themes/twentytwentythree/templates/search.html
wp-content/themes/twentytwentythree/theme.json
wp-content/themes/twentytwentytwo/parts/header.html
wp-content/themes/twentytwentytwo/readme.txt
wp-content/themes/twentytwentytwo/style.css
wp-content/themes/twentytwentytwo/theme.json
wp-includes/Requests/src/Cookie.php
wp-includes/Requests/src/Requests.php
wp-includes/Requests/src/Transport/Fsockopen.php
wp-includes/admin-bar.php
wp-includes/assets/script-loader-packages.min.php
wp-includes/assets/script-loader-packages.php
wp-includes/block-bindings.php
wp-includes/block-editor.php
wp-includes/block-supports/background.php
wp-includes/block-supports/duotone.php
wp-includes/block-supports/elements.php
wp-includes/block-supports/layout.php
wp-includes/block-supports/shadow.php
wp-includes/block-supports/typography.php
wp-includes/block-template-utils.php
wp-includes/block-template.php
wp-includes/blocks.php
wp-includes/blocks/archives.php
wp-includes/blocks/audio/style-rtl.css
wp-includes/blocks/audio/style-rtl.min.css
wp-includes/blocks/audio/style.css
wp-includes/blocks/audio/style.min.css
wp-includes/blocks/audio/theme-rtl.css
wp-includes/blocks/audio/theme-rtl.min.css
wp-includes/blocks/audio/theme.css
wp-includes/blocks/audio/theme.min.css
wp-includes/blocks/avatar.php
wp-includes/blocks/block.php
wp-includes/blocks/block/block.json
wp-includes/blocks/blocks-json.php
wp-includes/blocks/button/block.json
wp-includes/blocks/button/editor-rtl.css
wp-includes/blocks/button/editor-rtl.min.css
wp-includes/blocks/button/editor.css
wp-includes/blocks/button/editor.min.css
wp-includes/blocks/button/style-rtl.css
wp-includes/blocks/button/style-rtl.min.css
wp-includes/blocks/button/style.css
wp-includes/blocks/button/style.min.css
wp-includes/blocks/calendar.php
wp-includes/blocks/categories.php
wp-includes/blocks/comment-author-name.php
wp-includes/blocks/comment-content.php
wp-includes/blocks/comment-date.php
wp-includes/blocks/comment-edit-link.php
wp-includes/blocks/comment-reply-link.php
wp-includes/blocks/comment-template.php
wp-includes/blocks/comments-pagination-next.php
wp-includes/blocks/comments-pagination-numbers.php
wp-includes/blocks/comments-pagination-previous.php
wp-includes/blocks/comments-pagination.php
wp-includes/blocks/comments-title.php
wp-includes/blocks/comments.php
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
wp-includes/blocks/details/style-rtl.css
wp-includes/blocks/details/style-rtl.min.css
wp-includes/blocks/details/style.css
wp-includes/blocks/details/style.min.css
wp-includes/blocks/embed/editor-rtl.css
wp-includes/blocks/embed/editor-rtl.min.css
wp-includes/blocks/embed/editor.css
wp-includes/blocks/embed/editor.min.css
wp-includes/blocks/embed/style-rtl.css
wp-includes/blocks/embed/style-rtl.min.css
wp-includes/blocks/embed/style.css
wp-includes/blocks/embed/style.min.css
wp-includes/blocks/embed/theme-rtl.css
wp-includes/blocks/embed/theme-rtl.min.css
wp-includes/blocks/embed/theme.css
wp-includes/blocks/embed/theme.min.css
wp-includes/blocks/file.php
wp-includes/blocks/file/editor-rtl.css
wp-includes/blocks/file/editor-rtl.min.css
wp-includes/blocks/file/editor.css
wp-includes/blocks/file/editor.min.css
wp-includes/blocks/gallery.php
wp-includes/blocks/gallery/editor-rtl.css
wp-includes/blocks/gallery/editor-rtl.min.css
wp-includes/blocks/gallery/editor.css
wp-includes/blocks/gallery/editor.min.css
wp-includes/blocks/group/editor-rtl.css
wp-includes/blocks/group/editor-rtl.min.css
wp-includes/blocks/group/editor.css
wp-includes/blocks/group/editor.min.css
wp-includes/blocks/group/style-rtl.css
wp-includes/blocks/group/style-rtl.min.css
wp-includes/blocks/group/style.css
wp-includes/blocks/group/style.min.css
wp-includes/blocks/heading.php
wp-includes/blocks/heading/block.json
wp-includes/blocks/home-link.php
wp-includes/blocks/html/editor-rtl.css
wp-includes/blocks/html/editor-rtl.min.css
wp-includes/blocks/html/editor.css
wp-includes/blocks/html/editor.min.css
wp-includes/blocks/image.php
wp-includes/blocks/image/editor-rtl.css
wp-includes/blocks/image/editor-rtl.min.css
wp-includes/blocks/image/editor.css
wp-includes/blocks/image/editor.min.css
wp-includes/blocks/image/style-rtl.css
wp-includes/blocks/image/style-rtl.min.css
wp-includes/blocks/image/style.css
wp-includes/blocks/image/style.min.css
wp-includes/blocks/image/theme-rtl.css
wp-includes/blocks/image/theme-rtl.min.css
wp-includes/blocks/image/theme.css
wp-includes/blocks/image/theme.min.css
wp-includes/blocks/image/view.js
wp-includes/blocks/latest-comments.php
wp-includes/blocks/latest-posts.php
wp-includes/blocks/latest-posts/editor-rtl.css
wp-includes/blocks/latest-posts/editor-rtl.min.css
wp-includes/blocks/latest-posts/editor.css
wp-includes/blocks/latest-posts/editor.min.css
wp-includes/blocks/latest-posts/style-rtl.css
wp-includes/blocks/latest-posts/style-rtl.min.css
wp-includes/blocks/latest-posts/style.css
wp-includes/blocks/latest-posts/style.min.css
wp-includes/blocks/legacy-widget.php
wp-includes/blocks/list-item/block.json
wp-includes/blocks/list/block.json
wp-includes/blocks/list/style-rtl.css
wp-includes/blocks/list/style-rtl.min.css
wp-includes/blocks/list/style.css
wp-includes/blocks/list/style.min.css
wp-includes/blocks/loginout.php
wp-includes/blocks/media-text/block.json
wp-includes/blocks/media-text/editor-rtl.css
wp-includes/blocks/media-text/editor-rtl.min.css
wp-includes/blocks/media-text/editor.css
wp-includes/blocks/media-text/editor.min.css
wp-includes/blocks/media-text/style-rtl.css
wp-includes/blocks/media-text/style-rtl.min.css
wp-includes/blocks/media-text/style.css
wp-includes/blocks/media-text/style.min.css
wp-includes/blocks/more/block.json
wp-includes/blocks/navigation-link.php
wp-includes/blocks/navigation-link/style-rtl.css
wp-includes/blocks/navigation-link/style-rtl.min.css
wp-includes/blocks/navigation-link/style.css
wp-includes/blocks/navigation-link/style.min.css
wp-includes/blocks/navigation-submenu.php
wp-includes/blocks/navigation.php
wp-includes/blocks/navigation/block.json
wp-includes/blocks/navigation/editor-rtl.css
wp-includes/blocks/navigation/editor-rtl.min.css
wp-includes/blocks/navigation/editor.css
wp-includes/blocks/navigation/editor.min.css
wp-includes/blocks/navigation/style-rtl.css
wp-includes/blocks/navigation/style-rtl.min.css
wp-includes/blocks/navigation/style.css
wp-includes/blocks/navigation/style.min.css
wp-includes/blocks/navigation/view.js
wp-includes/blocks/page-list-item.php
wp-includes/blocks/page-list.php
wp-includes/blocks/paragraph/block.json
wp-includes/blocks/paragraph/style-rtl.css
wp-includes/blocks/paragraph/style-rtl.min.css
wp-includes/blocks/paragraph/style.css
wp-includes/blocks/paragraph/style.min.css
wp-includes/blocks/pattern.php
wp-includes/blocks/post-author-biography.php
wp-includes/blocks/post-author-name.php
wp-includes/blocks/post-author.php
wp-includes/blocks/post-comments-form.php
wp-includes/blocks/post-comments-form/style-rtl.css
wp-includes/blocks/post-comments-form/style-rtl.min.css
wp-includes/blocks/post-comments-form/style.css
wp-includes/blocks/post-comments-form/style.min.css
wp-includes/blocks/post-content.php
wp-includes/blocks/post-date.php
wp-includes/blocks/post-excerpt.php
wp-includes/blocks/post-featured-image.php
wp-includes/blocks/post-featured-image/block.json
wp-includes/blocks/post-featured-image/editor-rtl.css
wp-includes/blocks/post-featured-image/editor-rtl.min.css
wp-includes/blocks/post-featured-image/editor.css
wp-includes/blocks/post-featured-image/editor.min.css
wp-includes/blocks/post-navigation-link.php
wp-includes/blocks/post-template.php
wp-includes/blocks/post-template/style-rtl.css
wp-includes/blocks/post-template/style-rtl.min.css
wp-includes/blocks/post-template/style.css
wp-includes/blocks/post-template/style.min.css
wp-includes/blocks/post-terms.php
wp-includes/blocks/post-title.php
wp-includes/blocks/pullquote/style-rtl.css
wp-includes/blocks/pullquote/style-rtl.min.css
wp-includes/blocks/pullquote/style.css
wp-includes/blocks/pullquote/style.min.css
wp-includes/blocks/query-no-results.php
wp-includes/blocks/query-pagination-next.php
wp-includes/blocks/query-pagination-numbers.php
wp-includes/blocks/query-pagination-previous.php
wp-includes/blocks/query-pagination.php
wp-includes/blocks/query-title.php
wp-includes/blocks/query.php
wp-includes/blocks/query/editor-rtl.css
wp-includes/blocks/query/editor-rtl.min.css
wp-includes/blocks/query/editor.css
wp-includes/blocks/query/editor.min.css
wp-includes/blocks/quote/block.json
wp-includes/blocks/read-more.php
wp-includes/blocks/require-dynamic-blocks.php
wp-includes/blocks/require-static-blocks.php
wp-includes/blocks/rss.php
wp-includes/blocks/rss/editor-rtl.css
wp-includes/blocks/rss/editor-rtl.min.css
wp-includes/blocks/rss/editor.css
wp-includes/blocks/rss/editor.min.css
wp-includes/blocks/search.php
wp-includes/blocks/search/style-rtl.css
wp-includes/blocks/search/style-rtl.min.css
wp-includes/blocks/search/style.css
wp-includes/blocks/search/style.min.css
wp-includes/blocks/separator/editor-rtl.css
wp-includes/blocks/separator/editor-rtl.min.css
wp-includes/blocks/separator/editor.css
wp-includes/blocks/separator/editor.min.css
wp-includes/blocks/separator/style-rtl.css
wp-includes/blocks/separator/style-rtl.min.css
wp-includes/blocks/separator/style.css
wp-includes/blocks/separator/style.min.css
wp-includes/blocks/shortcode.php
wp-includes/blocks/shortcode/editor-rtl.css
wp-includes/blocks/shortcode/editor-rtl.min.css
wp-includes/blocks/shortcode/editor.css
wp-includes/blocks/shortcode/editor.min.css
wp-includes/blocks/site-logo.php
wp-includes/blocks/site-logo/editor-rtl.css
wp-includes/blocks/site-logo/editor-rtl.min.css
wp-includes/blocks/site-logo/editor.css
wp-includes/blocks/site-logo/editor.min.css
wp-includes/blocks/site-logo/style-rtl.css
wp-includes/blocks/site-logo/style-rtl.min.css
wp-includes/blocks/site-logo/style.css
wp-includes/blocks/site-logo/style.min.css
wp-includes/blocks/site-tagline.php
wp-includes/blocks/site-tagline/block.json
wp-includes/blocks/site-title.php
wp-includes/blocks/site-title/editor-rtl.css
wp-includes/blocks/site-title/editor-rtl.min.css
wp-includes/blocks/site-title/editor.css
wp-includes/blocks/site-title/editor.min.css
wp-includes/blocks/site-title/style-rtl.css
wp-includes/blocks/site-title/style-rtl.min.css
wp-includes/blocks/site-title/style.css
wp-includes/blocks/site-title/style.min.css
wp-includes/blocks/social-link.php
wp-includes/blocks/social-link/block.json
wp-includes/blocks/social-link/editor-rtl.css
wp-includes/blocks/social-link/editor-rtl.min.css
wp-includes/blocks/social-link/editor.css
wp-includes/blocks/social-link/editor.min.css
wp-includes/blocks/social-links/block.json
wp-includes/blocks/social-links/editor-rtl.css
wp-includes/blocks/social-links/editor-rtl.min.css
wp-includes/blocks/social-links/editor.css
wp-includes/blocks/social-links/editor.min.css
wp-includes/blocks/social-links/style-rtl.css
wp-includes/blocks/social-links/style-rtl.min.css
wp-includes/blocks/social-links/style.css
wp-includes/blocks/social-links/style.min.css
wp-includes/blocks/table/block.json
wp-includes/blocks/table/theme-rtl.css
wp-includes/blocks/table/theme-rtl.min.css
wp-includes/blocks/table/theme.css
wp-includes/blocks/table/theme.min.css
wp-includes/blocks/tag-cloud.php
wp-includes/blocks/tag-cloud/style-rtl.css
wp-includes/blocks/tag-cloud/style-rtl.min.css
wp-includes/blocks/tag-cloud/style.css
wp-includes/blocks/tag-cloud/style.min.css
wp-includes/blocks/template-part.php
wp-includes/blocks/template-part/editor-rtl.css
wp-includes/blocks/template-part/editor-rtl.min.css
wp-includes/blocks/template-part/editor.css
wp-includes/blocks/template-part/editor.min.css
wp-includes/blocks/template-part/theme-rtl.css
wp-includes/blocks/template-part/theme-rtl.min.css
wp-includes/blocks/template-part/theme.css
wp-includes/blocks/template-part/theme.min.css
wp-includes/blocks/term-description.php
wp-includes/blocks/video/style-rtl.css
wp-includes/blocks/video/style-rtl.min.css
wp-includes/blocks/video/style.css
wp-includes/blocks/video/style.min.css
wp-includes/blocks/video/theme-rtl.css
wp-includes/blocks/video/theme-rtl.min.css
wp-includes/blocks/video/theme.css
wp-includes/blocks/video/theme.min.css
wp-includes/blocks/widget-group.php
wp-includes/blocks/widget-group/block.json
wp-includes/bookmark-template.php
wp-includes/bookmark.php
wp-includes/capabilities.php
wp-includes/class-walker-comment.php
wp-includes/class-wp-admin-bar.php
wp-includes/class-wp-block-bindings-registry.php
wp-includes/class-wp-block-bindings-source.php
wp-includes/class-wp-block-patterns-registry.php
wp-includes/class-wp-block-styles-registry.php
wp-includes/class-wp-block-supports.php
wp-includes/class-wp-block-type.php
wp-includes/class-wp-block.php
wp-includes/class-wp-comment-query.php
wp-includes/class-wp-customize-control.php
wp-includes/class-wp-customize-manager.php
wp-includes/class-wp-customize-nav-menus.php
wp-includes/class-wp-customize-widgets.php
wp-includes/class-wp-duotone.php
wp-includes/class-wp-editor.php
wp-includes/class-wp-http.php
wp-includes/class-wp-image-editor-gd.php
wp-includes/class-wp-image-editor-imagick.php
wp-includes/class-wp-locale.php
wp-includes/class-wp-meta-query.php
wp-includes/class-wp-network-query.php
wp-includes/class-wp-network.php
wp-includes/class-wp-oembed-controller.php
wp-includes/class-wp-oembed.php
wp-includes/class-wp-plugin-dependencies.php
wp-includes/class-wp-post-type.php
wp-includes/class-wp-query.php
wp-includes/class-wp-script-modules.php
wp-includes/class-wp-site-query.php
wp-includes/class-wp-textdomain-registry.php
wp-includes/class-wp-theme-json-data.php
wp-includes/class-wp-theme-json-resolver.php
wp-includes/class-wp-theme-json-schema.php
wp-includes/class-wp-theme-json.php
wp-includes/class-wp-theme.php
wp-includes/class-wp-user-query.php
wp-includes/class-wp-walker.php
wp-includes/class-wpdb.php
wp-includes/block-supports/block-style-variations.php
wp-includes/blocks/button.php
wp-includes/blocks/list.php
wp-includes/blocks/media-text.php
wp-includes/class-wp-token-map.php
wp-includes/html-api/class-wp-html-decoder.php
wp-includes/html-api/class-wp-html-stack-event.php
wp-includes/html-api/html5-named-character-references.php
wp-includes/js/dist/vendor/react-dom.min.js.LICENSE.txt
wp-includes/js/dist/vendor/react-jsx-runtime.js
wp-includes/js/dist/vendor/react-jsx-runtime.min.js
wp-includes/js/dist/vendor/react-jsx-runtime.min.js.LICENSE.txt
wp-includes/js/dist/vendor/react.min.js.LICENSE.txt
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
wp-includes/css/dist/block-editor/default-editor-styles-rtl.css
wp-includes/css/dist/block-editor/default-editor-styles-rtl.min.css
wp-includes/css/dist/block-editor/default-editor-styles.css
wp-includes/css/dist/block-editor/default-editor-styles.min.css
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
wp-includes/css/dist/block-library/reset-rtl.css
wp-includes/css/dist/block-library/reset-rtl.min.css
wp-includes/css/dist/block-library/reset.css
wp-includes/css/dist/block-library/reset.min.css
wp-includes/css/dist/block-library/style-rtl.css
wp-includes/css/dist/block-library/style-rtl.min.css
wp-includes/css/dist/block-library/style.css
wp-includes/css/dist/block-library/style.min.css
wp-includes/css/dist/block-library/theme-rtl.css
wp-includes/css/dist/block-library/theme-rtl.min.css
wp-includes/css/dist/block-library/theme.css
wp-includes/css/dist/block-library/theme.min.css
wp-includes/css/dist/commands/style-rtl.css
wp-includes/css/dist/commands/style-rtl.min.css
wp-includes/css/dist/commands/style.css
wp-includes/css/dist/commands/style.min.css
wp-includes/css/dist/components/style-rtl.css
wp-includes/css/dist/components/style-rtl.min.css
wp-includes/css/dist/components/style.css
wp-includes/css/dist/components/style.min.css
wp-includes/css/dist/customize-widgets/style-rtl.css
wp-includes/css/dist/customize-widgets/style-rtl.min.css
wp-includes/css/dist/customize-widgets/style.css
wp-includes/css/dist/customize-widgets/style.min.css
wp-includes/css/dist/edit-post/classic-rtl.css
wp-includes/css/dist/edit-post/classic-rtl.min.css
wp-includes/css/dist/edit-post/classic.css
wp-includes/css/dist/edit-post/classic.min.css
wp-includes/css/dist/edit-post/style-rtl.css
wp-includes/css/dist/edit-post/style-rtl.min.css
wp-includes/css/dist/edit-post/style.css
wp-includes/css/dist/edit-post/style.min.css
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
wp-includes/css/dist/list-reusable-blocks/style-rtl.css
wp-includes/css/dist/list-reusable-blocks/style-rtl.min.css
wp-includes/css/dist/list-reusable-blocks/style.css
wp-includes/css/dist/list-reusable-blocks/style.min.css
wp-includes/css/dist/nux/style-rtl.css
wp-includes/css/dist/nux/style-rtl.min.css
wp-includes/css/dist/nux/style.css
wp-includes/css/dist/nux/style.min.css
wp-includes/css/dist/patterns/style-rtl.css
wp-includes/css/dist/patterns/style-rtl.min.css
wp-includes/css/dist/patterns/style.css
wp-includes/css/dist/patterns/style.min.css
wp-includes/css/dist/preferences/style-rtl.css
wp-includes/css/dist/preferences/style-rtl.min.css
wp-includes/css/dist/preferences/style.css
wp-includes/css/dist/preferences/style.min.css
wp-includes/css/dist/reusable-blocks/style-rtl.css
wp-includes/css/dist/reusable-blocks/style-rtl.min.css
wp-includes/css/dist/reusable-blocks/style.css
wp-includes/css/dist/reusable-blocks/style.min.css
wp-includes/css/dist/widgets/style-rtl.css
wp-includes/css/dist/widgets/style-rtl.min.css
wp-includes/css/dist/widgets/style.css
wp-includes/css/dist/widgets/style.min.css
wp-includes/css/editor-rtl.css
wp-includes/css/editor-rtl.min.css
wp-includes/css/editor.css
wp-includes/css/editor.min.css
wp-includes/css/media-views-rtl.css
wp-includes/css/media-views-rtl.min.css
wp-includes/css/media-views.css
wp-includes/css/media-views.min.css
wp-includes/css/wp-embed-template.css
wp-includes/css/wp-embed-template.min.css
wp-includes/customize/class-wp-customize-nav-menu-item-control.php
wp-includes/customize/class-wp-customize-themes-section.php
wp-includes/default-constants.php
wp-includes/default-filters.php
wp-includes/deprecated.php
wp-includes/embed.php
wp-includes/feed.php
wp-includes/fonts.php
wp-includes/fonts/class-wp-font-face.php
wp-includes/fonts/class-wp-font-utils.php
wp-includes/formatting.php
wp-includes/functions.php
wp-includes/functions.wp-scripts.php
wp-includes/functions.wp-styles.php
wp-includes/general-template.php
wp-includes/global-styles-and-settings.php
wp-includes/html-api/class-wp-html-open-elements.php
wp-includes/html-api/class-wp-html-processor.php
wp-includes/html-api/class-wp-html-tag-processor.php
wp-includes/http.php
wp-includes/interactivity-api/class-wp-interactivity-api-directives-processor.php
wp-includes/interactivity-api/class-wp-interactivity-api.php
wp-includes/interactivity-api/interactivity-api.php
wp-includes/js/admin-bar.js
wp-includes/js/admin-bar.min.js
wp-includes/js/customize-loader.js
wp-includes/js/customize-selective-refresh.js
wp-includes/js/customize-selective-refresh.min.js
wp-includes/js/dist/annotations.js
wp-includes/js/dist/annotations.min.js
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
wp-includes/js/dist/data.js
wp-includes/js/dist/data.min.js
wp-includes/js/dist/dom.js
wp-includes/js/dist/edit-post.js
wp-includes/js/dist/edit-post.min.js
wp-includes/js/dist/edit-site.js
wp-includes/js/dist/edit-site.min.js
wp-includes/js/dist/edit-widgets.js
wp-includes/js/dist/edit-widgets.min.js
wp-includes/js/dist/editor.js
wp-includes/js/dist/editor.min.js
wp-includes/js/dist/element.js
wp-includes/js/dist/format-library.js
wp-includes/js/dist/format-library.min.js
wp-includes/js/dist/html-entities.js
wp-includes/js/dist/interactivity-router.asset.php
wp-includes/js/dist/interactivity-router.js
wp-includes/js/dist/interactivity-router.min.asset.php
wp-includes/js/dist/interactivity-router.min.js
wp-includes/js/dist/interactivity.js
wp-includes/js/dist/interactivity.min.js
wp-includes/js/dist/keyboard-shortcuts.js
wp-includes/js/dist/keyboard-shortcuts.min.js
wp-includes/js/dist/list-reusable-blocks.js
wp-includes/js/dist/list-reusable-blocks.min.js
wp-includes/js/dist/nux.js
wp-includes/js/dist/nux.min.js
wp-includes/js/dist/patterns.js
wp-includes/js/dist/patterns.min.js
wp-includes/js/dist/plugins.js
wp-includes/js/dist/plugins.min.js
wp-includes/js/dist/preferences-persistence.js
wp-includes/js/dist/preferences-persistence.min.js
wp-includes/js/dist/preferences.js
wp-includes/js/dist/preferences.min.js
wp-includes/js/dist/primitives.js
wp-includes/js/dist/primitives.min.js
wp-includes/js/dist/private-apis.js
wp-includes/js/dist/private-apis.min.js
wp-includes/js/dist/redux-routine.js
wp-includes/js/dist/redux-routine.min.js
wp-includes/js/dist/reusable-blocks.js
wp-includes/js/dist/reusable-blocks.min.js
wp-includes/js/dist/rich-text.js
wp-includes/js/dist/rich-text.min.js
wp-includes/js/dist/router.js
wp-includes/js/dist/router.min.js
wp-includes/js/dist/server-side-render.js
wp-includes/js/dist/server-side-render.min.js
wp-includes/js/dist/style-engine.js
wp-includes/js/dist/style-engine.min.js
wp-includes/js/dist/url.js
wp-includes/js/dist/url.min.js
wp-includes/js/dist/vendor/react-dom.js
wp-includes/js/dist/vendor/react-dom.min.js
wp-includes/js/dist/vendor/react.js
wp-includes/js/dist/vendor/react.min.js
wp-includes/js/dist/viewport.js
wp-includes/js/dist/viewport.min.js
wp-includes/js/dist/warning.js
wp-includes/js/dist/widgets.js
wp-includes/js/dist/widgets.min.js
wp-includes/js/jquery/ui/accordion.js
wp-includes/js/jquery/ui/accordion.min.js
wp-includes/js/jquery/ui/autocomplete.js
wp-includes/js/jquery/ui/autocomplete.min.js
wp-includes/js/jquery/ui/button.js
wp-includes/js/jquery/ui/button.min.js
wp-includes/js/jquery/ui/checkboxradio.js
wp-includes/js/jquery/ui/checkboxradio.min.js
wp-includes/js/jquery/ui/controlgroup.js
wp-includes/js/jquery/ui/controlgroup.min.js
wp-includes/js/jquery/ui/core.js
wp-includes/js/jquery/ui/core.min.js
wp-includes/js/jquery/ui/datepicker.js
wp-includes/js/jquery/ui/datepicker.min.js
wp-includes/js/jquery/ui/dialog.js
wp-includes/js/jquery/ui/dialog.min.js
wp-includes/js/jquery/ui/draggable.js
wp-includes/js/jquery/ui/draggable.min.js
wp-includes/js/jquery/ui/droppable.js
wp-includes/js/jquery/ui/droppable.min.js
wp-includes/js/jquery/ui/effect-blind.js
wp-includes/js/jquery/ui/effect-blind.min.js
wp-includes/js/jquery/ui/effect-bounce.js
wp-includes/js/jquery/ui/effect-bounce.min.js
wp-includes/js/jquery/ui/effect-clip.js
wp-includes/js/jquery/ui/effect-clip.min.js
wp-includes/js/jquery/ui/effect-drop.js
wp-includes/js/jquery/ui/effect-drop.min.js
wp-includes/js/jquery/ui/effect-explode.js
wp-includes/js/jquery/ui/effect-explode.min.js
wp-includes/js/jquery/ui/effect-fade.js
wp-includes/js/jquery/ui/effect-fade.min.js
wp-includes/js/jquery/ui/effect-fold.js
wp-includes/js/jquery/ui/effect-fold.min.js
wp-includes/js/jquery/ui/effect-highlight.js
wp-includes/js/jquery/ui/effect-highlight.min.js
wp-includes/js/jquery/ui/effect-puff.js
wp-includes/js/jquery/ui/effect-puff.min.js
wp-includes/js/jquery/ui/effect-pulsate.js
wp-includes/js/jquery/ui/effect-pulsate.min.js
wp-includes/js/jquery/ui/effect-scale.js
wp-includes/js/jquery/ui/effect-scale.min.js
wp-includes/js/jquery/ui/effect-shake.js
wp-includes/js/jquery/ui/effect-shake.min.js
wp-includes/js/jquery/ui/effect-size.js
wp-includes/js/jquery/ui/effect-size.min.js
wp-includes/js/jquery/ui/effect-slide.js
wp-includes/js/jquery/ui/effect-slide.min.js
wp-includes/js/jquery/ui/effect-transfer.js
wp-includes/js/jquery/ui/effect-transfer.min.js
wp-includes/js/jquery/ui/effect.js
wp-includes/js/jquery/ui/effect.min.js
wp-includes/js/jquery/ui/menu.js
wp-includes/js/jquery/ui/menu.min.js
wp-includes/js/jquery/ui/mouse.js
wp-includes/js/jquery/ui/mouse.min.js
wp-includes/js/jquery/ui/progressbar.js
wp-includes/js/jquery/ui/progressbar.min.js
wp-includes/js/jquery/ui/resizable.js
wp-includes/js/jquery/ui/resizable.min.js
wp-includes/js/jquery/ui/selectable.js
wp-includes/js/jquery/ui/selectable.min.js
wp-includes/js/jquery/ui/selectmenu.js
wp-includes/js/jquery/ui/selectmenu.min.js
wp-includes/js/jquery/ui/slider.js
wp-includes/js/jquery/ui/slider.min.js
wp-includes/js/jquery/ui/sortable.js
wp-includes/js/jquery/ui/sortable.min.js
wp-includes/js/jquery/ui/spinner.js
wp-includes/js/jquery/ui/spinner.min.js
wp-includes/js/jquery/ui/tabs.js
wp-includes/js/jquery/ui/tabs.min.js
wp-includes/js/jquery/ui/tooltip.js
wp-includes/js/jquery/ui/tooltip.min.js
wp-includes/js/media-views.js
wp-includes/js/plupload/handlers.js
wp-includes/js/plupload/handlers.min.js
wp-includes/js/thickbox/thickbox.js
wp-includes/js/tinymce/plugins/wplink/plugin.js
wp-includes/js/tinymce/plugins/wplink/plugin.min.js
wp-includes/js/tinymce/wp-tinymce.js
wp-includes/js/wp-ajax-response.js
wp-includes/js/wp-ajax-response.min.js
wp-includes/js/wp-backbone.js
wp-includes/js/wplink.js
wp-includes/js/wplink.min.js
wp-includes/kses.php
wp-includes/l10n.php
wp-includes/l10n/class-wp-translation-controller.php
wp-includes/l10n/class-wp-translation-file.php
wp-includes/link-template.php
wp-includes/load.php
wp-includes/media-template.php
wp-includes/media.php
wp-includes/ms-blogs.php
wp-includes/ms-default-constants.php
wp-includes/ms-deprecated.php
wp-includes/ms-load.php
wp-includes/ms-site.php
wp-includes/nav-menu-template.php
wp-includes/nav-menu.php
wp-includes/option.php
wp-includes/pluggable.php
wp-includes/pomo/plural-forms.php
wp-includes/post-formats.php
wp-includes/post-template.php
wp-includes/post.php
wp-includes/rest-api.php
wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-block-patterns-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-font-faces-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-font-families-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-global-styles-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-global-styles-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-post-types-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-search-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-settings-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-template-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-themes-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php
wp-includes/revision.php
wp-includes/rss.php
wp-includes/script-loader.php
wp-includes/script-modules.php
wp-includes/shortcodes.php
wp-includes/style-engine.php
wp-includes/style-engine/class-wp-style-engine-css-rule.php
wp-includes/style-engine/class-wp-style-engine-css-rules-store.php
wp-includes/style-engine/class-wp-style-engine-processor.php
wp-includes/style-engine/class-wp-style-engine.php
wp-includes/taxonomy.php
wp-includes/theme-i18n.json
wp-includes/theme.json
wp-includes/theme.php
wp-includes/update.php
wp-includes/user.php
wp-includes/vars.php
wp-includes/version.php
wp-includes/widgets.php
wp-includes/widgets/class-wp-nav-menu-widget.php
wp-load.php
wp-login.php
wp-settings.php
```

First published

July 16, 2024

Last updated

August 5, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.