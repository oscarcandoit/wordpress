---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior
scraped_at: 2025-10-20T03:07:18.768Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS overscroll behavior

The **CSS overscroll behavior** module provides properties to control the behavior of a [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container) when its scroll position reaches the [scroll boundary](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_boundary). Controlling this aspect is particularly useful in scenarios where embedded scrollable areas should not trigger scrolling of the parent container.

When commenting on a blog, you might notice that if your comment exceeds the length of the provided [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/textarea), scrolling beyond the end of the text area causes the entire blog to scroll. This is because reaching the end of a scrollable area, known as the [scroll boundary](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_boundary), can lead to scrolling other content or the entire page. This continuous scrolling experience is called [scroll chaining](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_chaining).

In situations where the contents of an element are larger than its container and [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) allows or defaults to scrolling (like in `<textarea>`), continued scrolling past the element's scrollable area will initiate scrolling in the parent element or the underlying page.

Conversely, scrolling through a website's terms and conditions and reaching the end of the content to enable a checkbox, may not force the page to scroll or bounce (as on a phone). This example shows that you can control overscroll behavior and prevent scroll chaining.

This module defines the overscroll behavior, enabling you to specify the actions when a user scrolls beyond the boundaries of a scrollable element.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#reference)

### [CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#css_properties)

- [`overscroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior) shorthand
- [`overscroll-behavior-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block)
- [`overscroll-behavior-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-inline)
- [`overscroll-behavior-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x)
- [`overscroll-behavior-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y)

### [Glossary terms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#glossary_terms)

- [Scroll boundary](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_boundary)
- [Scroll chaining](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_chaining)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#guides)

[Learn: Overflowing content](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Overflow)

Learn what overflow is and how to manage it.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#related_concepts)

- [`scrollbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/scrollbar_role) ARIA role

- [Containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Containing_block) concept

- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module:
  - [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) shorthand property

    - [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
    - [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
    - [`overflow-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block)
    - [`overflow-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline)
  - [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin) property
  - [`scroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior) property
  - [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) property
- [Scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container) and [scrollport](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container#scrollport) glossary terms

- [CSS scroll snap](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap) module:
  - [`scroll-padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding) shorthand property
  - [`scroll-snap-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type) property
  - [`scroll-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin) shorthand property
  - [`scroll-snap-stop`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop) property
  - [`scroll-snap-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align) property
- [CSSOM view](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_view) module:
  - [`Element.getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect) method
  - [`Element.scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll) method
  - [`Element.scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy) method
  - [`Element.scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView) method
  - [`Element.scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo) method
  - [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event "scroll") Document event

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#specifications)

| Specification |
| --- |
| [CSS Overscroll Behavior Module Level 1](https://drafts.csswg.org/css-overscroll/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior\#see_also)

- [CSS scroll anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring) module
- [CSS scroll snap](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap) module
- [CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model) module
- [CSS logical properties and values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_overscroll_behavior/index.md?plain=1 "Folder: ⁨en-us/web/css/css_overscroll_behavior⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_overscroll_behavior&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_overscroll_behavior%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_overscroll_behavior%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_overscroll_behavior%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")