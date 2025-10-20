---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure
scraped_at: 2025-10-20T02:58:51.784Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS selector structure

The CSS selector represents a particular pattern of element or elements in a tree structure. The term "selector" can refer to a [simple selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector), a [compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector), or a [complex selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#complex_selector). When included in the `:has()` pseudo-class as a parameter, these selectors are referred to as [relative selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#relative_selector), representing elements relative to one or more anchor elements.

These selectors can be combined into a comma-separated [selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#selector_list). If any selector in a [non-forgiving selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#valid_and_invalid_selector_lists) list is invalid, the entire selector list is invalidated.

### [Simple selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#simple_selector)

A **simple selector** is a selector with a single component, such as a single type selector, attribute selector, or pseudo-class, that's not used in combination with or contains any other selector component or combinator. A given element is said to match a simple selector when that simple selector accurately describes the element. Any selector that contains a single [basic selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#basic_selectors), [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors), [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes), or [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) selector is a simple selector.

cssCopy

```
#myId {
}

[pattern*="\d"] {
}

```

### [Compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#compound_selector)

A **compound selector** is a sequence of [simple selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector) that are not separated by a [combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#combinators). A compound selector represents a set of simultaneous conditions on a single element. A given element is said to match a compound selector when the element matches all the simple selectors in the compound selector.

cssCopy

```
a#selected {
}

[type="checkbox"]:checked:focus {
}

```

In a compound selector, the [type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors) or [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors) must come first in the sequence of selectors. Only one type selector or universal selector is allowed in the sequence. As whitespace represents the [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator), no whitespace is allowed between the simple selectors that make up a compound selector.

### [Complex selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#complex_selector)

A **complex selector** is a sequence of one or more simple and/or compound selectors that are separated by combinators, including the white space [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator).

A complex selector represents a set of simultaneous conditions on a set of elements.

cssCopy

```
a#selected > .icon {
}

.box h2 + p {
}

```

Selectors can be read from right to left. For example, `a#selected > .icon` matches all elements with a class of `icon` that are the direct children of the `<a>` element with the id `selected`. The selector `.box h2 + p` matches the first `<p>` s to come immediately after any `<h2>` elements that are descendants of any element with the class of `box`.

### [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#selector_list)

A [**selector list**](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list) is a comma-separated list of simple, compound, and/or complex selectors. A given element is said to match a selector list when the element matches any (at least one) of the selectors in that selector list.

cssCopy

```
#main,
article.heading {
}

```

If any selector in a [non-forgiving selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#valid_and_invalid_selector_lists) list is invalid, the entire selector list is invalidated.

cssCopy

```
#main,
:bad-pseudoclass,
.validClass {
  /* `:bad-pseudoclass` is invalid, invalidating this style block */
}

```

The [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) and [`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where) pseudo-classes can be used to construct [forgiving selector lists](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list).

### [Relative selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#relative_selector)

A **relative selector** is a selector representing an element relative to one or more anchor elements preceded by a combinator. Relative selectors that don't begin with an explicit combinator have an implied [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator).

Relative selectors cannot be used in a selector list. Rather, it is accepted within certain contexts, such as the [`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has) pseudo-class.

cssCopy

```
:has(+ div#topic > #reference) {
}

:has(> .icon) {
}

dt:has(+ img) ~ dd {
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#specifications)

| Specification |
| --- |
| [Selectors Level 4](https://drafts.csswg.org/selectors/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure\#see_also)

- [CSS selectors and combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators)
- [Forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list)
- [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
- [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors) module
- [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_selectors/selector_structure/index.md?plain=1 "Folder: ⁨en-us/web/css/css_selectors/selector_structure⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FSelector_structure&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_selectors%2Fselector_structure%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FSelector_structure%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_selectors%2Fselector_structure%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")