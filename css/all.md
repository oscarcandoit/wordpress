---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/all
scraped_at: 2025-10-20T03:16:31.109Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/all#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/all#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# all


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨January 2020⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/all#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fall&level=high)

The **`all`** [shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property resets all of an element's properties except [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi), [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction), and [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties). It can set properties to their initial or inherited values, or to the values specified in another cascade layer or stylesheet origin.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#try_it)

- /\\* no all property \*/

- all: initial;

- all: inherit;

- all: unset;

- all: revert;


## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#constituent_properties)

This property is a shorthand for all CSS properties except for [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi), [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction), and [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#syntax)

cssCopy

```
/* Global values */
all: initial;
all: inherit;
all: unset;
all: revert;
all: revert-layer;

```

The `all` property is specified as one of the CSS global keyword values. Note that none of these values affect the [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) and [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) properties.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#values)

[`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial)

Specifies that all the element's properties should be changed to their [initial values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value).

[`inherit`](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit)

Specifies that all the element's properties should be changed to their [inherited values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance).

[`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset)

Specifies that all the element's properties should be changed to their inherited values if they inherit by default, or to their initial values if not.

[`revert`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert)

Specifies behavior that depends on the stylesheet origin to which the declaration belongs:

- If the rule belongs to the [author origin](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade#author_stylesheets), the `revert` value rolls back the [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade) to the user level, so that the [specified values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#specified_value) are calculated as if no author-level rules were specified for the element. For purposes of `revert`, the author origin includes the Override and Animation origins.
- If the rule belongs to the [user origin](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade#user_stylesheets), the `revert` value rolls back the [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade) to the user-agent level, so that the [specified values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#specified_value) are calculated as if no author-level or user-level rules were specified for the element.
- If the rule belongs to the [user-agent origin](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade#user-agent_stylesheets), the `revert` value acts like `unset`.

[`revert-layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert-layer)

Specifies that all the element's properties should roll back the cascade to a previous [cascade layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer), if one exists. If no other cascade layer exists, the element's properties will roll back to the matching rule, if one exists, in the current layer or to a previous [style origin](https://developer.mozilla.org/en-US/docs/Glossary/Style_origin).

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | There is no practical initial value for it. |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as the specified value applies to each property this is a shorthand for. |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand (all properties but [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi) and [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction)) |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#formal_syntax)

```
all =
  initial        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inherit        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  unset          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  revert         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  revert-layer

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#examples)

In this example, the CSS file contains styling for the [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote) element in addition to some styling for the parent `<body>` element. Various outputs in the Results subsection demonstrate how the styling of the `<blockquote>` element is affected when different values are applied to the `all` property inside the `blockquote` rule.

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#html)

htmlCopy

```
<blockquote id="quote">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</blockquote>
Phasellus eget velit sagittis.

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#css)

cssCopy

```
body {
  font-size: small;
  background-color: #f0f0f0;
  color: blue;
  margin: 0;
  padding: 0;
}

blockquote {
  background-color: skyblue;
  color: red;
}

```

### [Results](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#results)

#### A. No `all` property

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







This is the scenario in which no `all` property is set inside the `blockquote` rule. The [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote) element uses the browser's default styling which gives it a margin, together with a specific background and text color as specified in the stylesheet. It also behaves as a _block_ element: the text that follows it is beneath it.

#### B. `all: initial`

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







With the `all` property set to `initial` in the `blockquote` rule, the [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote) element doesn't use the browser default styling anymore: it is an _inline_ element now (initial value), its [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color#formal_definition) is `transparent` (initial value), its [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size#formal_definition) is `medium`, and its [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color#formal_definition) is `black` (initial value).

#### C. `all: inherit`

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







In this case, the [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote) element doesn't use the browser default styling. Instead, it inherits style values from its parent [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/body) element: it is a _block_ element now (inherited value), its [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) is `#F0F0F0` (inherited value), its [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) is `small` (inherited value), and its [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) is `blue` (inherited value).

#### D. `all: unset`

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







When the `unset` value is applied to the `all` property in the `blockquote` rule, the [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote) element doesn't use the browser default styling. Because [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color#formal_definition) is a non-inherited property and [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size#formal_definition) and [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color#formal_definition) are inherited properties, the `<blockquote>` element is an _inline_ element now (initial value), its [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) is `transparent` (initial value), but its [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) is still `small` (inherited value), and its [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) is `blue` (inherited value).

#### E. `all: revert`

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







When the `all` property is set to `revert` in the `blockquote` rule, the `blockquote` rule is considered to be non-existent and the styling property values are inherited from the ones applied to the parent element `<body>`. So the `<blockquote>` element gets styled as a _block_ element, with [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) `#F0F0F0`, [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) `small`, and [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) `blue` \- all values inherited from the `body` rule.

#### F. `all: revert-layer`

Play

> Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Phasellus eget velit sagittis.







There are no cascade layers defined in the CSS file, so the `<blockquote>` element inherits its style from the matching `body` rule. The `<blockquote>` element here is styled as a _block_ element, with [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) `#F0F0F0`, [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) `small`, and [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) `blue` \- all values inherited from the `body` rule. This scenario is an example of the case when `all` set to `revert-layer` behaves the same as when `all` is set to `revert`.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#specifications)

| Specification |
| --- |
| [CSS Cascading and Inheritance Level 4\<br>\# all-shorthand](https://drafts.csswg.org/css-cascade/#all-shorthand) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/all# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/all.json "File: ⁨css/properties/all.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `all` | Chrome – Full support<br>Chrome37<br>Chrome – Full support<br>Chrome37 (Release date: ⁨2014-08-26⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox27<br>Firefox – Full support<br>Firefox27 (Release date: ⁨2014-02-04⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera24<br>Opera – Full support<br>Opera24 (Release date: ⁨2014-09-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9.1<br>Safari – Full support<br>Safari9.1 (Release date: ⁨2016-03-21⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android37<br>Chrome Android – Full support<br>Chrome Android37 (Release date: ⁨2014-09-03⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android27<br>Firefox for Android – Full support<br>Firefox for Android27 (Release date: ⁨2014-02-04⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android24<br>Opera Android – Full support<br>Opera Android24 (Release date: ⁨2014-09-10⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9.3<br>Safari on iOS – Full support<br>Safari on iOS9.3 (Release date: ⁨2016-03-21⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet3<br>Samsung Internet – Full support<br>Samsung Internet3 (Release date: ⁨2015-04-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android37<br>WebView Android – Full support<br>WebView Android37 (Release date: ⁨2014-09-03⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9.3<br>WebView on iOS – Full support<br>WebView on iOS9.3 (Release date: ⁨2016-03-21⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/all\#see_also)

CSS global keyword values: [`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial), [`inherit`](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit), [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset), [`revert`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert), [`revert-layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert-layer)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/all/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/all/index.md?plain=1 "Folder: ⁨en-us/web/css/all⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fall&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fall%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fall%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fall%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F3d06d82cbddf640291fd66cf85cd9014c4e867c5%0A*+Document+last+modified%3A+2025-08-05T13%3A36%3A14.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")