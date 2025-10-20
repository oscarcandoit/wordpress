---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap
scraped_at: 2025-10-20T03:09:04.380Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#search)

# stroke-linecap


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨April 2017⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-linecap&level=high)

The **`stroke-linecap`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the shape to be used at the end of open subpaths of [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) elements' unclosed strokes. If present, it overrides the element's [`stroke-linecap`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-linecap) attribute.

This property applies to any SVG shape that can have unclosed strokes and text-content element (see [`stroke-linecap`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-linecap) for a full list), but as an inherited property, it may be applied to elements such as [`<g>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/g) and still have the intended effect on descendant elements' strokes.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#syntax)

cssCopy

```
/* keyword values */
stroke-linecap: butt;
stroke-linecap: round;
stroke-linecap: square;

/* Global values */
stroke-linecap: inherit;
stroke-linecap: initial;
stroke-linecap: revert;
stroke-linecap: revert-layer;
stroke-linecap: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#values)

[`butt`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#butt)

Indicates that the stroke for each subpath does not extend beyond its two endpoints. On a zero-length subpath, the path will not be rendered at all. This is the default value.

[`round`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#round)

Indicates that at the end of each subpath the stroke will be extended by a half circle with a diameter equal to the stroke width. On a zero-length subpath, the stroke consists of a full circle centered at the subpath's point.

[`square`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap#square)

Indicates that at the end of each subpath the stroke will be extended by a rectangle with a width equal to half the width of the stroke and a height equal to the width of the stroke. On a zero-length subpath, the stroke consists of a square with its width equal to the stroke width, centered at the subpath's point.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `butt` |
| Applies to | [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/circle), [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/ellipse), [`<line>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/line), [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path), [`<polygon>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/polygon), [`<polyline>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/polyline), and [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/rect) elements in an `svg` |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#formal_syntax)

```
stroke-linecap =
  butt     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  round    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  square

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#examples)

### [Linecaps](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#linecaps)

This example demonstrates the property's three keyword values.

#### HTML

We first set up a light-gray rectangle. Then, in a group, three paths are defined whose length is exactly the same as the width of the rectangle, and all of which start at the left edge of the rectangle. They are all set to have a `dodgerblue` stroke with a width of seven.

htmlCopy

```
<svg viewBox="0 0 100 50" width="500" height="250">
  <rect x="10" y="5" width="80" height="30" fill="#dddddd" />
  <g stroke="dodgerblue" stroke-width="7">
    <path d="M 10,10 h 80" />
    <path d="M 10,20 h 80" />
    <path d="M 10,30 h 80" />
  </g>
</svg>

```

#### CSS

We then apply a different linecap style to each path via CSS.

cssCopy

```
path:nth-of-type(1) {
  stroke-linecap: butt;
}
path:nth-of-type(2) {
  stroke-linecap: square;
}
path:nth-of-type(3) {
  stroke-linecap: round;
}

```

#### Results

The first path has `butt` linecaps, which essentially means the stroke runs exactly to the end points (both the start and the end) of the path, and no further. The second path has `square` linecaps, so the visible path extends out past the end points of the path, making the overall length of the path appear to be 87, since the path length is 80 and each of the two square caps is 3.5 wide. The third path has `circle` caps, so while it also appears to be 87 units long, the two caps are semicircular instead of square.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#specifications)

| Specification |
| --- |
| [CSS Fill and Stroke Module Level 3\<br>\# stroke-linecap](https://drafts.fxtf.org/fill-stroke-3/#stroke-linecap) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap\#see_also)

- [`stroke-dasharray`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dasharray)
- [`stroke-dashoffset`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dashoffset)
- [`stroke-linejoin`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linejoin)
- [`stroke-miterlimit`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit)
- [`stroke-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-opacity)
- [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width)
- [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke)
- SVG [`stroke-linecap`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-linecap) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/stroke-linecap/index.md?plain=1 "Folder: ⁨en-us/web/css/stroke-linecap⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-linecap&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fstroke-linecap%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-linecap%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fstroke-linecap%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")