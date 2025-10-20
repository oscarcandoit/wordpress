---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule
scraped_at: 2025-10-20T02:58:53.759Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_syntax%2FAt-rule "Take survey (Opens in a new tab)")

# At-rules

**At-rules** are [CSS statements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax#css_statements) that instruct CSS how to behave. They begin with an at-sign, `@` (U+0040 COMMERCIAL AT), followed by an identifier. They include everything from the at-keyword up to the next semicolon, `;` (U+003B SEMICOLON), or the next [CSS block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax#css_declaration_blocks), whichever comes first.

At-rules are used to group and structure style rules and other at-rules, declare style information not directly associated with selected content, and manage syntactic constructs such as imports and namespaces keyword mappings.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#syntax)

The at-rule is defined in the [CSS syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax) module, with different at-rules being defined in their respective modules. They generally take one of two forms depending on the specific rule and its purpose: statement at-rules and block at-rules, which can contain nested qualified rules, at-rules, or declarations.

### [Statement at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#statement_at-rules)

cssCopy

```
/* General structure */
@identifier (RULE);

/* Example: tells browser to use UTF-8 character set */
@charset "utf-8";

```

Statement at-rules end in a semicolon. There are several statement at-rules, designated by their identifiers, each with a different syntax:

[`@charset`](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset)

An algorithm (has the syntactic form of an at-rule, but isn't a definition) that determines the fallback character set used by the style sheet ( [CSS Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax)).

[`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)

Tells the CSS engine to include an external style sheet ( [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade)).

[`@layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer)

Defines the order of precedence in case of multiple cascade layers ( [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade)). Also used as a [block at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule#layer_2) to define a layer's styles.

[`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace)

Defines a default namespace for a style sheet or a namespace prefix that a selector only matches if the namespace and other selector components match ( [CSS namespaces](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_namespaces)).

### [Block at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#block_at-rules)

cssCopy

```
@identifier (RULE) {
}

```

Block at-rules end in a `{}`-block that contain nested rules, other at-rules, or property or descriptor declarations.

[`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style)

Define custom counter styles and extend predefined list styles ( [CSS counter styles](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles)).

[`@container`](https://developer.mozilla.org/en-US/docs/Web/CSS/@container)

A conditional group rule that applies its content if the container meets the [`<container-condition>`](https://developer.mozilla.org/en-US/docs/Web/CSS/@container#container-condition) s ( [CSS containment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment)).

[`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)

Defines font resource locations, both local and external, along with the style characteristics for when those resources are used with a declared [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) ( [CSS fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts)).

[`@font-feature-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values) (plus `@swash`, `@ornaments`, `@annotation`, `@stylistic`, `@styleset` and `@character-variant`)

Controls font display per font-family by defining font-specific alternates, or custom names, to feature indexes in [`font-variant-alternates`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-alternates) in OpenType ( [CSS fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts)).

[`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) (and the `@-webkit-keyframes` alias)

Define a named animation by describing defining CSS styles for intermediate steps (or keyframes) in the animation sequence ( [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations)).

[`@layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer)

Creates a named cascade layer with the CSS rules for that layer inside ( [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade)). Also used as a [statement at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule#layer) to define the order of precedence in case of multiple cascade layers

[`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)

A conditional group rule that applies its content if the device meets the criteria of the condition defined using a _media query_ ( [CSS conditional rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules)).

[`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page)

Specifies aspects of a page to be printed, such as its dimensions, orientation, and margins ( [CSS paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_paged_media)).

[`@position-try`](https://developer.mozilla.org/en-US/docs/Web/CSS/@position-try)

Defines custom position options which can be used to define fallback positioning and alignment options for anchor-positioned elements ( [CSS anchor positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_anchor_positioning)).

[`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property)

Defines a [CSS custom property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties), allowing for property type checking and constraining, setting default values, and defining whether a custom property can inherit values or not ( [CSS custom properties for cascading variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables)).

[`@scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/@scope)

Defines a scope in which to apply them to selected elements and the styles to apply to the elements in that scope ( [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade)).

[`@starting-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style)

Define the starting property values for an element to transition from when the element receives its first style update, such as when transitioning from `display: none` ( [CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions)).

[`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)

A conditional group rule applies its content if the browser supports the CSS features of the given condition ( [CSS conditional rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules)).

[`@view-transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/@view-transition)

Opts the current document into a [view transition](https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API), and the destination document as well in the case of cross-document navigation transitions.

## [Index](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#index)

- [`@charset`](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset)
- [`@color-profile`](https://developer.mozilla.org/en-US/docs/Web/CSS/@color-profile)
- [`@container`](https://developer.mozilla.org/en-US/docs/Web/CSS/@container)
- [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style)
- [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
- [`@font-feature-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values)
- [`@font-palette-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values)
- [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)
- [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
- [`@layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer)
- [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
- [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace)
- [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page)
- [`@position-try`](https://developer.mozilla.org/en-US/docs/Web/CSS/@position-try)
- [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property)
- [`@scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/@scope)
- [`@starting-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style)
- [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)
- [`@view-transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/@view-transition)

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#specifications)

| Specification |
| --- |
| [CSS Syntax Module Level 3](https://drafts.csswg.org/css-syntax/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule\#see_also)

- [CSS at-rule functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule_functions)
- [Nesting CSS at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting/Nesting_at-rules)
- [CSS statements](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax#css_statements)
- [CSSRule](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule) interface
- [CSS conditional rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules) module
- [CSS syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax)
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
- [Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_syntax/at-rule/index.md?plain=1 "Folder: ⁨en-us/web/css/css_syntax/at-rule⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_syntax%2FAt-rule&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_syntax%2Fat-rule%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_syntax%2FAt-rule%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_syntax%2Fat-rule%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")