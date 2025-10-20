---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration
scraped_at: 2025-10-20T03:13:13.300Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# text-decoration


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-decoration&level=high)

The **`text-decoration`** [shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the appearance of decorative lines on text. It is a shorthand for [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line), [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color), [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style), and the newer [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness) property.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#try_it)

- text-decoration: underline;

- text-decoration: underlinedotted;

- text-decoration: underlinedottedred;

- text-decoration: greenwavyunderline;

- text-decoration: underlineoverline #ff3028;


cssCopy

```
text-decoration: underline;

```

cssCopy

```
text-decoration: underline dotted;

```

cssCopy

```
text-decoration: underline dotted red;

```

cssCopy

```
text-decoration: green wavy underline;

```

cssCopy

```
text-decoration: underline overline #ff3028;

```

htmlCopy

```
<section id="default-example">
  <p>
    I'd far rather be
    <span class="transition-all" id="example-element">happy than right</span>
    any day.
  </p>
</section>

```

cssCopy

```
p {
  font: 1.5em sans-serif;
}

```

Text decorations are drawn across descendant text elements. This means that if an element specifies a text decoration, then a child element can't remove the decoration. For example, in the markup `<p>This text has <em>some emphasized words</em> in it.</p>`, the style rule `p { text-decoration: underline; }` would cause the entire paragraph to be underlined. The style rule `em { text-decoration: none; }` would not cause any change; the entire paragraph would still be underlined. However, the rule `em { text-decoration: overline; }` would cause a second decoration to appear on "some emphasized words".

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)
- [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line)
- [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style)
- [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#syntax)

cssCopy

```
text-decoration: underline;
text-decoration: overline red;
text-decoration: none;

/* Global values */
text-decoration: inherit;
text-decoration: initial;
text-decoration: revert;
text-decoration: revert-layer;
text-decoration: unset;

```

The `text-decoration` property is specified as one or more space-separated values representing the various longhand text-decoration properties.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#values)

[`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line)

Sets the kind of decoration used, such as `underline` or `line-through`.

[`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)

Sets the color of the decoration.

[`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style)

Sets the style of the line used for the decoration, such as `solid`, `wavy`, or `dashed`.

[`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness)

Sets the thickness of the line used for the decoration.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color): `currentcolor`<br>- [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style): `solid`<br>- [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line): `none` |
| Applies to | all elements. It also applies to [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter) and [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line). |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line): as specified<br>- [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style): as specified<br>- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color): computed color<br>- [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness): as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color): a [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#interpolation "Values of the <color> CSS data type are interpolated on each of their red, green, blue components, each handled as a real, floating-point number. Note that interpolation of colors happens in the alpha-premultiplied sRGBA color space to prevent unexpected grey colors to appear.")<br>- [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style): discrete<br>- [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line): discrete<br>- [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness): by computed value type |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#formal_syntax)

```
text-decoration =
  [<'text-decoration-line'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line)        [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'text-decoration-thickness'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness)   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'text-decoration-style'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style)       [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'text-decoration-color'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)

<text-decoration-line> =
  none                                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  underline  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  overline  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  line-through  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  blink  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  spelling-error                                       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  grammar-error

<text-decoration-thickness> =
  auto                  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  from-font             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage>

<text-decoration-style> =
  solid    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  double   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  dotted   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  dashed   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  wavy

<text-decoration-color> =
  [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#examples)

### [Demonstration of text-decoration values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#demonstration_of_text-decoration_values)

cssCopyPlay

```
.under {
  text-decoration: underline red;
}

.over {
  text-decoration: wavy overline lime;
}

.line {
  text-decoration: line-through;
}

.plain {
  text-decoration: none;
}

.underover {
  text-decoration: dashed underline overline;
}

.thick {
  text-decoration: solid underline purple 4px;
}

.blink {
  text-decoration: blink;
}

```

htmlCopyPlay

```
<p class="under">This text has a line underneath it.</p>
<p class="over">This text has a line over it.</p>
<p class="line">This text has a line going through it.</p>
<p>
  This <a class="plain" href="#">link will not be underlined</a>, as links
  generally are by default. Be careful when removing the text decoration on
  anchors since users often depend on the underline to denote hyperlinks.
</p>
<p class="underover">This text has lines above <em>and</em> below it.</p>
<p class="thick">
  This text has a really thick purple underline in supporting browsers.
</p>
<p class="blink">
  This text might blink for you, depending on the browser you use.
</p>

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#specifications)

| Specification |
| --- |
| [CSS Text Decoration Module Level 3\<br>\# text-decoration-property](https://drafts.csswg.org/css-text-decor/#text-decoration-property) |
| [Scalable Vector Graphics (SVG) 2\<br>\# TextDecorationProperties](https://svgwg.org/svg2-draft/text.html#TextDecorationProperties) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/text-decoration.json "File: ⁨css/properties/text-decoration.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `text-decoration` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera3.5<br>Opera – Full support<br>Opera3.5 (Release date: ⁨1998-11-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `text-decoration-color` and `text-decoration-style` included in shorthand | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox6<br>Firefox – Full support<br>Firefox6 (Release date: ⁨2011-08-16⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Preview browser support<br>SafariTP<br> <br>more<br>Safari – Full support<br>Safari8 (Release date: ⁨2014-10-16⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Preview browser support<br>SafariTP<br> <br>footnotePreview browser support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android6<br>Firefox for Android – Full support<br>Firefox for Android6 (Release date: ⁨2011-08-16⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS8<br>prefix<br>Safari on iOS – Full support<br>Safari on iOS8 (Release date: ⁨2014-09-17⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩ | Samsung Internet – Full support<br>Samsung Internet7<br>Samsung Internet – Full support<br>Samsung Internet7 (Release date: ⁨2018-03-16⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS8<br>prefix<br>WebView on iOS – Full support<br>WebView on iOS8 (Release date: ⁨2014-09-17⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩ |
| `text-decoration-thickness` included in shorthand | Chrome – Full support<br>Chrome87<br>Chrome – Full support<br>Chrome87 (Release date: ⁨2020-11-17⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge87<br>Edge – Full support<br>Edge87 (Release date: ⁨2020-11-19⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox70<br>Firefox – Full support<br>Firefox70 (Release date: ⁨2019-10-22⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera73<br>Opera – Full support<br>Opera73 (Release date: ⁨2020-12-09⁩)<br> <br>footnoteFull support | Safari – Preview browser support<br>SafariTP<br> <br>Safari – Preview browser support<br>SafariTP<br> <br>footnotePreview browser support | Chrome Android – Full support<br>Chrome Android87<br>Chrome Android – Full support<br>Chrome Android87 (Release date: ⁨2020-11-17⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android62<br>Opera Android – Full support<br>Opera Android62 (Release date: ⁨2021-02-16⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet14<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android87<br>WebView Android – Full support<br>WebView Android87 (Release date: ⁨2020-11-17⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

In development. Supported in a pre-release version.In development. Supported in a pre-release version.

No supportNo support

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration\#see_also)

- The individual text-decoration properties are [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line), [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color), [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style), and [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness).
- The [`text-decoration-skip-ink`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink), [`text-underline-offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset), and [`text-underline-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-position) properties also affect text-decoration, but are not included in the shorthand.
- The [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) property controls the appearance of items in HTML [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ol) and [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ul) lists.
- SVG [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/text-decoration) attribute

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/text-decoration/index.md?plain=1 "Folder: ⁨en-us/web/css/text-decoration⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-decoration&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftext-decoration%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-decoration%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftext-decoration%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")