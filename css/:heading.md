---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/:heading
scraped_at: 2025-10-20T03:13:17.169Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading#search)

# :heading

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Aheading&level=not)

**Experimental:** **This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**

Check the [Browser compatibility table](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading#browser_compatibility) carefully before using this in production.

The **`:heading`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) matches all [heading elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/Heading_Elements) in a document. This allows you to style all headings at once, rather than matching and styling them individually.

This pseudo-class matches only elements that by default are semantically recognized as headings ( `<h1>` through `<h6>`). Elements with [`role="heading"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/heading_role) are not matched; you can select those by using the `[role="heading"]` [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors).

**Note:**
The `:heading` pseudo-class has the same [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity#how_is_specificity_calculated) as a class selector, that is, `0-1-0`. So `:heading` would have a specificity of `0-1-0`, and `section:heading` would have a specificity of `0-1-1`.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#syntax)

cssCopy

```
:heading {
  /* ... */
}

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#examples)

### [Styling all headings](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#styling_all_headings)

The document in this example contains headings at three different levels.

htmlCopy

```
<h1>Mastering CSS</h1>
<h2>Chapter 1: Selectors</h2>
<h3>1.1 Pseudo-classes</h3>

```

cssCopy

```
:heading {
  color: tomato;
}

```

The `:heading` pseudo-class applies the `color` to all the headings in the document:

The `:heading` pseudo-class applies the `color` to all the headings in the document.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#specifications)

| Specification |
| --- |
| [Selectors Level 5\<br>\# headings](https://drafts.csswg.org/selectors-5/#headings) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading\#see_also)

- [`:heading()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading_function)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 20, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/:heading/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/_colon_heading/index.md?plain=1 "Folder: ⁨en-us/web/css/_colon_heading⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Aheading&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F_colon_heading%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Aheading%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F_colon_heading%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F1a1fe4efc4bfa6147f084aad12cf9908130f76ab%0A*+Document+last+modified%3A+2025-08-20T08%3A57%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")