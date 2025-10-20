---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow
scraped_at: 2025-10-20T02:59:33.235Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow "Take survey (Opens in a new tab)")

# overflow


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow&level=high)

The **`overflow`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) sets the desired behavior when content does not fit in the element's padding box (overflows) in the horizontal and/or vertical direction.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#try_it)

- overflow: visible;

- overflow: hidden;

- overflow: clip;

- overflow: scroll;

- overflow: auto;


## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
- [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#syntax)

cssCopy

```
/* Keyword values */
overflow: visible;
overflow: hidden;
overflow: clip;
overflow: scroll;
overflow: auto;
overflow: hidden visible;

/* Global values */
overflow: inherit;
overflow: initial;
overflow: revert;
overflow: revert-layer;
overflow: unset;

```

The `overflow` property is specified as one or two [`<overflow>`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow_value) keyword values. If only one keyword is specified, both `overflow-x` and `overflow-y` are set to the same value. If two keywords are specified, the first value applies to `overflow-x` in the horizontal direction and the second one applies to `overflow-y` in the vertical direction.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#values)

[`visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#visible)

Overflow content is not clipped and may be visible outside the element's padding box. The element box is not a [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container). This is the default value of the `overflow` property.

[`hidden`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#hidden)

Overflow content is clipped at the element's padding box. There are no scroll bars, and the clipped content is not visible (i.e., clipped content is hidden), but the content still exists. User agents do not add scroll bars and also do not allow users to view the content outside the clipped region by actions such as dragging on a touch screen or using the scroll wheel on a mouse. The content _can_ be scrolled programmatically (for example, by linking to anchor text, by tabbing to a hidden yet focusable element, or by setting the value of the [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft "scrollLeft") property or the [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo "scrollTo()") method), in which case the element box is a scroll container.

[`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#clip)

Overflow content is clipped at the element's _overflow clip edge_ that is defined using the [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin) property. As a result, content overflows the element's padding box by the [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value of `overflow-clip-margin` or by `0px` if not set. Overflow content outside the clipped region is not visible, user agents do not add a scroll bar, and programmatic scrolling is also not supported. No new [formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context) is created. To establish a formatting context, use `overflow: clip` along with [`display: flow-root`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flow-root). The element box is not a scroll container.

[`scroll`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#scroll)

Overflow content is clipped at the element's padding box, and overflow content can be scrolled into view using scroll bars. User agents display scroll bars whether or not any content is overflowing, so in the horizontal and vertical directions if the value applies to both directions. The use of this keyword, therefore, can prevent scroll bars from appearing and disappearing as content changes. Printers may still print overflow content. The element box is a scroll container.

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow#auto)

Overflow content is clipped at the element's padding box, and overflow content can be scrolled into view using scroll bars. Unlike `scroll`, user agents display scroll bars _only if_ the content is overflowing. If content fits inside the element's padding box, it looks the same as with `visible` but still establishes a new formatting context. The element box is a scroll container.

**Note:**
The keyword value `overlay` is a legacy value alias for `auto`. With `overlay`, the scroll bars are drawn on top of the content instead of taking up space.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#description)

Overflow options include hiding overflow content, enabling scroll bars to view overflow content or displaying the content flowing out of an element box into the surrounding area, and combinations there of.

The following nuances should be kept in mind while using the various keywords for `overflow`:

- Specifying a value other than `visible` (the default) or `clip` for `overflow` creates a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context). This is necessary for technical reasons; if a float intersects with a scrolling element, it would forcibly rewrap the content after each scroll step, leading to a slow scrolling experience.
- For an `overflow` setting to create the desired effect, the block-level element must have either a set height ( [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) or [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)) if the overflow is in the vertical direction, a set width ( [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) or [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)) if the overflow is in the horizontal direction, a set block-size (( [`block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/block-size) or [`max-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size)) if the overflow is in the block direction, or a set inline-size (( [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size) or [`max-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size)) or [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space) set to `nowrap` if the overflow is in the inline direction.
- Setting overflow to `visible` in one direction (i.e., `overflow-x` or `overflow-y`) when it isn't set to `visible` or `clip` in the other direction results in the `visible` value behaving as `auto`.
- Setting overflow to `clip` in one direction when it isn't set to `visible` or `clip` in the other direction results in the `clip` value behaving as `hidden`.
- The JavaScript [`Element.scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop) property may be used to scroll through content in a scroll container, except when `overflow` is set to `clip`.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `visible` |
| Applies to | Block-containers, flex containers, and grid containers |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x): as specified, except with `visible`/ `clip` computing to `auto`/ `hidden` respectively if one of [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x) or [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y) is neither `visible` nor clip<br>- [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y): as specified, except with `visible`/ `clip` computing to `auto`/ `hidden` respectively if one of [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x) or [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y) is neither `visible` nor clip |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#formal_syntax)

```
overflow =
  [<'overflow-block'>](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block) [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<overflow-block> =
  visible   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  hidden    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  clip      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  scroll    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

```

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#accessibility)

A scrolling content area is not keyboard-focusable, so it cannot be scrolled by a keyboard-only user. Firefox and Chrome 132 and later are exceptions; they make scroll containers focusable by default.

For other browsers, to enable keyboard-only users to scroll the container, you will need to assign a [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/tabindex) to the container using `tabindex="0"`. Unfortunately, when a screen reader encounters this tab-stop, it may have no context about the container and could likely announce entire contents of the container. To mitigate this, give the container an appropriate [WAI-ARIA role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles) ( `role="region"`, for example) and an accessible name (via [`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-label) or [`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-labelledby)).

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#examples)

### [Demonstrating results of various overflow keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#demonstrating_results_of_various_overflow_keywords)

#### HTML

htmlCopyPlay

```
<div>
  <code>visible</code>
  <p class="visible">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>hidden</code>
  <p class="hidden">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>clip</code>
  <p class="clip">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>scroll</code>
  <p class="scroll">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>auto</code>
  <p class="auto">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

<div>
  <code>overlay</code>
  <p class="overlay">
    Maya Angelou: "I've learned that people will forget what you said, people
    will forget what you did, but people will never forget how you made them
    feel."
  </p>
</div>

```

#### CSS

cssCopyPlay

```
p.visible {
  overflow: visible;
}

p.hidden {
  overflow: hidden;
}

p.clip {
  overflow: clip;
  overflow-clip-margin: 1em;
}

p.scroll {
  overflow: scroll;
}

p.auto {
  overflow: auto;
}

p.overlay {
  overflow: overlay;
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#specifications)

| Specification |
| --- |
| [CSS Overflow Module Level 3\<br>\# propdef-overflow](https://drafts.csswg.org/css-overflow/#propdef-overflow) |
| [Scalable Vector Graphics (SVG) 2\<br>\# OverflowAndClipProperties](https://svgwg.org/svg2-draft/render.html#OverflowAndClipProperties) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/overflow.json "File: ⁨css/properties/overflow.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `overflow` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>footnote<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnote<br>footnoteAfter Firefox 3.6, the `overflow` property is correctly applied to table group elements ( `<thead>`, `<tbody>`, `<tfoot>`). | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `auto` | Chrome – Full support<br>Chrome1<br>more<br>Chrome – Full support<br>Chrome114 (Release date: ⁨2023-05-30⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>more<br>Firefox – Full support<br>Firefox112 (Release date: ⁨2023-04-11⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>more<br>Opera – Full support<br>Opera100 (Release date: ⁨2023-06-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>more<br>Safari – Full support<br>Safari12 (Release date: ⁨2018-09-17⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>more<br>Chrome Android – Full support<br>Chrome Android114 (Release date: ⁨2023-05-30⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>more<br>Firefox for Android – Full support<br>Firefox for Android112 (Release date: ⁨2023-04-11⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>more<br>Opera Android – Full support<br>Opera Android76 (Release date: ⁨2023-06-26⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>more<br>Safari on iOS – Full support<br>Safari on iOS12 (Release date: ⁨2018-09-17⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>more<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>more<br>WebView Android – Full support<br>WebView Android114 (Release date: ⁨2023-05-30⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>more<br>WebView on iOS – Full support<br>WebView on iOS12 (Release date: ⁨2018-09-17⁩)<br> <br>altname<br>altnameAlternate name: ⁨overlay⁩<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `clip` | Chrome – Full support<br>Chrome90<br>Chrome – Full support<br>Chrome90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge90<br>Edge – Full support<br>Edge90 (Release date: ⁨2021-04-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox81<br>more<br>Firefox – No support<br>Firefox1.5 – 80 (Release date: ⁨2005-11-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨-moz-hidden-unscrollable⁩<br>Firefox – Full support<br>Firefox81 (Release date: ⁨2020-09-22⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera76<br>Opera – Full support<br>Opera76 (Release date: ⁨2021-04-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android90<br>Chrome Android – Full support<br>Chrome Android90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android81<br>more<br>Firefox for Android – No support<br>Firefox for Android4 – 80 (Release date: ⁨2011-03-29⁩)<br> <br>altname<br>altnameAlternate name: ⁨-moz-hidden-unscrollable⁩<br>Firefox for Android – Full support<br>Firefox for Android81 (Release date: ⁨2020-09-22⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android64<br>Opera Android – Full support<br>Opera Android64 (Release date: ⁨2021-05-25⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet15<br>Samsung Internet – Full support<br>Samsung Internet15 (Release date: ⁨2021-08-13⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android90<br>WebView Android – Full support<br>WebView Android90 (Release date: ⁨2021-04-13⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `hidden` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| Multiple keyword syntax for `overflow-x` and `overflow-y` | Chrome – Full support<br>Chrome68<br>Chrome – Full support<br>Chrome68 (Release date: ⁨2018-07-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox61<br>Firefox – Full support<br>Firefox61 (Release date: ⁨2018-06-26⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera55<br>Opera – Full support<br>Opera55 (Release date: ⁨2018-08-16⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari13.1<br>Safari – Full support<br>Safari13.1 (Release date: ⁨2020-03-24⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android68<br>Chrome Android – Full support<br>Chrome Android68 (Release date: ⁨2018-07-24⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android61<br>Firefox for Android – Full support<br>Firefox for Android61 (Release date: ⁨2018-06-26⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS13.4<br>Safari on iOS – Full support<br>Safari on iOS13.4 (Release date: ⁨2020-03-24⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android68<br>WebView Android – Full support<br>WebView Android68 (Release date: ⁨2018-07-24⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS13.4<br>WebView on iOS – Full support<br>WebView on iOS13.4 (Release date: ⁨2020-03-24⁩)<br> <br>footnoteFull support |
| `scroll` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `visible` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

See implementation notes.

Uses a non-standard name.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow\#see_also)

- [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x), [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
- [`overflow-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block), [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin), [`overflow-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline)
- [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip), [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display), [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow), [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- SVG [`overflow`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/overflow) attribute
- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module
- [Keyboard-only scrolling areas](https://adrianroselli.com/2022/06/keyboard-only-scrolling-areas.html) on adrianroselli.com (2022)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overflow/index.md?plain=1 "Folder: ⁨en-us/web/css/overflow⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverflow%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverflow%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")