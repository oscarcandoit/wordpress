---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior
scraped_at: 2025-10-20T02:59:53.436Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior#search)

# scroll-behavior


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscroll-behavior&level=high)

The **`scroll-behavior`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the behavior for a scrolling box when scrolling is triggered by the navigation or CSSOM scrolling APIs.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#try_it)

```
scroll-behavior: auto;

```

```
scroll-behavior: smooth;

```

```
<section id="default-example">
  <div class="container">
    <p class="nav">
      Scroll to:
      <a href="#pageA">A</a>
      <a href="#pageB">B</a>
      <a href="#pageC">C</a>
    </p>
    <scroll-container id="example-element">
      <scroll-page id="pageA">A</scroll-page>
      <scroll-page id="pageB">B</scroll-page>
      <scroll-page id="pageC">C</scroll-page>
    </scroll-container>
  </div>
</section>

```

```
.container {
  flex-direction: column;
}

.nav a {
  color: #009e5f;
}

scroll-container {
  border: 1px solid black;
  display: block;
  height: 200px;
  overflow-y: scroll;
  width: 200px;
}

scroll-page {
  align-items: center;
  display: flex;
  font-size: 5em;
  height: 100%;
  justify-content: center;
}

```

Note that any other scrolls, such as those performed by the user, are not affected by this property. When this property is specified on the root element, it applies to the viewport instead. This property specified on the `body` element will _not_ propagate to the viewport.

User agents are allowed to ignore this property.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#syntax)

css

```
/* Keyword values */
scroll-behavior: auto;
scroll-behavior: smooth;

/* Global values */
scroll-behavior: inherit;
scroll-behavior: initial;
scroll-behavior: revert;
scroll-behavior: revert-layer;
scroll-behavior: unset;

```

The `scroll-behavior` property is specified as one of the keyword values listed below.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior#auto)

The scrolling box scrolls instantly.

[`smooth`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior#smooth)

The scrolling box scrolls in a smooth fashion using a user-agent-defined easing function over a user-agent-defined period of time. User agents should follow platform conventions, if any.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | scrolling boxes |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#formal_syntax)

```
scroll-behavior =
  auto     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  smooth

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#examples)

### [Setting smooth scroll behavior](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#setting_smooth_scroll_behavior)

#### HTML

html

```
<nav>
  <a href="#page-1">1</a>
  <a href="#page-2">2</a>
  <a href="#page-3">3</a>
</nav>
<div class="scroll-container">
  <div class="scroll-page" id="page-1">1</div>
  <div class="scroll-page" id="page-2">2</div>
  <div class="scroll-page" id="page-3">3</div>
</div>

```

#### CSS

css

```
a {
  display: inline-block;
  width: 50px;
  text-decoration: none;
}
nav,
.scroll-container {
  display: block;
  margin: 0 auto;
  text-align: center;
}
nav {
  width: 339px;
  padding: 5px;
  border: 1px solid black;
}
.scroll-container {
  width: 350px;
  height: 200px;
  overflow-y: scroll;
  scroll-behavior: smooth;
}
.scroll-page {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  font-size: 5em;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#specifications)

| Specification |
| --- |
| [CSS Overflow Module Level 3\<br>\# smooth-scrolling](https://drafts.csswg.org/css-overflow/#smooth-scrolling) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior\#browser_compatibility)

Loading…

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/scroll-behavior/index.md?plain=1 "Folder: ⁨en-us/web/css/scroll-behavior⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscroll-behavior&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fscroll-behavior%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fscroll-behavior%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fscroll-behavior%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")