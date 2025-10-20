---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis
scraped_at: 2025-10-20T03:14:35.385Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#search)

# text-emphasis


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2022⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-emphasis&level=high)

The **`text-emphasis`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies emphasis marks to text (except spaces and control characters). It is a [shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) for [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style) and [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color).

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#try_it)

```
text-emphasis: none;

```

```
text-emphasis: filled red;

```

```
text-emphasis: "x";

```

```
text-emphasis: filled double-circle #ffb703;

```

```
<section id="default-example">
  <p>
    I'd far rather be
    <span class="transition-all" id="example-element">happy than right</span>
    any day.
  </p>
</section>

```

```
p {
  font: 1.5em sans-serif;
}

```

The `text-emphasis` property is quite different from [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration). The `text-decoration` property does not inherit, and the decoration specified is applied across the whole element. However, text-emphasis does inherit, which means it is possible to change emphasis marks for descendants.

The size of the emphasis symbol, like ruby symbols, is about 50% of the size of the font, and `text-emphasis` may affect line height when the current leading is not enough for the marks.

**Note:** `text-emphasis` doesn't reset the value of [`text-emphasis-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position). This is because if the style and the color of emphasis marks may vary in a text, it is extremely unlikely that their position will. In the very rare cases when this is needed, use the property [`text-emphasis-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position).

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color)
- [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#syntax)

css

```
/* Initial value */
text-emphasis: none; /* No emphasis marks */

/* <string> value */
text-emphasis: "x";
text-emphasis: "点";
text-emphasis: "\25B2";
text-emphasis: "*" #555555;
text-emphasis: "foo"; /* Should NOT use. It may be computed to or rendered as 'f' only */

/* Keywords value */
text-emphasis: filled;
text-emphasis: open;
text-emphasis: filled sesame;
text-emphasis: open sesame;

/* Keywords value combined with a color */
text-emphasis: filled sesame #555555;

/* Global values */
text-emphasis: inherit;
text-emphasis: initial;
text-emphasis: revert;
text-emphasis: revert-layer;
text-emphasis: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#values)

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#none)

No emphasis marks.

[`filled`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#filled)

The shape is filled with solid color. If neither `filled` nor `open` is present, this is the default.

[`open`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#open)

The shape is hollow.

[`dot`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#dot)

Display small circles as marks. The filled dot is `'•'` ( `U+2022`), and the open dot is `'◦'` ( `U+25E6`).

[`circle`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#circle)

Display large circles as marks. The filled circle is `'●'` ( `U+25CF`), and the open circle is `'○'` ( `U+25CB`). This is the default shape in horizontal writing modes when no other shape is given.

[`double-circle`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#double-circle)

Display double circles as marks. The filled double-circle is `'◉'` ( `U+25C9`), and the open double-circle is `'◎'` ( `U+25CE`).

[`triangle`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#triangle)

Display triangles as marks. The filled triangle is `'▲'` ( `U+25B2`), and the open triangle is `'△'` ( `U+25B3`).

[`sesame`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#sesame)

Display sesames as marks. The filled sesame is `'﹅'` ( `U+FE45`), and the open sesame is `'﹆'` ( `U+FE46`). This is the default shape in vertical writing modes when no other shape is given.

[`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#string)

Display the given string as marks. Authors should not specify more than one _character_ in `<string>`. The UA may truncate or ignore strings consisting of more than one grapheme cluster.

[`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis#color)

Defines the color of the mark. If no color is present, it defaults to `currentColor`.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style): `none`<br>- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color): `currentcolor` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | yes |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style): as specified<br>- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color): computed color |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color): a [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#interpolation "Values of the <color> CSS data type are interpolated on each of their red, green, blue components, each handled as a real, floating-point number. Note that interpolation of colors happens in the alpha-premultiplied sRGBA color space to prevent unexpected grey colors to appear.")<br>- [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style): discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#formal_syntax)

```
text-emphasis =
  [<'text-emphasis-style'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style)   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'text-emphasis-color'>](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color)

<text-emphasis-style> =
  none                                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  filled  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  open  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  dot  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  circle  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  double-circle  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  triangle  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  sesame  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)

<text-emphasis-color> =
  [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#examples)

### [A heading with emphasis shape and color](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#a_heading_with_emphasis_shape_and_color)

This example draws a heading with triangles used to emphasize each character.

#### CSS

css

```
h2 {
  text-emphasis: triangle #dd5555;
}

```

#### HTML

html

```
<h2>This is important!</h2>

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#specifications)

| Specification |
| --- |
| [CSS Text Decoration Module Level 3\<br>\# text-emphasis-property](https://drafts.csswg.org/css-text-decor/#text-emphasis-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis\#see_also)

- The longhand properties [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style), [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color).
- The [`text-emphasis-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position) property allowing to define the position of the emphasis marks.

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/text-emphasis/index.md?plain=1 "Folder: ⁨en-us/web/css/text-emphasis⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-emphasis&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftext-emphasis%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftext-emphasis%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftext-emphasis%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")