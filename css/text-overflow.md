---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow
scraped_at: 2025-10-20T03:13:55.885Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# text-overflow


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-overflow&level=high)

The **`text-overflow`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how hidden overflow content is signaled to users. It can be clipped, display an ellipsis ( `…`), or display a custom string.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#try_it)

- text-overflow: clip;

- text-overflow: ellipsis;

- text-overflow: "-";

- text-overflow: "";


cssCopy

```
text-overflow: clip;

```

cssCopy

```
text-overflow: ellipsis;

```

cssCopy

```
text-overflow: "-";

```

cssCopy

```
text-overflow: "";

```

htmlCopy

```
<section id="default-example">
  <div id="example-element-container">
    <p id="example-element">"Is there any tea on this spaceship?" he asked.</p>
  </div>
</section>

```

cssCopy

```
#example-element-container {
  width: 100%;
  max-width: 18em;
}

#example-element {
  line-height: 50px;
  border: 1px solid #c5c5c5;
  overflow: hidden;
  white-space: nowrap;
  font-family: sans-serif;
  padding: 0 0.5em;
  text-align: left;
}

```

The `text-overflow` property doesn't force an overflow to occur. To make text overflow its container, you have to set other CSS properties: [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) and [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space). For example:

cssCopy

```
overflow: hidden;
white-space: nowrap;

```

The `text-overflow` property only affects content that is overflowing a block container element in its _inline_ progression direction (not text overflowing at the bottom of a box, for example).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#syntax)

cssCopy

```
text-overflow: clip;
text-overflow: ellipsis ellipsis;
text-overflow: ellipsis " [..]";

/* Global values */
text-overflow: inherit;
text-overflow: initial;
text-overflow: revert;
text-overflow: revert-layer;
text-overflow: unset;

```

The `text-overflow` property may be specified using one or two values. If one value is given, it specifies overflow behavior for the end of the line (the right end for left-to-right text, the left end for right-to-left text). If two values are given, the first specifies overflow behavior for the left end of the line, and the second specifies it for the right end of the line. The property accepts either a keyword value ( `clip` or `ellipsis`) or a `<string>` value.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#values)

[`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#clip)

The default for this property. This keyword value will truncate the text at the limit of the [content area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model), therefore the truncation can happen in the middle of a character. To clip at the transition between characters you can specify `text-overflow` as an empty string, if that is supported in your target browsers: `text-overflow: '';`.

[`ellipsis`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#ellipsis)

This keyword value will display an ellipsis ( `'…'`, `U+2026 HORIZONTAL ELLIPSIS`) to represent clipped text. The ellipsis is displayed inside the [content area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model), decreasing the amount of text displayed. If there is not enough space to display the ellipsis, it is clipped.

[`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow#string)

The [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string) to be used to represent clipped text. The string is displayed inside the [content area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model), shortening the size of the displayed text. If there is not enough space to display the string itself, it is clipped.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `clip` |
| Applies to | block container elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#formal_syntax)

```
text-overflow =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  clip  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ellipsis  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  fade  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  <fade()>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<fade()> =
  fade(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") )

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#examples)

### [One-value syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#one-value_syntax)

This example shows different values for `text-overflow` applied to a paragraph, for left-to-right and right-to-left text.

#### HTML

htmlCopyPlay

```
<div class="ltr">
  <h2>Left to right text</h2>
  <pre>clip</pre>
  <p class="overflow-clip">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>ellipsis</pre>
  <p class="overflow-ellipsis">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>" [..]"</pre>
  <p class="overflow-string">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
</div>

<div class="rtl">
  <h2>Right to left text</h2>
  <pre>clip</pre>
  <p class="overflow-clip">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>ellipsis</pre>
  <p class="overflow-ellipsis">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
  <pre>" [..]"</pre>
  <p class="overflow-string">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </p>
</div>

```

#### CSS

cssCopyPlay

```
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* Both of the following are required for text-overflow */
  white-space: nowrap;
  overflow: hidden;
}

.overflow-clip {
  text-overflow: clip;
}

.overflow-ellipsis {
  text-overflow: ellipsis;
}

.overflow-string {
  text-overflow: " [..]";
}

body {
  display: flex;
  justify-content: space-around;
}

.ltr > p {
  direction: ltr;
}

.rtl > p {
  direction: rtl;
}

```

#### Result

Play

### [Two-value syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#two-value_syntax)

This example shows the two-value syntax for `text-overflow`, where you can define different overflow behavior for the start and end of the text.
To show the effect we have to scroll the line so the start of the line is also hidden.

#### HTML

htmlCopyPlay

```
<pre>clip clip</pre>
<p class="overflow-clip-clip">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>clip ellipsis</pre>
<p class="overflow-clip-ellipsis">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>ellipsis ellipsis</pre>
<p class="overflow-ellipsis-ellipsis">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>
<pre>ellipsis " [..]"</pre>
<p class="overflow-ellipsis-string">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
</p>

```

#### CSS

cssCopyPlay

```
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* Both of the following are required for text-overflow */
  white-space: nowrap;
  overflow: scroll;
}

.overflow-clip-clip {
  text-overflow: clip clip;
}

.overflow-clip-ellipsis {
  text-overflow: clip ellipsis;
}

.overflow-ellipsis-ellipsis {
  text-overflow: ellipsis ellipsis;
}

.overflow-ellipsis-string {
  text-overflow: ellipsis " [..]";
}

```

#### JavaScript

jsCopyPlay

```
// Scroll each paragraph so the start is also hidden
const paras = document.querySelectorAll("p");

for (const para of paras) {
  para.scroll(100, 0);
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#specifications)

| Specification |
| --- |
| [CSS Overflow Module Level 3\<br>\# text-overflow](https://drafts.csswg.org/css-overflow/#text-overflow) |
| [Scalable Vector Graphics (SVG) 2\<br>\# TextOverflowProperty](https://svgwg.org/svg2-draft/text.html#TextOverflowProperty) |

A previous version of this interface reached the _Candidate Recommendation_ status. As some not-listed-at-risk features needed to be removed, the spec was demoted to the _Working Draft_ level, explaining why browsers implemented this property unprefixed, though not at the CR state.

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/text-overflow.json "File: ⁨css/properties/text-overflow.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `text-overflow` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox7<br>footnote<br>Firefox – Full support<br>Firefox7 (Release date: ⁨2011-09-27⁩)<br> <br>footnote<br>footnoteUntil Firefox 10, handling of `text-overflow` on blocks with inline overflow on both horizontal sides was incorrect. Before Firefox 10, if only one value was specified (such as `text-overflow: ellipsis;`), text was ellipsed on both sides of the block, instead of only the end edge based on the block's text direction. | Opera – Full support<br>Opera11<br>more<br>Opera – No support<br>Opera9 – 12.1 (Release date: ⁨2006-06-20⁩)<br> <br>prefix<br>footnoteRemoved in ⁨15⁩ and laterprefixImplemented with the vendor prefix: ⁨-o-⁩<br>Opera – Full support<br>Opera11 (Release date: ⁨2010-12-16⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1.3<br>Safari – Full support<br>Safari1.3 (Release date: ⁨2005-04-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android7<br>footnote<br>Firefox for Android – Full support<br>Firefox for Android7 (Release date: ⁨2011-09-27⁩)<br> <br>footnote<br>footnoteUntil Firefox for Android 10, handling of `text-overflow` on blocks with inline overflow on both horizontal sides was incorrect. Before Firefox for Android 10, if only one value was specified (such as `text-overflow: ellipsis;`), text was ellipsed on both sides of the block, instead of only the end edge based on the block's text direction. | Opera Android – Full support<br>Opera Android11<br>more<br>Opera Android – No support<br>Opera Android10.1 – 12.1 (Release date: ⁨2010-11-09⁩)<br> <br>prefix<br>footnoteRemoved in ⁨14⁩ and laterprefixImplemented with the vendor prefix: ⁨-o-⁩<br>Opera Android – Full support<br>Opera Android11 (Release date: ⁨2011-03-22⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `clip` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox7<br>Firefox – Full support<br>Firefox7 (Release date: ⁨2011-09-27⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1.3<br>Safari – Full support<br>Safari1.3 (Release date: ⁨2005-04-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android7<br>Firefox for Android – Full support<br>Firefox for Android7 (Release date: ⁨2011-09-27⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `ellipsis` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox7<br>Firefox – Full support<br>Firefox7 (Release date: ⁨2011-09-27⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1.3<br>Safari – Full support<br>Safari1.3 (Release date: ⁨2005-04-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android7<br>Firefox for Android – Full support<br>Firefox for Android7 (Release date: ⁨2011-09-27⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| <string> | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>EdgeNo<br> <br>Edge – No support<br>Edge<br>footnoteNo support | Firefox – Full support<br>Firefox9<br>Firefox – Full support<br>Firefox9 (Release date: ⁨2011-12-20⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – Full support<br>Firefox for Android9<br>Firefox for Android – Full support<br>Firefox for Android9 (Release date: ⁨2011-12-21⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Two-value syntax | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>EdgeNo<br> <br>Edge – No support<br>Edge<br>footnoteNo support | Firefox – Full support<br>Firefox9<br>Firefox – Full support<br>Firefox9 (Release date: ⁨2011-12-20⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – Full support<br>Firefox for Android9<br>Firefox for Android – Full support<br>Firefox for Android9 (Release date: ⁨2011-12-21⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

No supportNo support

See implementation notes.

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow\#see_also)

- Related CSS properties: [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow), [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- CSS properties that control line breaks in words: [`overflow-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap), [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/text-overflow/index.md?plain=1 "Folder: ⁨en-us/web/css/text-overflow⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-overflow&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftext-overflow%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-overflow%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftext-overflow%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")