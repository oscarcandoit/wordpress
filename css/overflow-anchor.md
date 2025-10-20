---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor
scraped_at: 2025-10-20T02:59:35.910Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# overflow-anchor

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-anchor&level=not)

The **`overflow-anchor`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property provides a way to opt out of the browser's scroll anchoring behavior, which adjusts scroll position to minimize content shifts.

Scroll anchoring behavior is enabled by default in any browser that supports it. Therefore, changing the value of this property is typically only required if you are experiencing problems with scroll anchoring in a document or part of a document and need to turn the behavior off.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#try_it)

- overflow-anchor: auto;

- overflow-anchor: none;


Start lottery

Magic numbers for today are:

cssCopy

```
overflow-anchor: auto;

```

cssCopy

```
overflow-anchor: none;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="whole-content-wrapper">
    <button id="playback" type="button">Start lottery</button>
    <p>Magic numbers for today are:</p>
    <div id="example-element"></div>
  </div>
</section>

```

cssCopy

```
.whole-content-wrapper {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
}

#example-element {
  height: 100%;
  border: 2px dashed dodgerblue;
  padding: 0.75em;
  text-align: left;
  overflow: scroll;
}

#playback {
  font-size: 1em;
  width: 10em;
  height: 4em;
  font-weight: bold;
  margin: 1em auto;
  background-color: aliceblue;
  border: solid 2px dodgerblue;
  border-radius: 5px;
}

#playback:hover {
  border-color: lightseagreen;
}

#playback:active {
  filter: brightness(0.9);
}

```

jsCopy

```
const example = document.getElementById("example-element");
const button = document.getElementById("playback");
let intervalId;

function setInitialState() {
  example.innerHTML = "";
  Array.from({ length: 10 }, (_, i) => i).forEach(addContent);
  example.scrollTop = example.scrollHeight;
}

function addContent() {
  console.log("adding content");
  const magicNumber = Math.floor(Math.random() * 10000);
  example.insertAdjacentHTML(
    "afterbegin",
    `<div class="new-content-container">New Magic Number: ${magicNumber}</div>`,
  );
}

button.addEventListener("click", () => {
  if (example.classList.contains("running")) {
    example.classList.remove("running");
    button.textContent = "Start lottery";
    clearInterval(intervalId);
  } else {
    example.classList.add("running");
    button.textContent = "Stop lottery";
    setInitialState();
    intervalId = setInterval(addContent, 1000);
  }
});

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#syntax)

cssCopy

```
/* Keyword values */
overflow-anchor: auto;
overflow-anchor: none;

/* Global values */
overflow-anchor: inherit;
overflow-anchor: initial;
overflow-anchor: revert;
overflow-anchor: revert-layer;
overflow-anchor: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor#auto)

The element becomes a potential anchor when adjusting scroll position.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor#none)

The element won't be selected as a potential anchor.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#formal_syntax)

```
overflow-anchor =
  auto   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#examples)

### [Prevent scroll anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#prevent_scroll_anchoring)

To prevent scroll anchoring in a document, use the `overflow-anchor` property.

cssCopy

```
* {
  overflow-anchor: none;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#specifications)

| Specification |
| --- |
| [CSS Scroll Anchoring Module Level 1\<br>\# exclusion-api](https://drafts.csswg.org/css-scroll-anchoring/#exclusion-api) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/overflow-anchor.json "File: ⁨css/properties/overflow-anchor.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `overflow-anchor` | Chrome – Full support<br>Chrome56<br>Chrome – Full support<br>Chrome56 (Release date: ⁨2017-01-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox66<br>Firefox – Full support<br>Firefox66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera43<br>Opera – Full support<br>Opera43 (Release date: ⁨2017-02-07⁩)<br> <br>footnoteFull support | Safari – Preview browser support<br>SafariTP<br> <br>footnote<br>Safari – Preview browser support<br>SafariTP<br> <br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099)footnotePreview browser support | Chrome Android – Full support<br>Chrome Android56<br>Chrome Android – Full support<br>Chrome Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android66<br>Firefox for Android – Full support<br>Firefox for Android66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet6<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android56<br>WebView Android – Full support<br>WebView Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `auto` | Chrome – Full support<br>Chrome56<br>Chrome – Full support<br>Chrome56 (Release date: ⁨2017-01-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox66<br>Firefox – Full support<br>Firefox66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera43<br>Opera – Full support<br>Opera43 (Release date: ⁨2017-02-07⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>footnote<br>Safari – No support<br>Safari<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) | Chrome Android – Full support<br>Chrome Android56<br>Chrome Android – Full support<br>Chrome Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android66<br>Firefox for Android – Full support<br>Firefox for Android66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>footnote<br>Safari on iOS – No support<br>Safari on iOS<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) | Samsung Internet – Full support<br>Samsung Internet6<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android56<br>WebView Android – Full support<br>WebView Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>footnote<br>WebView on iOS – No support<br>WebView on iOS<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) |
| `none` | Chrome – Full support<br>Chrome56<br>Chrome – Full support<br>Chrome56 (Release date: ⁨2017-01-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox66<br>Firefox – Full support<br>Firefox66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera43<br>Opera – Full support<br>Opera43 (Release date: ⁨2017-02-07⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>footnote<br>Safari – No support<br>Safari<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) | Chrome Android – Full support<br>Chrome Android56<br>Chrome Android – Full support<br>Chrome Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android66<br>Firefox for Android – Full support<br>Firefox for Android66 (Release date: ⁨2019-03-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>footnote<br>Safari on iOS – No support<br>Safari on iOS<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) | Samsung Internet – Full support<br>Samsung Internet6<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android56<br>WebView Android – Full support<br>WebView Android56 (Release date: ⁨2017-02-01⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>footnote<br>WebView on iOS – No support<br>WebView on iOS<br>footnote<br>footnoteSee [⁨bug 171099⁩](https://webkit.org/b/171099) |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

In development. Supported in a pre-release version.In development. Supported in a pre-release version.

No supportNo support

See implementation notes.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor\#see_also)

- [Overview of scroll anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring)
- [CSS scroll anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Sep 11, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overflow-anchor/index.md?plain=1 "Folder: ⁨en-us/web/css/overflow-anchor⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-anchor&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverflow-anchor%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-anchor%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverflow-anchor%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F116577234db1d6275c74a8bb879fce54d944f4ed%0A*+Document+last+modified%3A+2025-09-11T16%3A42%3A02.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")