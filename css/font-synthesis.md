---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis
scraped_at: 2025-10-20T03:18:52.730Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#search)

# font-synthesis


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨January 2022⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffont-synthesis&level=high)

The **`font-synthesis`** [shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets you specify whether or not the browser may synthesize the bold, italic, small-caps, and/or subscript and superscript typefaces when they are missing in the specified font-family.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#try_it)

```
font-synthesis: weight style small-caps;

```

```
font-synthesis: none;

```

```
font-synthesis: weight;

```

```
font-synthesis: style;

```

```
font-synthesis: small-caps;

```

```
font-synthesis: position;

```

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    <p class="english">
      This font does not include <span class="bold">bold</span>,
      <span class="italic">italic</span>,
      <span class="small-caps">small-caps</span>, and
      <span class="sub">subscript</span> or
      <span class="sup">superscript</span> variants.
    </p>
    <p class="chinese">
      中文排版通常不运用<span class="bold">粗体</span>或<span class="italic"
        >斜体</span
      ><span class="sub">常不</span><span class="sup">运用</span>。
    </p>
  </div>
</section>

```

```
@font-face {
  font-family: "Oxygen";
  font-style: normal;
  font-weight: normal;
  src: url("https://fonts.gstatic.com/s/oxygen/v14/2sDfZG1Wl4LcnbuKjk0m.woff2")
    format("woff2");
}

/* [108] */
@font-face {
  font-family: "Ma Shan Zheng";
  font-style: normal;
  font-weight: normal;
  font-display: swap;
  src: url("https://fonts.gstatic.com/s/mashanzheng/v10/NaPecZTRCLxvwo41b4gvzkXaRMGEFoZJFdX0wQ5Xo5Hr21L9zCcRFhbSe5Nk0pIMuUkHEA.108.woff2")
    format("woff2");
}
/* [110] */
@font-face {
  font-family: "Ma Shan Zheng";
  font-style: normal;
  font-weight: normal;
  font-display: swap;
  src: url("https://fonts.gstatic.com/s/mashanzheng/v10/NaPecZTRCLxvwo41b4gvzkXaRMGEFoZJFdX0wQ5Xo5Hr21L9zCcRFhbSe5Nk0pIMuUkHEA.110.woff2")
    format("woff2");
}
/* [117] */
@font-face {
  font-family: "Ma Shan Zheng";
  font-style: normal;
  font-weight: normal;
  font-display: swap;
  src: url("https://fonts.gstatic.com/s/mashanzheng/v10/NaPecZTRCLxvwo41b4gvzkXaRMGEFoZJFdX0wQ5Xo5Hr21L9zCcRFhbSe5Nk0pIMuUkHEA.117.woff2")
    format("woff2");
}
/* [118] */
@font-face {
  font-family: "Ma Shan Zheng";
  font-style: normal;
  font-weight: normal;
  font-display: swap;
  src: url("https://fonts.gstatic.com/s/mashanzheng/v10/NaPecZTRCLxvwo41b4gvzkXaRMGEFoZJFdX0wQ5Xo5Hr21L9zCcRFhbSe5Nk0pIMuUkHEA.118.woff2")
    format("woff2");
}
/* [119] */
@font-face {
  font-family: "Ma Shan Zheng";
  font-style: normal;
  font-weight: normal;
  font-display: swap;
  src: url("https://fonts.gstatic.com/s/mashanzheng/v10/NaPecZTRCLxvwo41b4gvzkXaRMGEFoZJFdX0wQ5Xo5Hr21L9zCcRFhbSe5Nk0pIMuUkHEA.119.woff2")
    format("woff2");
}

.english {
  font-size: 1.2em;
  font-family: "Oxygen", sans-serif;
}

.chinese {
  font-size: 1.2em;
  font-family: "Ma Shan Zheng", cursive;
}

.bold {
  font-weight: bold;
}

.italic {
  font-style: italic;
}

.small-caps {
  font-variant: small-caps;
}

.sub {
  font-variant: sub;
}

.sup {
  font-variant: super;
}

```

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [font-synthesis-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-weight)
- [font-synthesis-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-style)
- [font-synthesis-small-caps](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-small-caps)
- [font-synthesis-position](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-position)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#syntax)

css

```
/* none or one or more of the other keyword values */
font-synthesis: none;
font-synthesis: weight;
font-synthesis: style;
font-synthesis: position;
font-synthesis: small-caps style; /* property values can be in any order */
font-synthesis: style small-caps weight position; /* property values can be in any order */

/* Global values */
font-synthesis: inherit;
font-synthesis: initial;
font-synthesis: revert;
font-synthesis: revert-layer;
font-synthesis: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#values)

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#none)

Indicates that no bold, italic, or small-caps typeface may be synthesized by the browser.

[`weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#weight)

Indicates that the missing bold typeface may be synthesized by the browser if needed.

[`style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#style)

Indicates that the italic typeface may be synthesized by the browser if needed.

[`small-caps`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#small-caps)

Indicates that the small-caps typeface may be synthesized by the browser if needed.

[`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis#position)

Indicates that the subscript and superscript typeface may be synthesized by the browser, if needed, when using [`font-variant-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-position).

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#description)

Most standard Western fonts include italic and bold variants, and some fonts include a small-caps and subscript/superscript variants. However, many fonts do not. Fonts used for Chinese, Japanese, Korean and other logographic scripts tend not to include these variants and synthesizing them might impede the legibility or change the meaning of the text. In these cases, it may be desirable to switch off the browser's default font-synthesis.

For example, using the [:lang()](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang) pseudo-class, you can disable the browser from synthesizing bold and oblique characters for a language, in this case Arabic:

css

```
*:lang(ar) {
  font-synthesis: none;
}

```

The table below shows how a value of the shorthand `font-synthesis` property maps to the constituent longhand properties.

| font-synthesis value | [font-synthesis-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-weight) value | [font-synthesis-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-style) value | [font-synthesis-small-caps](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-small-caps) value | [font-synthesis-position](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-position) value |
| :-- | :-- | :-- | :-- | :-- |
| `none` | `none` | `none` | `none` | `none` |
| `weight` | `auto` | `none` | `none` | `none` |
| `style` | `none` | `auto` | `none` | `none` |
| `small-caps` | `none` | `none` | `auto` | `none` |
| `position` | `none` | `none` | `none` | `auto` |
| `weight style` | `auto` | `auto` | `none` | `none` |
| `weight small-caps` | `auto` | `none` | `auto` | `none` |
| `weight position` | `auto` | `none` | `none` | `auto` |
| `style small-caps` | `none` | `auto` | `auto` | `none` |
| `style position` | `none` | `auto` | `none` | `auto` |
| `weight style small-caps` | `auto` | `auto` | `auto` | `none` |
| `weight style position` | `auto` | `auto` | `none` | `auto` |
| `weight small-caps position` | `auto` | `none` | `auto` | `auto` |
| `style small-caps position` | `none` | `auto` | `auto` | `auto` |
| `weight style small-caps position` | `auto` | `auto` | `auto` | `auto` |

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `weight style small-caps position ` |
| Applies to | all elements and text. It also applies to [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter) and [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line). |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#formal_syntax)

```
font-synthesis =
  none                                            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  weight  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  style  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  small-caps  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  position  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#examples)

### [Disabling font synthesis](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#disabling_font_synthesis)

This example shows the browser's default font-synthesis behavior and compares it with when the synthesis behavior is turned off. Notice that the example uses two imported fonts to demonstrate this behavior. You might not be able to replicate turning off of font-synthesis on fonts available on your operating system by default.

#### HTML

html

```
<pre> DEFAULT </pre>
<p class="english">
  This font supports <strong>bold</strong> and <em>italic</em>.
</p>
<p class="chinese">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>
<br />

<pre> SYNTHESIS IS DISABLED </pre>
<p class="english no-syn">
  This font supports <strong>bold</strong> and <em>italic.</em>
</p>
<p class="chinese no-syn">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>
<br />

<pre> SYNTHESIS IS ENABLED </pre>
<p class="english">
  This font supports <strong>bold</strong> and <em>italic</em>.
</p>
<p class="chinese syn">这个字体支持<strong>加粗</strong>和<em>斜体</em></p>

```

#### CSS

css

```
@import "https://fonts.googleapis.com/css2?family=Montserrat&display=swap";
@import "https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&display=swap";

.english {
  font-family: "Montserrat", sans-serif;
}
.chinese {
  font-family: "Ma Shan Zheng", cursive;
}
.no-syn {
  font-synthesis: none;
}
.syn {
  font-synthesis: style weight;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#specifications)

| Specification |
| --- |
| [CSS Fonts Module Level 4\<br>\# font-synthesis](https://drafts.csswg.org/css-fonts/#font-synthesis) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis\#see_also)

- [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
- [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
- [`font-variant-caps`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps)
- [`font-variant-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-position)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 18, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/font-synthesis/index.md?plain=1 "Folder: ⁨en-us/web/css/font-synthesis⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffont-synthesis&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ffont-synthesis%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffont-synthesis%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ffont-synthesis%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F6ed02a2b0e0d891f7d3b4c2a6b1d9cc05c90ed9c%0A*+Document+last+modified%3A+2025-10-18T01%3A41%3A26.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")