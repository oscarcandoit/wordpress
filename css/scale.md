---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/scale
scraped_at: 2025-10-20T03:18:57.338Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# scale


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨August 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscale&level=high)

The **`scale`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows you to specify scale transforms individually and independently of the [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` value.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#try_it)

- scale: none;

- scale: 1.5;

- scale: 1.7 50%;

- scale: 1 -1;

- scale: 1.2 1.2 2;


## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#syntax)

cssCopy

```
/* Keyword values */
scale: none;

/* Single values */
/* values of more than 1 or 100% make the element grow */
scale: 2;
/* values of less than 1 or 100% make the element shrink */
scale: 50%;

/* Two values */
scale: 2 0.5;

/* Three values */
scale: 200% 50% 200%;

/* Global values */
scale: inherit;
scale: initial;
scale: revert;
scale: revert-layer;
scale: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#values)

[Single value](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#single_value)

A [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) specifying a scale factor to make the affected element scale by the same factor along both the X and Y axes. Equivalent to a `scale()` (2D scaling) function with a single value specified.

[Two values](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#two_values)

Two [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values that specify the X and Y axis scaling values (respectively) of a 2D scale. Equivalent to a `scale()` (2D scaling) function with two values specified.

[Three values](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#three_values)

Three [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values that specify the X, Y, and Z axis scaling values (respectively) of a 3D scale. Equivalent to a `scale3d()` (3D scaling) function.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/scale#none)

Specifies that no scaling should be applied.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `none` |
| Applies to | transformable elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a transform |
| Creates [stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context) | yes |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#formal_syntax)

```
scale =
  none                               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<number>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,3}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#examples)

### [Scaling an element on hover](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#scaling_an_element_on_hover)

The following example shows how to scale an element on hover.
Two boxes are shown, one with a single `scale` value which scales the element along both axes.
The second box has two `scale` values which scales the element along the X and Y axes independently.

#### HTML

htmlCopyPlay

```
<div class="box" id="box1">single value</div>
<div class="box" id="box2">two values</div>

```

#### CSS

cssCopyPlay

```
.box {
  float: left;
  margin: 1em;
  width: 7em;
  line-height: 7em;
  text-align: center;
  transition: 0.5s ease-in-out;
  border: 3px dotted;
}

#box1:hover {
  scale: 1.25;
}

#box2:hover {
  scale: 1.25 0.75;
}

```

#### Result

Play

single value

two values

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#specifications)

| Specification |
| --- |
| [CSS Transforms Module Level 2\<br>\# individual-transforms](https://drafts.csswg.org/css-transforms-2/#individual-transforms) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/scale# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/scale.json "File: ⁨css/properties/scale.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `scale` | Chrome – Full support<br>Chrome104<br>Chrome – Full support<br>Chrome104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge104<br>Edge – Full support<br>Edge104 (Release date: ⁨2022-08-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox72<br>Firefox – Full support<br>Firefox72 (Release date: ⁨2020-01-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera90<br>Opera – Full support<br>Opera90 (Release date: ⁨2022-08-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari14.1<br>Safari – Full support<br>Safari14.1 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android104<br>Chrome Android – Full support<br>Chrome Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android71<br>Opera Android – Full support<br>Opera Android71 (Release date: ⁨2022-09-16⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS14.5<br>Safari on iOS – Full support<br>Safari on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet20<br>Samsung Internet – Full support<br>Samsung Internet20 (Release date: ⁨2023-02-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android104<br>WebView Android – Full support<br>WebView Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS14.5<br>WebView on iOS – Full support<br>WebView on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome104<br>Chrome – Full support<br>Chrome104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge104<br>Edge – Full support<br>Edge104 (Release date: ⁨2022-08-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox72<br>Firefox – Full support<br>Firefox72 (Release date: ⁨2020-01-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera90<br>Opera – Full support<br>Opera90 (Release date: ⁨2022-08-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari14.1<br>Safari – Full support<br>Safari14.1 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android104<br>Chrome Android – Full support<br>Chrome Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android71<br>Opera Android – Full support<br>Opera Android71 (Release date: ⁨2022-09-16⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS14.5<br>Safari on iOS – Full support<br>Safari on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet20<br>Samsung Internet – Full support<br>Samsung Internet20 (Release date: ⁨2023-02-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android104<br>WebView Android – Full support<br>WebView Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS14.5<br>WebView on iOS – Full support<br>WebView on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/scale\#see_also)

- [`translate`](https://developer.mozilla.org/en-US/docs/Web/CSS/translate)
- [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/rotate)
- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

Note: skew is not an independent transform value

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/scale/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/scale/index.md?plain=1 "Folder: ⁨en-us/web/css/scale⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscale&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fscale%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscale%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fscale%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")