---
url: https://wordpress.org/documentation/wordpress-version/version-6-5
scraped_at: 2025-10-20T02:01:54.904Z
---

[Skip to content](https://wordpress.org/documentation/wordpress-version/version-6-5/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Version 6.5

[Home](https://wordpress.org/documentation)Version 6.5

Search documentation

# Version 6.5

## In this article

Table of Contents

- [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-5/#installation-update-information)
- [Highlights: What’s inside 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/#highlights)
  - [Add and manage fonts across your site](https://wordpress.org/documentation/wordpress-version/version-6-5/#add-and-manage-fonts-across-your-site)
  - [Get more from your revisions—including revisions for templates and template parts](https://wordpress.org/documentation/wordpress-version/version-6-5/#get-more-from-your-revisions-including-revisions-for-templates-and-template-parts)
  - [Play with enhanced background and shadow tools](https://wordpress.org/documentation/wordpress-version/version-6-5/#play-with-enhanced-background-and-shadow-tools)
  - [Discover new Data Views](https://wordpress.org/documentation/wordpress-version/version-6-5/#discover-new-data-views)
  - [Smoother drag-and-drop](https://wordpress.org/documentation/wordpress-version/version-6-5/#smoother-drag-and-drop)
  - [Improved link controls](https://wordpress.org/documentation/wordpress-version/version-6-5/#improved-link-controls)
- [What’s fresh for developers in 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/#whats-fresh-for-developers-in-6-5)
  - [Bring interactions to blocks with the Interactivity API](https://wordpress.org/documentation/wordpress-version/version-6-5/#bring-interactions-to-blocks-with-the-interactivity-api)
  - [Connect blocks to custom fields or other dynamic content](https://wordpress.org/documentation/wordpress-version/version-6-5/#connect-blocks-to-custom-fields-or-other-dynamic-content)
  - [Add appearance tools to Classic themes](https://wordpress.org/documentation/wordpress-version/version-6-5/#add-appearance-tools-to-classic-themes)
  - [Explore improvements to the plugin experience](https://wordpress.org/documentation/wordpress-version/version-6-5/#explore-improvements-to-the-plugin-experience)
  - [From fast to faster: Performance updates](https://wordpress.org/documentation/wordpress-version/version-6-5/#from-fast-to-faster-performance-updates)
  - [A tradition of inclusion](https://wordpress.org/documentation/wordpress-version/version-6-5/#a-tradition-of-inclusion)
- [Learn more about WordPress 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/#learn-more-about-wordpress-6-5)
- [The 6.5 release squad](https://wordpress.org/documentation/wordpress-version/version-6-5/#the-6-5-release-squad)
- [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-5/#changelog)
  - [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-5/#updated-packages)
  - [List of Files Revised](https://wordpress.org/documentation/wordpress-version/version-6-5/#list-of-files-revised)

[↑ Back to top](https://wordpress.org/documentation/wordpress-version/version-6-5/#wp--skip-link--target)

On April 2, 2024, WordPress 6.5 “Regina” was released to the public. For more information on this release, read the [WordPress 6.5 announcement](https://wordpress.org/news/?p=17132).

For Version 6.5, the database version ( **db\_version** in **wp\_options**) was `57155` and Trac revision was `57914`.

A [full list of tickets included in 6.5](https://core.trac.wordpress.org/milestone/6.5) can be found on [Trac](https://core.trac.wordpress.org/).

## [Installation/Update Information](https://wordpress.org/documentation/wordpress-version/version-6-5/\#installation-update-information)

To download WordPress 6.5, update automatically from the Dashboard > Updates menu in your site’s admin area or visit the [release archive](https://wordpress.org/download/release-archive/).

For step-by-step instructions on installing and updating WordPress:

- [Updating WordPress](https://wordpress.org/documentation/article/updating-wordpress/)

If you are new to WordPress, we recommend that you begin with the following:

- [New To WordPress – Where to Start](https://wordpress.org/support/article/new_to_wordpress_-_where_to_start/)
- [First Steps with WordPress (Classic Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-classic/) or [First Steps with WordPress (Block Editor)](https://wordpress.org/documentation/article/first-steps-with-wordpress-block-editor/)
- [Upgrading WordPress Extended](https://wordpress.org/documentation/article/upgrading-wordpress-extended-instructions/)

* * *

## [Highlights: What’s inside 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/\#highlights)

### [Add and manage fonts across your site](https://wordpress.org/documentation/wordpress-version/version-6-5/\#add-and-manage-fonts-across-your-site)

The new Font Library puts you in control of an essential piece of your site’s design—typography—without coding or extra steps. Effortlessly install, remove, and activate local and Google Fonts across your site for any Block theme. The ability to include custom typography collections gives site creators and publishers more options when it comes to styling content.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/Font-Manager-2.png?resize=1024%2C656&ssl=1)

### [Get more from your revisions—including revisions for templates and template parts](https://wordpress.org/documentation/wordpress-version/version-6-5/\#get-more-from-your-revisions-including-revisions-for-templates-and-template-parts)

Work through creative projects with a more comprehensive picture of what’s been done—and what you can fall back on. Get details like time stamps, quick summaries, and a paginated list of all revisions. View revisions from the Style Book to see how changes impact every block. Revisions are also now available for templates and template parts.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/Revisions-1.png?resize=1024%2C656&ssl=1)

### [Play with enhanced background and shadow tools](https://wordpress.org/documentation/wordpress-version/version-6-5/\#play-with-enhanced-background-and-shadow-tools)

- Control the size, repeat, and focal point options for background images in Group blocks so you can explore subtle or splashy ways to add visual interest to layouts.
- Set aspect ratios for Cover block images and easily add color overlays that automatically source color from your chosen image.
- Add box shadow support to more block types and create layouts with visual depth, or throw a little personality into your design.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/design-tools-1.png?resize=1024%2C656&ssl=1)

### [Discover new Data Views](https://wordpress.org/documentation/wordpress-version/version-6-5/\#discover-new-data-views)

Every piece of your site comes with a library of information and data—now, you can find what you need quickly and organize it however you like. Data views for pages, templates, patterns, and template parts let you see data in a table or grid view, with the option to toggle fields and make bulk changes.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/Data-Views-1.png?resize=1024%2C656&ssl=1)

### [Smoother drag-and-drop](https://wordpress.org/documentation/wordpress-version/version-6-5/\#smoother-drag-and-drop)

Feel the difference when you move things around, with helpful visual cues like displaced items in List View or frictionless dragging to anywhere in your workspace—from beginning to end.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/drag-and-drop-1.png?resize=1024%2C656&ssl=1)

### [Improved link controls](https://wordpress.org/documentation/wordpress-version/version-6-5/\#improved-link-controls)

Create and manage links easily with a more intuitive link-building experience, like a streamlined UI and a shortcut for copying links.

![](https://i0.wp.com/wordpress.org/news/files/2024/04/link-controls-1.png?resize=1024%2C656&ssl=1)

## [What’s fresh for developers in 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/\#whats-fresh-for-developers-in-6-5)

### [Bring interactions to blocks with the Interactivity API](https://wordpress.org/documentation/wordpress-version/version-6-5/\#bring-interactions-to-blocks-with-the-interactivity-api)

The [Interactivity API](https://make.wordpress.org/core/2024/03/04/interactivity-api-dev-note/) offers developers a standardized method for building interactive front-end experiences with blocks. It simplifies the process, with fewer dependencies on external tooling, while maintaining optimal performance. Use it to create memorable user experiences, like fetching search results instantly or letting visitors interact with content in real time.

### [Connect blocks to custom fields or other dynamic content](https://wordpress.org/documentation/wordpress-version/version-6-5/\#connect-blocks-to-custom-fields-or-other-dynamic-content)

Link core block attributes to custom fields and use the value of custom fields without creating custom blocks. Powered by the [Block Bindings API](https://make.wordpress.org/core/2024/03/06/new-feature-the-block-bindings-api/), developers can extend this capability further to connect blocks to any dynamic content—even beyond custom fields. If there’s data stored elsewhere, easily point blocks to that new source with only a few lines of code.

### [Add appearance tools to Classic themes](https://wordpress.org/documentation/wordpress-version/version-6-5/\#add-appearance-tools-to-classic-themes)

Give designers and creators using Classic themes access to an upgraded design experience. Opt in to support for spacing, border, typography, and color options, even without using theme.json. Once support is enabled, more tools will be automatically added as they become available.

### [Explore improvements to the plugin experience](https://wordpress.org/documentation/wordpress-version/version-6-5/\#explore-improvements-to-the-plugin-experience)

There’s now an [easier way to manage plugin dependencies](https://make.wordpress.org/core/2024/03/05/introducing-plugin-dependencies-in-wordpress-6-5/). Plugin authors can supply a new `Requires Plugins` header with a comma-separated list of required plugin slugs, presenting users with links to install and activate those plugins first.

### [From fast to faster: Performance updates](https://wordpress.org/documentation/wordpress-version/version-6-5/\#from-fast-to-faster-performance-updates)

This release includes 110+ performance updates, resulting in an impressive increase in speed and efficiency across the Post Editor and Site Editor. Loading is over two times faster than in 6.4, with input processing speed up to five times faster than the previous release.

Translated sites see up to 25% improvement in load time for this release courtesy of [Performant Translations](https://make.wordpress.org/core/2024/02/27/i18n-improvements-6-5-performant-translations/). Additional performance highlights include [AVIF image support](https://make.wordpress.org/core/2024/02/23/wordpress-6-5-adds-avif-support/) and improvements for [registering block variations with callbacks](https://make.wordpress.org/core/2024/02/29/performance-improvements-for-registering-block-variations-with-callbacks/).

### [A tradition of inclusion](https://wordpress.org/documentation/wordpress-version/version-6-5/\#a-tradition-of-inclusion)

This release includes more than 65 accessibility improvements across the platform, making it more accessible than ever. It contains an important fix that unblocks access to the admin submenus for screen reader users and others who navigate by keyboard. This release also adds fixes to color contrast in admin focus states, positioning of elements, and cursor focus, among many others, that help improve the WordPress experience for everyone.

## [Learn more about WordPress 6.5](https://wordpress.org/documentation/wordpress-version/version-6-5/\#learn-more-about-wordpress-6-5)

Check out the new [WordPress 6.5 page](https://wordpress.org/download/releases/6-5/) to learn more about the numerous enhancements and features of this release—including short demos of some of the highlighted features.

Explore [Learn WordPress](https://learn.wordpress.org/) for quick how-to videos, [online workshops](https://learn.wordpress.org/social-learning/), and other free resources to level up your WordPress knowledge and skills.

Check out the [WordPress 6.5 Field Guide](https://make.wordpress.org/core/2024/03/15/wordpress-6-5-field-guide/) for detailed technical information and [developer notes](https://make.wordpress.org/core/tag/dev-notes-6-5/) to help you build with WordPress and get the most out of this release. Don’t forget to subscribe to the [Developer Blog](https://developer.wordpress.org/news/) for developer updates, feature tutorials, and other helpful WordPress content from a developer perspective.

For more information about installation, file changes, fixes, and other updates, read the [6.5 release notes](https://wordpress.org/documentation/wordpress-version/version-6-5/).

## [The 6.5 release squad](https://wordpress.org/documentation/wordpress-version/version-6-5/\#the-6-5-release-squad)

Every release has many moving parts with its own triumphs and challenges. It takes a dedicated team of enthusiastic contributors to help keep things on track and moving smoothly. 6.5 is made possible by a cross-functional group of contributors, always ready to champion ideas, remove blockers, and resolve issues.

- Release Lead: [Matt Mullenweg](https://profiles.wordpress.org/matt/)
- Release Coordinators: [Akshaya Rane](https://profiles.wordpress.org/akshayar/), [Héctor Prieto](https://profiles.wordpress.org/priethor/), [Mary Baum](https://profiles.wordpress.org/marybaum/)
- Core Tech Leads: [David Baumwald](https://profiles.wordpress.org/davidbaumwald/), [Pascal Birchler](https://profiles.wordpress.org/swissspidy/)
- Editor Tech Leads: [David Smith](https://profiles.wordpress.org/get_dave/), [Riad Benguella](https://profiles.wordpress.org/youknowriad/)
- Core Triage Leads: [Ahmed Kabir Chaion](https://profiles.wordpress.org/chaion07/), [Jb Audras](https://profiles.wordpress.org/audrasjb/), [Rajin Sharwar](https://profiles.wordpress.org/rajinsharwar/)
- Editor Triage Leads: [Anne McCarthy](https://profiles.wordpress.org/annezazu/), [Fabian Kägy](https://profiles.wordpress.org/fabiankaegy/)
- Design Leads: [Benjamin Zekavica](https://profiles.wordpress.org/benjamin_zekavica/), [Rich Tabor](https://profiles.wordpress.org/richtabor/)
- Marketing and Communication Leads: [Dan Soschin](https://profiles.wordpress.org/dansoschin/), [Lauren Stein](https://profiles.wordpress.org/laurlittle/)
- Documentation Leads: [Estela Rueda](https://profiles.wordpress.org/estelaris/), [Leonardus Nugraha](https://profiles.wordpress.org/leonnugraha/), [Steven Lin](https://profiles.wordpress.org/stevenlinx/)
- Performance Leads: [Joe McGill](https://profiles.wordpress.org/joemcgill/), [Mukesh Panchal](https://profiles.wordpress.org/mukesh27/)
- Test Leads: [Olga Gleckler](https://profiles.wordpress.org/oglekler/), [Patrick Lumumba](https://profiles.wordpress.org/lumiblog/), [Vipul Ghori](https://profiles.wordpress.org/vipuljnext/)
- Default Themes Leads: [Carolina Nymark](https://profiles.wordpress.org/poena/)

## [Changelog](https://wordpress.org/documentation/wordpress-version/version-6-5/\#changelog)

### [Updated packages](https://wordpress.org/documentation/wordpress-version/version-6-5/\#updated-packages)

```
@pmmmwh/react-refresh-webpack-plugin - 0.5.11
@wordpress/babel-preset-default - 7.35.1
@wordpress/dependency-extraction-webpack-plugin - 5.2.1
@wordpress/e2e-test-utils - 10.22.1
@wordpress/e2e-test-utils-playwright - 0.19.2
@wordpress/prettier-config - 3.8.1
@wordpress/scripts - 27.2.5
autoprefixer - 10.4.17
copy-webpack-plugin - 12.0.2
cssnano - 6.0.3
dotenv - 16.4.4
dotenv-expand - 11.0.3
grunt-patch-wordpress - ~4.0.0
postcss - 8.4.35
sass - 1.70.0
sinon - 16.1.3
source-map-loader - 5.0.0
terser-webpack-plugin - 5.3.10
wait-on - 7.2.0
webpack - 5.90.2
@wordpress/a11y - 3.51.1
@wordpress/annotations - 2.51.4
@wordpress/api-fetch - 6.48.1
@wordpress/autop - 3.51.1
@wordpress/blob - 3.51.1
@wordpress/block-directory - 4.28.9
@wordpress/block-editor - 12.19.7
@wordpress/block-library - 8.28.9
@wordpress/block-serialization-default-parser - 4.51.1
@wordpress/blocks - 12.28.6
@wordpress/commands - 0.22.5
@wordpress/components - 26.0.5
@wordpress/compose - 6.28.1
@wordpress/core-commands - 0.20.7
@wordpress/core-data - 6.28.7
@wordpress/customize-widgets - 4.28.9
@wordpress/data - 9.21.1
@wordpress/data-controls - 3.20.1
@wordpress/dataviews - 0.5.6
@wordpress/date - 4.51.1
@wordpress/deprecated - 3.51.1
@wordpress/dom - 3.51.1
@wordpress/dom-ready - 3.51.1
@wordpress/edit-post - 7.28.9
@wordpress/edit-site - 5.28.9
@wordpress/edit-widgets - 5.28.9
@wordpress/editor - 13.28.7
@wordpress/element - 5.28.1
@wordpress/escape-html - 2.51.1
@wordpress/format-library - 4.28.7
@wordpress/hooks - 3.51.1
@wordpress/html-entities - 3.51.1
@wordpress/i18n - 4.51.1
@wordpress/icons - 9.42.4
@wordpress/interactivity - 5.0.5
@wordpress/interactivity-router - 1.1.5
@wordpress/interface - 5.28.5
@wordpress/is-shallow-equal - 4.51.1
@wordpress/keyboard-shortcuts - 4.28.1
@wordpress/keycodes - 3.51.1
@wordpress/list-reusable-blocks - 4.28.5
@wordpress/media-utils - 4.42.2
@wordpress/notices - 4.19.1
@wordpress/nux - 8.13.5
@wordpress/patterns - 1.12.7
@wordpress/plugins - 6.19.5
@wordpress/preferences - 3.28.5
@wordpress/preferences-persistence - 1.43.1
@wordpress/primitives - 3.49.1
@wordpress/priority-queue - 2.51.1
@wordpress/private-apis - 0.33.1
@wordpress/redux-routine - 4.51.1
@wordpress/reusable-blocks - 4.28.7
@wordpress/rich-text - 6.28.4
@wordpress/router - 0.20.1
@wordpress/server-side-render - 4.28.6
@wordpress/shortcode - 3.51.1
@wordpress/style-engine - 1.34.1
@wordpress/sync - 0.13.1
@wordpress/token-list - 2.51.1
@wordpress/undo-manager - 0.11.1
@wordpress/url - 3.52.1
@wordpress/viewport - 5.28.1
@wordpress/warning - 2.51.1
@wordpress/widgets - 3.28.7
@wordpress/wordcount - 3.51.1
es-module-shims - 1.8.2
react-is - 18.2.0
```

### [List of Files Revised](https://wordpress.org/documentation/wordpress-version/version-6-5/\#list-of-files-revised)

```
Edited Files:

license.txt
readme.html
wp-activate.php
wp-admin/.DS_Store
wp-admin/about.php
wp-admin/admin-ajax.php
wp-admin/contribute.php
wp-admin/credits.php
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
wp-admin/css/deprecated-media-rtl.css
wp-admin/css/deprecated-media-rtl.min.css
wp-admin/css/deprecated-media.css
wp-admin/css/deprecated-media.min.css
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
wp-admin/css/revisions-rtl.css
wp-admin/css/revisions-rtl.min.css
wp-admin/css/revisions.css
wp-admin/css/revisions.min.css
wp-admin/css/site-health-rtl.css
wp-admin/css/site-health-rtl.min.css
wp-admin/css/site-health.css
wp-admin/css/site-health.min.css
wp-admin/css/site-icon-rtl.css
wp-admin/css/site-icon-rtl.min.css
wp-admin/css/site-icon.css
wp-admin/css/site-icon.min.css
wp-admin/css/themes-rtl.css
wp-admin/css/themes-rtl.min.css
wp-admin/css/themes.css
wp-admin/css/themes.min.css
wp-admin/css/widgets-rtl.css
wp-admin/css/widgets-rtl.min.css
wp-admin/css/widgets.css
wp-admin/css/widgets.min.css
wp-admin/edit-form-advanced.php
wp-admin/freedoms.php
wp-admin/images/about-release-badge.svg
wp-admin/images/bubble_bg-2x.gif
wp-admin/images/contribute-code.svg
wp-admin/images/contribute-main.svg
wp-admin/images/contribute-no-code.svg
wp-admin/images/freedom-1.svg
wp-admin/images/freedom-2.svg
wp-admin/images/freedom-3.svg
wp-admin/images/freedom-4.svg
wp-admin/images/loading.gif
wp-admin/images/media-button-music.gif
wp-admin/images/media-button-other.gif
wp-admin/images/privacy.svg
wp-admin/images/wpspin_light-2x.gif
wp-admin/images/wpspin_light.gif
wp-admin/images/xit.gif
wp-admin/import.php
wp-admin/includes/ajax-actions.php
wp-admin/includes/class-custom-background.php
wp-admin/includes/class-custom-image-header.php
wp-admin/includes/class-file-upload-upgrader.php
wp-admin/includes/class-ftp.php
wp-admin/includes/class-language-pack-upgrader.php
wp-admin/includes/class-pclzip.php
wp-admin/includes/class-plugin-installer-skin.php
wp-admin/includes/class-plugin-upgrader.php
wp-admin/includes/class-theme-installer-skin.php
wp-admin/includes/class-theme-upgrader-skin.php
wp-admin/includes/class-theme-upgrader.php
wp-admin/includes/class-wp-application-passwords-list-table.php
wp-admin/includes/class-wp-comments-list-table.php
wp-admin/includes/class-wp-debug-data.php
wp-admin/includes/class-wp-filesystem-base.php
wp-admin/includes/class-wp-filesystem-direct.php
wp-admin/includes/class-wp-filesystem-ftpext.php
wp-admin/includes/class-wp-filesystem-ftpsockets.php
wp-admin/includes/class-wp-filesystem-ssh2.php
wp-admin/includes/class-wp-list-table.php
wp-admin/includes/class-wp-ms-sites-list-table.php
wp-admin/includes/class-wp-ms-users-list-table.php
wp-admin/includes/class-wp-plugin-install-list-table.php
wp-admin/includes/class-wp-plugins-list-table.php
wp-admin/includes/class-wp-privacy-policy-content.php
wp-admin/includes/class-wp-screen.php
wp-admin/includes/class-wp-site-health.php
wp-admin/includes/class-wp-site-icon.php
wp-admin/includes/class-wp-theme-install-list-table.php
wp-admin/includes/class-wp-themes-list-table.php
wp-admin/includes/class-wp-upgrader-skin.php
wp-admin/includes/class-wp-users-list-table.php
wp-admin/includes/dashboard.php
wp-admin/includes/deprecated.php
wp-admin/includes/export.php
wp-admin/includes/file.php
wp-admin/includes/image-edit.php
wp-admin/includes/image.php
wp-admin/includes/media.php
wp-admin/includes/menu.php
wp-admin/includes/meta-boxes.php
wp-admin/includes/misc.php
wp-admin/includes/ms.php
wp-admin/includes/nav-menu.php
wp-admin/includes/options.php
wp-admin/includes/plugin-install.php
wp-admin/includes/plugin.php
wp-admin/includes/post.php
wp-admin/includes/revision.php
wp-admin/includes/schema.php
wp-admin/includes/template.php
wp-admin/includes/theme-install.php
wp-admin/includes/theme.php
wp-admin/includes/update-core.php
wp-admin/includes/update.php
wp-admin/includes/upgrade.php
wp-admin/includes/user.php
wp-admin/install.php
wp-admin/js/comment.js
wp-admin/js/common.js
wp-admin/js/common.min.js
wp-admin/js/customize-controls.js
wp-admin/js/customize-controls.min.js
wp-admin/js/customize-nav-menus.js
wp-admin/js/customize-nav-menus.min.js
wp-admin/js/inline-edit-post.js
wp-admin/js/inline-edit-post.min.js
wp-admin/js/media.js
wp-admin/js/media.min.js
wp-admin/js/post.js
wp-admin/js/post.min.js
wp-admin/js/site-health.js
wp-admin/js/site-health.min.js
wp-admin/js/tags-suggest.js
wp-admin/js/tags-suggest.min.js
wp-admin/js/theme.js
wp-admin/js/updates.js
wp-admin/js/updates.min.js
wp-admin/js/user-profile.js
wp-admin/menu.php
wp-admin/options-general.php
wp-admin/options-permalink.php
wp-admin/options-privacy.php
wp-admin/options.php
wp-admin/plugin-editor.php
wp-admin/plugin-install.php
wp-admin/plugins.php
wp-admin/press-this.php
wp-admin/privacy-policy-guide.php
wp-admin/privacy.php
wp-admin/setup-config.php
wp-admin/site-editor.php
wp-admin/theme-editor.php
wp-admin/update-core.php
wp-admin/user-new.php
wp-admin/widgets-form.php
wp-config-sample.php
wp-content/.DS_Store
wp-content/plugins/akismet/akismet.php
wp-content/plugins/akismet/class.akismet-admin.php
wp-content/plugins/akismet/class.akismet-rest-api.php
wp-content/plugins/akismet/class.akismet.php
wp-content/plugins/akismet/readme.txt
wp-content/plugins/akismet/views/config.php
wp-content/plugins/akismet/views/notice.php
wp-content/themes/.DS_Store
wp-content/themes/twentytwentyfour/functions.php
wp-content/themes/twentytwentyfour/parts/header.html
wp-content/themes/twentytwentyfour/patterns/footer.php
wp-content/themes/twentytwentyfour/patterns/hidden-portfolio-hero.php
wp-content/themes/twentytwentyfour/patterns/page-about-business.php
wp-content/themes/twentytwentyfour/patterns/page-home-blogging.php
wp-content/themes/twentytwentyfour/patterns/page-home-business.php
wp-content/themes/twentytwentyfour/patterns/page-home-portfolio-gallery.php
wp-content/themes/twentytwentyfour/patterns/page-home-portfolio.php
wp-content/themes/twentytwentyfour/patterns/page-newsletter-landing.php
wp-content/themes/twentytwentyfour/patterns/page-portfolio-overview.php
wp-content/themes/twentytwentyfour/patterns/page-rsvp-landing.php
wp-content/themes/twentytwentyfour/readme.txt
wp-content/themes/twentytwentyfour/screenshot.png
wp-content/themes/twentytwentyfour/style.css
wp-content/themes/twentytwentyfour/styles/ember.json
wp-content/themes/twentytwentyfour/theme.json
wp-content/themes/twentytwentythree/assets/fonts/dm-sans/DMSans-Bold-Italic.woff2
wp-content/themes/twentytwentythree/assets/fonts/dm-sans/DMSans-Bold.woff2
wp-content/themes/twentytwentythree/assets/fonts/dm-sans/DMSans-Regular-Italic.woff2
wp-content/themes/twentytwentythree/assets/fonts/dm-sans/DMSans-Regular.woff2
wp-content/themes/twentytwentythree/readme.txt
wp-content/themes/twentytwentythree/screenshot.png
wp-content/themes/twentytwentythree/style.css
wp-content/themes/twentytwentythree/styles/aubergine.json
wp-content/themes/twentytwentythree/styles/block-out.json
wp-content/themes/twentytwentythree/styles/pitch.json
wp-content/themes/twentytwentythree/styles/whisper.json
wp-content/themes/twentytwentythree/theme.json
wp-content/themes/twentytwentytwo/assets/images/bird-on-black.jpg
wp-content/themes/twentytwentytwo/assets/images/bird-on-gray.jpg
wp-content/themes/twentytwentytwo/assets/images/bird-on-green.jpg
wp-content/themes/twentytwentytwo/assets/images/bird-on-salmon.jpg
wp-content/themes/twentytwentytwo/assets/images/ducks.jpg
wp-content/themes/twentytwentytwo/assets/images/flight-path-on-gray-a.jpg
wp-content/themes/twentytwentytwo/assets/images/flight-path-on-gray-b.jpg
wp-content/themes/twentytwentytwo/assets/images/flight-path-on-gray-c.jpg
wp-content/themes/twentytwentytwo/assets/images/flight-path-on-salmon.jpg
wp-content/themes/twentytwentytwo/assets/images/icon-bird.jpg
wp-content/themes/twentytwentytwo/inc/block-patterns.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-large-image-and-buttons.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-links-dark.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-links.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-media-left.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-media-right.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-simple-dark.php
wp-content/themes/twentytwentytwo/inc/patterns/page-about-solid-color.php
wp-content/themes/twentytwentytwo/inc/patterns/page-layout-image-and-text.php
wp-content/themes/twentytwentytwo/inc/patterns/page-layout-image-text-and-video.php
wp-content/themes/twentytwentytwo/inc/patterns/page-layout-two-columns.php
wp-content/themes/twentytwentytwo/inc/patterns/page-sidebar-blog-posts-right.php
wp-content/themes/twentytwentytwo/inc/patterns/page-sidebar-blog-posts.php
wp-content/themes/twentytwentytwo/inc/patterns/page-sidebar-grid-posts.php
wp-content/themes/twentytwentytwo/inc/patterns/page-sidebar-poster.php
wp-content/themes/twentytwentytwo/readme.txt
wp-content/themes/twentytwentytwo/screenshot.png
wp-content/themes/twentytwentytwo/style.css
wp-content/themes/twentytwentytwo/theme.json
wp-includes/.DS_Store
wp-includes/ID3/getid3.lib.php
wp-includes/ID3/getid3.php
wp-includes/ID3/license.txt
wp-includes/ID3/module.audio-video.asf.php
wp-includes/ID3/module.audio-video.matroska.php
wp-includes/ID3/module.audio-video.quicktime.php
wp-includes/ID3/module.audio-video.riff.php
wp-includes/ID3/module.audio.mp3.php
wp-includes/ID3/module.audio.ogg.php
wp-includes/ID3/module.tag.apetag.php
wp-includes/ID3/module.tag.id3v1.php
wp-includes/ID3/module.tag.id3v2.php
wp-includes/ID3/readme.txt
wp-includes/PHPMailer/PHPMailer.php
wp-includes/PHPMailer/SMTP.php
wp-includes/Requests/.DS_Store
wp-includes/SimplePie/.DS_Store
wp-includes/Text/Diff.php
wp-includes/admin-bar.php
wp-includes/assets/script-loader-packages.min.php
wp-includes/assets/script-loader-packages.php
wp-includes/assets/script-loader-react-refresh-entry.min.php
wp-includes/assets/script-loader-react-refresh-entry.php
wp-includes/assets/script-loader-react-refresh-runtime.min.php
wp-includes/assets/script-loader-react-refresh-runtime.php
wp-includes/block-patterns.php
wp-includes/block-supports/background.php
wp-includes/block-supports/dimensions.php
wp-includes/block-supports/elements.php
wp-includes/block-supports/layout.php
wp-includes/block-supports/shadow.php
wp-includes/block-supports/typography.php
wp-includes/block-template-utils.php
wp-includes/blocks.php
wp-includes/blocks/.DS_Store
wp-includes/blocks/archives/block.json
wp-includes/blocks/audio/block.json
wp-includes/blocks/audio/theme-rtl.css
wp-includes/blocks/audio/theme-rtl.min.css
wp-includes/blocks/audio/theme.css
wp-includes/blocks/audio/theme.min.css
wp-includes/blocks/avatar/block.json
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
wp-includes/blocks/buttons/block.json
wp-includes/blocks/calendar.php
wp-includes/blocks/calendar/block.json
wp-includes/blocks/categories.php
wp-includes/blocks/categories/block.json
wp-includes/blocks/code/block.json
wp-includes/blocks/column/block.json
wp-includes/blocks/columns/block.json
wp-includes/blocks/comment-author-name/block.json
wp-includes/blocks/comment-date/block.json
wp-includes/blocks/comment-edit-link/block.json
wp-includes/blocks/comment-template/block.json
wp-includes/blocks/comments-pagination-next/block.json
wp-includes/blocks/comments-pagination-numbers/block.json
wp-includes/blocks/comments-pagination-previous/block.json
wp-includes/blocks/comments-pagination/block.json
wp-includes/blocks/comments-title/block.json
wp-includes/blocks/cover/block.json
wp-includes/blocks/cover/style-rtl.css
wp-includes/blocks/cover/style-rtl.min.css
wp-includes/blocks/cover/style.css
wp-includes/blocks/cover/style.min.css
wp-includes/blocks/details/block.json
wp-includes/blocks/embed/block.json
wp-includes/blocks/embed/editor-rtl.css
wp-includes/blocks/embed/editor-rtl.min.css
wp-includes/blocks/embed/editor.css
wp-includes/blocks/embed/editor.min.css
wp-includes/blocks/embed/theme-rtl.css
wp-includes/blocks/embed/theme-rtl.min.css
wp-includes/blocks/embed/theme.css
wp-includes/blocks/embed/theme.min.css
wp-includes/blocks/file.php
wp-includes/blocks/file/block.json
wp-includes/blocks/file/view.asset.php
wp-includes/blocks/file/view.js
wp-includes/blocks/file/view.min.asset.php
wp-includes/blocks/file/view.min.js
wp-includes/blocks/footnotes.php
wp-includes/blocks/footnotes/block.json
wp-includes/blocks/freeform/editor-rtl.css
wp-includes/blocks/freeform/editor-rtl.min.css
wp-includes/blocks/freeform/editor.css
wp-includes/blocks/freeform/editor.min.css
wp-includes/blocks/gallery.php
wp-includes/blocks/gallery/block.json
wp-includes/blocks/gallery/editor-rtl.css
wp-includes/blocks/gallery/editor-rtl.min.css
wp-includes/blocks/gallery/editor.css
wp-includes/blocks/gallery/editor.min.css
wp-includes/blocks/gallery/style-rtl.css
wp-includes/blocks/gallery/style-rtl.min.css
wp-includes/blocks/gallery/style.css
wp-includes/blocks/gallery/style.min.css
wp-includes/blocks/gallery/theme-rtl.css
wp-includes/blocks/gallery/theme-rtl.min.css
wp-includes/blocks/gallery/theme.css
wp-includes/blocks/gallery/theme.min.css
wp-includes/blocks/group/block.json
wp-includes/blocks/heading/block.json
wp-includes/blocks/home-link.php
wp-includes/blocks/home-link/block.json
wp-includes/blocks/html/block.json
wp-includes/blocks/html/editor-rtl.css
wp-includes/blocks/html/editor-rtl.min.css
wp-includes/blocks/html/editor.css
wp-includes/blocks/html/editor.min.css
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
wp-includes/blocks/image/theme-rtl.css
wp-includes/blocks/image/theme-rtl.min.css
wp-includes/blocks/image/theme.css
wp-includes/blocks/image/theme.min.css
wp-includes/blocks/image/view.asset.php
wp-includes/blocks/image/view.js
wp-includes/blocks/image/view.min.asset.php
wp-includes/blocks/image/view.min.js
wp-includes/blocks/latest-comments/block.json
wp-includes/blocks/latest-posts/block.json
wp-includes/blocks/legacy-widget/block.json
wp-includes/blocks/list-item/block.json
wp-includes/blocks/list/block.json
wp-includes/blocks/loginout/block.json
wp-includes/blocks/media-text/block.json
wp-includes/blocks/media-text/style-rtl.css
wp-includes/blocks/media-text/style-rtl.min.css
wp-includes/blocks/media-text/style.css
wp-includes/blocks/media-text/style.min.css
wp-includes/blocks/missing/block.json
wp-includes/blocks/more/block.json
wp-includes/blocks/navigation-link.php
wp-includes/blocks/navigation-link/block.json
wp-includes/blocks/navigation-link/editor-rtl.css
wp-includes/blocks/navigation-link/editor-rtl.min.css
wp-includes/blocks/navigation-link/editor.css
wp-includes/blocks/navigation-link/editor.min.css
wp-includes/blocks/navigation-link/style-rtl.css
wp-includes/blocks/navigation-link/style-rtl.min.css
wp-includes/blocks/navigation-link/style.css
wp-includes/blocks/navigation-link/style.min.css
wp-includes/blocks/navigation-submenu/block.json
wp-includes/blocks/navigation-submenu/editor-rtl.css
wp-includes/blocks/navigation-submenu/editor-rtl.min.css
wp-includes/blocks/navigation-submenu/editor.css
wp-includes/blocks/navigation-submenu/editor.min.css
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
wp-includes/blocks/navigation/view.asset.php
wp-includes/blocks/navigation/view.js
wp-includes/blocks/navigation/view.min.asset.php
wp-includes/blocks/navigation/view.min.js
wp-includes/blocks/nextpage/block.json
wp-includes/blocks/page-list-item/block.json
wp-includes/blocks/page-list/block.json
wp-includes/blocks/page-list/editor-rtl.css
wp-includes/blocks/page-list/editor-rtl.min.css
wp-includes/blocks/page-list/editor.css
wp-includes/blocks/page-list/editor.min.css
wp-includes/blocks/paragraph/block.json
wp-includes/blocks/pattern.php
wp-includes/blocks/pattern/block.json
wp-includes/blocks/post-author-biography/block.json
wp-includes/blocks/post-author-name/block.json
wp-includes/blocks/post-author/block.json
wp-includes/blocks/post-date/block.json
wp-includes/blocks/post-excerpt/block.json
wp-includes/blocks/post-featured-image.php
wp-includes/blocks/post-featured-image/block.json
wp-includes/blocks/post-featured-image/editor-rtl.css
wp-includes/blocks/post-featured-image/editor-rtl.min.css
wp-includes/blocks/post-featured-image/editor.css
wp-includes/blocks/post-featured-image/editor.min.css
wp-includes/blocks/post-featured-image/style-rtl.css
wp-includes/blocks/post-featured-image/style-rtl.min.css
wp-includes/blocks/post-featured-image/style.css
wp-includes/blocks/post-featured-image/style.min.css
wp-includes/blocks/post-navigation-link.php
wp-includes/blocks/post-navigation-link/block.json
wp-includes/blocks/post-template/block.json
wp-includes/blocks/post-template/style-rtl.css
wp-includes/blocks/post-template/style-rtl.min.css
wp-includes/blocks/post-template/style.css
wp-includes/blocks/post-template/style.min.css
wp-includes/blocks/post-terms.php
wp-includes/blocks/post-terms/block.json
wp-includes/blocks/post-title.php
wp-includes/blocks/post-title/block.json
wp-includes/blocks/preformatted/block.json
wp-includes/blocks/pullquote/block.json
wp-includes/blocks/pullquote/style-rtl.css
wp-includes/blocks/pullquote/style-rtl.min.css
wp-includes/blocks/pullquote/style.css
wp-includes/blocks/pullquote/style.min.css
wp-includes/blocks/query-no-results/block.json
wp-includes/blocks/query-pagination-next.php
wp-includes/blocks/query-pagination-next/block.json
wp-includes/blocks/query-pagination-numbers.php
wp-includes/blocks/query-pagination-numbers/block.json
wp-includes/blocks/query-pagination-previous.php
wp-includes/blocks/query-pagination-previous/block.json
wp-includes/blocks/query-pagination/block.json
wp-includes/blocks/query-pagination/style-rtl.css
wp-includes/blocks/query-pagination/style-rtl.min.css
wp-includes/blocks/query-pagination/style.css
wp-includes/blocks/query-pagination/style.min.css
wp-includes/blocks/query-title/block.json
wp-includes/blocks/query.php
wp-includes/blocks/query/block.json
wp-includes/blocks/query/editor-rtl.css
wp-includes/blocks/query/editor-rtl.min.css
wp-includes/blocks/query/editor.css
wp-includes/blocks/query/editor.min.css
wp-includes/blocks/query/view.asset.php
wp-includes/blocks/query/view.js
wp-includes/blocks/query/view.min.asset.php
wp-includes/blocks/query/view.min.js
wp-includes/blocks/quote/block.json
wp-includes/blocks/quote/style-rtl.css
wp-includes/blocks/quote/style-rtl.min.css
wp-includes/blocks/quote/style.css
wp-includes/blocks/quote/style.min.css
wp-includes/blocks/read-more/block.json
wp-includes/blocks/read-more/style-rtl.css
wp-includes/blocks/read-more/style-rtl.min.css
wp-includes/blocks/read-more/style.css
wp-includes/blocks/read-more/style.min.css
wp-includes/blocks/rss/block.json
wp-includes/blocks/search.php
wp-includes/blocks/search/block.json
wp-includes/blocks/search/editor-rtl.css
wp-includes/blocks/search/editor-rtl.min.css
wp-includes/blocks/search/editor.css
wp-includes/blocks/search/editor.min.css
wp-includes/blocks/search/style-rtl.css
wp-includes/blocks/search/style-rtl.min.css
wp-includes/blocks/search/style.css
wp-includes/blocks/search/style.min.css
wp-includes/blocks/search/view.asset.php
wp-includes/blocks/search/view.js
wp-includes/blocks/search/view.min.asset.php
wp-includes/blocks/search/view.min.js
wp-includes/blocks/separator/block.json
wp-includes/blocks/separator/style-rtl.css
wp-includes/blocks/separator/style-rtl.min.css
wp-includes/blocks/separator/style.css
wp-includes/blocks/separator/style.min.css
wp-includes/blocks/shortcode/editor-rtl.css
wp-includes/blocks/shortcode/editor-rtl.min.css
wp-includes/blocks/shortcode/editor.css
wp-includes/blocks/shortcode/editor.min.css
wp-includes/blocks/site-logo/block.json
wp-includes/blocks/site-logo/editor-rtl.css
wp-includes/blocks/site-logo/editor-rtl.min.css
wp-includes/blocks/site-logo/editor.css
wp-includes/blocks/site-logo/editor.min.css
wp-includes/blocks/site-tagline/block.json
wp-includes/blocks/site-title/block.json
wp-includes/blocks/social-link.php
wp-includes/blocks/social-link/block.json
wp-includes/blocks/social-links/block.json
wp-includes/blocks/social-links/style-rtl.css
wp-includes/blocks/social-links/style-rtl.min.css
wp-includes/blocks/social-links/style.css
wp-includes/blocks/social-links/style.min.css
wp-includes/blocks/spacer/block.json
wp-includes/blocks/spacer/editor-rtl.css
wp-includes/blocks/spacer/editor-rtl.min.css
wp-includes/blocks/spacer/editor.css
wp-includes/blocks/spacer/editor.min.css
wp-includes/blocks/table/block.json
wp-includes/blocks/table/editor-rtl.css
wp-includes/blocks/table/editor-rtl.min.css
wp-includes/blocks/table/editor.css
wp-includes/blocks/table/editor.min.css
wp-includes/blocks/table/style-rtl.css
wp-includes/blocks/table/style-rtl.min.css
wp-includes/blocks/table/style.css
wp-includes/blocks/table/style.min.css
wp-includes/blocks/table/theme-rtl.css
wp-includes/blocks/table/theme-rtl.min.css
wp-includes/blocks/table/theme.css
wp-includes/blocks/table/theme.min.css
wp-includes/blocks/tag-cloud/block.json
wp-includes/blocks/template-part.php
wp-includes/blocks/template-part/block.json
wp-includes/blocks/term-description/block.json
wp-includes/blocks/text-columns/block.json
wp-includes/blocks/verse/block.json
wp-includes/blocks/video/block.json
wp-includes/blocks/video/theme-rtl.css
wp-includes/blocks/video/theme-rtl.min.css
wp-includes/blocks/video/theme.css
wp-includes/blocks/video/theme.min.css
wp-includes/blocks/widget-group/block.json
wp-includes/bookmark.php
wp-includes/canonical.php
wp-includes/class-simplepie.php
wp-includes/class-wp-admin-bar.php
wp-includes/class-wp-block-list.php
wp-includes/class-wp-block-patterns-registry.php
wp-includes/class-wp-block-type.php
wp-includes/class-wp-block.php
wp-includes/class-wp-comment-query.php
wp-includes/class-wp-customize-control.php
wp-includes/class-wp-customize-manager.php
wp-includes/class-wp-customize-nav-menus.php
wp-includes/class-wp-customize-widgets.php
wp-includes/class-wp-date-query.php
wp-includes/class-wp-duotone.php
wp-includes/class-wp-editor.php
wp-includes/class-wp-fatal-error-handler.php
wp-includes/class-wp-http.php
wp-includes/class-wp-image-editor-gd.php
wp-includes/class-wp-image-editor-imagick.php
wp-includes/class-wp-image-editor.php
wp-includes/class-wp-locale-switcher.php
wp-includes/class-wp-matchesmapregex.php
wp-includes/class-wp-network-query.php
wp-includes/class-wp-paused-extensions-storage.php
wp-includes/class-wp-query.php
wp-includes/class-wp-recovery-mode-key-service.php
wp-includes/class-wp-scripts.php
wp-includes/class-wp-site-query.php
wp-includes/class-wp-tax-query.php
wp-includes/class-wp-term-query.php
wp-includes/class-wp-text-diff-renderer-inline.php
wp-includes/class-wp-textdomain-registry.php
wp-includes/class-wp-theme-json-resolver.php
wp-includes/class-wp-theme-json.php
wp-includes/class-wp-theme.php
wp-includes/class-wp-user-query.php
wp-includes/class-wp-user.php
wp-includes/class-wp-walker.php
wp-includes/class-wp-xmlrpc-server.php
wp-includes/class-wpdb.php
wp-includes/comment-template.php
wp-includes/comment.php
wp-includes/compat.php
wp-includes/cron.php
wp-includes/css/buttons-rtl.css
wp-includes/css/buttons-rtl.min.css
wp-includes/css/buttons.css
wp-includes/css/buttons.min.css
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
wp-includes/css/jquery-ui-dialog-rtl.css
wp-includes/css/jquery-ui-dialog-rtl.min.css
wp-includes/css/jquery-ui-dialog.css
wp-includes/css/jquery-ui-dialog.min.css
wp-includes/css/media-views-rtl.css
wp-includes/css/media-views-rtl.min.css
wp-includes/css/media-views.css
wp-includes/css/media-views.min.css
wp-includes/css/wp-auth-check-rtl.css
wp-includes/css/wp-auth-check-rtl.min.css
wp-includes/css/wp-auth-check.css
wp-includes/css/wp-auth-check.min.css
wp-includes/css/wp-embed-template.css
wp-includes/css/wp-embed-template.min.css
wp-includes/customize/class-wp-customize-media-control.php
wp-includes/customize/class-wp-customize-nav-menu-item-control.php
wp-includes/customize/class-wp-customize-nav-menu-location-control.php
wp-includes/customize/class-wp-customize-site-icon-control.php
wp-includes/default-filters.php
wp-includes/deprecated.php
wp-includes/embed.php
wp-includes/feed-atom-comments.php
wp-includes/feed-rss2-comments.php
wp-includes/fonts.php
wp-includes/fonts/class-wp-font-face-resolver.php
wp-includes/formatting.php
wp-includes/functions.php
wp-includes/general-template.php
wp-includes/global-styles-and-settings.php
wp-includes/html-api/class-wp-html-active-formatting-elements.php
wp-includes/html-api/class-wp-html-attribute-token.php
wp-includes/html-api/class-wp-html-open-elements.php
wp-includes/html-api/class-wp-html-processor.php
wp-includes/html-api/class-wp-html-span.php
wp-includes/html-api/class-wp-html-tag-processor.php
wp-includes/html-api/class-wp-html-text-replacement.php
wp-includes/images/.DS_Store
wp-includes/images/smilies/icon_cry.gif
wp-includes/images/smilies/icon_lol.gif
wp-includes/images/smilies/icon_redface.gif
wp-includes/images/smilies/icon_rolleyes.gif
wp-includes/images/wpspin-2x.gif
wp-includes/images/wpspin.gif
wp-includes/images/xit.gif
wp-includes/js/.DS_Store
wp-includes/js/admin-bar.js
wp-includes/js/admin-bar.min.js
wp-includes/js/dist/a11y.js
wp-includes/js/dist/a11y.min.js
wp-includes/js/dist/annotations.js
wp-includes/js/dist/annotations.min.js
wp-includes/js/dist/api-fetch.js
wp-includes/js/dist/api-fetch.min.js
wp-includes/js/dist/autop.js
wp-includes/js/dist/autop.min.js
wp-includes/js/dist/blob.js
wp-includes/js/dist/blob.min.js
wp-includes/js/dist/block-directory.js
wp-includes/js/dist/block-directory.min.js
wp-includes/js/dist/block-editor.js
wp-includes/js/dist/block-editor.min.js
wp-includes/js/dist/block-library.js
wp-includes/js/dist/block-library.min.js
wp-includes/js/dist/block-serialization-default-parser.js
wp-includes/js/dist/block-serialization-default-parser.min.js
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
wp-includes/js/dist/data-controls.min.js
wp-includes/js/dist/data.js
wp-includes/js/dist/data.min.js
wp-includes/js/dist/date.js
wp-includes/js/dist/date.min.js
wp-includes/js/dist/deprecated.js
wp-includes/js/dist/deprecated.min.js
wp-includes/js/dist/development/react-refresh-entry.js
wp-includes/js/dist/development/react-refresh-entry.min.js
wp-includes/js/dist/development/react-refresh-runtime.js
wp-includes/js/dist/development/react-refresh-runtime.min.js
wp-includes/js/dist/dom-ready.js
wp-includes/js/dist/dom-ready.min.js
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
wp-includes/js/dist/escape-html.min.js
wp-includes/js/dist/format-library.js
wp-includes/js/dist/format-library.min.js
wp-includes/js/dist/hooks.js
wp-includes/js/dist/hooks.min.js
wp-includes/js/dist/html-entities.js
wp-includes/js/dist/html-entities.min.js
wp-includes/js/dist/i18n.js
wp-includes/js/dist/i18n.min.js
wp-includes/js/dist/interactivity.js
wp-includes/js/dist/interactivity.min.js
wp-includes/js/dist/is-shallow-equal.js
wp-includes/js/dist/is-shallow-equal.min.js
wp-includes/js/dist/keyboard-shortcuts.js
wp-includes/js/dist/keyboard-shortcuts.min.js
wp-includes/js/dist/keycodes.js
wp-includes/js/dist/keycodes.min.js
wp-includes/js/dist/list-reusable-blocks.js
wp-includes/js/dist/list-reusable-blocks.min.js
wp-includes/js/dist/media-utils.js
wp-includes/js/dist/media-utils.min.js
wp-includes/js/dist/notices.js
wp-includes/js/dist/notices.min.js
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
wp-includes/js/dist/priority-queue.js
wp-includes/js/dist/priority-queue.min.js
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
wp-includes/js/dist/shortcode.js
wp-includes/js/dist/shortcode.min.js
wp-includes/js/dist/style-engine.js
wp-includes/js/dist/style-engine.min.js
wp-includes/js/dist/token-list.js
wp-includes/js/dist/token-list.min.js
wp-includes/js/dist/undo-manager.js
wp-includes/js/dist/undo-manager.min.js
wp-includes/js/dist/url.js
wp-includes/js/dist/url.min.js
wp-includes/js/dist/vendor/lodash.min.js
wp-includes/js/dist/vendor/wp-polyfill.js
wp-includes/js/dist/vendor/wp-polyfill.min.js
wp-includes/js/dist/viewport.js
wp-includes/js/dist/viewport.min.js
wp-includes/js/dist/warning.js
wp-includes/js/dist/warning.min.js
wp-includes/js/dist/widgets.js
wp-includes/js/dist/widgets.min.js
wp-includes/js/dist/wordcount.js
wp-includes/js/dist/wordcount.min.js
wp-includes/js/media-audiovideo.js
wp-includes/js/media-audiovideo.min.js
wp-includes/js/media-grid.js
wp-includes/js/media-grid.min.js
wp-includes/js/media-models.js
wp-includes/js/media-models.min.js
wp-includes/js/media-views.js
wp-includes/js/media-views.min.js
wp-includes/js/mediaelement/wp-playlist.js
wp-includes/js/mediaelement/wp-playlist.min.js
wp-includes/js/plupload/handlers.js
wp-includes/js/plupload/handlers.min.js
wp-includes/js/plupload/wp-plupload.js
wp-includes/js/plupload/wp-plupload.min.js
wp-includes/js/thickbox/thickbox.js
wp-includes/js/tinymce/plugins/wplink/plugin.js
wp-includes/js/tinymce/plugins/wplink/plugin.min.js
wp-includes/js/tinymce/utils/form_utils.js
wp-includes/js/tinymce/wp-tinymce.js
wp-includes/js/twemoji.js
wp-includes/js/twemoji.min.js
wp-includes/js/wp-emoji-loader.js
wp-includes/js/wp-emoji-loader.min.js
wp-includes/js/wp-emoji-release.min.js
wp-includes/kses.php
wp-includes/l10n.php
wp-includes/link-template.php
wp-includes/load.php
wp-includes/media.php
wp-includes/ms-blogs.php
wp-includes/ms-functions.php
wp-includes/nav-menu-template.php
wp-includes/option.php
wp-includes/php-compat/readonly.php
wp-includes/pluggable.php
wp-includes/pomo/entry.php
wp-includes/pomo/po.php
wp-includes/pomo/translations.php
wp-includes/post.php
wp-includes/rest-api.php
wp-includes/rest-api/.DS_Store
wp-includes/rest-api/class-wp-rest-server.php
wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-block-types-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-comments-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-global-styles-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-posts-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-revisions-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-search-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-templates-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-terms-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-users-controller.php
wp-includes/rest-api/fields/class-wp-rest-meta-fields.php
wp-includes/rest-api/search/class-wp-rest-post-format-search-handler.php
wp-includes/rest-api/search/class-wp-rest-post-search-handler.php
wp-includes/rest-api/search/class-wp-rest-term-search-handler.php
wp-includes/rss.php
wp-includes/script-loader.php
wp-includes/shortcodes.php
wp-includes/sitemaps/providers/class-wp-sitemaps-posts.php
wp-includes/sodium_compat/.DS_Store
wp-includes/style-engine/class-wp-style-engine.php
wp-includes/taxonomy.php
wp-includes/template.php
wp-includes/theme-compat/sidebar.php
wp-includes/theme-previews.php
wp-includes/theme.json
wp-includes/theme.php
wp-includes/user.php
wp-includes/vars.php
wp-includes/version.php
wp-includes/widgets.php
wp-login.php
wp-settings.php
xmlrpc.php

Deleted Files:

wp-includes/blocks/query/style-rtl.css
wp-includes/blocks/query/style-rtl.min.css
wp-includes/blocks/query/style.css
wp-includes/blocks/query/style.min.css
wp-admin/images/about-header-about.svg
wp-admin/images/about-header-background.svg
wp-admin/images/about-header-contribute.svg
wp-admin/images/about-header-credits.svg
wp-admin/images/about-header-freedoms.svg
wp-admin/images/about-header-privacy.svg
wp-includes/ID3/license.commercial.txt

Added Files:

wp-admin/js/site-icon.js
wp-admin/js/site-icon.min.js
wp-includes/block-bindings.php
wp-includes/block-bindings/
wp-includes/blocks/post-content/editor-rtl.css
wp-includes/blocks/post-content/editor-rtl.min.css
wp-includes/blocks/post-content/editor.css
wp-includes/blocks/post-content/editor.min.css
wp-includes/class-avif-info.php
wp-includes/class-wp-block-bindings-registry.php
wp-includes/class-wp-block-bindings-source.php
wp-includes/class-wp-plugin-dependencies.php
wp-includes/class-wp-script-modules.php
wp-includes/css/dist/preferences/
wp-includes/fonts/class-wp-font-collection.php
wp-includes/fonts/class-wp-font-library.php
wp-includes/fonts/class-wp-font-utils.php
wp-includes/images/media/archive.svg
wp-includes/images/media/audio.svg
wp-includes/images/media/code.svg
wp-includes/images/media/default.svg
wp-includes/images/media/document.svg
wp-includes/images/media/interactive.svg
wp-includes/images/media/spreadsheet.svg
wp-includes/images/media/text.svg
wp-includes/images/media/video.svg
wp-includes/interactivity-api/
wp-includes/js/dist/interactivity-router.asset.php
wp-includes/js/dist/interactivity-router.js
wp-includes/js/dist/interactivity-router.min.asset.php
wp-includes/js/dist/interactivity-router.min.js
wp-includes/js/dist/vendor/wp-polyfill-importmap.js
wp-includes/js/dist/vendor/wp-polyfill-importmap.min.js
wp-includes/l10n/
wp-includes/rest-api/endpoints/class-wp-rest-font-collections-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-font-faces-controller.php
wp-includes/rest-api/endpoints/class-wp-rest-font-families-controller.php
wp-includes/script-modules.php
```

First published

April 2, 2024

Last updated

April 3, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.