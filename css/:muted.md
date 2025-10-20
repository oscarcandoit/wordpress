---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:muted
scraped_at: 2025-10-20T03:14:47.175Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted#search)

# :muted

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Amuted&level=not)

The **`:muted`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) selector represents an element that is capable of making sound, such as [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video), but is muted (forced silent).

Muted is different from [`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked) in that the page author has control over whether a media element can be muted or un-muted.
User agents may set media `muted` value according to use preferences (e.g., remembering the last set value across sessions, on a per-site basis, or otherwise).
An element that is `:volume-locked` cannot be muted, un-muted, or have its volume changed via JavaScript because of an operating system or user agent preference.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#syntax)

cssCopy

```
:muted {
  /* ... */
}

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#examples)

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#css)

cssCopy

```
:muted {
  outline: 5px solid red;
}

video:muted {
  outline: 5px solid blue;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#specifications)

| Specification |
| --- |
| [Selectors Level 4\<br>\# selectordef-muted](https://drafts.csswg.org/selectors/#selectordef-muted) |
| [HTML\<br>\# selector-muted](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-muted) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/selectors/muted.json "File: ⁨css/selectors/muted.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `:muted` | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>EdgeNo<br> <br>Edge – No support<br>Edge<br>footnoteNo support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

No supportNo support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted\#see_also)

- [`:buffering`](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering)
- [`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)
- [`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)
- [`:seeking`](https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking)
- [`:stalled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled)
- [`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked)
- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)
- [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted) property of [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) objects

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_muted/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_muted⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Amuted&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_muted%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Amuted%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_muted%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")