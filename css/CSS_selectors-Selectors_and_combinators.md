---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators
scraped_at: 2025-10-20T03:13:03.741Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators#search)

# CSS selectors and combinators

CSS selectors are used to define a pattern of the elements that you want to select for applying a set of CSS rules on the selected elements. Combinators define the relationship between the selectors. Using various selectors and combinators, you can precisely select and style the desired elements based on their type, attributes, state, or relationship to other elements.

## [Types of selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#types_of_selectors)

There are over 80 selectors and combinators. CSS selectors can be grouped into the following categories based on the type of elements they can select.

### [Basic selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#basic_selectors)

The [type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors) selects all elements that have the given node name. For example, `div` will select all [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) elements and `input` will match any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) element. The [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors), denoted with an asterisk ( `*`), is a special type selector that selects all elements.

The [class selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) selects all elements that have the given `class` attribute denoted by the class name prefixed with a period ( `.`). For example, `.index` will match any element that has `class="index"`. The [ID selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors) selects an element based on the value of its `id` attribute. The selector is the `id` prefixed with a "number sign" (U+0023, `#`). For example, `#toc` will match the element that has `id="toc"`. Both [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/class) and [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/id) are global attributes. There should be only one element with a given `id` in a document; but if there is more than one, the ID selector will match all the elements with that `id`.

When combining a type or universal selector with a class or id selector to create a [compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector), the type or universal selector must precede the class or id.

#### CSS

In this example, we declare four [simple selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector) and one [compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector) using the four basic selector types, as described above.

css

```
* {
  font-style: italic;
}
p {
  color: red;
}
.myClass {
  text-decoration: underline;
}
#myId {
  font-family: monospace;
}
p.myClass#myId {
  font-size: 1.5rem;
}

```

#### HTML

html

```
<p class="myClass" id="myId">I match everything.</p>
<p>I match the universal and type selectors only.</p>

```

#### Result

## [Combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#combinators)

Using CSS combinators, we can combine selectors to select DOM nodes based on their relationship to other elements within the document node tree. This combining of selectors with combinators creates [complex selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#complex_selector).

### [Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#descendant_combinator)

The [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator), denoted with one or more spaces, selects nodes that are descendants of the first element. For example, `div span` will match all [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/span) elements that are inside a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) element.

### [Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#child_combinator)

The [child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator) is more specific than the descendant combinator. Denoted with the greater than character ( `>`), the child combinator selects nodes that are direct children of the first element. Comparing with our previous example, `div > span` will match only the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/span) elements that are direct children of a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) element.

### [Subsequent-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#subsequent-sibling_combinator)

In addition to descendant selectors, CSS also enables selecting elements based on their siblings. The [subsequent-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Subsequent-sibling_combinator), denoted with a tilde ( `~`), selects siblings. Given `A ~ B`, all elements matching `B` will be selected if they are preceded by `A`, provided both `A` and `B` share the same parent. For example, `h2 ~ p` will match all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/p) elements that follow an [h2](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/Heading_Elements), immediately or not.

### [Next-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#next-sibling_combinator)

The [next-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator), denoted by the plus symbol ( `+`), is similar to the subsequent-sibling. However, given `A + B`, it only matches `B` if `B` is immediately preceded by `A`, with both sharing the same parent. Amending our previous example, `h2 + p` will match only the single `<p>` element that _immediately_ follows an `<h2>` element.

### [Column combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#column_combinator)

There is also a [column combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator), denoted by two pipe characters ( `||`), which, when supported, selects nodes that belong to a column. For example, `col || td` will match all [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/td) elements that belong to the scope of the [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/col).

### [Namespace separator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#namespace_separator)

The [namespace separator](https://developer.mozilla.org/en-US/docs/Web/CSS/Namespace_separator) is another combinator that is generally used in conjunction with the [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace) at-rule. This combinator is denoted by a single pipe character ( `|`). It enables limiting [type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors) and the [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors) to a specific namespace. For example, by defining a namespace such as `@namespace SVG url('http://www.w3.org/2000/svg');`, you can include selectors that target elements nested in an SVG namespace only. Declaring `SVG|a` would match links within SVGs and not those in the rest of the document. Namespacing can be useful to target MathML, SVG, or other XML-based content within your HTML.

#### CSS

In this example, we declare five [relative selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#relative_selector) using [simple selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector) combined with combinators.

css

```
h2 + p ~ p {
  font-style: italic;
}
h2 + p + p {
  color: red;
}
.myClass + p {
  text-decoration: underline;
}
#myId > .myClass {
  outline: 3px dashed red;
}
* > p {
  font-size: 1.1rem;
}

```

#### HTML

html

```
<h2 class="myClass" id="myId">
  No selectors match. <span class="myClass">This span has an outline</span> as
  it is both myClass and a child of #myId.
</h2>
<p>The first paragraph is underlined. All the paragraphs are 1.1rem.</p>
<p>
  The second paragraph is red. This and the following paragraphs are italic.
</p>
<p>The third paragraph is NOT red. It is italic and 1.1rem.</p>
<p class="myClass">
  Does not have an outline; this is a sibling of H2, not a child. It is italic
  and 1.1rem.
</p>

```

#### Result

### [Creating complex selectors with CSS nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#creating_complex_selectors_with_css_nesting)

The above complex selectors can also be defined using simple selectors, combinators, and [CSS nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting), with or without the [`&` nesting selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Nesting_selector).

#### CSS

In this example, we replicate the same five relative selectors using simple selectors combined with combinators, but this time with CSS nesting.

css

```
h2 {
  & + p {
    & ~ p {
      font-style: italic;
    }
    & + p {
      color: red;
    }
  }
}
.myClass {
  & + p {
    text-decoration: underline;
  }
}
#myId {
  & > .myClass {
    outline: 3px dashed red;
  }
}
* {
  & > p {
    font-size: 1.1rem;
  }
}

```

#### HTML

html

```
<h2 class="myClass" id="myId">
  No selectors match. <span class="myClass">This span has an outline</span> as
  it is both myClass and a child of #myId.
</h2>
<p>The first paragraph is underlined. All the paragraphs are 1.1rem.</p>
<p>
  The second paragraph is red. This and the following paragraphs are italic.
</p>
<p>The third paragraph is NOT red. It is italic and 1.1rem.</p>
<p class="myClass">
  Does not have an outline; this is a sibling of H2, not a child. It is italic
  and 1.1rem.
</p>

```

#### Result

## [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#attribute_selectors)

[Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) select all elements that, depending on how the selector is written, either have the given attribute or have the given attribute with a substring value match.
For example, `[type]` will match all elements that have the `type` attribute set (to any value), and `[type="submit"]` will match `<input type="submit">` and `<button type="submit">`, or any element with `type="submit"` set, even though this attribute-value pair is only supported on [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) and [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/button) elements. The match is case-insensitive.

The case sensitivity of the attribute depends on the language. Generally, in HTML, if an attribute is [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated), the value in the selector is case-insensitive, even if the value is not one of the enumerated values or if the attribute is not a valid value for the element on which it is set. For non-enumerated attributes, like `class`, `id`, or any `data-*` attribute, or for non-HTML attributes, like `role` or `aria-*` attributes, the value match is case-sensitive; the match can be made case-insensitive with a case-insensitive modifier ( `i`).

## [Pseudo-class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#pseudo-class_selectors)

The [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors) module defines over 60 [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes). Pseudo-classes are [simple selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#simple_selector), prefixed with a colon ( `:`), that allow the selection of elements based on state information that is not contained in the document tree. [`pseudo-classes`](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) can be used to style an element based on its _state_.
For example, the [`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target) simple selector targets element of a URL containing a fragment identifier, and the [`a:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited) [compound selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector) matches all [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a) elements that have been visited by a user.

The pseudo-classes can be categorized as [element display state](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#element_display_state_pseudo-classes), [input](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#input_pseudo-classes), [linguistic](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#linguistic_pseudo-classes), [location](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#location_pseudo-classes), [resource state](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#resource_state_pseudo-classes), [time-dimensional](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#time-dimensional_pseudo-classes), [tree-structural](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#tree-structural_pseudo-classes), [user action](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#user_action_pseudo-classes), and [functional](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#functional_pseudo-classes).

Multiple pseudo-classes can be combined to create [compound selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure#compound_selector). When combining a pseudo-class into a compound selector with a type or universal selector, the pseudo-class must follow the type selector or universal selector, if present.

## [Pseudo-element selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#pseudo-element_selectors)

Not all CSS selectors are defined in the [CSS selectors module](https://developer.mozilla.org/en-US/docs/Web/CSS). CSS pseudo-element selectors are defined in the [CSS pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements) module.

CSS [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements), prefixed with two colons ( `::`), represent entities that are not included in HTML. For example, the simple [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker) selector selects list item bullets, and the compound selector [`p::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line) matches the first line of all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/p) elements.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#specifications)

| Specification |
| --- |
| [Selectors Level 4](https://drafts.csswg.org/selectors/) |
| [CSS Pseudo-Elements Module Level 4](https://drafts.csswg.org/css-pseudo/) |

See the [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#specifications) and [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements#specifications) specification tables for details on those.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators\#see_also)

- [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list)
- [CSS selector structure](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selector_structure)
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
- [CSS nesting module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_selectors/selectors_and_combinators/index.md?plain=1 "Folder: ⁨en-us/web/css/css_selectors/selectors_and_combinators⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FSelectors_and_combinators&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_selectors%2Fselectors_and_combinators%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_selectors%2FSelectors_and_combinators%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_selectors%2Fselectors_and_combinators%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")