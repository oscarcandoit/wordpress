---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/inherit
scraped_at: 2025-10-20T03:01:07.973Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# inherit


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Finherit&level=high)

The **`inherit`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) keyword causes the element to take the [computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) of the property from its parent element. It can be applied to any CSS property, including the CSS shorthand property [`all`](https://developer.mozilla.org/en-US/docs/Web/CSS/all).

For [inherited properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance#inherited_properties), this reinforces the default behavior, and is only needed to override another rule.

**Note:**
Inheritance is always from the parent element in the document tree, even when the parent element is not the containing block.

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit\#examples)

### [Exclude selected elements from a rule](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit\#exclude_selected_elements_from_a_rule)

cssCopy

```
/* Make second-level headers green */
h2 {
  color: green;
}

/* Leave those in the sidebar alone so they use their parent's color */
#sidebar h2 {
  color: inherit;
}

```

In this example, the `h2` elements inside the sidebar might be different colors. For example, consider one of them that would by the child of a `div` matched by the rule:

cssCopy

```
div#current {
  color: blue;
}

```

Then, it would be blue.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit\#specifications)

| Specification |
| --- |
| [CSS Cascading and Inheritance Level 4\<br>\# inherit](https://drafts.csswg.org/css-cascade/#inherit) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit\#see_also)

- [Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance)
- Use the [`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial) keyword to set a property to its initial value.
- Use the [`revert`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert) keyword to reset a property to the value established by the user-agent stylesheet (or by user styles, if any exist).
- Use the [`revert-layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert-layer) keyword to reset a property to the value established in a previous cascade layer.
- Use the [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset) keyword to set a property to its inherited value if it inherits or to its initial value if not.
- The [`all`](https://developer.mozilla.org/en-US/docs/Web/CSS/all) property lets you reset all properties to their initial, inherited, reverted, or unset state at once.

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 1, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/inherit/index.md?plain=1 "Folder: ⁨en-us/web/css/inherit⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Finherit&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Finherit%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Finherit%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Finherit%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F7e1296fc0722c86fb7e15487b5e9626597c7a2a0%0A*+Document+last+modified%3A+2025-10-01T11%3A08%3A41.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")