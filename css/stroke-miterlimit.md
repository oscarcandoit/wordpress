---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit
scraped_at: 2025-10-20T03:15:10.518Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit#search)

# stroke-miterlimit


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨April 2017⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-miterlimit&level=high)

The **`stroke-miterlimit`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a limit on the ratio of the miter length to the [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width) when the shape to be used at the corners of an [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) element's stroked path is a mitered join. If the limit defined by this property is exceeded, the join is converted from `miter` to `bevel`, thus making the corner appear truncated.

This property applies to any SVG corner-generating shape or text-content element (see [`stroke-miterlimit`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-miterlimit) for a full list), but as an inherited property, it may be applied to elements such as [`<g>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/g) and still have the intended effect on descendant elements' strokes. If present, it overrides the element's [`stroke-miterlimit`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-miterlimit) attribute.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#description)

When two line segments meet at a sharp angle and `miter` joins have been specified for [`stroke-linejoin`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linejoin), or if they default to that value, it is possible for the miter to extend far beyond the thickness of the line stroking the path. The `stroke-miterlimit` ratio is used to define a limit, past which the join is converted from a miter to a bevel.

The ratio of miter length (the distance between the outer tip and the inner corner of the miter) to [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width) is directly related to the angle (theta) between the segments in user space by the formula:

stroke-miterlimit=miterLengthstroke-width=1sin(θ2)\\text{stroke-miterlimit} = \\frac{\\text{miterLength}}{\\text{stroke-width}} = \\frac{1}{\\sin\\left(\\frac{\\theta}{2}\\right)}

For example, a miter limit of `1.414` converts miters to bevels for a theta value of less than 90 degrees, a limit of `4.0` converts them for a theta less than approximately 29 degrees, and a limit of `10.0` converts them for theta less than approximately 11.5 degrees.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#syntax)

cssCopy

```
/* number values */
stroke-miterlimit: 1;
stroke-miterlimit: 3.1416;

/* Global values */
stroke-miterlimit: inherit;
stroke-miterlimit: initial;
stroke-miterlimit: revert;
stroke-miterlimit: revert-layer;
stroke-miterlimit: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#values)

[`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number)

Any real positive number equal to or greater than `1`; values below that are invalid. The initial value is `4`.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `4` |
| Applies to | [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/circle), [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/ellipse), [`<line>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/line), [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path), [`<polygon>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/polygon), [`<polyline>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/polyline), and [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/rect) elements in an `svg` |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | by computed value type |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#formal_syntax)

```
stroke-miterlimit =
  [<number>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#examples)

### [Various miter limits](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#various_miter_limits)

This example demonstrates the effect of different values for the `stroke-miterlimit` property.

#### HTML

We set up five multi-segment paths, all of which use a black stroke with a width of one, and no fill. Each path creates a series of mountain symbols, going from left (a shallow corner angle) to right (an extreme corner angle).

htmlCopy

```
<svg viewBox="0 0 39 36" xmlns="http://www.w3.org/2000/svg">
  <g stroke="black" stroke-width="1" fill="none">
    <path
      d="M1,5 l7   ,-3 l7   ,3
         m2,0 l3.5 ,-3 l3.5 ,3
         m2,0 l2   ,-3 l2   ,3
         m2,0 l0.75,-3 l0.75,3
         m2,0 l0.5 ,-3 l0.5 ,3" />
    <path
      d="M1,12 l7,-3 l7,3 m2,0 l3.5,-3 l3.5,3 m2,0 l2,-3 l2,3 m2,0 l0.75,-3 l0.75,3 m2,0 l0.5,-3 l0.5,3" />
    <path
      d="M1,19 l7,-3 l7,3 m2,0 l3.5,-3 l3.5,3 m2,0 l2,-3 l2,3 m2,0 l0.75,-3 l0.75,3 m2,0 l0.5,-3 l0.5,3" />
    <path
      d="M1,26 l7,-3 l7,3 m2,0 l3.5,-3 l3.5,3 m2,0 l2,-3 l2,3 m2,0 l0.75,-3 l0.75,3 m2,0 l0.5,-3 l0.5,3" />
    <path
      d="M1,33 l7,-3 l7,3 m2,0 l3.5,-3 l3.5,3 m2,0 l2,-3 l2,3 m2,0 l0.75,-3 l0.75,3 m2,0 l0.5,-3 l0.5,3" />
  </g>
</svg>

```

#### CSS

We apply increasingly large values of `stroke-miterlimit` to the paths, such that for the first path, only the first (leftmost) subpath is mitered; for the second path, the first two subpaths are mitered; and so on until for the fifth path, all five subpaths are mitered.

cssCopy

```
path:nth-child(1) {
  stroke-miterlimit: 1.1;
}
path:nth-child(2) {
  stroke-miterlimit: 1.4;
}
path:nth-child(3) {
  stroke-miterlimit: 1.9;
}
path:nth-child(4) {
  stroke-miterlimit: 4.2;
}
path:nth-child(5) {
  stroke-miterlimit: 6.1;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#specifications)

| Specification |
| --- |
| [CSS Fill and Stroke Module Level 3\<br>\# stroke-miterlimit](https://drafts.fxtf.org/fill-stroke-3/#stroke-miterlimit) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit\#see_also)

- [`stroke-dasharray`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dasharray)
- [`stroke-dashoffset`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dashoffset)
- [`stroke-linecap`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap)
- [`stroke-linejoin`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linejoin)
- [`stroke-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-opacity)
- [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width)
- [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke)
- SVG [`stroke-miterlimit`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke-miterlimit) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/stroke-miterlimit/index.md?plain=1 "Folder: ⁨en-us/web/css/stroke-miterlimit⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-miterlimit&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fstroke-miterlimit%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fstroke-miterlimit%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fstroke-miterlimit%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")