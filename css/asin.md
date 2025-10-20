---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/asin
scraped_at: 2025-10-20T03:04:33.508Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/asin#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/asin#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# asin()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2023⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/asin#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fasin&level=high)

The **`asin()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) is a trigonometric function that returns the inverse sine of a number between `-1` and `1`. The function contains a single calculation that returns the number of radians representing an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) between `-90deg` and `90deg`.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#syntax)

cssCopy

```
/* Single <number> values */
transform: rotate(asin(-0.2));
transform: rotate(asin(2 * 0.125));

/* Other values */
transform: rotate(asin(pi / 5));
transform: rotate(asin(e / 3));

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#parameters)

The `asin(number)` function accepts only one value as its parameter.

[`number`](https://developer.mozilla.org/en-US/docs/Web/CSS/asin#number)

A calculation which resolves to a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) between `-1` and `1`.

### [Return value](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#return_value)

The inverse sine of an `number` will always return an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) between `-90deg` and `90deg`.

- If `number` is less than `-1` or greater than `1`, the result is `NaN`.
- If `number` is `0⁻`, the result is `0⁻`.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#formal_syntax)

```
<asin()> =
  asin( <calc-sum> )

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

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#examples)

### [Rotate elements](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#rotate_elements)

The `asin()` function can be used to [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate) elements as it return an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle).

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
  transform: rotate(asin(1));
}
div.box-2 {
  transform: rotate(asin(0.5));
}
div.box-3 {
  transform: rotate(asin(0));
}
div.box-4 {
  transform: rotate(asin(-0.5));
}
div.box-5 {
  transform: rotate(asin(-1));
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 4\<br>\# trig-funcs](https://drafts.csswg.org/css-values/#trig-funcs) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/asin# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/asin.json "File: ⁨css/types/asin.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `asin()` | Chrome – Full support<br>Chrome111<br>Chrome – Full support<br>Chrome111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge111<br>Edge – Full support<br>Edge111 (Release date: ⁨2023-03-13⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox108<br>Firefox – Full support<br>Firefox108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera97<br>Opera – Full support<br>Opera97 (Release date: ⁨2023-03-22⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android111<br>Chrome Android – Full support<br>Chrome Android111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android108<br>Firefox for Android – Full support<br>Firefox for Android108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android75<br>Opera Android – Full support<br>Opera Android75 (Release date: ⁨2023-05-17⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet22<br>Samsung Internet – Full support<br>Samsung Internet22 (Release date: ⁨2023-07-14⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android111<br>WebView Android – Full support<br>WebView Android111 (Release date: ⁨2023-03-01⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/asin\#see_also)

- [`sin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sin)
- [`cos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cos)
- [`tan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/tan)
- [`acos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/acos)
- [`atan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan)
- [`atan2()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/asin/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/asin/index.md?plain=1 "Folder: ⁨en-us/web/css/asin⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fasin&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fasin%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fasin%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fasin%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")