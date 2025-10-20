---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units
scraped_at: 2025-10-20T02:58:58.492Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS values and units

Every CSS declaration consists of a property/value pair. The value can take various forms depending on the property, such as a single integer, keyword, function, or a combination of different items; some values have units, while others do not. Every property also accepts the CSS-wide values. The CSS values and units module defines the data types — values and units — that CSS properties accept. This module also defines the CSS value definition syntax, or formal grammar, used to define the set of valid values for every CSS property and function.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#properties)

- [`interpolate-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/interpolate-size)

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#functions)

- [`abs()`](https://developer.mozilla.org/en-US/docs/Web/CSS/abs)
- [`acos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/acos)
- [`asin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/asin)
- [`atan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan)
- [`atan2()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2)
- [`attr()`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr)
- [`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)
- [`calc-size()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-size)
- [`clamp()`](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)
- [`cos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cos)
- [`exp()`](https://developer.mozilla.org/en-US/docs/Web/CSS/exp)
- [`hypot()`](https://developer.mozilla.org/en-US/docs/Web/CSS/hypot)
- [`<ident()>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ident)
- [`if()`](https://developer.mozilla.org/en-US/docs/Web/CSS/if)
- [`inherit()`](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit)
- [`log()`](https://developer.mozilla.org/en-US/docs/Web/CSS/log)
- [`max()`](https://developer.mozilla.org/en-US/docs/Web/CSS/max)
- [`min()`](https://developer.mozilla.org/en-US/docs/Web/CSS/min)
- [`mod()`](https://developer.mozilla.org/en-US/docs/Web/CSS/mod)
- [`pow()`](https://developer.mozilla.org/en-US/docs/Web/CSS/pow)
- [`progress()`](https://developer.mozilla.org/en-US/docs/Web/CSS/progress)
- [`rem()`](https://developer.mozilla.org/en-US/docs/Web/CSS/rem)
- [`round()`](https://developer.mozilla.org/en-US/docs/Web/CSS/round)
- [`sibling-count()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sibling-count)
- [`sibling-index()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sibling-index)
- [`sign()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sign)
- [`sin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sin)
- [`sqrt()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sqrt)
- [`tan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/tan)
- [`url()`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function)

The CSS values and units module also introduces the `calc-mix()`, `crossorigin()`, `first-valid()`, `integrity()`, `random()`, `random-item()`, `referrerpolicy()`, `src()`, `type()`, and `toggle()` functions. Currently, no browsers support these features.

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#data_types)

- [`<angle-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle-percentage)
- [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle)
- [`<animation-timeline>`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline)
- [`<attr-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr#attr-name)
- [`<attr-type>`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr#attr-type)
- [`<calc-keyword>`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-keyword) ( `e`, `pi`, `infinity`, [NaN](https://developer.mozilla.org/en-US/docs/Glossary/NaN))
- [`<calc-size-basis>`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-size#calc-size-basis)
- [`<calc-sum>`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-sum)
- [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident)
- [`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident)
- [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension)
- [`<easing-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)
- [`<first-valid()>`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`<ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ident)
- [`<integer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)
- [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage)
- [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)
- [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number)
- [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)
- [`<position>`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [`<ratio>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ratio)
- [`<resolution>`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution)
- [`<rounding-strategy>`](https://developer.mozilla.org/en-US/docs/Web/CSS/round#rounding-strategy) ( `down`, `up`, `to-zero`)
- [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string)
- [`<syntax>`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax)
- [`<time-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/time-percentage)
- [`<time>`](https://developer.mozilla.org/en-US/docs/Web/CSS/time)
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)
- [`<url-modifier>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_function#url-modifier)
- [`<view-timeline-name>`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name)

The CSS values and units module also introduces the [`<frequency>`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency) and [`<frequency-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency-percentage) data types. Currently, no browsers support these features.

#### Units

- [`%` (percentage)](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)
- [`cap`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#cap)
- [`ch`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#ch)
- [`cm`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#cm)
- [`deg`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle#deg)
- [`dpcm`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution#dpcm)
- [`dpi`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution#dpi)
- [`dppx`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution#dppx)
- [`dvb`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vb)
- [`dvh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vh)
- [`dvi`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vi)
- [`dvmax`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmax)
- [`dvmin`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmin)
- [`dvw`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vw)
- [`em`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#em)
- [`ex`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#ex)
- [`grad`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle#grad)
- [`Hz`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency#hz)
- [`ic`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#ic)
- [`in`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#in)
- [`kHz`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency#khz)
- [`lh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#lh)
- [`lvb`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vb)
- [`lvh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vh)
- [`lvi`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vi)
- [`lvmax`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmax)
- [`lvmin`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmin)
- [`lvw`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vw)
- [`mm`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#mm)
- [`ms`](https://developer.mozilla.org/en-US/docs/Web/CSS/time#ms)
- [`pc`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#pc)
- [`pt`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#pt)
- [`px`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#px)
- [`Q`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#q)
- [`rad`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle#rad)
- [`rcap`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#rcap)
- [`rch`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#rch)
- [`rem`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#rem)
- [`rex`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#rex)
- [`ric`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#ric)
- [`rlh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#rlh)
- [`s`](https://developer.mozilla.org/en-US/docs/Web/CSS/time#s)
- [`svb`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vb)
- [`svh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vh)
- [`svi`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vi)
- [`svmax`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmax)
- [`svmin`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmin)
- [`svw`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vw)
- [`turn`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle#turn)
- [`vb`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vb)
- [`vh`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vh)
- [`vi`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vi)
- [`vmax`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmax)
- [`vmin`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vmin)
- [`vw`](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vw)
- [`x`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution#x)

[Flex units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#flex_units) ( `fr`) and [container units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#container_units) ( `cqb`, `cqh`, `cqi`, `cqmax`, `cqmin`, `cqw`) are defined in the [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) and [CSS conditional rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules) modules, respectively.

#### Unit categorizations

- [Absolute length units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#absolute_length_units) ( `cm`, `in`, `mm`, `pc`, `pt`, `px`, `Q`)
- [Angle units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#angle_units) ( `deg`, `grad`, `rad`, `turn`)
- [Default viewport units](https://developer.mozilla.org/en-US/docs/Web/CSS/length#default_viewport_units) ( `vb` , `vh`, `vi` , `vmax`, `vmin`, `vw`)
- [Dynamic viewport units](https://developer.mozilla.org/en-US/docs/Web/CSS/length#dynamic_viewport_units) ( `dvb`, `dvh`, `dvi`, `dvmax`, `dvmin`, `dvw`)
- [Frequency units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#frequency_units) ( `Hz`, `kHz`)
- [Large viewport-percentage units](https://developer.mozilla.org/en-US/docs/Web/CSS/length#large_viewport_units) ( `lvb`, `lvh`, `lvi`, `lvmax`, `lvmin`, `lvw`)
- [Local font-relative length units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#local_font-relative_lengths) ( `cap`, `ch`, `em`, `ex`, `ic`, `lh`)
- [Physical units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#absolute_length_units) ( `cm`, `in`, `mm`, `pc`, `pt`, `Q`)
- [Relative length units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types) ( `cap`, `ch`, `em`, `ex`, `ic`, `lh`, `rem`, `rlh`, `vb`, `vh`, `vi`, `vmax`, `vmin`, `vw`)
- [Resolution units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#resolution_units) ( `dpcm`, `dpi` , `dppx`, `x`)
- [Root font-relative length units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#root_font-relative_lengths) ( `rcap`, `rch`, `rem`, `rex`, `ric`, `rlh`)
- [Small viewport-percentage unit](https://developer.mozilla.org/en-US/docs/Web/CSS/length#small_viewport_units) ( `svb`, `svh`, `svi`, `svmax`, `svmin`, `svw`)
- [Time units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#time_units) ( `ms`, `s`)
- [Viewport units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#viewport_units) ( `dvh`, `dvw`, `lvh`, `lvw`, `svh`, `svw`, `vb` , `vh`, `vi` , `vmax`, `vmin`, `vw`)
- [Visual angle unit](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#absolute_length_units) ( `px`)

### [Key concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#key_concepts)

- [Advance measure](https://developer.mozilla.org/en-US/docs/Glossary/Advance_measure)
- [Bracketed range notation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#bracketed_range_notation_minmax)
- [Component value combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#component_value_combinators)
- [CSS-wide keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types#css-wide_keywords)
- [Device pixel](https://developer.mozilla.org/en-US/docs/Glossary/Device_pixel)
- [Functional notation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions)
- [Identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier)
- [Interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
- [Keyword](https://developer.mozilla.org/en-US/docs/Glossary/Keyword)
- [Math function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Using_CSS_math_functions)
- [Numeric data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types)
- [Origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin)
- [Pixel](https://developer.mozilla.org/en-US/docs/Glossary/Pixel)
- [Textual data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Textual_data_types)
- [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL)
- [Value definition syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#guides)

[CSS data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types)

Introduction to CSS data types that define typical values accepted by CSS properties and functions.

[Numeric data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types)

Overview of the numeric data types, including integers, numbers, percentages, and dimensions, along with relative and absolute dimensions, angles, and time units.

[Textual data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Textual_data_types)

Overview of the textual data types, including pre-defined keyword values, global CSS keyword values, and URLs.

[CSS value functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions)

Overview of the CSS statements that invoke special data processing or calculations to return a CSS value for a CSS property.

[Using CSS math functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Using_CSS_math_functions)

The CSS math functions that allow a property value to be written as a mathematical expression.

[Value definition syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax)

The formal grammar used to define the set of valid values for CSS properties and functions.

[Using CSS typed arithmetic](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Using_CSS_typed_arithmetic)

An explanation of CSS typed arithmetic behavior and use cases enabled by it.

[Learn: Values and units](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Values_and_units)

A look at some of the most frequently used value types, what they are, and how they work.

## [Related](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#related)

- [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade) module
  - [`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial)
  - [`inherit`](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit)
  - [`revert`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert)
  - [`revert-layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert-layer)
  - [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset)
  - [`all`](https://developer.mozilla.org/en-US/docs/Web/CSS/all)
- [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) module
  - [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value)
  - [Flex units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#flex_units) ( `fr`)
- [CSS conditional rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules) module
  - [Container units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Numeric_data_types#container_units) ( `cqb`, `cqh`, `cqi`, `cqmax`, `cqmin`, `cqw`)
- [CSS colors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors) module
  - [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)
  - [`<system-color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/system-color)
  - [`color-mix()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix)
- [CSS images](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images) module
  - [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image)
  - [`<gradient>`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 3](https://drafts.csswg.org/css-values-3/) |
| [CSS Values and Units Module Level 4](https://drafts.csswg.org/css-values-4/) |
| [CSS Values and Units Module Level 5](https://drafts.csswg.org/css-values-5/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units\#see_also)

- [CSS syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax) module
- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 11, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_values_and_units/index.md?plain=1 "Folder: ⁨en-us/web/css/css_values_and_units⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_values_and_units&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_values_and_units%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_values_and_units%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_values_and_units%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F11ef719d1a0bd75b1600d39abd6dfbdcd835c1e2%0A*+Document+last+modified%3A+2025-10-11T03%3A06%3A53.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")