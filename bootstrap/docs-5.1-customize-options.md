---
url: https://getbootstrap.com/docs/5.1/customize/options
scraped_at: 2025-10-20T02:39:42.898Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/customize/options/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/customize/options/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/customize/options.md "View and edit this file on GitHub")

# Options

Quickly customize Bootstrap with built-in variables to easily toggle global CSS preferences for controlling style and behavior.

Customize Bootstrap with our built-in custom variables file and easily toggle global CSS preferences with new `$enable-*` Sass variables. Override a variable’s value and recompile with `npm run test` as needed.

You can find and customize these variables for key global options in Bootstrap’s `scss/_variables.scss` file.

| Variable | Values | Description |
| --- | --- | --- |
| `$spacer` | `1rem` (default), or any value > 0 | Specifies the default spacer value to programmatically generate our [spacer utilities](https://getbootstrap.com/docs/5.1/utilities/spacing/). |
| `$enable-rounded` | `true` (default) or `false` | Enables predefined `border-radius` styles on various components. |
| `$enable-shadows` | `true` or `false` (default) | Enables predefined decorative `box-shadow` styles on various components. Does not affect `box-shadow` s used for focus states. |
| `$enable-gradients` | `true` or `false` (default) | Enables predefined gradients via `background-image` styles on various components. |
| `$enable-transitions` | `true` (default) or `false` | Enables predefined `transition` s on various components. |
| `$enable-reduced-motion` | `true` (default) or `false` | Enables the [`prefers-reduced-motion` media query](https://getbootstrap.com/docs/5.1/getting-started/accessibility/#reduced-motion), which suppresses certain animations/transitions based on the users' browser/operating system preferences. |
| `$enable-grid-classes` | `true` (default) or `false` | Enables the generation of CSS classes for the grid system (e.g. `.row`, `.col-md-1`, etc.). |
| `$enable-caret` | `true` (default) or `false` | Enables pseudo element caret on `.dropdown-toggle`. |
| `$enable-button-pointers` | `true` (default) or `false` | Add “hand” cursor to non-disabled button elements. |
| `$enable-rfs` | `true` (default) or `false` | Globally enables [RFS](https://getbootstrap.com/docs/5.1/getting-started/rfs/). |
| `$enable-validation-icons` | `true` (default) or `false` | Enables `background-image` icons within textual inputs and some custom forms for validation states. |
| `$enable-negative-margins` | `true` or `false` (default) | Enables the generation of [negative margin utilities](https://getbootstrap.com/docs/5.1/utilities/spacing/#negative-margin). |
| `$enable-deprecation-messages` | `true` (default) or `false` | Set to `false` to hide warnings when using any of the deprecated mixins and functions that are planned to be removed in `v6`. |
| `$enable-important-utilities` | `true` (default) or `false` | Enables the `!important` suffix in utility classes. |
| `$enable-smooth-scroll` | `true` (default) or `false` | Applies `scroll-behavior: smooth` globally, except for users asking for reduced motion through [`prefers-reduced-motion` media query](https://getbootstrap.com/docs/5.1/getting-started/accessibility/#reduced-motion) |