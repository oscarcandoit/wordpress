---
url: https://developer.wordpress.org/block-editor/how-to-guides/themes
scraped_at: 2025-10-20T03:49:49.358Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/themes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Themes


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)Themes

Search

# Themes

## In this article

Table of Contents

- [Types of themes](https://developer.wordpress.org/block-editor/how-to-guides/themes/#types-of-themes)
  - [Classic theme](https://developer.wordpress.org/block-editor/how-to-guides/themes/#classic-theme)
  - [Block theme](https://developer.wordpress.org/block-editor/how-to-guides/themes/#block-theme)
  - [Full site editing (FSE)](https://developer.wordpress.org/block-editor/how-to-guides/themes/#full-site-editing-fse)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/themes/#wp--skip-link--target)

The block editor provides a number of options for theme designers and developers, to interact with it, including theme-defined color settings, font size control, and much more.

## [Types of themes](https://developer.wordpress.org/block-editor/how-to-guides/themes/\#types-of-themes)

### [Classic theme](https://developer.wordpress.org/block-editor/how-to-guides/themes/\#classic-theme)

In terms of block editor terminology this is any theme that defines its templates in the traditional `.php` file format, and that doesn’t have an `index.html` format template in the `/block-templates` or `/templates` folders. A `Classic` theme has the ability to provide configuration and styling options to the block editor, and block content, via [Theme Supports](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-support/), or by including a [theme.json](https://developer.wordpress.org/block-editor/how-to-guides/themes/global-settings-and-styles/) file. A theme does not have to be a `Block` theme in order to take advantage of some of the flexibility provided by the use of a `theme.json` file.

### [Block theme](https://developer.wordpress.org/block-editor/how-to-guides/themes/\#block-theme)

This is any theme that has, at a minimum, an `index.html` format template in the `/block-templates` or `/templates` folders, and with templates provided in form of block content markup. While many `Block` themes will make use of a `theme.json` file to provide configuration and styling settings, a `theme.json` is not a requirement of `Block` themes. The advantage of `Block` themes is that the block editor can be used to edit all areas of the site: headers, footers, sidebars, etc.

### [Full site editing (FSE)](https://developer.wordpress.org/block-editor/how-to-guides/themes/\#full-site-editing-fse)

There isn’t an FSE specific theme type. In WordPress > 5.9 FSE is enabled for any `Block` theme, ie. any theme that has an `index.html` format template in the `/block-templates` or `/templates` folders.

**Contents**

- [Global Settings (theme.json)](https://developer.wordpress.org/block-editor/how-to-guides/themes/global-settings-and-styles/)
- [Theme Support](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-support/)

First published

April 26, 2021

Last updated

January 29, 2024

Edit article

[Improve it on GitHub: Themes](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/themes/README.md)

[PreviousPropagating updates for block typesPrevious: Propagating updates for block types](https://developer.wordpress.org/block-editor/how-to-guides/propagating-updates/)

[NextGlobal Settings & Styles (theme.json)Next: Global Settings & Styles (theme.json)](https://developer.wordpress.org/block-editor/how-to-guides/themes/global-settings-and-styles/)

Notifications