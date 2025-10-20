---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists
scraped_at: 2025-10-20T03:04:37.485Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS lists and counters

The **CSS lists and counters** module enables styling and positioning of list item bullets and manipulating their values with a combination of strings, counters, and other features.

A list item's marker, whether a bullet symbol or ordinal counter, is its defining feature. List items are not limited to [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/li) elements nested within [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ol) or [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ul) elements. Rather, list items are any element with `display: list-item` set.

This module defines CSS features to set and reset a list's counters, set which [counter-styles](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles) or symbols to use as its markers, and position those markers. It also provides developers with the ability to create customized markers.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#properties)

- [`counter-increment`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment)
- [`counter-reset`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset)
- [`counter-set`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set)
- [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)
- [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
- [`list-style-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position)
- [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) shorthand

There is also a `marker-side` property, which is yet to be fully defined or implemented.

### [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#pseudo-elements)

- [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#functions)

- [`counter()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter)
- [`counters()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counters)

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#data_types)

- [`<counter>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content#counter)
- [`<counter-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter#counter-name)
- [`<counter-style>`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter#counter-style)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#guides)

[Consistent list indentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists/Consistent_list_indentation)

Explains how to achieve consistent list indentation across different browsers.

[Using CSS Counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters)

Explains how to use the CSS counter properties to control list counters.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#related_concepts)

- [CSS counter styles](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles)
  - [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style) at-rule
  - [`<counter-style-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style#counter-style-name) data type
  - [`<symbol>`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols#values) data type
  - [`symbols()`](https://developer.mozilla.org/en-US/docs/Web/CSS/symbols) function
- [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ol) `start`, `reversed`, and `type` attributes

- [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ul) `type` attribute

- [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/li) `type` and `value` attributes


## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#specifications)

| Specification |
| --- |
| [CSS Lists and Counters Module Level 3](https://drafts.csswg.org/css-lists/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists\#see_also)

- [CSS counter styles](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles) module
- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module
- [CSS generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_lists/index.md?plain=1 "Folder: ⁨en-us/web/css/css_lists⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_lists&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_lists%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_lists%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_lists%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")