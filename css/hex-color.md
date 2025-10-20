---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color
scraped_at: 2025-10-20T02:59:20.518Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fhex-color "Take survey (Opens in a new tab)")

# <hex-color>


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fhex-color&level=high)

The **`<hex-color>`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types) is a notation for describing the _hexadecimal color syntax_ of an [sRGB](https://developer.mozilla.org/en-US/docs/Glossary/RGB) color using its primary color components (red, green, blue) written as hexadecimal numbers, as well as its transparency.

A `<hex-color>` value can be used everywhere where a [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) can be used.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#syntax)

```
#RGB        // The three-value syntax
#RGBA       // The four-value syntax
#RRGGBB     // The six-value syntax
#RRGGBBAA   // The eight-value syntax

```

### [Value](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#value)

[`R` or `RR`](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#r)

The _red_ component of the color, as a case-insensitive hexadecimal number between `0` and `ff` (255). If there is only one number, it is duplicated: `1` means `11`.

[`G` or `GG`](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#g)

The _green_ component of the color, as a case-insensitive hexadecimal number between `0` and `ff` (255). If there is only one number, it is duplicated: `c` means `cc`.

[`B` or `BB`](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#b)

The _blue_ component of the color, as a case-insensitive hexadecimal number between `0` and `ff` (255). If there is only one number, it is duplicated: `9` means `99`.

[`A` or `AA` Optional](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color#a)

The _alpha_ component of the color, indicating its transparency, as a case-insensitive hexadecimal number between `0` and `ff` (255). If there is only one number, it is duplicated: `e` means `ee`. `0`, or `00`, represents a fully transparent color, and `f`, or `ff`, a fully opaque one.

**Note:**
The syntax is case-insensitive: `#00ff00` is the same as `#00FF00`.

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#examples)

### [Hexadecimal hot pink](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#hexadecimal_hot_pink)

This example includes four hot pink squares, with fully opaque or semi-transparent backgrounds created using four different-length case-insensitive hex-color syntaxes.

#### HTML

htmlCopyPlay

```
<div>
  #F09
  <div class="c1"></div>
</div>
<div>
  #f09a
  <div class="c2"></div>
</div>
<div>
  #ff0099
  <div class="c3"></div>
</div>
<div>
  #FF0099AA
  <div class="c4"></div>
</div>

```

#### CSS

The hot pink background colors are created using the three-, four-, six-, and eight-value hex notations, using both uppercase and lowercase letters.

cssCopyPlay

```
body {
  display: flex;
  justify-content: space-evenly;
  font-family: monospace;
}
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

```

cssCopyPlay

```
[class] {
  width: 40px;
  height: 40px;
}
.c1 {
  background: #f09;
}
.c2 {
  background: #f09a;
}
.c3 {
  background: #ff0099;
}
.c4 {
  background: #ff0099aa;
}

```

#### Result

Play

#F09


#f09a


#ff0099


#FF0099AA


## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#specifications)

| Specification |
| --- |
| [CSS Color Module Level 4\<br>\# hex-notation](https://drafts.csswg.org/css-color/#hex-notation) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/color.json "File: ⁨css/types/color.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| RGB hexadecimal notation ( `#RRGGBB`, `#RGB`, …) | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera3.5<br>Opera – Full support<br>Opera3.5 (Release date: ⁨1998-11-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| RGBA hexadecimal notation ( `#RRGGBBAA`, `#RGBA`) | Chrome – Full support<br>Chrome62<br>Chrome – Full support<br>Chrome62 (Release date: ⁨2017-10-17⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox49<br>Firefox – Full support<br>Firefox49 (Release date: ⁨2016-09-20⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera49<br>Opera – Full support<br>Opera49 (Release date: ⁨2017-11-08⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10<br>Safari – Full support<br>Safari10 (Release date: ⁨2016-09-20⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android62<br>Chrome Android – Full support<br>Chrome Android62 (Release date: ⁨2017-10-24⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android49<br>Firefox for Android – Full support<br>Firefox for Android49 (Release date: ⁨2016-09-20⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android47<br>Opera Android – Full support<br>Opera Android47 (Release date: ⁨2018-07-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9.3<br>Safari on iOS – Full support<br>Safari on iOS9.3 (Release date: ⁨2016-03-21⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android62<br>WebView Android – Full support<br>WebView Android62 (Release date: ⁨2017-10-24⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9.3<br>WebView on iOS – Full support<br>WebView on iOS9.3 (Release date: ⁨2016-03-21⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color\#see_also)

- [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) data type
- [`<named-color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color) data-type
- [`rgb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb) color function
- [CSS color](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/hex-color/index.md?plain=1 "Folder: ⁨en-us/web/css/hex-color⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fhex-color&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fhex-color%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fhex-color%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fhex-color%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")