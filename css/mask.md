---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/mask
scraped_at: 2025-10-20T03:14:23.296Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#search)

# mask


Baseline

2023


Newly available

Since ⁨December 2023⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fmask&level=low)

The **`mask`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) hides an element (partially or fully) by masking or clipping a specified area of the image. It is a shorthand for all the [`mask-*`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#constituent_properties) properties. The property accepts one or more comma-separated values, where each value corresponds to a [`<mask-layer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#mask-layer).

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip)
- [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite)
- [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image)
- [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode)
- [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin)
- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position)
- [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat)
- [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#syntax)

cssCopy

```
/* Keyword values */
mask: none;

/* Image values */
mask: url("mask.png"); /* Raster image used as mask */
mask: url("masks.svg#star"); /* SVG used as mask */

/* Combined values */
mask: url("masks.svg#star") luminance; /* Luminance mask */
mask: url("masks.svg#star") 40px 20px; /* Mask positioned 40px from the top and 20px from the left */
mask: url("masks.svg#star") 0 0/50px 50px; /* Mask with a width and height of 50px */
mask: url("masks.svg#star") repeat-x; /* Horizontally-repeated mask */
mask: url("masks.svg#star") stroke-box; /* Mask extends to the inside edge of the stroke box */
mask: url("masks.svg#star") exclude; /* Mask combined with background using non-overlapping parts */

/* Multiple masks */
mask:
  url("masks.svg#star") left / 16px repeat-y,
  /* 16px-wide mask on the left side */ url("masks.svg#circle") right / 16px
    repeat-y; /* 16px-wide mask against right side */

/* Global values */
mask: inherit;
mask: initial;
mask: revert;
mask: revert-layer;
mask: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#values)

[`<mask-layer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#mask-layer)

One or more comma-separated mask layers, consisting of the following components:

[`<mask-reference>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#mask-reference)

Sets the mask image source. See [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image).

[`<masking-mode>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#masking-mode)

Sets the masking mode of the mask image. See [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode).

[`<position>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#position)

Sets the position of the mask image. See [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position).

[`<bg-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#bg-size)

Sets the size of the mask image. See [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size).

[`<repeat-style>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#repeat-style)

Sets the repetition of the mask image. See [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat).

[`<geometry-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#geometry-box)

If only one `<geometry-box>` value is given, it sets both the [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin) and [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip) property values. If two `<geometry-box>` values are present, the first defines the `mask-origin` and the second defines the `mask-clip`.

[`<geometry-box> | no-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#geometry-box_no-clip)

Sets the area affected by the mask image. See [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip).

[`<compositing-operator>`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask#compositing-operator)

Sets the compositing operation used on the current mask layer. See [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite).

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#description)

The `mask` shorthand property hides part or all of the element it is applied to. The parts of the element that are hidden, visible, or partially shown depend on either the opacity (alpha channel of the mask) or the brightness (luminance) of the mask. In alpha masking, opaque areas of the mask reveal the element, and transparent areas hide it. In luminance masking, light opaque areas of the mask reveal the element, and dark or transparent areas hide it.

While not all constituent mask properties need to be declared, any values that are omitted default to their initial values, which are:

cssCopy

```
mask-image: none;
mask-mode: match-source;
mask-position: 0% 0%;
mask-size: auto;
mask-repeat: repeat;
mask-origin: border-box;
mask-clip: border-box;
mask-composite: add;

```

Within each `<mask-layer>`, the `mask-size` component must go after the `mask-position` value, with a forward slash ( `/`) separating the two.

If there are two `<geometry-box>` values present, the first is the `mask-origin` value, while the second is the `mask-clip` value. If one `<geometry-box>` value and the `no-clip` keyword are present, the `<geometry-box>` is the value of the `mask-origin` property, as the `no-clip` is only valid for the `mask-clip` property. In this case, the order of the two values doesn't matter. If only one `<geometry-box>` value is present (with no `no-clip` keyterm specified), this value is used for both the `mask-origin` and `mask-clip` properties.

As the `mask` shorthand resets all the `mask-border-*` properties to their `initial` value, you should declare these properties — or the [`mask-border`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border) shorthand — after any `mask` declarations. When setting `mask` in your declaration block, you also implicitly set the following:

cssCopy

```
mask-border-source: none;
mask-border-mode: alpha;
mask-border-outset: 0;
mask-border-repeat: stretch;
mask-border-slice: 0;
mask-border-width: auto;

```

For this reason, the specification recommends using the `mask` shorthand rather than the individual component properties to override any masks set earlier in the cascade. This ensures that `mask-border` has also been reset.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image): `none`<br>- [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode): `match-source`<br>- [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat): `repeat`<br>- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position): `0% 0%`<br>- [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip): `border-box`<br>- [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin): `border-box`<br>- [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size): `auto`<br>- [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite): `add` |
| Applies to | all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/defs) element and all graphics elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | as each of the properties of the shorthand:<br>- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position): refer to size of mask painting area minus size of mask layer image (see the text for [`background-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position)) |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image): as specified, but with [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) values made absolute<br>- [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode): as specified<br>- [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat): Consists of two keywords, one per dimension<br>- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position): Consists of two keywords representing the origin and two offsets from that origin, each given as an absolute length (if given a <length>), otherwise as a percentage.<br>- [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip): as specified<br>- [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin): as specified<br>- [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size): as specified, but with relative lengths converted into absolute lengths<br>- [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite): as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image): discrete<br>- [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode): discrete<br>- [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat): discrete<br>- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position): a repeatable list<br>- [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip): discrete<br>- [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin): discrete<br>- [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size): a repeatable list<br>- [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite): discrete |
| Creates [stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context) | yes |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#formal_syntax)

```
mask =
  <mask-layer> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma")

<mask-layer> =
  <mask-reference>               [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  <position>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") / <bg-size>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")    [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  <repeat-style>                 [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  <geometry-box>                 [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <geometry-box>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  no-clip  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  <compositing-operator>         [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  <masking-mode>

<mask-reference> =
  none            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image>         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <mask-source>

<position> =
  <position-one>    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <position-two>    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <position-four>

<bg-size> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage [0,∞]>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  auto  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  cover                                       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  contain

<repeat-style> =
  repeat-x            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  repeat-y            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <repetition> [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<geometry-box> =
  <shape-box>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  fill-box      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  stroke-box    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  view-box

<compositing-operator> =
  add         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  subtract    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  intersect   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  exclude

<masking-mode> =
  alpha          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  luminance      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  match-source

<image> =
  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image()>        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image-set()>    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <cross-fade()>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <element()>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<gradient>](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)

<mask-source> =
  [<url>](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)

<position-one> =
  left                  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  center                [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  right                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  top                   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  bottom                [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  x-start               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  x-end                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  y-start               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  y-end                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  block-start           [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  block-end             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-start          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-end            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage>

<position-two> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  left  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  right  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  top  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  bottom  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  left  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  right  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-end  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  top  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  bottom  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-end  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  block-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  block-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  inline-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  inline-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  center  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<position-four> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  left  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  right  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  x-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  top  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  bottom  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  y-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  block-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  block-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  inline-start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  inline-end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  end  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

<repetition> =
  repeat      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  space       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  round       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  no-repeat

<shape-box> =
  <visual-box>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  margin-box        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  half-border-box

<image()> =
  image( <image-tags> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <image-src> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") , [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")! )

<image-set()> =
  image-set( <image-set-option> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") )

<cross-fade()> =
  cross-fade( <cf-image> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") )

<element()> =
  element( <id-selector> )

<visual-box> =
  content-box   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  padding-box   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  border-box

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

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#examples)

### [Masking an image](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#masking_an_image)

In this example, an image is masked using a CSS-generated repeating conic gradient as a mask source. We'll also show the gradient as a background image for comparison.

#### HTML

We include an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img) and an empty [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) element.

htmlCopy

```
<img
  src="https://mdn.github.io/shared-assets/images/examples/progress-pride-flag.jpg"
  alt="Pride flag" />
<div></div>

```

#### CSS

We set the same [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border), [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding), and sizing on both the `<img>` and `<div>`.

cssCopy

```
img,
div {
  border: 20px dashed rebeccapurple;
  box-sizing: content-box;
  padding: 20px;
  height: 220px;
  width: 220px;
}

```

We then apply a mask to the `<img>`. The `mask-image` is generated using a [`repeating-conic-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-conic-gradient) function. We define it to be a `100px` by `100px` gradient, which repeats starting at the top and left corner of the image's `content-box`. We include two `<geometry-box>` values; the first sets the `mask-origin` and the second defines the `mask-clip` property value. The gradient goes from transparent to solid `lightgreen`. We used `lightgreen` to demonstrate that it isn't the color of the mask that is important, but rather its transparency.

cssCopy

```
img {
  mask: repeating-radial-gradient(
      circle,
      transparent 0 5px,
      lightgreen 15px 20px
    )
    content-box border-box 0% 0% / 100px 100px repeat;
}

```

Finally, we use the same value for the `<div>`'s [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) shorthand property as we used for the `mask`.

cssCopy

```
div {
  background: repeating-radial-gradient(
      circle,
      transparent 0 5px,
      lightgreen 15px 20px
    )
    content-box border-box 0% 0% / 100px 100px repeat;
}

```

#### Results

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#specifications)

| Specification |
| --- |
| [CSS Masking Module Level 1\<br>\# the-mask](https://drafts.fxtf.org/css-masking/#the-mask) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/mask\#see_also)

- [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
- [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
- [Introduction to CSS masking](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking/Masking)
- [CSS `mask` properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking/Mask_properties)
- [Declaring multiple masks](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking/Multiple_masks)
- [CSS masking](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking) module
- SVG [`mask`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/mask) attribute
- [Applying SVG effects to HTML content](https://developer.mozilla.org/en-US/docs/Web/SVG/Guides/Applying_SVG_effects_to_HTML_content)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 5, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/mask/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/mask/index.md?plain=1 "Folder: ⁨en-us/web/css/mask⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fmask&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fmask%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fmask%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fmask%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F9944f7b12ef1a6aecd54d4b2f0c188a82fdeaaf0%0A*+Document+last+modified%3A+2025-08-05T13%3A32%3A56.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")