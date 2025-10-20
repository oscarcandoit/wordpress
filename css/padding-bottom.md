---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom
scraped_at: 2025-10-20T03:09:30.828Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# padding-bottom


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fpadding-bottom&level=high)

The **`padding-bottom`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the height of the [padding area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#padding_area) on the bottom of an element.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#try_it)

- padding-bottom: 1em;

- padding-bottom: 10%;

- padding-bottom: 20px;

- padding-bottom: 1ch;

- padding-bottom: 0;


cssCopy

```
padding-bottom: 1em;

```

cssCopy

```
padding-bottom: 10%;

```

cssCopy

```
padding-bottom: 20px;

```

cssCopy

```
padding-bottom: 1ch;

```

cssCopy

```
padding-bottom: 0;

```

htmlCopy

```
<section id="default-example">
  <div class="transition-all" id="example-element">
    <div class="box">
      Far out in the uncharted backwaters of the unfashionable end of the
      western spiral arm of the Galaxy lies a small unregarded yellow sun.
    </div>
  </div>
</section>

```

cssCopy

```
#example-element {
  border: 10px solid #ffc129;
  overflow: hidden;
  text-align: left;
}

.box {
  border: dashed 1px;
}

```

An element's padding area is the space between its content and its border.

![The effect of the CSS padding-bottom property on the element box](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom/padding-bottom.svg)

**Note:**
The [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) property can be used to set paddings on all four sides of an element with a single declaration.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#syntax)

cssCopy

```
/* <length> values */
padding-bottom: 0.5em;
padding-bottom: 0;
padding-bottom: 2cm;

/* <percentage> value */
padding-bottom: 10%;

/* Global values */
padding-bottom: inherit;
padding-bottom: initial;
padding-bottom: revert;
padding-bottom: revert-layer;
padding-bottom: unset;

```

The `padding-bottom` property is specified as a single value chosen from the list below. Unlike margins, negative values are not allowed for padding.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#values)

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

The size of the padding as a percentage, relative to the inline size ( _width_ in a horizontal language, defined by [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)) of the [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Containing_block). Must be nonnegative.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `0` |
| Applies to | all elements, except `table-row-group`, `table-header-group`, `table-footer-group`, `table-row`, `table-column-group` and `table-column`. It also applies to [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter) and [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line). |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | refer to the width of the containing block |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | the percentage as specified or the absolute length |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers.") |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#formal_syntax)

```
padding-bottom =
  <length-percentage [0,∞]>

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#examples)

### [Setting padding bottom with pixels and percentages](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#setting_padding_bottom_with_pixels_and_percentages)

cssCopy

```
.content {
  padding-bottom: 5%;
}
.side-box {
  padding-bottom: 10px;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#specifications)

| Specification |
| --- |
| [CSS Box Model Module Level 3\<br>\# padding-physical](https://drafts.csswg.org/css-box/#padding-physical) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/padding-bottom.json "File: ⁨css/properties/padding-bottom.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `padding-bottom` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera3.5<br>Opera – Full support<br>Opera3.5 (Release date: ⁨1998-11-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom\#see_also)

- [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top), [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right), and [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left)
- [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) shorthand
- [`padding-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-start), [`padding-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end), [`padding-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start), and [`padding-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end)
- [`padding-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block) and [`padding-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline) shorthands
- [Introduction to the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) guide
- [CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/padding-bottom/index.md?plain=1 "Folder: ⁨en-us/web/css/padding-bottom⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fpadding-bottom&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fpadding-bottom%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fpadding-bottom%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fpadding-bottom%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")