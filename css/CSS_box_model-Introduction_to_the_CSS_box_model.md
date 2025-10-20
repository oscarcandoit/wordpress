---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model
scraped_at: 2025-10-20T02:58:38.060Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# Introduction to the CSS box model

When laying out a document, the browser's rendering engine represents each element as a rectangular box according to the standard **CSS basic box model**. CSS determines the size, position, and properties (color, background, border size, etc.) of these boxes.

Every box is composed of four parts (or _areas_), defined by their respective edges: the _content edge_, _padding edge_, _border edge_, and _margin edge_.

![CSS Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model/boxmodel.png)

## [Content area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model\#content_area)

The **content area**, bounded by the content edge, contains the "real" content of the element, such as text, an image, or a video player. Its dimensions are the _content width_ (or _content-box width_) and the _content height_ (or _content-box height_). It often has a background color or background image.

If the [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) property is set to `content-box` (default) and if the element is a block element, the content area's size can be explicitly defined with the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), and [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties.

## [Padding area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model\#padding_area)

The **padding area**, bounded by the padding edge, extends the content area to include the element's padding. Its dimensions are the _padding-box width_ and the _padding-box height_.

The thickness of the padding is determined by the [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top), [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right), [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom), [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left), and shorthand [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) properties.

## [Border area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model\#border_area)

The **border area**, bounded by the border edge, extends the padding area to include the element's borders. Its dimensions are the _border-box width_ and the _border-box height_.

The thickness of the borders are determined by the [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) and shorthand [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) properties. If the [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) property is set to `border-box`, the border area's size can be explicitly defined with the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), and [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties. When there is a background ( [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) or [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)) set on a box, it extends to the outer edge of the border (i.e., extends underneath the border in z-ordering). This default behavior can be altered with the [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip) CSS property.

## [Margin area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model\#margin_area)

The **margin area**, bounded by the margin edge, extends the border area to include an empty area used to separate the element from its neighbors. Its dimensions are the _margin box width_ and the _margin box height_.

The size of the margin area is determined by the [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top), [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right), [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom), [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left), and shorthand [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) properties. When [margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing) occurs, the margin area is not clearly defined since margins are shared between boxes.

Finally, note that for non-replaced inline elements, the amount of space taken up (the contribution to the height of the line) is determined by the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property, even though the borders and padding are still displayed around the content.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model\#see_also)

- [Layout and the containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Containing_block)
- [Introducing the CSS Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade)
- [Learn: Handling conflicts](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Handling_conflicts)
- CSS key concepts:
  - [CSS syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax)
  - [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule)
  - [Comments](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Comments)
  - [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
  - [Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance)
  - [Layout modes](https://developer.mozilla.org/en-US/docs/Glossary/Layout_mode)
  - [Visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model)
  - [Margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)
  - Values
    - [Initial values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value)
    - [Computed values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value)
    - [Used values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#used_value)
    - [Actual values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#actual_value)
  - [Value definition syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax)
  - [Shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties)
  - [Replaced elements](https://developer.mozilla.org/en-US/docs/Glossary/Replaced_elements)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_box_model/introduction_to_the_css_box_model/index.md?plain=1 "Folder: ⁨en-us/web/css/css_box_model/introduction_to_the_css_box_model⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_box_model%2FIntroduction_to_the_CSS_box_model&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_box_model%2Fintroduction_to_the_css_box_model%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_box_model%2FIntroduction_to_the_CSS_box_model%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_box_model%2Fintroduction_to_the_css_box_model%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")