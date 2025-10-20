---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces
scraped_at: 2025-10-20T03:04:21.942Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS namespaces

The **CSS namespaces** module defines the syntax for using [namespaces](https://developer.mozilla.org/en-US/docs/Glossary/Namespace) in CSS.

CSS isn't just for styling HTML. A stylesheet may be used to style SVG, MathML, XML, or HTML, each of which has a different namespace or a document containing multiple namespaces.

The [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace) at-rule defined in this module enables distinguishing between same-named elements in different namespaces. Element tag names are not unique to a single language. For example, the `<a>` element isn't limited to HTML. You may want to style the `<a>` s within your SVGs differently from the links in your HTML. You also will likely want to ensure that [`querySelectorAll("a")`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll "querySelectorAll(\"a\")") selects the right kind of element. Namespacing can help.

The `@namespace` rule is used for declaring a default namespace and for binding namespaces to namespace prefixes. The namespaces module also defines the syntax for using these prefixes to represent namespace-qualified names. That's it. What a name means or if the name is even valid depends on the context and host language.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#reference)

### [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#at-rules)

- [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#guides)

[Namespaces crash course](https://developer.mozilla.org/en-US/docs/Web/SVG/Guides/Namespaces_crash_course)

Deep dive into what a namespace is and how they are used in XML and XML-based markup languages.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#related_concepts)

- CSS [namespace separator ( `|`)](https://developer.mozilla.org/en-US/docs/Web/CSS/Namespace_separator) combinator
- CSS [type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)
- CSS [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)
- [`CSSNamespaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule) interface

  - [`CSSNamespaceRule.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/namespaceURI) property
  - [`CSSNamespaceRule.prefix`](https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/prefix) property
- [`Document.createAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttributeNS) method
- [`Document.createElementNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS) method
- [`Document.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS) method
- [`Element.getAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS) method
- [`Element.getAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS) method
- [`Element.getElementsByTagNameNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS) method
- [`Element.hasAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributeNS) method
- [`Element.namespaceURI`](https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI) property
- [`Element.removeAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNS) method
- [`Element.setAttributeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS) method
- [`Element.setAttributeNodeNS()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNodeNS) method
- [`NamedNodeMap.getNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/getNamedItemNS) method
- [`NamedNodeMap.removeNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/removeNamedItemNS) method
- [`NamedNodeMap.setNamedItemNS()`](https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap/setNamedItemNS) method
- [Namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace) glossary term

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#specifications)

| Specification |
| --- |
| [CSS Namespaces Module Level 3](https://drafts.csswg.org/css-namespaces/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces\#see_also)

- [`<a>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/a#example) SVG element
- [CSS `<url>` type](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)
- [CSS at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule)
- [CSS at-rule functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule_functions)
- [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_namespaces/index.md?plain=1 "Folder: ⁨en-us/web/css/css_namespaces⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_namespaces&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_namespaces%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_namespaces%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_namespaces%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")