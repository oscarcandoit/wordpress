---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables
scraped_at: 2025-10-20T03:14:17.679Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables#search)

# CSS environment variables

The **CSS environment variables** module defines the concept of environment variables and the [`env()`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) function. Environment variables work similarly to [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) and the [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var) function, except that they are globally defined; they are global variables scoped to the entire document. They are user agent values, provided by the browser or operating system, you can access using the [`env()`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) function enabling you to adapt your styles to the user's device or context.

Environment variables provide values that can be used on the page based on information the user agent has access to, such as the size of the titlebar, dynamic keyboard, and safe area insets. Safe area insets define a rectangle that is guaranteed to be visible on non-rectangular displays, based on its distance from the edges of the viewport. You can include the user-agent sizes in your styles, enabling you to modify the layout of essential content based on the available space inside the safe area rectangle, next to a visible dynamic keyboard, or adjacent to a visible title bar.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#reference)

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#functions)

- [`env()`](https://developer.mozilla.org/en-US/docs/Web/CSS/env)

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#data_types)

- [`<environment-variable-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables#browser-defined_environment_variables)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#guides)

[Using environment variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables)

An overview of what environment variables are, browser-defined environment variables, and how to use the `env()` function.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#related_concepts)

- [CSS media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries) module
- [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
- [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var)
- [`VirtualKeyboard`](https://developer.mozilla.org/en-US/docs/Web/API/VirtualKeyboard) interface
- [`display_override`](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest/Reference/display_override) manifest field
[Window Controls Overlay API](https://developer.mozilla.org/en-US/docs/Web/API/Window_Controls_Overlay_API) and [`WindowControlsOverlay`](https://developer.mozilla.org/en-US/docs/Web/API/WindowControlsOverlay) interface

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#specifications)

| Specification |
| --- |
| [Unknown specification](https://drafts.csswg.org/css-env-1) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables\#see_also)

- [CSS value functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) guide
- [CSS properties and values API](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_properties_and_values_API) module
- [CSS custom properties for cascading variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_environment_variables/index.md?plain=1 "Folder: ⁨en-us/web/css/css_environment_variables⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_environment_variables&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_environment_variables%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_environment_variables%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_environment_variables%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")