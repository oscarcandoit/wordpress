---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:has
scraped_at: 2025-10-20T02:59:18.356Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:has#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:has#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahas "Take survey (Opens in a new tab)")

# :has()


Baseline

2023


Newly available

Since ⁨December 2023⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:has#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahas&level=low)

The functional **`:has()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) represents an element if any of the [relative selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#relative_selector) that are passed as an argument match at least one element when anchored against this element. This pseudo-class presents a way of selecting a parent element or a previous sibling element with respect to a reference element by taking a [relative selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#relative_selector_list) as an argument.

cssCopy

```
/* Selects an h1 heading with a
paragraph element that immediately follows
the h1 and applies the style to h1 */
h1:has(+ p) {
  margin-bottom: 0;
}

```

The `:has()` pseudo-class takes on the [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity) of the most specific selector in its arguments the same way as [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) and [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not) do.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#syntax)

cssCopy

```
:has(<relative-selector-list>) {
  /* ... */
}

```

If the `:has()` pseudo-class itself is not supported in a browser, the entire selector block will fail unless `:has()` is in a forgiving selector list, such as in [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) and [`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where).

The `:has()` pseudo-class cannot be nested within another `:has()`.

Pseudo-elements are also not valid selectors within `:has()` and pseudo-elements are not valid anchors for `:has()`. This is because many pseudo-elements exist conditionally based on the styling of their ancestors and allowing these to be queried by `:has()` can introduce cyclic querying.

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#examples)

### [Selecting a parent element](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#selecting_a_parent_element)

You may be looking for a "parent [combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#combinators)", which allows you to go up the DOM tree and select the parent of a specific element. The `:has()` pseudo-class does that by using `parent:has(child)` (for any parent) or `parent:has(> child)` (for direct parent). This example shows how to style a `<section>` element when it contains a child with the `featured` class.

htmlCopyPlay

```
<section>
  <article class="featured">Featured content</article>
  <article>Regular content</article>
</section>
<section>
  <article>Regular content</article>
</section>

```

cssCopyPlay

```
section:has(.featured) {
  border: 2px solid blue;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#result)

Play

Featured contentRegular contentRegular content

### [With the sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#with_the_sibling_combinator)

The `:has()` style declaration in the following example adjusts the spacing after `<h1>` headings if they are immediately followed by an `<h2>` heading.

#### HTML

htmlCopyPlay

```
<section>
  <article>
    <h1>Morning Times</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
</section>

```

#### CSS

cssCopyPlay

```
section {
  display: flex;
  align-items: start;
  justify-content: space-around;
}

article {
  display: inline-block;
  width: 40%;
}

h1,
h2 {
  font-size: 1.2em;
}

h2 {
  font-size: 1em;
  color: rgb(150 149 149);
}

```

cssCopyPlay

```
h1,
h2 {
  margin: 0 0 1rem 0;
}

h1:has(+ h2) {
  margin: 0 0 0.25rem 0;
}

```

#### Result

Play

# Morning Times

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua.


# Morning Times

## Delivering you news every morning

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua.


This example shows two similar texts side-by-side for comparison – the left one with an `H1` heading followed by a paragraph and the right one with an `H1` heading followed by an `H2` heading and then a paragraph. In the example on the right, `:has()` helps to select the `H1` element that is immediately followed by an `H2` element (indicated by the next-sibling combinator [`+`](https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator)) and the CSS rule reduces the spacing after such an `H1` element. Without the `:has()` pseudo-class, you cannot use CSS selectors to select a preceding sibling of a different type or a parent element.

### [With the :is() pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#with_the_is_pseudo-class)

This example builds on the previous example to show how to select multiple elements with `:has()`.

#### HTML

htmlCopyPlay

```
<section>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
  <article>
    <h1>Morning Times</h1>
    <h2>Delivering you news every morning</h2>
    <h3>8:00 am</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua.
    </p>
  </article>
</section>

```

#### CSS

cssCopyPlay

```
section {
  display: flex;
  align-items: start;
  justify-content: space-around;
}

article {
  display: inline-block;
  width: 40%;
}

h1 {
  font-size: 1.2em;
}

h2 {
  font-size: 1em;
  color: rgb(150 149 149);
}

h3 {
  font-size: 0.9em;
  color: darkgrey;
}

```

cssCopyPlay

```
h1,
h2,
h3 {
  margin: 0 0 1rem 0;
}

:is(h1, h2, h3):has(+ :is(h2, h3, h4)) {
  margin: 0 0 0.25rem 0;
}

```

#### Result

Play

# Morning Times

## Delivering you news every morning

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua.


# Morning Times

## Delivering you news every morning

### 8:00 am

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua.


Here, the first [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) pseudo-class is used to select any of the heading elements in the list. The second `:is()` pseudo-class is used to pass a list of next-sibling selectors as an argument to `:has()`. The `:has()` pseudo-class helps to select any `H1`, `H2`, or `H3` element that is immediately followed by (indicated by [`+`](https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator)) an `H2`, `H3`, or `H4` element and the CSS rule reduces the spacing after such `H1`, `H2`, or `H3` elements.

This selector could have also been written as:

cssCopyPlay

```
:is(h1, h2, h3):has(+ h2, + h3, + h4) {
  margin: 0 0 0.25rem 0;
}

```

### [Logical operations](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#logical_operations)

The `:has()` relational selector can be used to check if one of the multiple features is true or if all the features are true.

By using comma-separated values inside the `:has()` relational selector, you are checking to see if any of the parameters exist. `x:has(a, b)` will style `x` if descendant `a` OR `b` exists.

By chaining together multiple `:has()` relational selectors together, you are checking to see if all of the parameters exist. `x:has(a):has(b)` will style `x` if descendant `a` AND `b` exist.

cssCopy

```
body:has(video, audio) {
  /* styles to apply if the content contains audio OR video */
}
body:has(video):has(audio) {
  /* styles to apply if the content contains both audio AND video */
}

```

## [Analogy between :has() and regular expressions](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#analogy_between_has_and_regular_expressions)

Interestingly, we can relate some CSS `:has()` constructs with the [lookahead assertion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion) in regular expressions because they both allow you to select elements (or strings in regular expressions) based on a condition without actually selecting the condition matching the element (or string) itself.

### [Positive lookahead (?=pattern)](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#positive_lookahead_pattern)

In the regular expression `abc(?=xyz)`, the string `abc` is matched only if it is immediately followed by the string `xyz`. As it is a lookahead operation, the `xyz` is not included in the match.

The analogous construct in CSS would be `.abc:has(+ .xyz)`: it selects the element `.abc` only if there is a next sibling `.xyz`. The part `:has(+ .xyz)` acts as a lookahead operation because the element `.abc` is selected and not the element `.xyz`.

### [Negative lookahead (?!pattern)](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#negative_lookahead_!pattern)

Similarly, for the negative lookahead case, in the regular expression `abc(?!xyz)`, the string `abc` is matched only if it is _not_ followed by `xyz`. The analogous CSS construct `.abc:has(+ :not(.xyz))` doesn't select the element `.abc` if the next element is `.xyz`.

## [Performance considerations](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#performance_considerations)

Certain uses of the `:has()` pseudo-class can significantly impact page performance, particularly during dynamic updates (DOM mutations). Browser engines must re-evaluate `:has()` selectors when the DOM changes, and complex or poorly constrained selectors can lead to expensive computations.

### [Avoid broad anchoring](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#avoid_broad_anchoring)

The anchor selector (the `A` in `A:has(B)`) should not be an element that has too many children, like `body`, `:root`, or `*`. Anchoring `:has()` to very general selectors can degrade performance because any DOM change within the entire subtree of a broadly selected element requires the browser to re-check the `:has()` condition.

cssCopy

```
/* Avoid anchoring :has() to broad elements */
body:has(.sidebar) {
  /* styles */
}
:root:has(.content) {
  /* styles */
}
*:has(.item) {
  /* styles */
}

```

Instead, anchor `:has()` to specific elements like `.container` or `.gallery` to reduce the scope and improve performance.

cssCopy

```
/* Use specific containers to limit scope */
.container:has(.sidebar-expanded) {
  /* styles */
}
.content-wrapper:has(> article[data-priority="high"]) {
  /* styles */
}
.gallery:has(> img[data-loaded="false"]) {
  /* styles */
}

```

### [Minimize subtree traversals](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#minimize_subtree_traversals)

The inner selector (the `B` in `A:has(B)`) should use combinators like `>` or `+` to limit traversal. When the selector inside `:has()` is not tightly constrained, the browser might need to traverse the entire subtree of the anchor element on every DOM mutation to check if the condition still holds.

In this example, any change within `.ancestor` requires checking all descendants for `.foo`:

cssCopy

```
/* May trigger full subtree traversal */
.ancestor:has(.foo) {
  /* styles */
}

```

Using child or sibling combinators limits the scope of the inner selector, reducing the performance cost of DOM mutations. In this example, the browser only needs to check direct children or a specific sibling's descendants:

cssCopy

```
/* More constrained - limits traversal */
.ancestor:has(> .foo) {
  /* direct child */
}
.ancestor:has(+ .sibling .foo) {
  /* descendant of adjacent sibling */
}

```

Certain inner selectors can force the browser to traverse up the ancestor chain for every DOM mutation, looking for potential anchors that might need updating. This happens when the structure implies a need to check ancestors of the mutated element.

In this example, any DOM change requires checking if the changed element is any element ( `*`) that is a direct child of `.foo`, and if its parent (or further ancestors) is `.ancestor`.

cssCopy

```
/* Might trigger ancestor traversal */
.ancestor:has(.foo > *) {
  /* styles */
}

```

Constraining the inner selector with specific classes or direct child combinators (e.g., `.specific-child` in the next snippet) reduces expensive ancestor traversals by limiting the browser's check to a well-defined element, improving performance.

cssCopy

```
/* Constrain the inner selector to avoid ancestor traversals */
.ancestor:has(.foo > .specific-child) {
  /* styles */
}

```

**Note:**
These performance characteristics may improve as browsers optimize `:has()` implementations, but the fundamental constraints remain: `:has()` needs to traverse a whole subtree, so you need to minimize the subtree's size. In a selector like `A:has(B)`, make sure your `A` does not have too many children, and make sure your `B` is tightly constrained to avoid unnecessary traversal.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#specifications)

| Specification |
| --- |
| [Selectors Level 4\<br>\# relational](https://drafts.csswg.org/selectors/#relational) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/:has# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/selectors/has.json "File: ⁨css/selectors/has.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `:has()` | Chrome – Full support<br>Chrome105<br>Chrome – Full support<br>Chrome105 (Release date: ⁨2022-09-02⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge105<br>Edge – Full support<br>Edge105 (Release date: ⁨2022-09-01⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox121<br>Firefox – Full support<br>Firefox121 (Release date: ⁨2023-12-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera91<br>Opera – Full support<br>Opera91 (Release date: ⁨2022-09-14⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android105<br>Chrome Android – Full support<br>Chrome Android105 (Release date: ⁨2022-09-02⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android121<br>Firefox for Android – Full support<br>Firefox for Android121 (Release date: ⁨2023-12-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android72<br>Opera Android – Full support<br>Opera Android72 (Release date: ⁨2022-10-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet20<br>Samsung Internet – Full support<br>Samsung Internet20 (Release date: ⁨2023-02-10⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android105<br>WebView Android – Full support<br>WebView Android105 (Release date: ⁨2022-09-02⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:has\#see_also)

- [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is), [`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where), [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
- [CSS selectors and combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators)
- [CSS selector structure](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure)
- [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list)
- [CSS selector module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)
- [Locating DOM elements using selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Locating_DOM_elements_using_selectors)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 1, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:has/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_has/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_has⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahas&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_has%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Ahas%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_has%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F7e1296fc0722c86fb7e15487b5e9626597c7a2a0%0A*+Document+last+modified%3A+2025-10-01T11%3A08%3A41.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")