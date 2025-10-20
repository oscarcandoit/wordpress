---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems
scraped_at: 2025-10-20T03:09:07.866Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems#search)

# Introduction to writing mode systems

CSS supports different content directionalities, or **writing modes**, including right-to-left, left-to-right, and top-to-bottom. The guide provides a brief overview of writing mode systems and their directionalities.

## [Block and inline](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#block_and_inline)

Before examining the directionality of various writing systems, it's important to understand the terms "block" and "inline". The term **inline** refers to how characters and words flow within a line. The term **block** refers to how lines, or blocks of content, stack up next to one another. The document's writing mode determines a document's block and inline directions. They are not based on physical directions such as left, right, top, and bottom.

### [Dimensions and directions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#dimensions_and_directions)

Everything on a web page is laid out in either the **inline** or **block** dimension. The _inline dimension_ is the dimension along which a line of text runs in the current writing mode, whereas the _block dimension_ is the dimension in which blocks — such as paragraphs — display one after the other. The inline dimension is perpendicular to the block dimension.

In an English document, with the text running horizontally left-to-right, or an Arabic document with the text running horizontally right-to-left, the inline dimension is horizontal, while the _inline direction_ is left-to-right and right-to-left, respectively. In both cases, the block dimension is vertical, with the _block direction_ being top-to-bottom. In a vertical writing mode such as Japanese, the inline dimension is vertical, as lines in that writing mode run vertically, while the block dimension is horizontal.

### [Inline and block boxes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#inline_and_block_boxes)

The _outer display_ type of boxes in a [normal flowing layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model#normal_flow) determines how the box behaves alongside other elements on the page. _Inline boxes_ wrap each line of text and are laid out along the inline dimension.

_Block boxes_ represent containers on the page that can contain other block and inline elements. They are laid out along the block dimension and will extend in the inline dimension to fill all the space available in their container (provided a specific size is not set in the inline dimension using a property such as [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size)). Block boxes are only displayed from the top to the bottom of the page if you are using a writing mode that displays text horizontally, such as English.

The [CSS logical properties and values module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values#properties) defines [flow-relative mappings](https://developer.mozilla.org/en-US/docs/Glossary/Flow_relative_values) for many of the [physical properties](https://developer.mozilla.org/en-US/docs/Glossary/Physical_properties) and values in CSS, which is helpful in understanding the [basic concepts of logical properties and values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values/Basic_concepts_of_logical_properties_and_values).

### [Inline base and block flow directions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#inline_base_and_block_flow_directions)

The _inline base direction_ is the primary direction in which content is ordered on a line and defines the "start" and "end" of a line. The [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) property specifies the inline base direction of a box and, together with the [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) property and the inherent directionality of any text content, determines the ordering of inline-level content within a line.

The _block flow direction_ is the direction in which block-level and line boxes stack within a block container. The [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode) property determines the block flow direction.

## [Writing system modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#writing_system_modes)

Different writing systems have different writing modes. A horizontal writing mode is one with horizontal lines of text, i.e., a downward or upward block flow. A vertical writing mode is one with vertical lines of text, i.e., a leftward or rightward block flow.

Latin- and Slavic-based systems are typically written using a left-to-right inline direction with a top-to-bottom block flow direction. Latin-based languages include English, Spanish, Romanian, and Portuguese. Slavic-based languages include Ukrainian, Polish, and Czech.

htmlCopy

```
<p lang="en-US" dir="auto">This is written in English</p>
<p lang="lt-LT" dir="auto">Tai parašyta lietuviu kalba</p>
<p lang="el-GR" dir="auto">Αυτό είναι γραμμένο στα ελληνικά</p>

```

Arabic-based systems are typically written using a right-to-left inline direction with a top-to-bottom block flow direction. There are several horizontal right-to-left languages, including Arabic, Aramaic, Azeri, Divehi, Fula, Hebrew, Kurdish, N'ko, Persian, Rohingya, Syriac, and Urdu.

htmlCopy

```
<p lang="ur-PK" dir="auto">یہ اردو میں لکھا ہے۔</p>
<p lang="ku-CRB" dir="auto">ئەمە بە کوردی نووسراوە</p>

```

Han-based systems are commonly written using a left-to-right inline direction with a top-to-bottom block flow direction, or a top-to-bottom inline direction with a right-to-left block flow direction. Traditionally, Chinese, Vietnamese, Korean, and Japanese are written vertically in columns, going from top to bottom, with a right-to-left block direction, but will often be rendered horizontally online, going from left to right.

htmlCopy

```
<p lang="jp-JP" dir="auto">これはベトナム語で書かれています</p>

```

Mongolian-based systems are typically written vertically, top to bottom, in columns that flow left to right; a top-to-bottom inline direction with a left-to-right block flow direction. This differs from Chinese, Japanese, and Korean, whose vertical text columns are read right to left. It derives from the fact that Mongolian script descended from Old Uyghur, which was written left-to-right.

htmlCopy

```
<p lang="mn-MONG" dir="auto">Үүнийг монгол хэлээр бичжээ</p>

```

To render the writing modes correctly, we use the global HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/dir) attribute. Because browsers can turn off CSS styling, it is recommended to use the `dir` attribute and [`<bdo>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/bdo) element to ensure correct bidirectional layout in the absence of a style sheet, rather than the CSS [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) property.

For vertical languages, we use the [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode) and [`text-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation) properties:

cssCopy

```
[lang|="jp"] {
  writing-mode: vertical-rl;
  text-orientation: sideways;
}
[lang|="mn"] {
  writing-mode: vertical-lr;
  text-orientation: sideways;
}

```

## [Mixing writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#mixing_writing_modes)

While these different languages have different writing modes, sites that predominantly use one type of writing mode may contain content from a different language or writing mode. For example, articles in an Arabic, right-to-left language news site may include Latin-style numbers, which are written left to right. Many magazines and newspapers mix different writing modes on the same page. This guide, which demonstrates different writing modes, does too.

The typographic mode determines whether to use typographic conventions specific to vertical flow for vertical scripts (vertical typographic mode) or to use the typographic conventions of horizontal writing modes (horizontal typographic mode). This concept distinguishes vertical typesetting from rotated horizontal typesetting.

The `text-orientation` component of the writing mode controls the glyph orientation in vertical typographic modes, dictating whether a particular typographic character unit is typeset upright or typeset sideways.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems\#see_also)

- [CSS writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 17, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Writing_mode_systems/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_writing_modes/writing_mode_systems/index.md?plain=1 "Folder: ⁨en-us/web/css/css_writing_modes/writing_mode_systems⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_writing_modes%2FWriting_mode_systems&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_writing_modes%2Fwriting_mode_systems%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_writing_modes%2FWriting_mode_systems%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_writing_modes%2Fwriting_mode_systems%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5f406af7cc71ebbd0ce080c9216b6094f58732cf%0A*+Document+last+modified%3A+2025-10-17T11%3A39%3A18.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")