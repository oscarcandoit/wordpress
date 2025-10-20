---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content
scraped_at: 2025-10-20T03:06:20.031Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS generated content

The **CSS generated content** module defines how an element's content can be replaced and content can be added to a document with CSS.

Generated content can be used for content replacement, in which case the content of a DOM node is replaced with a CSS `<image>`. The CSS generated content also enables generating language-specific quotes, creating custom list item numbers and bullets, and visually adding content by generating content on select pseudo-elements as anonymous replaced elements.

## [Generated content in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#generated_content_in_action)

htmlCopyPlay

```
<div></div>

```

cssCopyPlay

```
body,
div {
  background-repeat: no-repeat;
}
body {
  background-image: linear-gradient(#3a67ab, #e8f6ff 100%);
}
div {
  position: relative;
  width: 400px;
  height: 400px;
  background-image:
    linear-gradient(
      115deg,
      transparent 48%,
      brown,
      #996600,
      brown,
      transparent 52%
    ),
    linear-gradient(
      60deg,
      transparent 48%,
      brown,
      #996600,
      brown,
      transparent 52%
    ),
    radial-gradient(
      circle 10px at 50% 50%,
      #333333 30%,
      #999999 50%,
      transparent 50%
    ),
    radial-gradient(
      circle 10px at 50% 50%,
      #333333 30%,
      #999999 50%,
      transparent 50%
    ),
    radial-gradient(circle at 50% 50%, white 30%, #eeeeee 50%, transparent 50%),
    radial-gradient(circle at 50% 50%, white 30%, #eeeeee 50%, transparent 50%),
    radial-gradient(circle at 50% 50%, white 30%, #eeeeee 50%, transparent 50%);
  background-size:
    100px 100px,
    100px 100px,
    15px 15px,
    15px 15px,
    200px 200px,
    300px 300px,
    400px 400px;
  background-position:
    95% 120px,
    5% 120px,
    46% 80px,
    54% 80px,
    50% 0,
    50% 90px,
    50% 220px;
}
div::after {
  content: "";
  border: transparent solid 4px;
  border-left: orange 30px solid;
  height: 1px;
  width: 1px;
  position: absolute;
  left: 50%;
  top: 100px;
}

div::before {
  content: "Only one <div>";
  font-size: min(6vh, 2rem);
  justify-content: center;
  display: flex;
  font-family: "Comic Sans", "Papyrus", sans-serif;
}

```

Play

The HTML for this sample is a single, empty [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) inside an otherwise empty [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/body). The snowman was created with [CSS images](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images) and [CSS backgrounds and borders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders). The carrot nose was added using generated content: an empty box with a wide orange [left border](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left) added to the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) pseudo-element. The text is also generated content: "only one <div>" was generated with the [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property applied to the [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-element.

Click "Play" in the example above to see or edit the code in the MDN Playground.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#properties)

- [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
- [`quotes`](https://developer.mozilla.org/en-US/docs/Web/CSS/quotes)

The CSS generated content module also introduces four at-risk properties: `string-set`, `bookmark-label`, `bookmark-level`, and `bookmark-state`. Currently, no browsers support these features.

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#functions)

The CSS generated content module introduces six yet-to-be implemented CSS functions including `content()`, `string()`, and `leader()`, and the three [`<target>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content#target) functions `target-counter()`, `target-counters()`, and `target-text()`.

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#data_types)

- [`<content-list>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
- `<content-replacement>` (see [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image))
- [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image)
- [`<counter>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content#counter)
- [`<quote>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content#quote)
- [`<target>`](https://developer.mozilla.org/en-US/docs/Web/CSS/content#target)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#guides)

["How to" guide for generated content](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Solve_CSS_problems/Generated_content)

Learn how to add text or image content to a document using the [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property.

[Create fancy boxes with generated content](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Solve_CSS_problems/Create_fancy_boxes)

Example of styling generated content for visual effects.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#related_concepts)

- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module
  - [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) pseudo-element
  - [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-element
  - [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker) pseudo-element
- [CSS lists and counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists) module
  - [`counter()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter) function
  - [`counters()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counters) function
  - [`counter-increment`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment) property
  - [`counter-reset`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset) property
- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module
  - [`::scroll-button()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-button) pseudo-element
  - [`::scroll-marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker) pseudo-element
  - [`:target-current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-current) pseudo-class
- [CSS values and units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units) module
  - [`attr()`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr) function
  - [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string) data type
  - [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image) data type

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#specifications)

| Specification |
| --- |
| [CSS Generated Content Module Level 3](https://drafts.csswg.org/css-content/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content\#see_also)

- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module
- [CSS lists and counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_lists) module
- [Replaced elements](https://developer.mozilla.org/en-US/docs/Glossary/Replaced_elements)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_generated_content/index.md?plain=1 "Folder: ⁨en-us/web/css/css_generated_content⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_generated_content&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_generated_content%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_generated_content%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_generated_content%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fbb52c01c1534149f1e3e4755e2576ef7828ecc0f%0A*+Document+last+modified%3A+2025-10-13T00%3A08%3A12.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")