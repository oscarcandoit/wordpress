---
url: https://developer.wordpress.org/themes/global-settings-and-styles/settings
scraped_at: 2025-10-20T03:19:44.768Z
---

[Skip to content](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Settings


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Global Settings and Styles (theme.json)](https://developer.wordpress.org/themes/global-settings-and-styles/)Settings

Search

# Settings

## In this article

Table of Contents

- [The settings property](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#the-settings-property)
- [Settings documentation](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#settings-documentation)

[↑ Back to top](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#wp--skip-link--target)

The `settings` property in `theme.json` lets you configure a wide range of settings for a WordPress install. It covers everything from color presets, to enabling typography design tools, to layout, and a little bit of everything in between.

This document contains links for learning about each of these settings, which have their own individual documentation pages.

## [The settings property](https://developer.wordpress.org/themes/global-settings-and-styles/settings/\#the-settings-property)

`settings` is a top-level property in `theme.json` and has multiple nested properties that you can define. And some of those nested properties have multiple levels of nesting of their own.

The following is an overarching look at these properties in the context of a `theme.json` file:

``
[Expand code](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#)

[Copy](https://developer.wordpress.org/themes/global-settings-and-styles/settings/#)

```json
{
	"version": 2,
	"settings": {
		"appearanceTools": false,
		"border": {},
		"color": {},
		"custom": {},
		"dimensions": {},
		"layout": {},
		"position": {},
		"shadow": {},
		"spacing": {},
		"typography": {},
		"useRootPaddingAwareAlignments": false,
		"blocks": {}
	}
}
```

## [Settings documentation](https://developer.wordpress.org/themes/global-settings-and-styles/settings/\#settings-documentation)

Use the following links to explore specific settings that you can configure in your `theme.json` file:

- **[`appearanceTools`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/appearance-tools/):** A catchall setting for enabling multiple other settings.
- **`[border](https://developer.wordpress.org/themes/global-settings-and-styles/settings/border/)`:** Used for controlling the border width, style, color, and radius.
- **[`color`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/color/):** Lets you register a color palette, gradients, duotone and configure color-related settings.
- [`custom`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/custom/): An object for adding custom settings, which are output as CSS custom properties.
- **[`dimensions`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/dimensions/):** Lets you configure the minimum height setting.
- **[`layout`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/layout/):** Used for setting layout properties like the content and wide widths.
- **[`lightbox`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/lightbox/):** Lets you configure the image lightbox feature.
- **[`position`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/position/):** Currently lets you define support for sticky positioning.
- **[`shadow`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/shadow/):** Lets you configure box-shadow support and define custom shadow presets.
- **[`spacing`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/spacing/):** Used for configuring spacing-related settings, such as margin and padding,
- **[`typography`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/typography/):** Used for configuring typography-related settings, defining custom font sizes, and registering font families.
- **[`useRootPaddingAwareAlignments`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/use-root-padding-aware-alignments/):** A boolean setting for how padding on the root element should work.
- **[`blocks`](https://developer.wordpress.org/themes/global-settings-and-styles/settings/blocks/):** An object for configuring per-block settings.

The Theme Handbook also maintains a [reference for available settings](https://developer.wordpress.org/themes/global-settings-and-styles/settings/settings-reference/) based on the `theme.json` schema.

First published

October 10, 2023

Last updated

December 14, 2023

[PreviousIntroduction to theme.jsonPrevious: Introduction to theme.json](https://developer.wordpress.org/themes/global-settings-and-styles/introduction-to-theme-json/)

[NextAppearance ToolsNext: Appearance Tools](https://developer.wordpress.org/themes/global-settings-and-styles/settings/appearance-tools/)

Notifications