---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/cy
scraped_at: 2025-10-20T03:17:37.434Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/cy#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/cy#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# cy


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2020⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/cy#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcy&level=high)

The **`cy`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the y-axis center point of an SVG [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/circle) or [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/ellipse) elements. If present, it overrides the element's [`cy`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/cy) attribute.

**Note:**
While the SVG [`<radialGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/radialGradient) element supports the [`cy`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/cy) attribute, the `cy` property only applies to [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/circle) and [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/ellipse) elements nested in an [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/svg). This attribute does not apply to `<radialGradient>` or other SVG elements nor to HTML elements or pseudo-elements.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#syntax)

cssCopy

```
/* length and percentage values */
cy: 3px;
cy: 20%;

/* Global values */
cy: inherit;
cy: initial;
cy: revert;
cy: revert-layer;
cy: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#values)

The [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) and [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values denote the vertical center of the circle or ellipse.

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

As an absolute or relative length, it can be expressed in any unit allowed by the CSS [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) data type. Negative values are invalid.

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

Percentages refer to the height of the current SVG viewport.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `0` |
| Applies to | [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/ellipse) and [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/circle) elements in [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/svg) |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | refer to the height of the current SVG viewport |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | the percentage as specified or the absolute length |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | by computed value type |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#formal_syntax)

```
cy =
  <length-percentage>

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#examples)

### [Defining the y-axis coordinate of a circle and ellipse](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#defining_the_y-axis_coordinate_of_a_circle_and_ellipse)

In this example, we have two identical `<circle>` and two identical `<ellipse>` elements in an SVG; their `cy` attribute values ar `50` and `150`, respectively.

htmlCopyPlay

```
<svg xmlns="http://www.w3.org/2000/svg">
  <circle cx="50" cy="50" r="30" />
  <circle cx="50" cy="50" r="30" />
  <ellipse cx="150" cy="50" rx="20" ry="40" />
  <ellipse cx="150" cy="50" rx="20" ry="40" />
</svg>

```

With CSS, we style only the first circle and first ellipse, allowing their twin shapes to use default styles (with ( [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill) defaulting to black). We use the `cy` property to override the value of the SVG [`cy`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/cy) attribute and also give it a `fill` and [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke) to differentiate the first shapes in each pair from their twin. The browser renders SVG images as `300px` wide and `150px` tall by default.

cssCopyPlay

```
svg {
  border: 1px solid;
}

circle:first-of-type {
  cy: 30px;
  fill: lightgreen;
  stroke: black;
}
ellipse:first-of-type {
  cy: 100px;
  fill: pink;
  stroke: black;
}

```

Play

The styled circle's center is `30px` from the top edge of the SVG viewport and the styled ellipse is `100px` from that edge, as defined in the CSS `cy` property values. The unstyled shapes centers are both `50px` from the top edge of the SVG viewport, as defined in their SVG `cy` attribute values.

### [y-axis coordinates as percentage values](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#y-axis_coordinates_as_percentage_values)

In this example, we use the same markup as the previous example. The only difference is the CSS `cy` property value; in this case, we use percentage values of `30%` and `50%`.

cssCopyPlay

```
svg {
  border: 1px solid;
}

circle:first-of-type {
  cy: 30%;
  fill: lightgreen;
  stroke: black;
}
ellipse:first-of-type {
  cy: 50%;
  fill: pink;
  stroke: black;
}

```

Play

In this case, the y-axis coordinates of the center of the circle and ellipse are `30%` and `50%` of the height of the current SVG viewport, respectively. As the image's height defaulted to `150px`, meaning the `cy` value is the equivalent of `45px` and `120px`.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#specifications)

| Specification |
| --- |
| [Scalable Vector Graphics (SVG) 2\<br>\# CY](https://svgwg.org/svg2-draft/geometry.html#CY) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/cy# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/cy.json "File: ⁨css/properties/cy.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `cy` | Chrome – Full support<br>Chrome43<br>Chrome – Full support<br>Chrome43 (Release date: ⁨2015-05-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox69<br>Firefox – Full support<br>Firefox69 (Release date: ⁨2019-09-03⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera30<br>Opera – Full support<br>Opera30 (Release date: ⁨2015-06-09⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android43<br>Chrome Android – Full support<br>Chrome Android43 (Release date: ⁨2015-05-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android30<br>Opera Android – Full support<br>Opera Android30 (Release date: ⁨2015-06-10⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet4<br>Samsung Internet – Full support<br>Samsung Internet4 (Release date: ⁨2016-03-11⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android43<br>WebView Android – Full support<br>WebView Android43 (Release date: ⁨2015-05-27⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/cy\#see_also)

- SVG [`cy`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/cy) attribute
- Geometry properties: `cy`, [`cx`](https://developer.mozilla.org/en-US/docs/Web/CSS/cx), [`r`](https://developer.mozilla.org/en-US/docs/Web/CSS/r), [`rx`](https://developer.mozilla.org/en-US/docs/Web/CSS/rx), [`ry`](https://developer.mozilla.org/en-US/docs/Web/CSS/ry), [`x`](https://developer.mozilla.org/en-US/docs/Web/CSS/x), [`y`](https://developer.mozilla.org/en-US/docs/Web/CSS/y), [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)
- [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill)
- [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke)
- [`paint-order`](https://developer.mozilla.org/en-US/docs/Web/CSS/paint-order)
- [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) shorthand property
- [`radial-gradient`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient)
- [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape) data type

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/cy/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/cy/index.md?plain=1 "Folder: ⁨en-us/web/css/cy⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcy&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcy%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcy%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcy%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")