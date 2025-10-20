---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model
scraped_at: 2025-10-20T03:05:52.644Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS box model

The **CSS box model** module defines the `margin` and `padding` properties, which along with the [height](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing), [width](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing) and [border properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders), make up the CSS [box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model).

Every visible element on a webpage is a box laid out according to the [visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model). CSS properties define their size, position, and stacking level, with the box model properties (and others) defining the extrinsic size of each box, and the space around them.

Each box has a rectangular content area, inside which any text, images, and other content is displayed. The content may be surrounded by padding, a border, and a margin, on one or more sides. The padding is around the content, the border is around the padding, and the margin sits outside the border. The box model describes how these features — the content, padding, border, and margin — work together to create a box as displayed by CSS.

![The components of the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/boxmodel.png)

The CSS box model module defines physical (or "page relative") properties such as `margin-top` and `padding-top`. Flow-relative properties such as `margin-block-start` and `margin-inline-start` (which relate to text direction) are defined in [Logical Properties and Values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values). The box model module is extended by the [CSS box sizing module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing), which introduces the [intrinsic size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size) value and enables defining [aspect ratio](https://developer.mozilla.org/en-US/docs/Glossary/Aspect_ratio) for elements that are auto-sized in at least one dimension.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#properties)

- [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) shorthand
- [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom)
- [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)
- [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
- [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top)
- [`margin-trim`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-trim)
- [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) shorthand
- [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom)
- [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left)
- [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right)
- [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top)

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#data_types)

- [`<box-edge>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge)
  - [`<visual-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge#visual-box)
  - [`<layout-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge#layout-box)
  - [`<paint-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge#paint-box)
  - [`<coord-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge#coord-box)
  - [`<geometry-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge#geometry-box)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#guides)

[Introduction to the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)

Explains one of the fundamental concepts of CSS: the box model. This model defines how CSS lays out elements, including their content, padding, border, and margin areas.

[Mastering margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)

Sometimes, two adjacent margins are collapsed into one. This article describes the rules that govern when and why this happens, and how to control it.

[Visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model)

Explains the visual formatting model.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#related_concepts)

- [CSS backgrounds and borders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders) module

  - [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) shorthand
  - [`border-bottom-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width)
  - [`border-left-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width)
  - [`border-right-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width)
  - [`border-top-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width)
- [CSS logical properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values) module

  - [`block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/block-size)
  - [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size)
  - [`max-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size)
  - [`max-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size)
  - [`min-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-block-size)
  - [`min-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size)
  - [`margin-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block)
  - [`margin-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-end)
  - [`margin-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-start)
  - [`margin-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline)
  - [`margin-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end)
  - [`margin-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-start)
  - [`padding-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block)
  - [`padding-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end)
  - [`padding-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-start)
  - [`padding-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline)
  - [`padding-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end)
  - [`padding-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start)
  - [`border-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block)
  - [`border-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end)
  - [`border-block-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-width)
  - [`border-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start)
  - [`border-block-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-width)
  - [`border-block-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-style)
  - [`border-block-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-width)
  - [`border-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline)
  - [`border-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end)
  - [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width)
  - [`border-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start)
  - [`border-inline-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width)
  - [`border-inline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-width)
- [CSS box sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing) module

  - [`aspect-ratio`](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)
  - [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
  - [`contain-intrinsic-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-block-size)
  - [`contain-intrinsic-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-height)
  - [`contain-intrinsic-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-inline-size)
  - [`contain-intrinsic-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-size)
  - [`contain-intrinsic-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-width)
  - [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)
  - [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
  - [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)
  - [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height)
  - [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width)
  - [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module

  - [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) shorthand
  - [`overflow-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block)
  - [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin)
  - [`overflow-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline)
  - [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
  - [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
  - [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#specifications)

| Specification |
| --- |
| [CSS Box Model Module Level 4](https://drafts.csswg.org/css-box-4/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model\#see_also)

- [CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) module
- [CSS flex layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) module
- [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) module
- [CSS table](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_table) module
- [CSS positioned layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout) module
- [CSS fragmentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fragmentation) module
- [Understanding aspect ratios](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing/Understanding_aspect-ratio)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_box_model/index.md?plain=1 "Folder: ⁨en-us/web/css/css_box_model⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_box_model&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_box_model%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_box_model%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_box_model%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")