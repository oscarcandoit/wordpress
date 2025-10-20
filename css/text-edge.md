---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge
scraped_at: 2025-10-20T03:11:20.129Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# <text-edge>

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-edge&level=not)

The **`<text-edge>`** [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types) defines keywords that specify font metrics representing specific regions on a font's block-start edge and block-end edge. Each keyword specifies a position of a font's over and/or under edge.

The `<text-edge>` values are used in the [`text-box-edge`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-edge) property to specify an amount of space to trim from the block-start and block-end edge of a text element's block container.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#syntax)

The `<text-edge>` data type is composed of one or two keywords representing specific regions on a font's block-start (over) edge and/or block-end (under) edge:

- When one value is specified, the position of the font's over edge and under edge are specified using that same keyword.
- When two values are specified, the first value specifies the position of the font's over edge, and the second value specifies the position of the font's under edge.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#values)

#### Single keyword values

[`text`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#text)

The font's over and under edges are its text-over baseline/text-under baseline: this includes the font's ascenders and descenders but excludes the [half-leading](https://developer.mozilla.org/en-US/docs/Glossary/Leading) set on the text.

**Note:**
The amount of half-leading included on a text element can be controlled using the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property.

**Note:**
The `ideographic` and `ideographic-ink` keywords are intended to specify over and under edge positions specific to [CJK language characters](https://en.wikipedia.org/wiki/CJK_characters). Currently their exact behavior is being debated and they are not supported by any browser.

#### Two keyword values

[`alphabetic`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#alphabetic)

The font's under edge is its alphabetic baseline, which is the bottom of its short lower-case letters (for example, "m", "n", and "o") or capital letters.

[`cap`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#cap)

The font's over edge is its cap-height baseline, which is the top of its capital letters.

[`ex`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#ex)

The font's over edge is its x-height baseline, which is the top of its short lower-case letters.

[`text`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge#text_2)

The font's over edge is its text-over baseline (includes the font's ascenders but excludes the over edge half-leading), or its under edge is its text-under baseline (includes the font's descenders but excludes the under edge half-leading), depending on which edge the value is set for.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#formal_syntax)

```
<text-edge> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  text  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic-ink  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  text  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic-ink  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  cap  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ex  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  text  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  ideographic-ink  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  alphabetic  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#examples)

See [`text-box-edge` examples](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-edge#examples)

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#specifications)

| Specification |
| --- |
| [CSS Inline Layout Module Level 3\<br>\# typedef-text-edge](https://drafts.csswg.org/css-inline-3/#typedef-text-edge) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/text-edge.json "File: ⁨css/types/text-edge.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `<text-edge>` | Chrome – Full support<br>Chrome133<br>Chrome – Full support<br>Chrome133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge133<br>Edge – Full support<br>Edge133 (Release date: ⁨2025-02-06⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera118<br>Opera – Full support<br>Opera118 (Release date: ⁨2025-04-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18.2<br>Safari – Full support<br>Safari18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android133<br>Chrome Android – Full support<br>Chrome Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android88<br>Opera Android – Full support<br>Opera Android88 (Release date: ⁨2025-03-19⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18.2<br>Safari on iOS – Full support<br>Safari on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android133<br>WebView Android – Full support<br>WebView Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18.2<br>WebView on iOS – Full support<br>WebView on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support |
| `alphabetic` | Chrome – Full support<br>Chrome133<br>Chrome – Full support<br>Chrome133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge133<br>Edge – Full support<br>Edge133 (Release date: ⁨2025-02-06⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera118<br>Opera – Full support<br>Opera118 (Release date: ⁨2025-04-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18.2<br>Safari – Full support<br>Safari18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android133<br>Chrome Android – Full support<br>Chrome Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android88<br>Opera Android – Full support<br>Opera Android88 (Release date: ⁨2025-03-19⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18.2<br>Safari on iOS – Full support<br>Safari on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android133<br>WebView Android – Full support<br>WebView Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18.2<br>WebView on iOS – Full support<br>WebView on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support |
| `cap` | Chrome – Full support<br>Chrome133<br>Chrome – Full support<br>Chrome133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge133<br>Edge – Full support<br>Edge133 (Release date: ⁨2025-02-06⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera118<br>Opera – Full support<br>Opera118 (Release date: ⁨2025-04-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18.2<br>Safari – Full support<br>Safari18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android133<br>Chrome Android – Full support<br>Chrome Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android88<br>Opera Android – Full support<br>Opera Android88 (Release date: ⁨2025-03-19⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18.2<br>Safari on iOS – Full support<br>Safari on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android133<br>WebView Android – Full support<br>WebView Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18.2<br>WebView on iOS – Full support<br>WebView on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support |
| `ex` | Chrome – Full support<br>Chrome133<br>Chrome – Full support<br>Chrome133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge133<br>Edge – Full support<br>Edge133 (Release date: ⁨2025-02-06⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera118<br>Opera – Full support<br>Opera118 (Release date: ⁨2025-04-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18.2<br>Safari – Full support<br>Safari18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android133<br>Chrome Android – Full support<br>Chrome Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android88<br>Opera Android – Full support<br>Opera Android88 (Release date: ⁨2025-03-19⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18.2<br>Safari on iOS – Full support<br>Safari on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android133<br>WebView Android – Full support<br>WebView Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18.2<br>WebView on iOS – Full support<br>WebView on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support |
| `text` | Chrome – Full support<br>Chrome133<br>Chrome – Full support<br>Chrome133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge133<br>Edge – Full support<br>Edge133 (Release date: ⁨2025-02-06⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera118<br>Opera – Full support<br>Opera118 (Release date: ⁨2025-04-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18.2<br>Safari – Full support<br>Safari18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android133<br>Chrome Android – Full support<br>Chrome Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android88<br>Opera Android – Full support<br>Opera Android88 (Release date: ⁨2025-03-19⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18.2<br>Safari on iOS – Full support<br>Safari on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android133<br>WebView Android – Full support<br>WebView Android133 (Release date: ⁨2025-02-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18.2<br>WebView on iOS – Full support<br>WebView on iOS18.2 (Release date: ⁨2024-12-11⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

In development. Supported in a pre-release version.In development. Supported in a pre-release version.

No supportNo support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge\#see_also)

- [`text-box`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box), [`text-box-edge`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-edge), [`text-box-trim`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
- [CSS inline layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_inline_layout) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/text-edge/index.md?plain=1 "Folder: ⁨en-us/web/css/text-edge⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-edge&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftext-edge%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-edge%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftext-edge%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")