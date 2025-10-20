---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/border-image
scraped_at: 2025-10-20T02:58:28.638Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# border-image


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-image&level=high)

The **`border-image`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property draws an image around a given element. It replaces the element's regular [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border).

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#try_it)

- border-image: url("/shared-assets/images/examples/border-diamonds.png") 30;

- border-image: url("/shared-assets/images/examples/border-diamonds.png") 30 /



19pxround;

- border-image: url("/shared-assets/images/examples/border-diamonds.png") 30



fill / 30px / 30pxspace;

- border-image: linear-gradient(#f6b73c, #4d9f0c) 30;

- border-image: repeating-linear-gradient(30deg, #4d9f0c, #9198e5, #4d9f0c 20px)



60;


This is a box with a border around it.

cssCopy

```
border-image: url("/shared-assets/images/examples/border-diamonds.png") 30;

```

cssCopy

```
border-image: url("/shared-assets/images/examples/border-diamonds.png") 30 /
  19px round;

```

cssCopy

```
border-image: url("/shared-assets/images/examples/border-diamonds.png") 30
  fill / 30px / 30px space;

```

cssCopy

```
border-image: linear-gradient(#f6b73c, #4d9f0c) 30;

```

cssCopy

```
border-image: repeating-linear-gradient(30deg, #4d9f0c, #9198e5, #4d9f0c 20px)
  60;

```

htmlCopy

```
<section id="default-example">
  <div id="example-element">This is a box with a border around it.</div>
</section>

```

cssCopy

```
#example-element {
  width: 80%;
  height: 80%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px;
  background: #fff3d4;
  color: black;
  border: 30px solid;
  border-image: url("/shared-assets/images/examples/border-diamonds.png") 30
    round;
  font-size: 1.2em;
}

```

**Note:**
You should specify a separate [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) in case the border image fails to load. Although the specification doesn't strictly require it, some browsers don't render the border image if [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) is `none` or [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) is `0`.

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset)
- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat)
- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice)
- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source)
- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#syntax)

cssCopy

```
/* source | slice */
border-image: linear-gradient(red, blue) 27;

/* source | slice | repeat */
border-image: url("/images/border.png") 27 space;

/* source | slice | width */
border-image: linear-gradient(red, blue) 27 / 35px;

/* source | slice | width | outset | repeat */
border-image: url("/images/border.png") 27 23 / 50px 30px / 1rem round space;

/* Global values */
border-image: inherit;
border-image: initial;
border-image: revert;
border-image: revert-layer;
border-image: unset;

```

The `border-image` property may be specified with anywhere from one to five of the values listed below.

**Note:**
If the [computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) of [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source) is `none`, or if the image cannot be displayed, the [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) will be displayed instead.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#values)

[`<'border-image-source'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#border-image-source)

The source image. See [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source).

[`<'border-image-slice'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#border-image-slice)

The dimensions for slicing the source image into regions. Up to four values may be specified. See [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice).

[`<'border-image-width'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#border-image-width)

The width of the border image. Up to four values may be specified. See [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width).

[`<'border-image-outset'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#border-image-outset)

The distance of the border image from the element's outside edge. Up to four values may be specified. See [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset).

[`<'border-image-repeat'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image#border-image-repeat)

Defines how the edge regions of the source image are adjusted to fit the dimensions of the border image. Up to two values may be specified. See [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat).

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#accessibility)

Assistive technology cannot parse border images. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source): `none`<br>- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice): `100%`<br>- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width): `1`<br>- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset): `0`<br>- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat): `stretch` |
| Applies to | all elements, except internal table elements when [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) is `collapse`. It also applies to [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter). |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | as each of the properties of the shorthand:<br>- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice): refer to the size of the border image<br>- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width): refer to the width or height of the border image area |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset): as specified, but with relative lengths converted into absolute lengths<br>- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat): as specified<br>- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice): one to four percentage(s) (as specified) or absolute length(s), plus the keyword `fill` if specified<br>- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source): `none` or the image with its URI made absolute<br>- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width): as specified, but with relative lengths converted into absolute lengths |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset): by computed value type<br>- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat): discrete<br>- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice): by computed value type<br>- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source): discrete<br>- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width): by computed value type |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#formal_syntax)

```
border-image =
  [<'border-image-source'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source)                              [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'border-image-slice'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice)  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") / [<'border-image-width'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") / [<'border-image-width'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") / [<'border-image-outset'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'border-image-repeat'>](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat)

<border-image-source> =
  none      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image>

<border-image-slice> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<number \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<percentage \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,4}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")   [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  fill [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<border-image-width> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage [0,∞]>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<number \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  auto  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,4}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<border-image-outset> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<length \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<number \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,4}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<border-image-repeat> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  stretch  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  repeat  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  round  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  space  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<image> =
  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image()>        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image-set()>    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <cross-fade()>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <element()>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<gradient>](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

<image()> =
  image( <image-tags> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <image-src> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") , [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")! )

<image-set()> =
  image-set( <image-set-option> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") )

<cross-fade()> =
  cross-fade( <cf-image> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") )

<element()> =
  element( <id-selector> )

<image-tags> =
  ltr   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  rtl

<image-src> =
  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)

<image-set-option> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <image>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<resolution>](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution)  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  type(  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string) )  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<cf-image> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <image>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  [<percentage \[0,100\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<id-selector> =
  <hash-token>

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#examples)

### [Bitmap](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#bitmap)

In this example, we will apply a diamond pattern to an element's borders. The source for the border image is a ".png" file of 81 by 81 pixels, with three diamonds going vertically and horizontally:

![Eight diamonds: four red diamonds, one in each corner, and four orange diamonds, one on each side. The middle is empty.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image/border.png)

#### HTML

htmlCopyPlay

```
<div id="bitmap">
  This element is surrounded by a bitmap-based border image!
</div>

```

#### CSS

To match the size of a single diamond, we will use a value of 81 divided by 3, or `27`, for slicing the image into corner and edge regions. To center the border image on the edge of the element's background, we will make the outset values equal to half of the width values. Finally, a repeat value of `round` will make the border slices fit evenly, i.e., without clipping or gaps.

cssCopyPlay

```
#bitmap {
  width: 200px;
  background-color: #ffffaa;
  border: 36px solid orange;
  margin: 30px;
  padding: 10px;

  border-image: url("border.png") 27 / 36px 28px 18px 8px / 18px 14px 9px 4px
    round;
}

```

#### Result

Play

This element is surrounded by a bitmap-based border image!

### [Gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#gradient)

#### HTML

htmlCopyPlay

```
<div id="gradient">
  This element is surrounded by a gradient-based border image!
</div>

```

#### CSS

cssCopyPlay

```
#gradient {
  width: 200px;
  border: 30px solid;
  border-image: repeating-linear-gradient(45deg, #ff3333, #33bbff, #ff3333 30px)
    60;
  padding: 20px;
}

```

#### Result

Play

This element is surrounded by a gradient-based border image!

### [Rounded borders](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#rounded_borders)

[`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) has no effect on the border image. This is because [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset) is able to place the image outside the border box, so it doesn't make sense for the border image to be clipped by the border area. To create rounded borders when using a border image, you should create the image itself with rounded corners, or, in the case of a gradient, draw it as the background instead. Below, we show one approach to do this, which is to use two [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) s: one that extends the border box, and another for the padding box.

#### HTML

htmlCopyPlay

```
<div id="rounded">
  This element is surrounded by a border image with rounded corners!
</div>

```

#### CSS

cssCopyPlay

```
#rounded {
  width: 200px;
  /* Use transparent so the background image is visible */
  border: 10px solid transparent;
  padding: 20px;
  border-radius: 20px;
  background-image:
    linear-gradient(white, white), linear-gradient(to right, cyan, lime);
  background-origin: border-box;
  background-clip: padding-box, border-box;
}

```

#### Result

Play

This element is surrounded by a border image with rounded corners!

**Note:**
There is a new ``[`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip): border-area`` value [being proposed](https://github.com/w3c/csswg-drafts/issues/9456) to address this use case.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#specifications)

| Specification |
| --- |
| [CSS Backgrounds and Borders Module Level 3\<br>\# border-image](https://drafts.csswg.org/css-backgrounds/#border-image) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/border-image.json "File: ⁨css/properties/border-image.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `border-image` | Chrome – Full support<br>Chrome16<br>footnotemore<br>Chrome – Full support<br>Chrome7 (Release date: ⁨2010-10-19⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome – Full support<br>Chrome16 (Release date: ⁨2011-12-13⁩)<br> <br>footnote<br>footnoteBefore Chrome 112, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | Edge – Full support<br>Edge12<br>footnotemore<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnote<br>footnoteBefore Edge 112, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | Firefox – Full support<br>Firefox15<br>footnotemore<br>Firefox – Full support<br>Firefox3.5 (Release date: ⁨2009-06-30⁩)<br> <br>prefixfootnote<br>prefixImplemented with the vendor prefix: ⁨-moz-⁩footnoteBefore Firefox 15, an earlier version of the specification was implemented, prefixed.<br>Firefox – Full support<br>Firefox15 (Release date: ⁨2012-08-28⁩)<br> <br>footnote<br>footnoteSmall SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ( [bug 1284797](https://bugzil.la/1284797)).footnoteUntil Firefox 47, SVGs without viewport were not sliced correctly ( [bug 619500](https://bugzil.la/619500)).footnoteFrom Firefox 48 until Firefox 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ( [bug 1264809](https://bugzil.la/1264809)).footnoteUntil Firefox 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ( [bug 1290782](https://bugzil.la/1290782)). | Opera – Full support<br>Opera11<br>footnotemore<br>Opera – No support<br>Opera10.5 – 12.1 (Release date: ⁨2010-03-02⁩)<br> <br>prefix<br>footnoteRemoved in ⁨15⁩ and laterprefixImplemented with the vendor prefix: ⁨-o-⁩<br>Opera – Full support<br>Opera11 (Release date: ⁨2010-12-16⁩)<br> <br>footnote<br>footnoteBefore Opera 98, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | Safari – Full support<br>Safari6<br>more<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Full support<br>Safari6 (Release date: ⁨2012-07-25⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>footnotemore<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnote<br>footnoteBefore Chrome Android 112, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | Firefox for Android – Full support<br>Firefox for Android15<br>footnotemore<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>prefixfootnote<br>prefixImplemented with the vendor prefix: ⁨-moz-⁩footnoteBefore Firefox for Android 15, an earlier version of the specification was implemented, prefixed.<br>Firefox for Android – Full support<br>Firefox for Android15 (Release date: ⁨2012-08-28⁩)<br> <br>footnote<br>footnoteSmall SVGs are incorrectly stretched, because percentages in [`border-image-slice`](https://developer.mozilla.org/docs/Web/CSS/border-image-slice) are computed to integers instead of floats ( [bug 1284797](https://bugzil.la/1284797)).footnoteUntil Firefox for Android 47, SVGs without viewport were not sliced correctly ( [bug 619500](https://bugzil.la/619500)).footnoteFrom Firefox for Android 48 until Firefox for Android 49, SVGs without viewport are displayed the same as SVGs with viewport, but if the slices are not exactly 50%, they are incorrectly stretched ( [bug 1264809](https://bugzil.la/1264809)).footnoteUntil Firefox for Android 57, an issue persisted for SVGs without viewport when [e10s](https://wiki.mozilla.org/Electrolysis) was disabled ( [bug 1290782](https://bugzil.la/1290782)). | Opera Android – Full support<br>Opera Android11<br>footnotemore<br>Opera Android – No support<br>Opera Android11 – 12.1 (Release date: ⁨2011-03-22⁩)<br> <br>prefix<br>footnoteRemoved in ⁨14⁩ and laterprefixImplemented with the vendor prefix: ⁨-o-⁩<br>Opera Android – Full support<br>Opera Android11 (Release date: ⁨2011-03-22⁩)<br> <br>footnote<br>footnoteA border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | Safari on iOS – Full support<br>Safari on iOS6<br>more<br>Safari on iOS – Full support<br>Safari on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari on iOS – Full support<br>Safari on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>footnotemore<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnote<br>footnoteBefore Samsung Internet 23.0, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | WebView Android – Full support<br>WebView Android4.4<br>footnotemore<br>WebView Android – Full support<br>WebView Android2 (Release date: ⁨2009-10-26⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnote<br>footnoteBefore WebView 112, a border image's absolute or percentage length width may not take precedence over a narrower `border-width` ( [bug 40541033](https://crbug.com/40541033)). | WebView on iOS – Full support<br>WebView on iOS6<br>more<br>WebView on iOS – Full support<br>WebView on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView on iOS – Full support<br>WebView on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support |
| `fill` | Chrome – Full support<br>Chrome16<br>Chrome – Full support<br>Chrome16 (Release date: ⁨2011-12-13⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox15<br>Firefox – Full support<br>Firefox15 (Release date: ⁨2012-08-28⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari6<br>Safari – Full support<br>Safari6 (Release date: ⁨2012-07-25⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android15<br>Firefox for Android – Full support<br>Firefox for Android15 (Release date: ⁨2012-08-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS6<br>Safari on iOS – Full support<br>Safari on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS6<br>WebView on iOS – Full support<br>WebView on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support |
| `<gradient>` | Chrome – Full support<br>Chrome7<br>Chrome – Full support<br>Chrome7 (Release date: ⁨2010-10-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox29<br>Firefox – Full support<br>Firefox29 (Release date: ⁨2014-04-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari4<br>Safari – Full support<br>Safari4 (Release date: ⁨2009-06-08⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android29<br>Firefox for Android – Full support<br>Firefox for Android29 (Release date: ⁨2014-04-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS3.2<br>Safari on iOS – Full support<br>Safari on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS3.2<br>WebView on iOS – Full support<br>WebView on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>footnoteFull support |
| optional `<border-image-slice>` | Chrome – Full support<br>Chrome16<br>Chrome – Full support<br>Chrome16 (Release date: ⁨2011-12-13⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox15<br>Firefox – Full support<br>Firefox15 (Release date: ⁨2012-08-28⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari6<br>Safari – Full support<br>Safari6 (Release date: ⁨2012-07-25⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android15<br>Firefox for Android – Full support<br>Firefox for Android15 (Release date: ⁨2012-08-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS6<br>Safari on iOS – Full support<br>Safari on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS6<br>WebView on iOS – Full support<br>WebView on iOS6 (Release date: ⁨2012-09-10⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

See implementation notes.

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image\#see_also)

- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
- [`outline`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
- [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)
- [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) type
- Gradient functions: [`conic-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/conic-gradient), [`repeating-conic-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-conic-gradient), [`linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient), [`repeating-linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-linear-gradient), [`radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient), [`repeating-radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-radial-gradient)
- [Border images in CSS: A key focus area for Interop 2023](https://developer.mozilla.org/en-US/blog/border-images-interop-2023/) on MDN blog (2023)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/border-image/index.md?plain=1 "Folder: ⁨en-us/web/css/border-image⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-image&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fborder-image%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-image%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fborder-image%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe82803beedb7f1d8a8e918c1071752f18e1e3f28%0A*+Document+last+modified%3A+2025-08-13T01%3A57%3A35.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")