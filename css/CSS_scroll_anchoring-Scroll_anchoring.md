---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring
scraped_at: 2025-10-20T03:11:10.723Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring#search)

# Overview of scroll anchoring

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_scroll_anchoring%2FScroll_anchoring&level=not)

As a user of the web, you are probably familiar with the problem that scroll anchoring solves. You browse to a long page on a slow connection and begin to scroll to read the content; while you are busy reading, the part of the page you are looking at suddenly jumps. This has happened because large images or some other elements have just loaded further up in the content.

Scroll anchoring is a browser feature that aims to solve this problem of content jumping, which happens if content loads in after the user has already scrolled to a new part of the document.

## [How does it work?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#how_does_it_work)

Scroll anchoring adjusts the scroll position to compensate for the changes outside of the viewport. This means that the point in the document the user is looking at remains in the viewport, which may mean their scroll position actually changes in terms of how _far_ they have moved through the document.

## [How do I turn on scroll anchoring?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#how_do_i_turn_on_scroll_anchoring)

You don't! The feature is enabled by default in supporting browsers. In most cases anchored scrolling is exactly what you want — content jumping is a poor experience for anyone.

## [What if I need to debug it?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#what_if_i_need_to_debug_it)

If your page is not behaving well with scroll anchoring enabled, it is probably because some `scroll` event listener is not handling the extra scrolling to compensate for the anchor node movement.

You can check whether disabling scroll anchoring fixes the issue in Firefox by changing `layout.css.scroll-anchoring.enabled` to `false` in `about:config`. You can also check what node Firefox is using as the anchor using the `layout.css.scroll-anchoring.highlight` switch. That will show a purple overlay on top of the anchor node.

If a node doesn't seem to be an appropriate anchor, you can exclude it using [`overflow-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor), as described below.

## [What if I need to disable it?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#what_if_i_need_to_disable_it)

The [CSS scroll anchoring module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring) provides the [`overflow-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor) property, which can be used to disable scroll anchoring on all or part of the document. It's essentially a way to opt out of the behavior.

The only possible values are `auto` or `none`:

- `auto` is the initial value; as long as the user's browser supports scroll anchoring, the behavior will happen, and they should see fewer content jumps.
- `none` means that you have explicitly opted the document, or part of the document, out of scroll anchoring.

To opt out the entire document, you can set it on the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/body) element:

cssCopy

```
body {
  overflow-anchor: none;
}

```

To opt out of scroll anchoring for a section of the document, set `overflow-anchor: none` on the section's container element:

cssCopy

```
.container {
  overflow-anchor: none;
}

```

If opting out of scroll anchoring on the document or a section thereof, a descendant of an opted-out area cannot be opted back in. For example, if you opt out the entire document, you can't set `overflow-anchor: auto` on a descendant node to turn scroll anchoring back on for a subsection.

### [Suppression triggers](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#suppression_triggers)

There are some _suppression triggers_, which disable scroll anchoring in places where it might be problematic. If any of the triggers happen on the anchor node, or an ancestor of it, anchoring is suppressed.

These suppression triggers are changes to the computed value of any of the following properties:

- [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right), or [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom)
- [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) or [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
- Any [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) or [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)-related properties
- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) and the individual transform properties [`translate`](https://developer.mozilla.org/en-US/docs/Web/CSS/translate), [`scale`](https://developer.mozilla.org/en-US/docs/Web/CSS/scale), and [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/rotate)

Additionally, [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) changes anywhere inside the [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container) also disable scroll anchoring.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#specifications)

| Specification |
| --- |
| [CSS Scroll Anchoring Module Level 1\<br>\# exclusion-api](https://drafts.csswg.org/css-scroll-anchoring/#exclusion-api) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#browser_compatibility)

Loading…

To conditionally apply styles based on whether scroll anchoring can be disabled, use [`@supports` feature queries](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) to test support for the `overflow-anchor` property.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring\#see_also)

- [Original scroll anchoring explainer](https://github.com/WICG/ScrollAnchoring/blob/master/explainer.md) via WICG (2016)
- [Scroll anchoring for web developers](https://blog.chromium.org/2017/04/scroll-anchoring-for-web-developers.html) via Chromium (2017)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring/Scroll_anchoring/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_scroll_anchoring/scroll_anchoring/index.md?plain=1 "Folder: ⁨en-us/web/css/css_scroll_anchoring/scroll_anchoring⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_scroll_anchoring%2FScroll_anchoring&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_scroll_anchoring%2Fscroll_anchoring%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_scroll_anchoring%2FScroll_anchoring%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_scroll_anchoring%2Fscroll_anchoring%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")