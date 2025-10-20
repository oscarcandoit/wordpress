---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x
scraped_at: 2025-10-20T02:59:42.159Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# overscroll-behavior-x


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨September 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior-x&level=high)

The **`overscroll-behavior-x`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the browser's behavior when the horizontal boundary of a scrolling area is reached.

See [`overscroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior) for a full explanation.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#syntax)

cssCopy

```
/* Keyword values */
overscroll-behavior-x: auto; /* default */
overscroll-behavior-x: contain;
overscroll-behavior-x: none;

/* Global values */
overscroll-behavior-x: inherit;
overscroll-behavior-x: initial;
overscroll-behavior-x: revert;
overscroll-behavior-x: revert-layer;
overscroll-behavior-x: unset;

```

The `overscroll-behavior-x` property is specified as a keyword chosen from the list of values below.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#auto)

The default scroll overflow behavior occurs as normal.

[`contain`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#contain)

Default scroll overflow behavior (e.g., "bounce" effects) is observed inside the element where this value is set. However, no [scroll chaining](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_chaining) occurs on neighboring scrolling areas; the underlying elements will not scroll. The `contain` value disables native browser navigation, including the vertical pull-to-refresh gesture and horizontal swipe navigation.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x#none)

No scroll chaining occurs to neighboring scrolling areas, and default scroll overflow behavior is prevented.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | non-replaced block-level elements and non-replaced inline-block elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#formal_syntax)

```
overscroll-behavior-x =
  contain   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#examples)

### [Preventing an underlying element from scrolling horizontally](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#preventing_an_underlying_element_from_scrolling_horizontally)

In our [overscroll-behavior-x example](https://mdn.github.io/css-examples/overscroll-behavior/overscroll-behavior-x) (see [source code](https://github.com/mdn/css-examples/blob/main/overscroll-behavior/overscroll-behavior-x.html) also), we have two block-level boxes, one inside the other. The outer box has a large [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) set on it so the page will scroll horizontally. The inner box has a small width (and [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)) set on it so it sits comfortably inside the viewport, but its content is given a large `width` so it will scroll horizontally.

By default, when the inner box is scrolled and a scroll boundary is reached, the whole page will begin to scroll, which is probably not what we want. To avoid this, you can set `overscroll-behavior-x: contain` on the inner box:

cssCopy

```
main > div {
  height: 300px;
  width: 500px;
  overflow: auto;
  position: relative;
  top: 100px;
  left: 100px;
  overscroll-behavior-x: contain;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#specifications)

| Specification |
| --- |
| [CSS Overscroll Behavior Module Level 1\<br>\# overscroll-behavior-longhands-physical](https://drafts.csswg.org/css-overscroll/#overscroll-behavior-longhands-physical) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/overscroll-behavior-x.json "File: ⁨css/properties/overscroll-behavior-x.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `overscroll-behavior-x` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge18<br>Edge – Full support<br>Edge18 (Release date: ⁨2018-10-02⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `auto` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge18<br>Edge – Full support<br>Edge18 (Release date: ⁨2018-10-02⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `contain` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge18<br>Edge – Full support<br>Edge18 (Release date: ⁨2018-10-02⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>more<br>Edge – Partial support<br>Edge18 – 18 (Release date: ⁨2018-10-02⁩)<br> <br>footnotePartial supportfootnoteThe `none` value incorrectly behaves as `contain` (allowing for the elastic bounce effect).<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x\#see_also)

- [`overscroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior)
- [`overscroll-behavior-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y)
- [`overscroll-behavior-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-inline)
- [`overscroll-behavior-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block)
- [CSS overscroll behavior](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overscroll-behavior-x/index.md?plain=1 "Folder: ⁨en-us/web/css/overscroll-behavior-x⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior-x&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverscroll-behavior-x%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior-x%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverscroll-behavior-x%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")