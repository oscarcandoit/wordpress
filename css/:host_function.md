---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function
scraped_at: 2025-10-20T03:11:35.477Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# :host()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨January 2020⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahost_function&level=high)

The **`:host()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) function selects the shadow host of the [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM) containing the CSS it is used inside (so you can select a custom element from inside its shadow DOM) — but only if the selector given as the function's parameter matches the shadow host. **`:host()`** has no effect when used outside a shadow DOM.

The most obvious use of this is to put a class name only on certain custom element instances, and then include the relevant class selector as the function argument. You can't use this with a descendant selector expression to select only instances of the custom element that are inside a particular ancestor. That's the job of [`:host-context()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context).

**Note:**
While other functional pseudo-classes such as [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) and [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not) accept a list of selectors as their parameters, `:host()` takes a single compound selector as its parameter. In addition, while `:is()` and `:not()` only take into account the specificity of their argument, the specificity of `:host()` is both the specificity of the pseudo-class **and** the specificity of its argument.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#try_it)

CSS

99

1

2

3

4

5

6

7

8

9

10

/\\* Following CSS is being applied inside the shadow DOM. \*/

:host(h1) {

color: red;

}

:host(#shadow-dom-host) {

border: 2pxdashedblue;

}

HTML

9

1

2

3

4

5

<!\-\- elements outside shadow dom -->

<div id="container">

<h1 id="shadow-dom-host"></h1>

</div>

JavaScript

99

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

constshadowDom = init();

// add a <span> element in the shadow DOM

constspan = document.createElement("span");

span.textContent = "Inside shadow DOM";

shadowDom.appendChild(span);

// attach shadow DOM to the #shadow-dom-host element

functioninit() {

consthost = document.getElementById("shadow-dom-host");

constshadowDom = host.attachShadow({ mode: "open" });

constcssTab = document.querySelector("#css-output");

constshadowStyle = document.createElement("style");

shadowStyle.textContent = cssTab.textContent;

shadowDom.appendChild(shadowStyle);

cssTab.addEventListener("change", () =\> {

shadowStyle.textContent = cssTab.textContent;

});

return shadowDom;

}

#### Output

cssCopy

```
/* Following CSS is being applied inside the shadow DOM. */

:host(h1) {
  color: red;
}

:host(#shadow-dom-host) {
  border: 2px dashed blue;
}

```

htmlCopy

```
<!-- elements outside shadow dom -->
<div id="container">
  <h1 id="shadow-dom-host"></h1>
</div>

```

jsCopy

```
const shadowDom = init();

// add a <span> element in the shadow DOM
const span = document.createElement("span");
span.textContent = "Inside shadow DOM";
shadowDom.appendChild(span);

// attach shadow DOM to the #shadow-dom-host element
function init() {
  const host = document.getElementById("shadow-dom-host");
  const shadowDom = host.attachShadow({ mode: "open" });

  const cssTab = document.querySelector("#css-output");
  const shadowStyle = document.createElement("style");
  shadowStyle.textContent = cssTab.textContent;
  shadowDom.appendChild(shadowStyle);

  cssTab.addEventListener("change", () => {
    shadowStyle.textContent = cssTab.textContent;
  });
  return shadowDom;
}

```

cssCopy

```
/* Selects a shadow root host, only if it is
   matched by the selector argument */
:host(.special-custom-element) {
  font-weight: bold;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#syntax)

cssCopy

```
:host(<compound-selector>) {
  /* ... */
}

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#examples)

### [Selectively styling shadow hosts](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#selectively_styling_shadow_hosts)

The following snippets are taken from our [host-selectors example](https://github.com/mdn/web-components-examples/tree/main/host-selectors) ( [see it live also](https://mdn.github.io/web-components-examples/host-selectors/)).

In this example we have a custom element — `<context-span>` — that you can wrap around text:

htmlCopy

```
<h1>
  Host selectors <a href="#"><context-span>example</context-span></a>
</h1>

```

Inside the element's constructor, we create `style` and `span` elements, fill the `span` with the content of the custom element, and fill the `style` element with some CSS rules:

jsCopy

```
const style = document.createElement("style");
const span = document.createElement("span");
span.textContent = this.textContent;

const shadowRoot = this.attachShadow({ mode: "open" });
shadowRoot.appendChild(style);
shadowRoot.appendChild(span);

style.textContent =
  "span:hover { text-decoration: underline; }" +
  ":host-context(h1) { font-style: italic; }" +
  ':host-context(h1)::after { content: " - no links in headers!" }' +
  ":host-context(article, aside) { color: gray; }" +
  ":host(.footer) { color : red; }" +
  ":host { background: rgb(0 0 0 / 10%); padding: 2px 5px; }";

```

The `:host(.footer) { color : red; }` rule styles all instances of the `<context-span>` element (the shadow host in this instance) in the document that have the `footer` class set on them — we've used it to give instances of the element inside the [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/footer) a special color.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#specifications)

| Specification |
| --- |
| [CSS Scoping Module Level 1\<br>\# host-selector](https://drafts.csswg.org/css-scoping/#host-selector) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/selectors/hostfunction.json "File: ⁨css/selectors/hostfunction.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `:host()` | Chrome – Full support<br>Chrome54<br>Chrome – Full support<br>Chrome54 (Release date: ⁨2016-10-12⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox63<br>Firefox – Full support<br>Firefox63 (Release date: ⁨2018-10-23⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera41<br>Opera – Full support<br>Opera41 (Release date: ⁨2016-10-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10<br>footnote<br>Safari – Full support<br>Safari10 (Release date: ⁨2016-09-20⁩)<br> <br>footnote<br>footnoteCertain CSS selectors do not work (:host > .local-child) and styling slotted content (::slotted) is buggy. | Chrome Android – Full support<br>Chrome Android54<br>Chrome Android – Full support<br>Chrome Android54 (Release date: ⁨2016-10-19⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android63<br>Firefox for Android – Full support<br>Firefox for Android63 (Release date: ⁨2018-10-23⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android41<br>Opera Android – Full support<br>Opera Android41 (Release date: ⁨2016-10-25⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS10<br>footnote<br>Safari on iOS – Full support<br>Safari on iOS10 (Release date: ⁨2016-09-13⁩)<br> <br>footnote<br>footnoteCertain CSS selectors do not work (:host > .local-child) and styling slotted content (::slotted) is buggy. | Samsung Internet – Full support<br>Samsung Internet6<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android54<br>WebView Android – Full support<br>WebView Android54 (Release date: ⁨2016-10-19⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS10<br>footnote<br>WebView on iOS – Full support<br>WebView on iOS10 (Release date: ⁨2016-09-13⁩)<br> <br>footnote<br>footnoteCertain CSS selectors do not work (:host > .local-child) and styling slotted content (::slotted) is buggy. |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

See implementation notes.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function\#see_also)

- [Web components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
- [`:host`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host)
- [`:host-context()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context)
- [`:state()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:state)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_host_function/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_host_function⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahost_function&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_host_function%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahost_function%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_host_function%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")