---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/sin
scraped_at: 2025-10-20T03:05:37.596Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/sin#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/sin#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# sin()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2023⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/sin#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fsin&level=high)

The **`sin()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) is a trigonometric function that returns the sine of a number, which is a value between `-1` and `1`. The function contains a single calculation that must resolve to either a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) or an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) by interpreting the result of the argument as radians. That is, `sin(45deg)`, `sin(0.125turn)`, and `sin(3.14159 / 4)` all represent the same value, approximately `0.707`.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#try_it)

- transform: translateX(calc(cos(0deg) \\* 140px))



translateY(calc(sin(0deg) \\* -140px));

- transform: translateX(calc(cos(90deg) \\* 140px))



translateY(calc(sin(90deg) \\* -140px));

- transform: translateX(calc(cos(135deg) \\* 140px))



translateY(calc(sin(135deg) \\* -140px));

- transform: translateX(calc(cos(180deg) \\* 140px))



translateY(calc(sin(180deg) \\* -140px));

- transform: translateX(calc(cos(-45deg) \\* 140px))



translateY(calc(sin(-45deg) \\* -140px));


cssCopy

```
transform: translateX(calc(cos(0deg) * 140px))
  translateY(calc(sin(0deg) * -140px));

```

cssCopy

```
transform: translateX(calc(cos(90deg) * 140px))
  translateY(calc(sin(90deg) * -140px));

```

cssCopy

```
transform: translateX(calc(cos(135deg) * 140px))
  translateY(calc(sin(135deg) * -140px));

```

cssCopy

```
transform: translateX(calc(cos(180deg) * 140px))
  translateY(calc(sin(180deg) * -140px));

```

cssCopy

```
transform: translateX(calc(cos(-45deg) * 140px))
  translateY(calc(sin(-45deg) * -140px));

```

htmlCopy

```
<div class="circle">
  <span class="dot" id="example-element"></span>
</div>

```

cssCopy

```
:root {
  --radius: 140px;
  --dot-size: 10px;
}
.circle {
  display: grid;
  place-content: center;
  margin: 0 auto;
  width: calc(var(--radius) * 2);
  aspect-ratio: 1;
  border-radius: 50%;
  border: 2px solid #666666;
  background-image:
    radial-gradient(black var(--dot-size), transparent var(--dot-size)),
    linear-gradient(135deg, blue, deepskyblue, lightgreen, lavender, honeydew);
}
.dot {
  display: block;
  width: var(--dot-size);
  aspect-ratio: 1;
  border-radius: 50%;
  border: 2px solid #666666;
  background-color: #ff6666;
  transform: translateX(calc(cos(0deg) * var(--radius)))
    translateY(calc(sin(0deg) * var(--radius) * -1));
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#syntax)

cssCopy

```
/* Single <angle> values */
width: calc(100px * sin(45deg));
width: calc(100px * sin(0.25turn));
width: calc(100px * sin(1.0471967rad));

/* Single <number> values */
width: calc(100px * sin(63.673));
width: calc(100px * sin(2 * 0.125));

/* Other values */
width: calc(100px * sin(pi / 2));
width: calc(100px * sin(e / 4));

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#parameters)

The `sin(angle)` function accepts only one value as its parameter.

[`angle`](https://developer.mozilla.org/en-US/docs/Web/CSS/sin#angle)

A calculation which resolves to a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) or an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle). When specifying unitless numbers they are interpreted as a number of radians, representing an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle)

### [Return value](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#return_value)

The sine of an `angle` will always return a number between `−1` and `1`.

- If `angle` is `infinity`, `-infinity`, or `NaN`, the result is `NaN`.
- If `angle` is `0⁻`, the result is `0⁻`.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#formal_syntax)

```
<sin()> =
  sin( <calc-sum> )

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

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#examples)

### [Changing box sizes](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#changing_box_sizes)

In this example, `sin(30deg)` will return `0.5`, making the box have a `50px` width and a `50px` height.

cssCopy

```
div {
  background-color: red;
  width: calc(sin(30deg) * 100px);
  height: calc(sin(30deg) * 100px);
}

```

### [Controlling animation duration](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#controlling_animation_duration)

Another use case is to control the [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), reducing the duration based on the sine value. In this case, the animation duration will be `1s`.

cssCopy

```
div {
  animation-name: myAnimation;
  animation-duration: calc(sin(0.25turn) * 1s);
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 4\<br>\# trig-funcs](https://drafts.csswg.org/css-values/#trig-funcs) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/sin# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/sin.json "File: ⁨css/types/sin.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `sin()` | Chrome – Full support<br>Chrome111<br>Chrome – Full support<br>Chrome111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge111<br>Edge – Full support<br>Edge111 (Release date: ⁨2023-03-13⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox108<br>Firefox – Full support<br>Firefox108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera97<br>Opera – Full support<br>Opera97 (Release date: ⁨2023-03-22⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android111<br>Chrome Android – Full support<br>Chrome Android111 (Release date: ⁨2023-03-07⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android108<br>Firefox for Android – Full support<br>Firefox for Android108 (Release date: ⁨2022-12-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android75<br>Opera Android – Full support<br>Opera Android75 (Release date: ⁨2023-05-17⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet22<br>Samsung Internet – Full support<br>Samsung Internet22 (Release date: ⁨2023-07-14⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android111<br>WebView Android – Full support<br>WebView Android111 (Release date: ⁨2023-03-01⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/sin\#see_also)

- [`cos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cos)
- [`tan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/tan)
- [`asin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/asin)
- [`acos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/acos)
- [`atan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan)
- [`atan2()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/sin/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/sin/index.md?plain=1 "Folder: ⁨en-us/web/css/sin⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fsin&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fsin%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fsin%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fsin%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")