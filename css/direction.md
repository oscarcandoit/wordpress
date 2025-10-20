---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/direction
scraped_at: 2025-10-20T03:05:18.548Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/direction#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/direction#search)

# direction


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/direction#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdirection&level=high)

**Warning:**
Where possible, authors are encouraged to avoid using the `direction` CSS property and use the HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/dir) global attribute instead.

The **`direction`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the direction of text, table and grid columns, and horizontal overflow. Use `rtl` for languages written from right to left (like Hebrew or Arabic), and `ltr` for those written from left to right (like English and most other languages).

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#try_it)

```
direction: ltr;

```

```
direction: rtl;

```

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
  </div>
</section>

```

```
#example-element {
  border: 1px solid #c5c5c5;
  padding: 0.75em;
  width: 80%;
  max-height: 300px;
  display: flex;
}

#example-element > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
  margin: 10px;
  flex: 1;
}

```

Note that text direction is usually defined within a document (e.g., with [HTML's `dir` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/dir)) rather than through direct use of the `direction` property.

The property sets the base text direction of block-level elements and the direction of embeddings created by the [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) property. It also sets the default alignment of text, block-level elements, and the direction that cells flow within a table or grid row.

Unlike the `dir` attribute in HTML, the `direction` property is not inherited from table columns into table cells, since CSS inheritance follows the document tree, and table cells are inside of rows but not inside of columns.

The `direction` and [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) properties are the only two properties which are not affected by the [`all`](https://developer.mozilla.org/en-US/docs/Web/CSS/all) shorthand property.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#syntax)

css

```
/* Keyword values */
direction: ltr;
direction: rtl;

/* Global values */
direction: inherit;
direction: initial;
direction: revert;
direction: revert-layer;
direction: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#values)

[`ltr`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction#ltr)

Text and other elements go from left to right. This is the default value.

[`rtl`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction#rtl)

Text and other elements go from right to left.

For the `direction` property to have any effect on inline-level elements, the [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) property's value must be `embed` or `override`.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `ltr` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#formal_syntax)

```
direction =
  ltr   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  rtl

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#examples)

### [Setting right-to-left direction](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#setting_right-to-left_direction)

In the example below are two strings of text, both which are displaying using `direction: rtl`. While the Arabic text is displayed correctly with this setting, the English text now has a full stop in an unusual location.

css

```
blockquote {
  direction: rtl;
  width: 300px;
}

```

html

```
<blockquote>
  <p>This paragraph is in English but incorrectly goes right to left.</p>
  <p></p>
</blockquote>

<blockquote>
  <p>هذه الفقرة باللغة العربية ، لذا يجب الانتقال من اليمين إلى اليسار.</p>
  <p></p>
</blockquote>

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#specifications)

| Specification |
| --- |
| [CSS Writing Modes Level 4\<br>\# direction](https://drafts.csswg.org/css-writing-modes/#direction) |
| [Scalable Vector Graphics (SVG) 2\<br>\# DirectionProperty](https://svgwg.org/svg2-draft/text.html#DirectionProperty) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/direction\#see_also)

- [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
- [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
- SVG [`direction`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/direction) attribute
- The HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/dir) global attribute
- [Creating vertical form controls](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Vertical_controls)
- [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Handling_different_text_directions)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/direction/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/direction/index.md?plain=1 "Folder: ⁨en-us/web/css/direction⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdirection&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fdirection%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdirection%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fdirection%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")