---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation
scraped_at: 2025-10-20T03:12:41.894Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#search)

# color-interpolation


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨January 2020⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolor-interpolation&level=high)

The `color-interpolation` CSS property is used in SVG to specify which color space to use for [`<linearGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/linearGradient) and [`<radialGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/radialGradient) SVG elements.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#syntax)

cssCopy

```
/* Keyword values */
color-interpolation: auto;
color-interpolation: sRGB;
color-interpolation: linearRGB;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#auto)

Indicates that the user agent can choose either the `sRGB` or `linearRGB` spaces for color interpolation. This option indicates that the author doesn't require that color interpolation occur in a particular color space.

[`sRGB`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#srgb)

Indicates that color interpolation should occur in the sRGB color space.
Defaults to this initial value if no `color-interpolation` property is set.

[`linearRGB`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation#linearrgb)

Indicates that color interpolation should occur in the linearized RGB color space as described in [the sRGB specification](https://webstore.iec.ch/en/publication/6169).

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#formal_definition)

| Value | `auto` \| `sRGB` \| `linearRGB` |
| Applies to | [`<linearGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/linearGradient) and [`<radialGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/radialGradient) |
| Default value | `auto` |
| Animatable | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#formal_syntax)

```
color-interpolation =
  auto        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  sRGB        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  linearRGB

```

## [Example](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#example)

In the first SVG, the `color-interpolation` property is not included on the `<linearGradient>` element and color interpolation defaults to `sRGB`.
The second example shows color interpolation using the `linearRGB` value.

htmlCopy

```
<svg width="450" height="70">
  <title>Example of using the color-interpolation CSS Property</title>
  <defs>
    <linearGradient id="sRGB">
      <stop offset="0%" stop-color="white" />
      <stop offset="25%" stop-color="blue" />
      <stop offset="50%" stop-color="white" />
      <stop offset="75%" stop-color="red" />
      <stop offset="100%" stop-color="white" />
    </linearGradient>
  </defs>
  <rect x="0" y="0" width="400" height="40" fill="url(#sRGB)" stroke="black" />
  <text x="0" y="60" font-family="courier" font-size="16">
    no color-interpolation (CSS property)
  </text>
</svg>

```

htmlCopy

```
<svg width="450" height="70">
  <title>Example of using the color-interpolation CSS Property</title>
  <defs>
    <linearGradient id="linearRGB">
      <stop offset="0%" stop-color="white" />
      <stop offset="25%" stop-color="blue" />
      <stop offset="50%" stop-color="white" />
      <stop offset="75%" stop-color="red" />
      <stop offset="100%" stop-color="white" />
    </linearGradient>
  </defs>
  <rect
    x="0"
    y="0"
    width="400"
    height="40"
    fill="url(#linearRGB)"
    stroke="black" />
  <text x="0" y="60" font-family="courier" font-size="16">
    color-interpolation: linearRGB; (CSS property)
  </text>
</svg>

```

cssCopy

```
svg {
  display: block;
}

#linearRGB {
  color-interpolation: linearRGB;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#specifications)

| Specification |
| --- |
| [Scalable Vector Graphics (SVG) 2\<br>\# ColorInterpolationProperty](https://svgwg.org/svg2-draft/painting.html#ColorInterpolationProperty) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation\#see_also)

- [`<linearGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/linearGradient)
- [`<radialGradient>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/radialGradient)
- SVG [`color-interpolation`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/color-interpolation) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/color-interpolation/index.md?plain=1 "Folder: ⁨en-us/web/css/color-interpolation⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolor-interpolation&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcolor-interpolation%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolor-interpolation%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcolor-interpolation%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")