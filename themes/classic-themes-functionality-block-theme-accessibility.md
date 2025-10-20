---
url: https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility
scraped_at: 2025-10-20T03:12:34.242Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block theme accessibility


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)Block theme accessibility

Search

# Block theme accessibility

## In this article

Table of Contents

- [Landmark](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#landmark)
- [Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#skip-to-content)
- [Accessible navigation menu](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#accessible-navigation-menu)
- [Additional resources](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#additional-resources)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#wp--skip-link--target)

Block themes support accessibility and simplify the process for adding accessibility.

## [Landmark](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/\#landmark)

Group, Template part, and Query blocks can become a landmark. There are two ways to create landmark.

**Using block markup**

`”tagName":"header”` creates header landmark.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#)

```
<!-- wp:group {"tagName":"header","layout":{"type":"constrained"}} -->
<header class="wp-block-group"><!-- wp:site-title /--></header>
<!-- /wp:group -->
```

**Using site editor**

HTML element under Advanced section in the Block panel provides the following landmark options.

HTML element under Advanced section in the Block panel provides the following landmark options.

`<header>` `<main>` `<section>` `<article>` `<aside>` `<footer>`.

## [Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/\#skip-to-content)

By selecting `<main>` landmark on Group, Template part, or Query block generates the Skip to Content link. Learn more about the [skip to content link here](https://make.wordpress.org/themes/handbook/review/required/#3-accessibility).

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/#)

```
<!-- wp:group {"tagName":"main","layout":{"type":"constrained"}} -->
<main class="wp-block-group"><!-- wp:heading -->
<h2 id="hello-world">Hello World</h2>
<p>Welcome to WordPress. This is your first post. </p>
<!-- /wp:heading -->
```

## [Accessible navigation menu](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/\#accessible-navigation-menu)

Navigation block enables the following accessibility without additional code.

- Support responsive view
- Support keyboard navigation
- Insert `<nav>` landmark role
- Insert ARIA attributes `aria-label` `aria-hidden`

## [Additional resources](https://developer.wordpress.org/themes/classic-themes/functionality/block-theme-accessibility/\#additional-resources)

- [Accessibility](https://make.wordpress.org/themes/handbook/review/accessibility/)

Changelog:

- **Updated** 2023-03-08 Updated code examples to reflect WordPress 6.1 block markup.
- **Created** 2022-01-25

First published

January 25, 2022

Last updated

August 29, 2023

[PreviousAdministration MenusPrevious: Administration Menus](https://developer.wordpress.org/themes/classic-themes/functionality/administration-menus/)

[NextCore-Supported FeaturesNext: Core-Supported Features](https://developer.wordpress.org/themes/classic-themes/functionality/core-supported/)

Notifications