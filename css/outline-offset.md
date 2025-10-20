---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset
scraped_at: 2025-10-20T03:11:24.335Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# outline-offset


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨April 2017⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline-offset&level=high)

The **`outline-offset`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the amount of space between an [outline](https://developer.mozilla.org/en-US/docs/Web/CSS/outline) and the edge or border of an element.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#try_it)

- outline-offset: 4px;

- outline-offset: 0.6rem;

- outline-offset: 12px;



outline: 5pxdashedblue;


This is a box with an outline around it.


cssCopy

```
outline-offset: 4px;

```

cssCopy

```
outline-offset: 0.6rem;

```

cssCopy

```
outline-offset: 12px;
outline: 5px dashed blue;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box with an outline around it.
  </div>
</section>

```

cssCopy

```
#example-element {
  border: 2px solid crimson;
  outline: 0.75em solid;
  padding: 0.75em;
  width: 80%;
  height: 100px;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#syntax)

cssCopy

```
/* <length> values */
outline-offset: 3px;
outline-offset: 0.2em;

/* Global values */
outline-offset: inherit;
outline-offset: initial;
outline-offset: revert;
outline-offset: revert-layer;
outline-offset: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#values)

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

The width of the space between the element and its outline. A negative value places the outline inside the element. A value of `0` places the outline so that there is no space between it and the element.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#description)

An outline is a line that is drawn around an element, outside the border edge. The space between an element and its outline is transparent. In other words, it is the same as the parent element's background.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `0` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, but with relative lengths converted into absolute lengths |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers.") |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#formal_syntax)

```
outline-offset =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#examples)

### [Setting outline offset in pixels](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#setting_outline_offset_in_pixels)

#### HTML

htmlCopyPlay

```
<p>Gallia est omnis divisa in partes tres.</p>

```

#### CSS

cssCopyPlay

```
p {
  outline: 1px dashed red;
  outline-offset: 10px;
  background: yellow;
  border: 1px solid blue;
  margin: 15px;
}

```

#### Result

Play

Gallia est omnis divisa in partes tres.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#specifications)

| Specification |
| --- |
| [CSS Basic User Interface Module Level 4\<br>\# outline-offset](https://drafts.csswg.org/css-ui/#outline-offset) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/outline-offset.json "File: ⁨css/properties/outline-offset.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `outline-offset` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge15<br>Edge – Full support<br>Edge15 (Release date: ⁨2017-04-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1.5<br>footnote<br>Firefox – Full support<br>Firefox1.5 (Release date: ⁨2005-11-29⁩)<br> <br>footnote<br>footnoteBefore Firefox 88, an outline does not follow the shape of `border-radius`. | Opera – Full support<br>Opera9.5<br>Opera – Full support<br>Opera9.5 (Release date: ⁨2008-06-12⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1.2<br>Safari – Full support<br>Safari1.2 (Release date: ⁨2004-02-02⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>footnote<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnote<br>footnoteBefore Firefox for Android 88, an outline does not follow the shape of `border-radius`. | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android37<br>WebView Android – Full support<br>WebView Android37 (Release date: ⁨2014-09-03⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

See implementation notes.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset\#see_also)

- [`outline`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width)
- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style)
- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/outline-offset/index.md?plain=1 "Folder: ⁨en-us/web/css/outline-offset⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline-offset&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foutline-offset%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline-offset%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foutline-offset%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")