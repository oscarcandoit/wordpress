---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor
scraped_at: 2025-10-20T03:19:03.878Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#search)

# text-anchor


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨August 2016⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-anchor&level=high)

The **`text-anchor`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property aligns a box containing a string of text where the wrapping area is determined from the [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size) property, and the text is then placed relative to the anchor point of the element, which is defined using the [`x`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/x) and [`y`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/y) (or [`dx`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/dx) and [`dy`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/dy)) attributes. If present, the value of the CSS property overrides any value of the element's [`text-anchor`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/text-anchor) attribute.

Each individual text fragment within an element is aligned independently; thus, a multi-line [`<text>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/text) element will have each line of text aligned as per the value of `text-anchor`. `text-anchor` values only have an effect on the [`<text>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/text), [`<textPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/textPath), and [`<tspan>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/tspan) SVG elements. `text-anchor` does not apply to automatically wrapped text; for that, see [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#syntax)

css

```
text-anchor: start;
text-anchor: middle;
text-anchor: end;

/* Global values */
text-anchor: inherit;
text-anchor: initial;
text-anchor: revert;
text-anchor: revert-layer;
text-anchor: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#values)

[`start`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#start)

Aligns the text such that the inline start of the text string is aligned with the anchor point. This alignment is relative to the writing direction of the text; thus, for example, in right-to-left top-to-bottom writing, the text will be placed to the left of the anchor point. If the text's inline direction is vertical, as with many Asian languages, the top edge of the text is aligned with the anchor point.

[`middle`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#middle)

Aligns the text such that the center (middle) of the text string's inline box is aligned with the anchor point.

[`end`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor#end)

Aligns the text such that the inline end of the text string is aligned with the anchor point. This alignment is relative to the writing direction of the text; thus, for example, in right-to-left top-to-bottom writing, the text will be placed to the right of the anchor point. If the text's inline direction is vertical, as with many Asian languages, the bottom edge of the text is aligned with the anchor point.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `start` |
| Applies to | [`<text>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/text), [`<textPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/textPath), and [`<tspan>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/tspan) elements in [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/svg) |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#formal_syntax)

```
text-anchor =
  start    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  middle   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  end

```

## [Example](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#example)

Three `<text>` elements are given the same `x` position, but different values for `text-anchor`. A dashed red line is included to mark the x-axis position of all three anchor points.

html

```
<svg
  viewBox="0 0 200 150"
  height="150"
  width="200"
  xmlns="http://www.w3.org/2000/svg">
  <line
    x1="100"
    y1="0"
    x2="100"
    y2="150"
    stroke="red"
    stroke-dasharray="10,5" />
  <text x="100" y="40">Anchored</text>
  <text x="100" y="80">Anchored</text>
  <text x="100" y="120">Anchored</text>
</svg>

```

```
text {
  font-size: 24px;
}

```

css

```
text:nth-of-type(1) {
  text-anchor: start;
}
text:nth-of-type(2) {
  text-anchor: middle;
}
text:nth-of-type(3) {
  text-anchor: end;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#specifications)

| Specification |
| --- |
| [Scalable Vector Graphics (SVG) 2\<br>\# TextAnchorProperty](https://svgwg.org/svg2-draft/text.html#TextAnchorProperty) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor\#see_also)

- [`dominant-baseline`](https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline)
- SVG [`<text>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/text) element
- SVG [`text-anchor`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/text-anchor) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/text-anchor/index.md?plain=1 "Folder: ⁨en-us/web/css/text-anchor⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-anchor&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftext-anchor%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-anchor%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftext-anchor%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")