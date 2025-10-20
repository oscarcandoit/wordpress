---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x
scraped_at: 2025-10-20T02:59:37.906Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-x "Take survey (Opens in a new tab)")

# overflow-x


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-x&level=high)

The **`overflow-x`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what shows when content overflows a block-level element's left and right edges. This may be nothing, a scroll bar, or the overflow content. This property may also be set by using the [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) shorthand property.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#try_it)

- overflow-x: visible;

- overflow-x: hidden;

- overflow-x: clip;

- overflow-x: scroll;

- overflow-x: auto;


cssCopy

```
overflow-x: visible;

```

cssCopy

```
overflow-x: hidden;

```

cssCopy

```
overflow-x: clip;

```

cssCopy

```
overflow-x: scroll;

```

cssCopy

```
overflow-x: auto;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div id="example-element">
    The value of Pi is 3.1415926535897932384626433832795029. The value of e is
    2.7182818284590452353602874713526625.
  </div>
</section>

```

cssCopy

```
#example-element {
  width: 15em;
  height: 9em;
  border: medium dotted;
  padding: 0.75em;
  text-align: left;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#syntax)

cssCopy

```
/* Keyword values */
overflow-x: visible;
overflow-x: hidden;
overflow-x: clip;
overflow-x: scroll;
overflow-x: auto;

/* Global values */
overflow-x: inherit;
overflow-x: initial;
overflow-x: revert;
overflow-x: revert-layer;
overflow-x: unset;

```

The `overflow-x` property is specified as a single [`<overflow>`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow_value) keyword value.

If [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y) is `hidden`, `scroll`, or `auto`, and the `overflow-x` property is `visible` (default), the value will be implicitly computed as `auto`.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#values)

[`visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#visible)

Overflow content is not clipped and may be visible outside the element's padding box on left and right edges. The element box is not a [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container).

[`hidden`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#hidden)

Overflow content is clipped if necessary to fit horizontally in the elements' padding box. No scroll bars are provided.

[`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#clip)

Overflow content is clipped at the element's _overflow clip edge_ that is defined using the [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin) property. As a result, content overflows the element's padding box by the [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value of `overflow-clip-margin` or by `0px` if not set. The difference between `clip` and `hidden` is that the `clip` keyword also forbids all scrolling, including programmatic scrolling. No new formatting context is created. To establish a formatting context, use `overflow: clip` along with [`display: flow-root`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flow-root). The element box is not a scroll container.

[`scroll`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#scroll)

Overflow content is clipped if necessary to fit horizontally inside the element's padding box. Browsers display scroll bars in the horizontal direction whether or not any content is actually clipped. (This prevents scroll bars from appearing or disappearing when the content changes.) Printers may still print overflowing content.

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x#auto)

Overflow content is clipped at the element's padding box, and overflow content can be scrolled into view. Unlike `scroll`, user agents display scroll bars _only if_ the content is overflowing and hide scroll bars by default. If content fits inside the element's padding box, it looks the same as with `visible`, but still establishes a new block-formatting context. Desktop browsers provide scroll bars if content overflows.

**Note:**
The keyword value `overlay` is a legacy value alias for `auto`. With `overlay`, the scroll bars are drawn on top of the content instead of taking up space.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `visible` |
| Applies to | Block-containers, flex containers, and grid containers |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, except with `visible`/ `clip` computing to `auto`/ `hidden` respectively if one of [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x) or [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y) is neither `visible` nor clip |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#formal_syntax)

```
overflow-x =
  visible   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  hidden    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  clip      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  scroll    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#examples)

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#html)

htmlCopyPlay

```
<ul>
  <li>
    <code>overflow-x:hidden</code> — hides the text outside the box
    <div id="div1">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:scroll</code> — always adds a scrollbar
    <div id="div2">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:visible</code> — displays the text outside the box if
    needed
    <div id="div3">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:auto</code> — on most browsers, equivalent to
    <code>scroll</code>
    <div id="div4">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>
</ul>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#css)

cssCopyPlay

```
#div1,
#div2,
#div3,
#div4 {
  border: 1px solid black;
  width: 250px;
  margin-bottom: 12px;
}

#div1 {
  overflow-x: hidden;
}
#div2 {
  overflow-x: scroll;
}
#div3 {
  overflow-x: visible;
}
#div4 {
  overflow-x: auto;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#result)

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#specifications)

| Specification |
| --- |
| [CSS Overflow Module Level 3\<br>\# overflow-properties](https://drafts.csswg.org/css-overflow/#overflow-properties) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/overflow-x.json "File: ⁨css/properties/overflow-x.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `overflow-x` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3.5<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera9.5<br>Opera – Full support<br>Opera9.5 (Release date: ⁨2008-06-12⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `auto` | Chrome – Full support<br>Chrome1<br>more<br>Chrome – Full support<br>Chrome15 (Release date: ⁨2011-10-25⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3.5<br>more<br>Firefox – Full support<br>Firefox112 (Release date: ⁨2023-04-11⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>more<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>more<br>Safari – Full support<br>Safari6 (Release date: ⁨2012-07-25⁩)<br> <br>footnotealtname<br>altnameAlternate name: ⁨overlay⁩footnoteBefore Safari 12.1, `overlay` only had an effect on legacy scrollbars on macOS. Since Safari 12.1, it is parsed as `auto`.<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>more<br>Chrome Android – Full support<br>Chrome Android100 (Release date: ⁨2022-03-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>more<br>Firefox for Android – Full support<br>Firefox for Android112 (Release date: ⁨2023-04-11⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>more<br>Opera Android – Full support<br>Opera Android69 (Release date: ⁨2022-05-09⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>more<br>Safari on iOS – Full support<br>Safari on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnotealtname<br>altnameAlternate name: ⁨overlay⁩footnoteBefore Safari on iOS 12.1, `overlay` only had an effect on legacy scrollbars on macOS. Since Safari on iOS 12.1, it is parsed as `auto`.<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>more<br>Samsung Internet – Full support<br>Samsung Internet19 (Release date: ⁨2022-11-01⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>more<br>WebView Android – Full support<br>WebView Android100 (Release date: ⁨2022-03-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>more<br>WebView on iOS – Full support<br>WebView on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnotealtname<br>altnameAlternate name: ⁨overlay⁩footnoteBefore WebView on iOS 12.1, `overlay` only had an effect on legacy scrollbars on macOS. Since WebView on iOS 12.1, it is parsed as `auto`.<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `clip` | Chrome – Full support<br>Chrome90<br>Chrome – Full support<br>Chrome90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge90<br>Edge – Full support<br>Edge90 (Release date: ⁨2021-04-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox81<br>more<br>Firefox – No support<br>Firefox3.5 – 80 (Release date: ⁨2009-06-30⁩)<br> <br>altname<br>altnameAlternate name: ⁨-moz-hidden-unscrollable⁩<br>Firefox – Full support<br>Firefox81 (Release date: ⁨2020-09-22⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera76<br>Opera – Full support<br>Opera76 (Release date: ⁨2021-04-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android90<br>Chrome Android – Full support<br>Chrome Android90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android81<br>more<br>Firefox for Android – No support<br>Firefox for Android4 – 80 (Release date: ⁨2011-03-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨-moz-hidden-unscrollable⁩<br>Firefox for Android – Full support<br>Firefox for Android81 (Release date: ⁨2020-09-22⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android64<br>Opera Android – Full support<br>Opera Android64 (Release date: ⁨2021-05-25⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet15<br>Samsung Internet – Full support<br>Samsung Internet15 (Release date: ⁨2021-08-13⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android90<br>WebView Android – Full support<br>WebView Android90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `hidden` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3.5<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `scroll` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3.5<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `visible` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3.5<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Uses a non-standard name.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x\#see_also)

- [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip), [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display), [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow), [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module
- [Learn: Overflowing content](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Overflow)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overflow-x/index.md?plain=1 "Folder: ⁨en-us/web/css/overflow-x⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-x&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverflow-x%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-x%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverflow-x%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")