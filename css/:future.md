---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:future
scraped_at: 2025-10-20T03:15:34.891Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:future#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:future#search)

# :future

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:future#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Afuture&level=not)

The **`:future`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) selector is a time-dimensional pseudo-class that will match for any element which appears entirely after an element that matches [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current). For example in a video with captions which are being displayed by [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API).

cssCopy

```
:future(p, span) {
  display: none;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#syntax)

cssCopy

```
:future {
  /* ... */
}

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#examples)

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#css)

cssCopy

```
:future(p, span) {
  display: none;
}

```

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#html)

htmlCopy

```
<video controls preload="metadata">
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <track
    label="English"
    kind="subtitles"
    srclang="en"
    src="subtitles.vtt"
    default />
</video>

```

### [WebVTT](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#webvtt)

```
WEBVTT FILE

1
00:00:03.500 --> 00:00:05.000
This is the first caption

2
00:00:06.000 --> 00:00:09.000
This is the second caption

3
00:00:11.000 --> 00:00:19.000
This is the third caption

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#specifications)

| Specification |
| --- |
| [Selectors Level 4\<br>\# the-future-pseudo](https://drafts.csswg.org/selectors/#the-future-pseudo) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:future\#see_also)

- [Web Video Text Tracks Format (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current)
- [`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:future/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_future/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_future⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Afuture&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_future%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Afuture%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_future%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")