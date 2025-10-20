---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors
scraped_at: 2025-10-20T02:58:49.441Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors "Take survey (Opens in a new tab)")

# CSS selectors

The **CSS selectors** module defines the patterns to select elements to which a set of CSS rules are then applied along with their [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity). The CSS selectors module provides us with more than 60 selectors and five combinators. [Other modules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors#related_concepts) provide additional pseudo-class selectors and pseudo-elements.

In CSS, selectors are patterns used to match, or select, the elements you want to style. Selectors are also used in JavaScript to enable selecting the DOM nodes to return as a [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList).

Selectors, whether used in CSS or JavaScript, enable targeting HTML elements based on their type, attributes, current states, and even position in the DOM. Combinators allow you to be more precise when selecting elements by enabling selecting elements based on their relationship to other elements.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#reference)

### [Combinators and separators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#combinators_and_separators)

- `+` ( [Next-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator))
- `>` ( [Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator))
- `~` ( [Subsequent sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Subsequent-sibling_combinator))
- " " ( [Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator))
- `|` ( [Namespace separator](https://developer.mozilla.org/en-US/docs/Web/CSS/Namespace_separator))
- `,` ( [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list))

The CSS selectors module also introduces the [column combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator) ( `||`). Currently, no browsers support this feature.

### [Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#selectors)

- [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)
- [`:any-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)
- [`:autofill`](https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill)
- [`:buffering`](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering)
- [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)
- [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default)
- [`:defined`](https://developer.mozilla.org/en-US/docs/Web/CSS/:defined)
- [`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)
- [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)
- [`:empty`](https://developer.mozilla.org/en-US/docs/Web/CSS/:empty)
- [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)
- [`:first-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)
- [`:first-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type)
- [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
- [`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)
- [`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen)
- [`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)
- [`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)
- [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
- [`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range)
- [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)
- [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
- [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)
- [`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)
- [`:last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)
- [`:last-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type)
- [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)
- `:matches()` (obsolete legacy selector alias for [`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is))
- [`:modal`](https://developer.mozilla.org/en-US/docs/Web/CSS/:modal)
- [`:muted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted)
- [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
- [`:nth-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
- [`:nth-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)
- [`:nth-last-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child)
- [`:nth-last-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type)
- [`:only-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)
- [`:only-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type)
- [`:open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:open)
- [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)
- [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
- [`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)
- [`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)
- [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)
- [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)
- [`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)
- [`:popover-open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:popover-open)
- [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only)
- [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write)
- [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)
- [`:root`](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)
- [`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope)
- [`:seeking`](https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking)
- [`:stalled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled)
- [`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
- [`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid)
- [`:user-valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid)
- [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
- [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)
- [`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked)
- [`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)
- [`:-webkit-` pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#pseudo-classes)
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
- [Class selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)
- [ID selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)
- [Type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)
- [Universal selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)

The CSS selectors module also introduces the [`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank), [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current), and [`:local-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link) pseudo-classes. Currently, no browsers support these features.

## [Terms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#terms)

- [Pseudo-class](https://developer.mozilla.org/en-US/docs/Glossary/Pseudo-class) glossary term
- [Functional pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#functional_pseudo-classes)
- [Combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#combinators)
- [Simple selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector)
- [Compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector)
- [Complex selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#complex_selector)
- [Relative selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#relative_selector)
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#guides)

[CSS selectors and combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators)

Overview of the different types of simple selectors and various combinators defined in the CSS selectors and the CSS pseudo modules.

[CSS selector structure](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure)

Explanation of the structure of CSS selectors and the terminologies introduced in the CSS selectors module, ranging from "simple selector" to "forgiving relative selector list".

[Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

Lists the pseudo-classes, selectors that allow the selection of elements based on state information that is not contained in the document tree, defined in the various CSS modules and HTML.

[Using the `:target` pseudo-class in selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Using_the_:target_pseudo-class_in_selectors)

Learn how to use the [`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target) pseudo-class to style the target element a URL's fragment identifier.

[Privacy and the `:visited` selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Privacy_and_the_visited_selector)

Explores the style limitations set on the `:visited` class for user privacy.

[CSS building blocks: CSS selectors](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Basic_selectors)

Introduction to basic CSS selectors, including tutorials on [Type, class, and ID selectors](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Basic_selectors), [Attribute selectors](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Attribute_selectors), [Pseudo-classes and pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Pseudo_classes_and_elements), and [Combinators](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Combinators).

[Learn: UI pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/UI_pseudo-classes)

Learn the different UI pseudo-classes available for styling forms in different states.

[Locating DOM elements using selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Locating_DOM_elements_using_selectors)

The selectors API enables using selectors in JavaScript to retrieve element nodes from the DOM.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#related_concepts)

- [`state()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:state) pseudo-class

- [CSS nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting) module
  - [`&` nesting selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Nesting_selector)
- [CSS scoping](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scoping) module
  - [`:host`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host) pseudo-class
  - [`:host()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function) pseudo-class
  - [`:host-context()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context) pseudo-class
  - [`:has-slotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has-slotted) pseudo-class
  - [`::slotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted) pseudo-element
- [CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow) module
  - [`::scroll-button()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-button)
  - [`::scroll-marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker)
  - [`::scroll-marker-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker-group)
  - [`:target-current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-current)
- [CSS multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout) module
  - [`::column`](https://developer.mozilla.org/en-US/docs/Web/CSS/::column)
- [CSS paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media) module
  - [`:left`](https://developer.mozilla.org/en-US/docs/Web/CSS/:left) pseudo-class
  - [`:right`](https://developer.mozilla.org/en-US/docs/Web/CSS/:right) pseudo-class
  - [`:first`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first) pseudo-class
  - `:blank` pseudo-class
- [CSS pseudo-element module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) (representing entities not included in HTML)
  - [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
  - [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
  - [`::file-selector-button`](https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button)
  - [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
  - [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line)
  - [`::grammar-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error)
  - [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)
  - [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
  - [`::selection`](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)
  - [`::spelling-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::spelling-error)
  - [`::target-text`](https://developer.mozilla.org/en-US/docs/Web/CSS/::target-text)
- [CSS shadow parts module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shadow_parts)
  - [`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part) pseudo-element
- [CSS positioned layout module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout)
  - [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- Other [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
  - [`::cue`](https://developer.mozilla.org/en-US/docs/Web/CSS/::cue)
- [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace) at-rule

- [`!important`](https://developer.mozilla.org/en-US/docs/Web/CSS/important)
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)

- [Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade)

- [`Document.querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) method

- [`Document.querySelectorAll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll) method

- [`NodeList.forEach()`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach) method


## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#specifications)

| Specification |
| --- |
| [Selectors Level 4](https://drafts.csswg.org/selectors/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors\#see_also)

- [CSS pseudo-element module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements)
- [CSS cascading and inheritance module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade)
- [CSS nesting module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting)
- [Using shadow DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 29, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_selectors/index.md?plain=1 "Folder: ⁨en-us/web/css/css_selectors⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_selectors%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_selectors%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe35c1a8397220f5aa1a9063c5e62444899d3aa26%0A*+Document+last+modified%3A+2025-08-29T07%3A42%3A07.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")