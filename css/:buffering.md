---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering
scraped_at: 2025-10-20T03:13:21.552Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# :buffering

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Abuffering&level=not)

The **`:buffering`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) selector represents an element that is playable, such as [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video), when the playable element is buffering a media resource.

An element is considered as buffering when that element cannot continue playing because it is trying to load media data but does not yet have enough data to begin or continue playback.
For more information, see the [Media buffering, seeking, and time ranges](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Audio_and_video_delivery/buffering_seeking_time_ranges#seekable) guide.

**Note:**
An element is still considered to be [`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing) when it is "buffering".
If `:buffering` matches an element, `:playing` will also match that element.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#syntax)

cssCopy

```
:buffering {
  /* ... */
}

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#examples)

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#css)

cssCopy

```
:buffering {
  outline: 5px solid red;
}

video:buffering {
  outline: 5px solid blue;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#specifications)

| Specification |
| --- |
| [Selectors Level 4\<br>\# selectordef-buffering](https://drafts.csswg.org/selectors/#selectordef-buffering) |
| [HTML\<br>\# selector-buffering](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-buffering) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering\#see_also)

- [`:muted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted)
- [`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)
- [`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)
- [`:seeking`](https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking)
- [`:stalled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled)
- [`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked)
- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_buffering/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_buffering⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Abuffering&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_buffering%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Abuffering%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_buffering%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")