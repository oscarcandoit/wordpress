---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/@import
scraped_at: 2025-10-20T02:59:22.482Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# @import


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40import&level=high)

The **`@import`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule) is used to import style rules from other valid stylesheets.
An `@import` rule _must_ be defined at the top of the stylesheet, before any other at-rule (except [@charset](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset) and [@layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer)) and style declarations, or it will be ignored.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#syntax)

cssCopy

```
@import url;
@import url layer;
@import url layer(layer-name);
@import url layer(layer-name) supports(supports-condition);
@import url layer(layer-name) supports(supports-condition) list-of-media-queries;
@import url layer(layer-name) list-of-media-queries;
@import url supports(supports-condition);
@import url supports(supports-condition) list-of-media-queries;
@import url list-of-media-queries;

```

where:

[_url_](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#url)

Is a [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string) or a [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) type representing the location of the resource to import. The URL may be absolute or relative.

[_list-of-media-queries_](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#list-of-media-queries)

Is a comma-separated list of [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries), which specify the media-dependent conditions for applying the CSS rules defined in the linked URL. If the browser does not support any of these queries, it does not load the linked resource.

[_layer-name_](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#layer-name)

Is the name of a [cascade layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer) into which the contents of the linked resource are imported. See [`layer()`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import/layer_function) for more information.

[_supports-condition_](https://developer.mozilla.org/en-US/docs/Web/CSS/@import#supports-condition)

Indicates the feature(s) that the browser must support in order for the stylesheet to be imported.
If the browser does not conform to the conditions specified in the _supports-condition_, it may not fetch the linked stylesheet, and even if downloaded through some other path, will not load it.
The syntax of `supports()` is almost identical to that described in [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports), and that topic can be used as a more complete reference.

Use `@import` together with the `layer` keyword or `layer()` function to import external style sheets (from frameworks, widget stylesheets, libraries, etc.) into layers.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#description)

Imported rules must come before all other types of rules, except [`@charset`](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset) rules and layer creating [`@layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer) statements.

cssCopy

```
* {
  margin: 0;
  padding: 0;
}
/* more styles */
@import "my-imported-styles.css";

```

As the `@import` at-rule is declared after the styles it is invalid and hence ignored.

cssCopy

```
@import "my-imported-styles.css";
* {
  margin: 0;
  padding: 0;
}
/* more styles */

```

The `@import` rule is not a [nested statement](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax#nested_statements). Therefore, it cannot be used inside [conditional group at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules#at-rules).

So that [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) can avoid retrieving resources for unsupported media types, authors may specify media-dependent import conditions. These conditional imports specify comma-separated [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) after the URL. In the absence of any media query, the import is not conditional on the media used. Specifying `all` for the `list-of-media-queries` has the same effect.

Similarly, user agents can use the `supports()` function in an `@import` at-rule to only fetch resources if a particular feature set is (or is not) supported.
This allows authors to take advantage of recently introduced CSS features, while providing graceful fallbacks for older browser versions.
Note that the conditions in the `supports()` function of an `@import` at-rule can be obtained in JavaScript using [`CSSImportRule.supportsText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSImportRule/supportsText).

The `@import` rule can also be used to create a [cascade layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer) by importing rules from a linked resource. Rules can also be imported into an existing cascade layer. The `layer` keyword or the `layer()` function is used with `@import` for this purpose. Declarations in style rules from imported stylesheets interact with the cascade as if they were written literally into the stylesheet at the point of the import.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#formal_syntax)

```
@import =
  @import [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  layer  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  layer( <layer-name> )  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <import-conditions> ;

<layer-name> =
  [<ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/ident)  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '.' [<ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/ident)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<import-conditions> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  supports(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <supports-condition>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") <declaration>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") )  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") <media-query-list> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<supports-condition> =
  not <supports-in-parens>                             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-in-parens>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  and <supports-in-parens>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-in-parens>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  or <supports-in-parens>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<supports-in-parens> =
  ( <supports-condition> )   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-feature>         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <general-enclosed>

<supports-feature> =
  <supports-selector-fn>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-font-tech-fn>     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-font-format-fn>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-at-rule-fn>       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <supports-decl>

<general-enclosed> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") <function-token> <any-value> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") ( <any-value> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

<supports-selector-fn> =
  selector( <complex-selector> )

<supports-font-tech-fn> =
  font-tech( <font-tech> )

<supports-font-format-fn> =
  font-format( <font-format> )

<supports-at-rule-fn> =
  at-rule( <at-keyword-token> )

<supports-decl> =
  ( <declaration> )

<complex-selector> =
  <complex-selector-unit>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <combinator> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <complex-selector-unit>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<font-tech> =
  <font-features-tech>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <color-font-tech>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  variations             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  palettes               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  incremental

<font-format> =
  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  collection          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  embedded-opentype   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  opentype            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  svg                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  truetype            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  woff                [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  woff2

<complex-selector-unit> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <compound-selector> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <pseudo-compound-selector> [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")!

<combinator> =
  '>'          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  '+'          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  '~'          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '|' '|' [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

<font-features-tech> =
  features-opentype   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  features-aat        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  features-graphite

<color-font-tech> =
  color-COLRv0   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  color-COLRv1   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  color-SVG      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  color-sbix     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  color-CBDT

<compound-selector> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <type-selector> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <subclass-selector> [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")!

<pseudo-compound-selector> =
  <pseudo-element-selector> <pseudo-class-selector> [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<type-selector> =
  <wq-name>          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <ns-prefix> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") '*'

<subclass-selector> =
  <id-selector>             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <class-selector>          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <attribute-selector>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <pseudo-class-selector>

<pseudo-element-selector> =
  : <pseudo-class-selector>          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <legacy-pseudo-element-selector>

<pseudo-class-selector> =
  : <ident-token>                    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  : <function-token> <any-value> )

<wq-name> =
  <ns-prefix> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") <ident-token>

<ns-prefix> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") <ident-token>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '*' [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") '|'

<id-selector> =
  <hash-token>

<class-selector> =
  '.' <ident-token>

<attribute-selector> =
  '[' <wq-name> ']'                                   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  '[' <wq-name> <attr-matcher>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") <string-token>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") <ident-token>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <attr-modifier> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") ']'

<legacy-pseudo-element-selector> =
  : [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  before  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  after  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  first-line  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  first-letter  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

<attr-matcher> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '~' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '|' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '^' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '$' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '*' [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") '='

<attr-modifier> =
  i   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  s

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#examples)

### [Importing CSS rules](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#importing_css_rules)

cssCopy

```
@import "custom.css";
@import url("chrome://communicator/skin/");

```

The two examples above show how to specify the _url_ as a `<string>` and as a `url()` function.

### [Importing CSS rules conditional on media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#importing_css_rules_conditional_on_media_queries)

cssCopy

```
@import "fine-print.css" print;
@import "bluish.css" print, screen;
@import "common.css" screen;
@import "landscape.css" screen and (orientation: landscape);

```

The `@import` rules in the above examples show media-dependent conditions that will need to be true before the linked CSS rules are applied. So for instance, the last `@import` rule will load the `landscape.css` stylesheet only on a screen device in landscape orientation.

### [Importing CSS rules conditional on feature support](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#importing_css_rules_conditional_on_feature_support)

cssCopy

```
@import "grid.css" supports(display: grid) screen and (width <= 400px);
@import "flex.css" supports((not (display: grid)) and (display: flex)) screen
  and (width <= 400px);

```

The `@import` rules above illustrate how you might import a layout that uses a grid if `display: grid` is supported, and otherwise imports CSS that uses `display: flex`.
While you can only have one `supports()` statement, you can combine any number of feature checks with `not`, `and`, and `or`. However, you must use parenthesis to define precedence when you mix them, e.g., `supports((..) or (..) and not (..))` is invalid, but `supports((..) or ((..) and (not (..))))` is valid.
Note that if you just have a single declaration then you don't need to wrap it in additional parentheses: this is shown in the first example above.

The examples above show support conditions using basic declaration syntax.
You can also specify CSS functions in `supports()`, and it will evaluate to `true` if they are supported and can be evaluated on the user-agent.
For example, the code below shows an `@import` that is conditional on both [child combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator) ( `selector()`) and the `font-tech()` function:

cssCopy

```
@import "whatever.css"
  supports((selector(h2 > p)) and (font-tech(color-COLRv1)));

```

### [Importing CSS rules into a cascade layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#importing_css_rules_into_a_cascade_layer)

cssCopy

```
@import "theme.css" layer(utilities);

```

In the above example, a cascade layer named `utilities` is created and it will include rules from the imported stylesheet `theme`.

cssCopy

```
@import "headings.css" layer(default);
@import "links.css" layer(default);

@layer default {
  audio[controls] {
    display: block;
  }
}

```

In the above example, the rules in `headings.css` and `links.css` stylesheets cascade within the same layer as the `audio[controls]` rule.

cssCopy

```
@import "theme.css" layer();
@import "style.css" layer;

```

This is an example of creating two separate unnamed cascade layers and importing the linked rules into each one separately. A cascade layer declared without a name is an unnamed cascade layer. Unnamed cascade layers are finalized when created: they do not provide any means for re-arranging or adding styles and they cannot be referenced from outside.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#specifications)

| Specification |
| --- |
| [CSS Cascading and Inheritance Level 5\<br>\# at-import](https://drafts.csswg.org/css-cascade-5/#at-import) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/@import# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/at-rules/import.json "File: ⁨css/at-rules/import.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `@import` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera3.5<br>Opera – Full support<br>Opera3.5 (Release date: ⁨1998-11-18⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| [`layer()`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import/layer_function) | Chrome – Full support<br>Chrome99<br>Chrome – Full support<br>Chrome99 (Release date: ⁨2022-03-01⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge99<br>Edge – Full support<br>Edge99 (Release date: ⁨2022-03-03⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox97<br>Firefox – Full support<br>Firefox97 (Release date: ⁨2022-02-08⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera85<br>Opera – Full support<br>Opera85 (Release date: ⁨2022-03-23⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android99<br>Chrome Android – Full support<br>Chrome Android99 (Release date: ⁨2022-03-01⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android97<br>Firefox for Android – Full support<br>Firefox for Android97 (Release date: ⁨2022-02-08⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android68<br>Opera Android – Full support<br>Opera Android68 (Release date: ⁨2022-03-30⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet18<br>Samsung Internet – Full support<br>Samsung Internet18 (Release date: ⁨2022-08-08⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android99<br>WebView Android – Full support<br>WebView Android99 (Release date: ⁨2022-03-01⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |
| `supports()` as import condition | Chrome – Full support<br>Chrome122<br>footnote<br>Chrome – Full support<br>Chrome122 (Release date: ⁨2024-02-20⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | Edge – Full support<br>Edge122<br>footnote<br>Edge – Full support<br>Edge122 (Release date: ⁨2024-02-23⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | Firefox – Full support<br>Firefox115<br>Firefox – Full support<br>Firefox115 (Release date: ⁨2023-07-04⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera108<br>footnote<br>Opera – Full support<br>Opera108 (Release date: ⁨2024-03-05⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | Safari – Full support<br>Safari17.5<br>Safari – Full support<br>Safari17.5 (Release date: ⁨2024-05-13⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android122<br>footnote<br>Chrome Android – Full support<br>Chrome Android122 (Release date: ⁨2024-02-20⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | Firefox for Android – Full support<br>Firefox for Android115<br>Firefox for Android – Full support<br>Firefox for Android115 (Release date: ⁨2023-07-04⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android81<br>footnote<br>Opera Android – Full support<br>Opera Android81 (Release date: ⁨2024-03-14⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | Safari on iOS – Full support<br>Safari on iOS17.5<br>Safari on iOS – Full support<br>Safari on iOS17.5 (Release date: ⁨2024-05-13⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet26<br>footnote<br>Samsung Internet – Full support<br>Samsung Internet26 (Release date: ⁨2024-06-07⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | WebView Android – Full support<br>WebView Android122<br>footnote<br>WebView Android – Full support<br>WebView Android122 (Release date: ⁨2024-02-20⁩)<br> <br>footnote<br>footnoteSee [⁨bug 40244647⁩](https://crbug.com/40244647) | WebView on iOS – Full support<br>WebView on iOS17.5<br>WebView on iOS – Full support<br>WebView on iOS17.5 (Release date: ⁨2024-05-13⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

See implementation notes.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/@import\#see_also)

- [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
- [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)
- [CSS cascading and inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade) module
- [CSS at-rule functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule_functions)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/@import/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/@import/index.md?plain=1 "Folder: ⁨en-us/web/css/@import⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40import&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F%40import%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40import%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F%40import%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9944f7b12ef1a6aecd54d4b2f0c188a82fdeaaf0%0A*+Document+last+modified%3A+2025-08-05T13%3A32%3A56.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")