---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/atan2
scraped_at: 2025-10-20T03:05:11.414Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# atan2()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2023⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fatan2&level=high)

The **`atan2()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) is a trigonometric function that returns the inverse tangent of two values between `-infinity` and `infinity`. The function accepts two arguments and returns the number of radians representing an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) between `-180deg` and `180deg`.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#syntax)

cssCopy

```
/* Two <number> values */
transform: rotate(atan2(3, 2));

/* Two <dimension> values */
transform: rotate(atan2(1rem, -0.5rem));

/* Two <percentage> values */
transform: rotate(atan2(20%, -30%));

/* Other values */
transform: rotate(atan2(pi, 45));
transform: rotate(atan2(e, 30));

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#parameters)

The `atan2(y, x)` function accepts two comma-separated values as its parameters. Each value can be a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number), a [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension), or a [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Both values must be of the same type, although if they are [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension) they can be of different units (example: `atan2(100px, 5vw)` is valid).

[`y`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2#y)

The y-coordinate of the point. A calculation which resolves to a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number), a [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension), or a [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage).

[`x`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2#x)

The x-coordinate of the point. A calculation which resolves to a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number), a [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension), or a [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage).

### [Return value](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#return_value)

Given two values `x` and `y`, the function `atan2(y, x)` calculates and returns the [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) between the positive x-axis and the ray from the origin to the point `(x, y)`.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#formal_syntax)

```
<atan2()> =
  atan2( <calc-sum> , <calc-sum> )

<calc-sum> =
  <calc-product>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '+' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '-' [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <calc-product>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<calc-product> =
  <calc-value>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '*' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") / [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <calc-value>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<calc-value> =
  [<number>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<dimension>](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension)      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <calc-keyword>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ( <calc-sum> )

<calc-keyword> =
  e           [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  pi          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  infinity    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  -infinity   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  NaN

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#examples)

### [Rotate elements](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#rotate_elements)

The `atan2()` function can be used to [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate) elements as it return an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle).

#### HTML

htmlCopyPlay

```
<div class="box box-1"></div>
<div class="box box-2"></div>
<div class="box box-3"></div>
<div class="box box-4"></div>
<div class="box box-5"></div>

```

#### CSS

cssCopyPlay

```
body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 50px;
}

```

cssCopyPlay

```
div.box {
  width: 100px;
  height: 100px;
  background: linear-gradient(orange, red);
}
div.box-1 {
  transform: rotate(atan2(3, 2));
}
div.box-2 {
  transform: rotate(atan2(3%, -2%));
}
div.box-3 {
  transform: rotate(atan2(-1, 0.5));
}
div.box-4 {
  transform: rotate(atan2(1, 0.5));
}
div.box-5 {
  transform: rotate(atan2(1rem, -0.5rem));
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 4\<br>\# trig-funcs](https://drafts.csswg.org/css-values/#trig-funcs) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/atan2.json "File: ⁨css/types/atan2.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `atan2()` | Chrome – Full support<br>Chrome111<br>Chrome – Full support<br>Chrome111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge111<br>Edge – Full support<br>Edge111 (Release date: ⁨2023-03-13⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox108<br>Firefox – Full support<br>Firefox108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera97<br>Opera – Full support<br>Opera97 (Release date: ⁨2023-03-22⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android111<br>Chrome Android – Full support<br>Chrome Android111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android108<br>Firefox for Android – Full support<br>Firefox for Android108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android75<br>Opera Android – Full support<br>Opera Android75 (Release date: ⁨2023-05-17⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet22<br>Samsung Internet – Full support<br>Samsung Internet22 (Release date: ⁨2023-07-14⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android111<br>WebView Android – Full support<br>WebView Android111 (Release date: ⁨2023-03-01⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2\#see_also)

- [`sin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sin)
- [`cos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cos)
- [`tan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/tan)
- [`asin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/asin)
- [`acos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/acos)
- [`atan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan)
- [Using CSS typed arithmetic](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Using_CSS_typed_arithmetic)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 11, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/atan2/index.md?plain=1 "Folder: ⁨en-us/web/css/atan2⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fatan2&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fatan2%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fatan2%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fatan2%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F11ef719d1a0bd75b1600d39abd6dfbdcd835c1e2%0A*+Document+last+modified%3A+2025-10-11T03%3A06%3A53.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")