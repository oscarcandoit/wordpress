---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap
scraped_at: 2025-10-20T03:14:52.586Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#search)

# overflow-wrap


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨October 2018⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-wrap&level=high)

The **`overflow-wrap`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies to text, setting whether the browser should insert line breaks within an otherwise unbreakable string to prevent text from overflowing its line box.

**Note:**
The property was originally a nonstandard and unprefixed Microsoft extension called `word-wrap`, and was implemented by most browsers with the same name. It has since been renamed to `overflow-wrap`, with `word-wrap` being an alias.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#try_it)

```
overflow-wrap: normal;

```

```
overflow-wrap: anywhere;

```

```
overflow-wrap: break-word;

```

```
<section class="default-example" id="default-example">
  <div class="example-container">
    Most words are short &amp; don't need to break. But
    <strong class="transition-all" id="example-element"
      >Antidisestablishmentarianism</strong
    >
    is long. The width is set to min-content, with a max-width of 11em.
  </div>
</section>

```

```
.example-container {
  background-color: rgb(255 0 200 / 0.2);
  border: 3px solid rebeccapurple;
  padding: 0.75em;
  width: min-content;
  max-width: 11em;
  height: 200px;
}

```

**Note:**
In contrast to [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break), `overflow-wrap` will only create a break if an entire word cannot be placed on its own line without overflowing.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#syntax)

css

```
/* Keyword values */
overflow-wrap: normal;
overflow-wrap: break-word;
overflow-wrap: anywhere;

/* Global values */
overflow-wrap: inherit;
overflow-wrap: initial;
overflow-wrap: revert;
overflow-wrap: revert-layer;
overflow-wrap: unset;

```

The `overflow-wrap` property is specified as a single keyword chosen from the list of values below.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#values)

[`normal`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#normal)

Lines may only break at normal word break points (such as a space between two words).

[`anywhere`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#anywhere)

To prevent overflow, an otherwise unbreakable string of characters — like a long word or URL — may be broken at any point if there are no otherwise-acceptable break points in the line. No hyphenation character is inserted at the break point. Soft wrap opportunities introduced by the word break are considered when calculating min-content intrinsic sizes.

[`break-word`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap#break-word)

The same as the `anywhere` value, with normally unbreakable words allowed to be broken at arbitrary points if there are no otherwise acceptable break points in the line, but soft wrap opportunities introduced by the word break are NOT considered when calculating min-content intrinsic sizes.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `normal` |
| Applies to | text elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#formal_syntax)

```
overflow-wrap =
  normal       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  break-word   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  anywhere

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#examples)

### [Comparing overflow-wrap, word-break, and hyphens](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#comparing_overflow-wrap_word-break_and_hyphens)

This example compares the results of `overflow-wrap`, `word-break`, and `hyphens` when breaking up a long word.

#### HTML

html

```
<p>
  They say the fishing is excellent at Lake
  <em class="normal">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>normal</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="ow-anywhere">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: anywhere</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="ow-break-word">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: break-word</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="word-break">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>word-break</code>)
</p>
<p>
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, without
  <code>lang</code> attribute)
</p>
<p lang="en">
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, English rules)
</p>
<p class="hyphens" lang="de">
  They say the fishing is excellent at Lake
  <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>, though
  I've never been there myself. (<code>hyphens</code>, German rules)
</p>

```

#### CSS

css

```
p {
  width: 13em;
  margin: 2px;
  background: gold;
}

.ow-anywhere {
  overflow-wrap: anywhere;
}

.ow-break-word {
  overflow-wrap: break-word;
}

.word-break {
  word-break: break-all;
}

.hyphens {
  hyphens: auto;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#specifications)

| Specification |
| --- |
| [CSS Text Module Level 3\<br>\# overflow-wrap-property](https://drafts.csswg.org/css-text/#overflow-wrap-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap\#see_also)

- [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
- [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- [`hyphens`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)
- [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)
- [Guide to wrapping and breaking text](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_text/Wrapping_breaking_text)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 9, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/overflow-wrap/index.md?plain=1 "Folder: ⁨en-us/web/css/overflow-wrap⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-wrap&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foverflow-wrap%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foverflow-wrap%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foverflow-wrap%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F4ec412012be0b083ebcae4a56b425f49901143f2%0A*+Document+last+modified%3A+2025-08-09T02%3A18%3A08.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")