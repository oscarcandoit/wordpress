---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles
scraped_at: 2025-10-20T03:01:16.083Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS counter styles

The **CSS counter styles** module lets you define your own counter styles to manage the appearance of [markers](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker) in lists and counters in [generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content). It also enables you to extend native browser list styles with your own customizations.

While we think of counters as numbers, they are actually strings with components that can be incremented. The counter styles module defines the `@counter-style` rule with ten descriptors, which enable developers to precisely define how counters are converted into strings. This module enables defining which characters to use for the counter bullets, the prefix to put before the counter and postfix that comes after, along with how to handle negative values. The descriptors can also set a range to limit the values a counter style can handle, while also providing fallback styles for when the counter value falls outside the defined range or otherwise can't render the counter value. The module also enables defining how the counter is read out loud by speech synthesizers.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#properties)

No properties are defined in this module

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#functions)

- [`symbols()`](https://developer.mozilla.org/en-US/docs/Web/CSS/symbols)

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#data_types)

- [`<counter-style-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style#counter-style-name)
- [`<symbol>`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols#values)
- [`<symbols-type>`](https://developer.mozilla.org/en-US/docs/Web/CSS/symbols#syntax)

### [At-rules and descriptors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#at-rules_and_descriptors)

- [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style)
  - [`system`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/system)
  - [`symbols`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols)
  - [`additive-symbols`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/additive-symbols)
  - [`negative`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative)
  - [`prefix`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/prefix)
  - [`suffix`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/suffix)
  - [`range`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range)
  - [`pad`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/pad)
  - [`speak-as`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as)
  - [`fallback`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback)

### [Interfaces](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#interfaces)

- [`CSSCounterStyleRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSCounterStyleRule) interface

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#guides)

[Using CSS counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters)

Describes how to use counters to number any HTML element or to perform complex counting.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#related_concepts)

[CSS lists and counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists) module:

- [`counter-increment`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment) property
- [`counter-reset`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset) property
- [`counter-set`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set) property
- [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property
- [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) shorthand property
- [`counter()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter) function
- [`counters()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counters) function

[CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module:

- [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-element
- [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) pseudo-element
- [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker) pseudo-element

[CSS generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content) module:

- [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#specifications)

| Specification |
| --- |
| [CSS Counter Styles Level 3](https://drafts.csswg.org/css-counter-styles/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles\#see_also)

- [CSS lists and counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists) module
- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module
- [CSS generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content) module
- [Ready-made counter styles](https://w3c.github.io/predefined-counter-styles/#builtins) via W3C (2023)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_counter_styles/index.md?plain=1 "Folder: ⁨en-us/web/css/css_counter_styles⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_counter_styles&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_counter_styles%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_counter_styles%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_counter_styles%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")