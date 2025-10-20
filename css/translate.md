---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/translate
scraped_at: 2025-10-20T03:06:05.225Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/translate#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/translate#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# translate


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨August 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/translate#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftranslate&level=high)

The **`translate`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows you to specify translation transforms individually and independently of the [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` value.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#try_it)

- translate: none;

- translate: 40px;

- translate: 50% -40%;

- translate: 20px 4rem;

- translate: 20px 4rem 150px;


1

2

3

4

cssCopy

```
translate: none;

```

cssCopy

```
translate: 40px;

```

cssCopy

```
translate: 50% -40%;

```

cssCopy

```
translate: 20px 4rem;

```

cssCopy

```
translate: 20px 4rem 150px;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    <div class="face front">1</div>
    <div class="face back">2</div>
    <div class="face right">3</div>
    <div class="face left">4</div>
    <div class="face top">5</div>
    <div class="face bottom">6</div>
  </div>
</section>

```

cssCopy

```
#default-example {
  background: linear-gradient(skyblue, khaki);
  perspective: 800px;
  perspective-origin: 150% 150%;
}

#example-element {
  width: 100px;
  height: 100px;
  perspective: 550px;
  transform-style: preserve-3d;
}

.face {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  position: absolute;
  backface-visibility: inherit;
  font-size: 60px;
  color: white;
}

.front {
  background: rgb(90 90 90 / 0.7);
  transform: translateZ(50px);
}

.back {
  background: rgb(0 210 0 / 0.7);
  transform: rotateY(180deg) translateZ(50px);
}

.right {
  background: rgb(210 0 0 / 0.7);
  transform: rotateY(90deg) translateZ(50px);
}

.left {
  background: rgb(0 0 210 / 0.7);
  transform: rotateY(-90deg) translateZ(50px);
}

.top {
  background: rgb(210 210 0 / 0.7);
  transform: rotateX(90deg) translateZ(50px);
}

.bottom {
  background: rgb(210 0 210 / 0.7);
  transform: rotateX(-90deg) translateZ(50px);
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#syntax)

cssCopy

```
/* Keyword values */
translate: none;

/* Single values */
translate: 100px;
translate: 50%;

/* Two values */
translate: 100px 200px;
translate: 50% 105px;

/* Three values */
translate: 50% 105px 5rem;

/* Global values */
translate: inherit;
translate: initial;
translate: revert;
translate: revert-layer;
translate: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#values)

Single [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value

A [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) that specifies a translation along the X-axis. Equivalent to a `translate()` (2D translation) function with a single value specified.

Two [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) values

Two [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) that specify the X and Y axis translation values (respectively) of a 2D translation. Equivalent to a `translate()` (2D translation) function with two values specified.

[Three values](https://developer.mozilla.org/en-US/docs/Web/CSS/translate#three_values)

Two [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) and single [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) values that specify the X, Y, and Z axis translation values (respectively) of a 3D translation. Equivalent to a `translate3d()` (3D translation) function.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/translate#none)

Specifies that no translation should be applied.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `none` |
| Applies to | transformable elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | refer to the size of bounding box |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, but with relative lengths converted into absolute lengths |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a transform |
| Creates [stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context) | yes |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#formal_syntax)

```
translate =
  none                                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#examples)

### [Translating an element on hover](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#translating_an_element_on_hover)

This example shows how to use the `translate` property to move an element in three axes.
The first box is moved along the X axis and the second box is moved along the X and Y axes.
The third box is moved along the X, Y and Z axes and has the appearance of moving toward the viewer because of the addition of [`perspective`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective) to the parent element.

#### HTML

htmlCopyPlay

```
<div class="wrapper">
  <div id="box1">translate X</div>
  <div id="box2">translate X,Y</div>
  <div id="box3">translate X,Y,Z</div>
</div>

```

#### CSS

cssCopyPlay

```
.wrapper {
  perspective: 100px;
  display: inline-flex;
  gap: 1em;
}
.wrapper > div {
  width: 7em;
  line-height: 7em;
  text-align: center;
  transition: 0.5s ease-in-out;
  border: 3px dotted;
}
#box1:hover {
  translate: 20px;
}

#box2:hover {
  translate: 20px 20px;
}

#box3:hover {
  translate: 5px 5px 30px;
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#specifications)

| Specification |
| --- |
| [CSS Transforms Module Level 2\<br>\# individual-transforms](https://drafts.csswg.org/css-transforms-2/#individual-transforms) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/translate# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/translate.json "File: ⁨css/properties/translate.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `translate` | Chrome – Full support<br>Chrome104<br>Chrome – Full support<br>Chrome104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge104<br>Edge – Full support<br>Edge104 (Release date: ⁨2022-08-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox72<br>Firefox – Full support<br>Firefox72 (Release date: ⁨2020-01-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera90<br>Opera – Full support<br>Opera90 (Release date: ⁨2022-08-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari14.1<br>Safari – Full support<br>Safari14.1 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android104<br>Chrome Android – Full support<br>Chrome Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android71<br>Opera Android – Full support<br>Opera Android71 (Release date: ⁨2022-09-16⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS14.5<br>Safari on iOS – Full support<br>Safari on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet20<br>Samsung Internet – Full support<br>Samsung Internet20 (Release date: ⁨2023-02-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android104<br>WebView Android – Full support<br>WebView Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS14.5<br>WebView on iOS – Full support<br>WebView on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome104<br>Chrome – Full support<br>Chrome104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge104<br>Edge – Full support<br>Edge104 (Release date: ⁨2022-08-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox72<br>Firefox – Full support<br>Firefox72 (Release date: ⁨2020-01-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera90<br>Opera – Full support<br>Opera90 (Release date: ⁨2022-08-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari14.1<br>Safari – Full support<br>Safari14.1 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android104<br>Chrome Android – Full support<br>Chrome Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android71<br>Opera Android – Full support<br>Opera Android71 (Release date: ⁨2022-09-16⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS14.5<br>Safari on iOS – Full support<br>Safari on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet20<br>Samsung Internet – Full support<br>Samsung Internet20 (Release date: ⁨2023-02-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android104<br>WebView Android – Full support<br>WebView Android104 (Release date: ⁨2022-08-02⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS14.5<br>WebView on iOS – Full support<br>WebView on iOS14.5 (Release date: ⁨2021-04-26⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/translate\#see_also)

- [`scale`](https://developer.mozilla.org/en-US/docs/Web/CSS/scale)
- [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/rotate)
- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

Note: skew is not an independent transform value

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/translate/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/translate/index.md?plain=1 "Folder: ⁨en-us/web/css/translate⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftranslate&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftranslate%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftranslate%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftranslate%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")