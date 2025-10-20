---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/exp
scraped_at: 2025-10-20T03:07:06.491Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/exp#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/exp#search)

# exp()


Baseline

2023


Newly available

Since ⁨December 2023⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/exp#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fexp&level=low)

The **`exp()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) is an exponential function that takes a number as an argument and returns the mathematical constant `e` raised to the power of the given number.

The mathematical constant [`e`](https://en.wikipedia.org/wiki/E_(mathematical_constant)) is the base of natural logarithms, and is approximately `2.718281828459045`.

The `exp(number)` function contains a calculation which returns the same value as [`pow(e, number)`](https://developer.mozilla.org/en-US/docs/Web/CSS/pow).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#syntax)

css

```
/* A <number> value */
width: calc(100px * exp(-1)); /* 100px * 0.367879441171442 = 36.8px */
width: calc(100px * exp(0)); /* 100px * 1 = 100px */
width: calc(100px * exp(1)); /* 100px * 2.718281828459045 = 271.8px */

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#parameters)

The `exp(number)` function accepts only one value as its parameter.

[`number`](https://developer.mozilla.org/en-US/docs/Web/CSS/exp#number)

A calculation which resolves to a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number). Representing the value to be raised by a power of `e`.

### [Return value](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#return_value)

Returns a non-negative [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) representing enumber, which is the result of calculating `e` raised to the power of `number`.

- If `number` is `-Infinity`, the result is `0`.
- If `number` is `0`, the result is `1`.
- If `number` is `1`, the result is `e` (i.e., `2.718281828459045`).
- If `number` is `Infinity`, the result is `Infinity`.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#formal_syntax)

```
<exp()> =
  exp( <calc-sum> )

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

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#examples)

### [Rotate elements](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#rotate_elements)

The `exp()` function can be used to [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate) elements as it return a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number).

#### HTML

html

```
<div class="box box-1"></div>
<div class="box box-2"></div>
<div class="box box-3"></div>
<div class="box box-4"></div>
<div class="box box-5"></div>

```

#### CSS

```
body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 50px;
}

```

css

```
div.box {
  width: 100px;
  height: 100px;
  background: linear-gradient(orange, red);
}
div.box-1 {
  transform: rotate(calc(1turn * exp(-1))); /* 0.3678794411714423turn */
}
div.box-2 {
  transform: rotate(calc(1turn * exp(-0.75))); /* 0.4723665527410147turn */
}
div.box-3 {
  transform: rotate(calc(1turn * exp(-0.5))); /* 0.6065306597126334turn */
}
div.box-4 {
  transform: rotate(calc(1turn * exp(-0.25))); /* 0.7788007830714049turn */
}
div.box-5 {
  transform: rotate(calc(1turn * exp(0))); /* 1turn */
}

```

#### Result

### [Scale headings by fixed ratio](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#scale_headings_by_fixed_ratio)

The `exp()` function can be useful for strategies like CSS modular scale, which relates all the font-sizes on a page to each other by a fixed ratio.

#### HTML

html

```
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>

```

#### CSS

css

```
h1 {
  font-size: calc(1rem * exp(1.25)); /* 3.4903429574618414rem */
}
h2 {
  font-size: calc(1rem * exp(1)); /* 2.718281828459045rem */
}
h3 {
  font-size: calc(1rem * exp(0.75)); /* 2.117000016612675rem */
}
h4 {
  font-size: calc(1rem * exp(0.5)); /* 1.6487212707001282rem */
}
h5 {
  font-size: calc(1rem * exp(0.25)); /* 1.2840254166877414rem */
}
h6 {
  font-size: calc(1rem * exp(0)); /* 1rem */
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 4\<br>\# exponent-funcs](https://drafts.csswg.org/css-values/#exponent-funcs) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/exp\#see_also)

- [`pow()`](https://developer.mozilla.org/en-US/docs/Web/CSS/pow)
- [`sqrt()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sqrt)
- [`hypot()`](https://developer.mozilla.org/en-US/docs/Web/CSS/hypot)
- [`log()`](https://developer.mozilla.org/en-US/docs/Web/CSS/log)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/exp/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/exp/index.md?plain=1 "Folder: ⁨en-us/web/css/exp⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fexp&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fexp%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fexp%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fexp%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")