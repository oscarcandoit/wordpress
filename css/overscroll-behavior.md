---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior
scraped_at: 2025-10-20T02:59:40.189Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior "Take survey (Opens in a new tab)")

# overscroll-behavior


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨September 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior&level=high)

The **`overscroll-behavior`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what a browser does when reaching the boundary of a scrolling area.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#try_it)

- overscroll-behavior: auto;

- overscroll-behavior: contain;

- overscroll-behavior: none;


cssCopy

```
overscroll-behavior: auto;

```

cssCopy

```
overscroll-behavior: contain;

```

cssCopy

```
overscroll-behavior: none;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="box">
      This is a scrollable container. Michaelmas term lately over, and the Lord
      Chancellor sitting in Lincoln's Inn Hall. Implacable November weather. As
      much mud in the streets as if the waters had but newly retired from the
      face of the earth.
      <br /><br />
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also the leap into electronic typesetting, remaining essentially
      unchanged.
    </div>
    <div id="example-element">
      This is the inner container. Focus on this container, scroll to the bottom
      and when you reach the bottom keep scrolling.
      <p>
        If you have
        <code class="language-css">overscroll-behavior: auto;</code> selected
        the outer container will start to scroll.
      </p>
      If you have
      <code class="language-css">overscroll-behavior: contain;</code> selected,
      the outer container will not scroll unless you move your cursor out of the
      inner container and try to perform scroll on the outer container.
    </div>
  </div>
</section>

```

cssCopy

```
.example-container {
  width: 35em;
  height: 18em;
  border: medium dotted;
  padding: 0.75em;
  text-align: left;
  overflow: auto;
  display: flex;
}

.box {
  width: 50%;
}

#example-element {
  width: 50%;
  height: 12em;
  border: medium dotted #1b76c4;
  padding: 0.3em;
  margin: 0 0.3em;
  text-align: left;
  overflow: auto;
  overscroll-behavior: contain;
}

```

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`overscroll-behavior-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x)
- [`overscroll-behavior-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#syntax)

cssCopy

```
/* Keyword values */
overscroll-behavior: auto; /* default */
overscroll-behavior: contain;
overscroll-behavior: none;

/* Two values */
overscroll-behavior: auto contain;

/* Global values */
overscroll-behavior: inherit;
overscroll-behavior: initial;
overscroll-behavior: revert;
overscroll-behavior: revert-layer;
overscroll-behavior: unset;

```

The `overscroll-behavior` property is specified as one or two keywords chosen from the list of values below.

Two keywords specifies the `overscroll-behavior` value on the `x` and `y` axes respectively. If only one value is specified, both x and y are assumed to have the same value.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#auto)

The default scroll overflow behavior occurs as normal.

[`contain`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#contain)

Default scroll overflow behavior (e.g., "bounce" effects) is observed inside the element where this value is set. However, no scroll chaining occurs on neighboring scrolling areas; the underlying elements will not scroll. The `contain` value disables native browser navigation, including the vertical pull-to-refresh gesture and horizontal swipe navigation.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior#none)

No scroll chaining occurs to neighboring scrolling areas, and default scroll overflow behavior is prevented.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#description)

By default, mobile browsers tend to provide a "bounce" effect or even a page refresh when the top or bottom of a page (or other scroll area) is reached. You may also have noticed that when you have a dialog box with scrolling content at the top of a page that also has scrolling content, once the dialog box's [scroll boundary](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_boundary) is reached, the underlying page will then start to scroll — this is called [scroll chaining](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_chaining).

In some cases, these behaviors are not desirable. You can use `overscroll-behavior` to get rid of unwanted scroll chaining and the browser's Facebook/Twitter app-inspired "pull to refresh"-type behavior.

Note that this property applies only to [scroll containers](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container). In particular, since an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/iframe) is not a scroll container, setting this property on an iframe has no effect. To control scroll chaining from an iframe, set `overscroll-behavior` on both the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/html) and the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/body) elements of the iframe's document.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | non-replaced block-level elements and non-replaced inline-block elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`overscroll-behavior-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x): as specified<br>- [`overscroll-behavior-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y): as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#formal_syntax)

```
overscroll-behavior =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  contain  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  none  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  auto  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#examples)

### [Preventing an underlying element from scrolling](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#preventing_an_underlying_element_from_scrolling)

In our [overscroll-behavior example](https://mdn.github.io/css-examples/overscroll-behavior/) (see the [source code](https://github.com/mdn/css-examples/tree/main/overscroll-behavior) also), we present a full-page list of fake contacts, and a dialog box containing a chat window.

![A popup chat window titled 'Active chat', showing a conversation between Chris and Bob. Behind the chat window is a contact list titled 'overscroll-behavior demo'.](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior/example.png)

Both of these areas scroll; normally if you scrolled the chat window until you hit a scroll boundary, the underlying contacts window would start to scroll too, which is not desirable. This can be stopped using `overscroll-behavior-y` ( `overscroll-behavior` would also work) on the chat window, like this:

cssCopy

```
.messages {
  height: 220px;
  overflow: auto;
  overscroll-behavior-y: contain;
}

```

We also wanted to get rid of the standard overscroll effects when the contacts are scrolled to the top or bottom (e.g., Chrome on Android refreshes the page when you scroll past the top boundary). This can be prevented by setting `overscroll-behavior: none` on the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/html) element:

cssCopy

```
html {
  margin: 0;
  overscroll-behavior: none;
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#specifications)

| Specification |
| --- |
| [CSS Overscroll Behavior Module Level 1\<br>\# overscroll-behavior-properties](https://drafts.csswg.org/css-overscroll/#overscroll-behavior-properties) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/overscroll-behavior.json "File: ⁨css/properties/overscroll-behavior.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `overscroll-behavior` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge18<br>Edge – Full support<br>Edge18 (Release date: ⁨2018-10-02⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `auto` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `contain` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome63<br>Chrome – Full support<br>Chrome63 (Release date: ⁨2017-12-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>more<br>Edge – Partial support<br>Edge18 – 18 (Release date: ⁨2018-10-02⁩)<br> <br>footnotePartial supportfootnoteThe `none` value incorrectly behaves as `contain` (allowing for the elastic bounce effect).<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera50<br>Opera – Full support<br>Opera50 (Release date: ⁨2018-01-04⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android63<br>Chrome Android – Full support<br>Chrome Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android46<br>Opera Android – Full support<br>Opera Android46 (Release date: ⁨2018-05-14⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android63<br>WebView Android – Full support<br>WebView Android63 (Release date: ⁨2017-12-05⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior\#see_also)

- [CSS overscroll behavior](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overscroll_behavior) module
- [CSS scroll anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_anchoring) module
- [Take control of your scroll: customizing pull-to-refresh and overflow effects](https://developer.chrome.com/blog/overscroll-behavior) on developer.chrome.com (2017)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overscroll-behavior/index.md?plain=1 "Folder: ⁨en-us/web/css/overscroll-behavior⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverscroll-behavior%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverscroll-behavior%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverscroll-behavior%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")