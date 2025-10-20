---
url: https://make.wordpress.org/themes/handbook/review/required/
scraped_at: 2025-10-20T03:00:52.533Z
---

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fthemes%2Fhandbook%2Freview%2Frequired%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[Skip to content](https://make.wordpress.org/themes/handbook/review/required/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Make WordPress Themes](https://make.wordpress.org/themes)

Required

[Home](https://make.wordpress.org/themes)[Handbook](https://make.wordpress.org/themes/handbook/)[Review Process](https://make.wordpress.org/themes/handbook/review/)Required

Search

# Required

## In this article

Table of Contents

- [1\. Licensing & copyright](https://make.wordpress.org/themes/handbook/review/required/#1-licensing-copyright)
- [2\. Privacy](https://make.wordpress.org/themes/handbook/review/required/#2-privacy)
- [3\. Accessibility](https://make.wordpress.org/themes/handbook/review/required/#3-accessibility)
- [4\. Code](https://make.wordpress.org/themes/handbook/review/required/#4-code)
- [5\. Functionality and Features](https://make.wordpress.org/themes/handbook/review/required/#5-functionality-and-features)
- [6\. Plugins](https://make.wordpress.org/themes/handbook/review/required/#6-plugins)
- [7\. Naming, spelling, and trademarks](https://make.wordpress.org/themes/handbook/review/required/#7-naming-spelling-and-trademarks)
- [8\. Language & internationalization](https://make.wordpress.org/themes/handbook/review/required/#8-language-internationalization)
- [9\. Files](https://make.wordpress.org/themes/handbook/review/required/#9-files)
- [10\. Classic themes](https://make.wordpress.org/themes/handbook/review/required/#10-classic-themes)
- [11\. Block themes](https://make.wordpress.org/themes/handbook/review/required/#11-block-themes)
- [12\. Theme settings pages and onboarding](https://make.wordpress.org/themes/handbook/review/required/#12-theme-settings-pages-and-onboarding)
- [13\. Selling, credits, links, and spam](https://make.wordpress.org/themes/handbook/review/required/#13-selling-credits-links-and-spam)
- [14\. Theme author and theme upload restrictions](https://make.wordpress.org/themes/handbook/review/required/#14-theme-author-and-theme-upload-restrictions)

[↑ Back to top](https://make.wordpress.org/themes/handbook/review/required/#wp--skip-link--target)

A theme must meet all of the following requirements to be included in the WordPress.org Theme Directory.

Themes that have **3 or more distinct issues may be closed** as not-approved. However, theme authors may resubmit the theme once they’ve corrected the issues.

* * *

### [1\. Licensing & copyright](https://make.wordpress.org/themes/handbook/review/required/\#1-licensing-copyright)

**Themes must be compatible with the GNU General Public License**

Although any GPL-compatible license is acceptable, using the same license as WordPress — “GPLv2 or later” — is strongly recommended.

All code, data, and images — anything in the theme zip file — must comply with the GPL or a GPL-Compatible license.

Included third-party libraries, code, images, or otherwise, must be compatible.

For a specific list of compatible licenses, please read the [GPL-Compatible license list on gnu.org](https://www.gnu.org/licenses/license-list.en.html#GPLCompatibleLicenses).

- Include copyright information for the theme itself.
- Include license, copyright information, and source for all resources included, such as fonts or images (For assets in the public domain, copyright information is excluded).
- Provide a list of all resources in one file.
- All code and design must be your own or legally yours. Cloning of designs is not acceptable.
- Copyright statements on the front end must only display the user’s copyright, not the theme author’s copyright.



[Read more about copyright and attribution.](https://make.wordpress.org/themes/2014/07/08/proper-copyrightlicense-attribution-for-themes/)

### [2\. Privacy](https://make.wordpress.org/themes/handbook/review/required/\#2-privacy)

Any tracking and collection of user data must be disabled by default and opt-in only.

Documentation on how any user data is collected and used needs to be in the theme readme.txt file, preferably with a clearly stated privacy policy.

### [3\. Accessibility](https://make.wordpress.org/themes/handbook/review/required/\#3-accessibility)

**Skip links**

Themes must include a mechanism that enables users to navigate directly to content or navigation on entering any given page.

These links may be positioned off-screen initially but must be available to screen reader users and must be visible on focus for sighted keyboard navigators.

A minimally conforming skip link must:

- Be the first focusable element perceived by a user via a screen reader or keyboard navigation
- Be visible when keyboard focus moves to the link
- Move focus to the main content area of the page when activated

**Notes:** This only applies if there is something to skip past, such as a menu or larger header section or secondary widget area before the main content.

In block themes, skip links are added automatically to the `<main>` tag.

**Keyboard navigation**

Theme authors must provide visual keyboard focus highlighting in navigation menus and for form fields, submit buttons, and text links.

- All controls and links must be reachable using the keyboard.
- All controls usable with the mouse must be usable with the keyboard, regardless of device and screen size. Including but not limited to responsive versions for small screens, mobile and other touch screen devices.

[Further reading about keyboard navigation](https://make.wordpress.org/themes/handbook/review/accessibility/required/#keyboard-navigation)

**Links within content and comments must be underlined**

When links appear within a larger body of block-level content, they must be clearly distinguishable from surrounding content (Post content, comment content, text widgets, custom options with large blocks of texts).

Links in navigation-like contexts (e.g., menus, lists of upcoming posts in widgets, grouped post meta data) do not need to be specifically distinguished from surrounding content.

The underline is the only accepted method of indicating links within the content. Bold, italicized, or color-differentiated text is ambiguous and will not pass.

If the theme has the tag ‘accessibility-ready’ then it needs to meet [these additional requirements.](https://make.wordpress.org/themes/handbook/review/accessibility/)

### [4\. Code](https://make.wordpress.org/themes/handbook/review/required/\#4-code)

There must not be any PHP or JavaScript errors, warnings, or notices.

The theme must be secure.

- Validate and sanitize untrusted data before entering it into the database.
- Escape all untrusted data before output (See: [Data Validation](https://codex.wordpress.org/Data_Validation)).

Do not use [deprecated functions or constants](https://codex.wordpress.org/Category:Deprecated_Functions).

**Prefix**

Provide a unique prefix for everything the theme defines in the public namespace, including options, functions, global variables, constants, post meta, wp\_enqueue\_script/style handle names, add\_image\_size names, wp\_script\_add\_data keys, slugs/ids for new categories created with register\_block\_pattern\_category etc.

A minimum of four letters is necessary for prefix length.

Exceptions:

- `wp_enqueue_script` & `wp_enqueue_style` handles should not be prefixed if they are 3rd-party assets, like a framework’s CSS files or any 3rd-party script.
- Menu locations and sidebar IDs.

### [5\. Functionality and Features](https://make.wordpress.org/themes/handbook/review/required/\#5-functionality-and-features)

Manipulating the preview on WordPress.org is not allowed and can result in suspension or your user account being terminated.

**Admin notices:**

- Use the [admin\_notices API](https://developer.wordpress.org/reference/hooks/admin_notices/) for all notifications generated by the theme.
- Notices must be dismissible.
- Everything wrapped in the admin notice must follow coreUI design for notices.

**Do not:**

- Place WordPress features behind a paywall
- Remove, hide, or otherwise block the admin bar from appearing
- Redirect on theme activation or modify the activation process
- Remove non-presentational hooks

**Do not include:**

- Custom post types
- Custom blocks
- Custom roles
- Custom user contact methods
- Custom mime types
- Shortcodes
- Functionality that is not related to design and presentation

**Examples of non-presentational hooks**

```
'wp_generator', // @link https://developer.wordpress.org/reference/functions/wp_generator/
'feed_links', // @link https://developer.wordpress.org/reference/functions/feed_links/
'feed_links_extra', // @link https://developer.wordpress.org/reference/functions/feed_links_extra/
'wp_resource_hints', // @link https://developer.wordpress.org/reference/functions/wp_resource_hints/
'adjacent_posts_rel_link_wp_head', // @link https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/
'wp_shortlink_wp_head', // @link https://developer.wordpress.org/reference/functions/wp_shortlink_wp_head/
'_admin_bar_bump_cb', // @link https://developer.wordpress.org/reference/functions/_admin_bar_bump_cb/
'rsd_link', // @link https://developer.wordpress.org/reference/functions/rsd_link/
'rest_output_link_wp_head', // @link https://developer.wordpress.org/reference/functions/rest_output_link_wp_head/
'wp_oembed_add_discovery_links', // @link https://developer.wordpress.org/reference/functions/wp_oembed_add_discovery_links/
'wp_oembed_add_host_js', // @link https://developer.wordpress.org/reference/functions/wp_oembed_add_host_js/
'rel_canonical', // @link https://developer.wordpress.org/reference/functions/rel_canonical/
```

### [6\. Plugins](https://make.wordpress.org/themes/handbook/review/required/\#6-plugins)

Themes may only recommend plugins that are hosted on WordPress.org.

Plugins may only be installed by user action, not automatically.

**Do not:**

- Include zip files or plugins in the theme folder, or download plugins automatically.
- Include plugin functionality.

If you are not sure if a feature is plugin functionality, contact the team and ask first. [themes@wordpress.org](mailto:themes@wordpress.org).

**Examples of plugin territory**

```
Analytics or tracking support
SEO options
Contact forms
Non-design related meta boxes
Resource caching
Social media ‘like’, ‘follow’ and ‘share buttons’
Session tampering
```

### [7\. Naming, spelling, and trademarks](https://make.wordpress.org/themes/handbook/review/required/\#7-naming-spelling-and-trademarks)

The themes team can decline themes based on the name and request that the name is changed if they decide that the name is inappropriate or too similar to an existing theme or brand.

- Theme names must not use: WordPress, Theme, Twenty\*
- Spell “WordPress” correctly in all public-facing text: all one word, with both an uppercase W and P
- No violation of trademarks.

### [8\. Language & internationalization](https://make.wordpress.org/themes/handbook/review/required/\#8-language-internationalization)

All text strings must be translatable using gettext, with the temporary exception of text in HTML template files.

Use the theme slug as the text-domain and add it to style.css.

The theme slug is the name of the theme in lower case, with spaces replaced by a hyphen (-).

It is also the folder name for the theme.

If the theme uses a framework, then no more than two unique text domains may be used (like tgmpa, redux-framework, kirki, or some other allowed framework)

[Read more about internationalization.](https://developer.wordpress.org/apis/handbook/internationalization/)

### [9\. Files](https://make.wordpress.org/themes/handbook/review/required/\#9-files)

Prepare your files:

- Themes must be complete at the time of submission.
- Remove code not intended for the free version of the theme.
- Remove directories such as .git, .svn, .hg, and .bzr.
- Make sure that only one type of line ending is used. If both DOS and UNIX line endings are used, this can cause problems with SVN, and your theme or theme update will not be uploaded to the directory.
- If your theme is based on a starter theme like Underscores (\_s), make sure that all files are updated correctly.

**Files that are not allowed**

```
thumbs.db          =>  Windows thumbnail store
desktop.ini        =>  windows system file
project.properties =>  NetBeans Project File
project.xml        =>  NetBeans Project File
.kpf               =>  Komodo Project File
php.ini            =>  PHP server settings file
dwsync.xml         =>  Dreamweaver project file
error_log          =>  PHP error log
web.config         =>  Server settings file
.sql               =>  SQL dump file
__MACOSX           =>  OSX system file
.lubith            =>  Lubith theme generator file
.wie               =>  Widget import file
.dat               =>  Customizer import file
.xml               =>  XML file
.sh                =>  Shell script file
favicon.ico        =>  Favicon

Hidden Files or Folders
Zip files

Allowed xml files:
wpml-config.xml,loco.xml,phpcs.xml,
```

**No remote resources are allowed without user consent**:

Include all scripts, images, videos and other resources in the theme zip file. The only exception to this requirement is Google Fonts.

**Do not:**

- Use CDN or similar services
- Fetch any files or data from a remote resource, including your websites, without the user’s explicit consent.

This is because of GDPR and privacy requirements.

**Main stylesheet**

The headers in style.css need to follow the guidelines and requirements for [the main stylesheet in the Theme Developer Handbook](https://developer.wordpress.org/themes/basics/main-stylesheet-style-css/#basic-structure).

**Required headers in style.css**

```
Theme Name: Name of the theme.
Author: The name of the individual or organization who developed the theme. Using the Theme Author’s wordpress.org username is recommended.
Description: A short description of the theme.
Version: The version, written in X.X or X.X.X format.
Requires at least: The oldest main WordPress version supported, written in X.X format.
Tested up to: The last main WordPress version the theme has been tested up to, i.e. 5.4. Only the number.
Requires PHP: The oldest PHP version supported, in X.X format, only the number
License: The license of the theme.
License URI: The URL of the theme license.
Text Domain: The string used for textdomain for translation.
```

Theme URI is optional. If used, it must be about the theme we’re hosting on WordPress.org.

Using WordPress.org in the Theme URI is reserved for the default themes (Twenty X).

Author URI is optional. If used, it must be a page or website about the author, author theme shop, or author project/development website.

For a list of available tags, see [Theme Tag List](https://make.wordpress.org/themes/handbook/review/required/theme-tags/).

**Readme.txt file**

A valid readme.txt file must be included.

**readme.txt example**

```
=== Theme Name ===
Contributors: (Should only contain one WordPress.org username.)
Requires at least: 5.0
Tested up to: 5.2
Requires PHP: 5.6
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Short description. No more than 150 chars.

== Description ==
Theme desc.

== Frequently Asked Questions ==

= A question that someone might have =

An answer to that question.

== Changelog ==

= 1.0 =
* Added new option

= 0.5 =
* Security bug addressed
* Changed thumbnail size

== Upgrade Notice ==

= 1.0 =
* Upgrade notices describe the reason a user should upgrade.  No more than 300 characters.

= 0.5 =

* This version fixes a security related bug.  Upgrade immediately.

== Resources ==
* magnify.jpg Jane Doe, CC0, example.com
* supermenu.js © 2013-2015 James Today, MIT, example.com


```

**Stylesheets and scripts**

When minified scripts or files are used, the original files must also be included in the theme folder.

**Use of third party libraries**

WordPress includes a number of libraries such as jQuery. For security and stability reasons, themes may not include those libraries in their own code. Instead, themes must use the versions of those libraries packaged with WordPress.

For a list of all JavaScript libraries included in WordPress, see [Default Scripts Included and Registered by WordPress.](https://developer.wordpress.org/reference/functions/wp_enqueue_script/#default-scripts-and-js-libraries-included-and-registered-by-wordpress)

**Images**

Images that promote hate or violence or images that show children with recognizable facial or body features are not permitted.

**Screenshot**

- The screenshot must not look like an advertisement. The reviewer can subjectively ask you to change screenshots if they find that it is not appropriate.
- The screenshot must not be bigger than 1200 x 900px
- The ratio of width to height needs to be 4:3

### [10\. Classic themes](https://make.wordpress.org/themes/handbook/review/required/\#10-classic-themes)

Have a valid DOCTYPE declaration and include [language\_attributes()](https://developer.wordpress.org/reference/functions/language_attributes/).

Call custom template files using [get\_template\_part()](https://developer.wordpress.org/reference/functions/get_template_part/) or [locate\_template()](https://developer.wordpress.org/reference/functions/locate_template/).

Display the correct content according to the front page setting ( [See explanation](https://make.wordpress.org/themes/2014/06/28/correct-handling-of-static-front-page-and-custom-blog-posts-index-template/)).

Use edit\_theme\_options capability for determining user permission to edit options, rather than relying on a role (e.g., administrator) or a different capability (e.g., edit\_themes, manage\_options).

Include:

- [wp\_head()](https://developer.wordpress.org/reference/functions/wp_head/) – (immediately before `</head>` )
- [body\_class()](https://developer.wordpress.org/reference/functions/body_class/) – (inside the body tag)
- [wp\_footer()](https://developer.wordpress.org/reference/functions/wp_footer/) – (immediately before `</body>` )
- [wp\_body\_open()](https://developer.wordpress.org/reference/functions/wp_body_open/) – (immediately after ` <body>`)
- [post\_class()](https://developer.wordpress.org/reference/functions/post_class/)
- [wp\_link\_pages()](https://developer.wordpress.org/reference/functions/wp_link_pages/)
- [add\_theme\_support( ‘title-tag’ )](https://developer.wordpress.org/reference/functions/add_theme_support/#title-tag)
- [add\_theme\_support( ‘automatic-feed-links’ )](https://developer.wordpress.org/reference/functions/add_theme_support/)

**Templates**

_If used in the theme,_ standard template files are required to be called by their respective function.

- header.php (via [get\_header()](https://developer.wordpress.org/reference/functions/get_header/) )
- footer.php (via [get\_footer()](https://developer.wordpress.org/reference/functions/get_footer/) )
- sidebar.php (via [get\_sidebar()](https://developer.wordpress.org/reference/functions/get_sidebar/) )
- searchform.php (via [get\_search\_form()](https://developer.wordpress.org/reference/functions/get_search_form/) )

### [11\. Block themes](https://make.wordpress.org/themes/handbook/review/required/\#11-block-themes)

Include required files: style.css, readme.txt, theme.json, and index.html.

Index.html needs to be placed inside a folder called `templates`.

Block templates must be complete, and blocks may not have missing or incorrect closing tags.

### [12\. Theme settings pages and onboarding](https://make.wordpress.org/themes/handbook/review/required/\#12-theme-settings-pages-and-onboarding)

**Admin notice / theme activation**

Themes must use the `admin_notices` hook to provide any custom messages to the user. These admin notices must either be a one-time message or permanently dismissible. This notice can be used to link to a settings page or start an onboarding process, for example. Popups are not allowed upon theme activation.

**Admin page**

Themes may optionally add custom sub-pages under Appearance in the WordPress admin.

They should only contain core WordPress UI elements and generally match the WordPress admin design.

If necessary, themes can include custom styles or scripts for their admin pages, but they cannot leak/spill out to other WordPress admin pages. Enqueue styles/scripts on the `admin_enqueue_scripts` hook and use `$hook_suffix` parameter to determine the page.

For React-based admin pages, make use of [Core components](https://developer.wordpress.org/block-editor/reference-guides/components/) for features if they are available.

Additionally, themes must reference the correct [user role capabilities](https://wordpress.org/documentation/article/roles-and-capabilities/) when performing any action inside of the WordPress admin. They must also use an appropriate capability selector or function, such as _`canUser`_ or `current_user_can()`.

Inserting posts/pages via `wp_insert|update_post()` can be used if the action is done with user consent.

**Options**

Themes must use the [Settings and Options APIs](https://developer.wordpress.org/plugins/settings/) when storing custom settings in the database.

Themes must also only add a single database option, which should be an array when storing multiple settings. This option must also be prefixed with the theme slug.

Themes may optionally custom core WordPress options that only affect the front-end and how the website displays (e.g., site logo, front page settings), as long as the user is notified that their saved options will be modified. User consent is required.

All data passed to `add_option()`, `update_option()`, or other functions for saving to the database must be validated and/or sanitized with the correct function or method for the data type.

**Not allowed**

The following features are not allowed as part of an admin menu or onboarding process:

- Demo imports
- External calls
- Tracking/Affiliate links

### [13\. Selling, credits, links, and spam](https://make.wordpress.org/themes/handbook/review/required/\#13-selling-credits-links-and-spam)

Themes can include one single front-facing credit link, which is restricted to the Theme URI or Author URI defined in style.css.

Themes can also have an additional front-facing credit link pointing to WordPress.org.

- Themes must not display obtrusive upselling
- Themes must not display upselling on the front

Themes must disclose all affiliates.

The theme and its public-facing pages, including theme description, readme files, bundled starter content, and translation files, may not be used to spam. Spammy behavior includes (but is not limited to) tags to competitors’ products, blackhat SEO, and keyword stuffing.

### [14\. Theme author and theme upload restrictions](https://make.wordpress.org/themes/handbook/review/required/\#14-theme-author-and-theme-upload-restrictions)

Only submit one new theme at a time. You can submit unlimited updates for your existing themes that are in the theme directory.

Theme names cannot be “reserved” for future use.

Intentionally attempting to exploit loopholes in the guidelines may lead to suspension.

**Licensing of themes distributed outside the theme directory**

If you distribute themes, you may only distribute themes that are 100% compatible with GPL.

Otherwise, you can not add themes to the WordPress.org Theme Directory ( [See explanation](https://make.wordpress.org/themes/2015/08/15/themes-should-be-100-gpl/)).

Example: If you have a Themeforest account and you’re selling themes on it, all those themes need to state on their sales page that they are 100% GPL compatible [(Info](https://help.market.envato.com/hc/en-us/articles/202501194-Theme-Plugin-Licensing-Options)).

Your site needs to state that the products you’re selling/distributing (free and paid) are GPL compatible. It needs to be in an easy-to-find place for visitors.

**Multiple Theme Author Accounts**

You can have multiple accounts with the following restrictions:

You can’t have more than one (1) open ticket in any of the Trac reports/queues or under review. That means you can’t have one (1) theme ticket from an account and another one from a secondary account simultaneously open in any of the queues.

Failing to respect the above requirement will result in the closing of all tickets and not having the possibility to upload those themes again. Also, a one (1) month no upload possibility for each ticket closed. Depending on the severity of the case, you might also end up with a permanent ban on all your accounts.

To avoid penalties, the team requests that you disclose all your accounts by emailing us at themes\[at\]wordpress.org.

* * *

Now that you have read and made sure that your theme follows all the requirements, you are welcome to [upload your theme](https://wordpress.org/themes/upload/).

First published

November 4, 2014

Last updated

December 13, 2024

[PreviousReview ProcessPrevious: Review Process](https://make.wordpress.org/themes/handbook/review/)

[NextTheme Check PluginNext: Theme Check Plugin](https://make.wordpress.org/themes/handbook/review/required/theme-check-plugin/)

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