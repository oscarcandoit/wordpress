---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/gap
scraped_at: 2025-10-20T03:15:51.861Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/gap#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/gap#search)

# gap


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨October 2017⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/gap#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fgap&level=high)

The **`gap`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) sets the gaps (also called [gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)) between rows and columns. This property applies to [multi-column](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout), [flex](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout), and [grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) containers.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#try_it)

```
gap: 0;

```

```
gap: 10%;

```

```
gap: 1em;

```

```
gap: 10px 20px;

```

```
gap: calc(20px + 10%);

```

```
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">
      <div>One</div>
      <div>Two</div>
      <div>Three</div>
      <div>Four</div>
      <div>Five</div>
    </div>
  </div>
</section>

```

```
#example-element {
  border: 1px solid #c5c5c5;
  display: grid;
  grid-template-columns: 1fr 1fr;
  width: 200px;
}

#example-element > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
}

```

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#syntax)

css

```
/* One <length> value */
gap: 20px;
gap: 1em;
gap: 3vmin;
gap: 0.5cm;

/* One <percentage> value */
gap: 16%;
gap: 100%;

/* Two <length> values */
gap: 20px 10px;
gap: 1em 0.5em;
gap: 3vmin 2vmax;
gap: 0.5cm 2mm;

/* One or two <percentage> values */
gap: 16% 100%;
gap: 21px 82%;

/* calc() values */
gap: calc(10% + 20px);
gap: calc(20px + 10%) calc(10% - 5px);

/* Global values */
gap: inherit;
gap: initial;
gap: revert;
gap: revert-layer;
gap: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#values)

This property is specified as a value for `<'row-gap'>`, followed optionally by a value for `<'column-gap'>`. If `<'column-gap'>` is omitted, it is set to the same value as `<'row-gap'>`. Both `<'row-gap'>` and `<'column-gap'>` can each be specified as a `<length>` or a `<percentage>`.

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

Specifies the width of the gutter separating columns, [flex items](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Item), flex lines, and [grid lines](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Lines).

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

Specifies the width of the gutter separating columns, flex items, flex lines, and grid lines relative to the dimension of the element.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#description)

This property defines gaps between columns in [CSS multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout), between flex items and flex lines in [CSS flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout), and between rows and columns in [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout).

The generated gaps create empty spaces that have the width or height of the gap's specified size, much like an empty item or track. The visible space between elements may differ from the provided `gap` value because margins, padding, and distributed alignment may increase the separation between elements beyond what is determined by `gap`.

In grid layout, the first value defines the gutter between rows, and the second defines the gutter between columns. In both grid and flex layouts, if only one value is included, that value is used for both dimensions.

With flex containers, whether the first value is the gap between flex items or between flex lines depends on the direction. Flex items are laid out in either rows or columns depending on the value of the [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) property. For rows ( `row` (the default) or `row-reverse`), the first value defines the gap between flex lines, and the second value defines the gap between items within each line. For columns ( `column` or `column-reverse`), the first value defines the gap between flex items within a flex line, and the second value defines the gaps between each flex line.

In multi-column containers, the first value defines the gap between columns. A dividing line can be added to the otherwise "empty space" by using the [`column-rule-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style) property or [`column-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule) shorthand.

Percentage gap values are always calculated against the [content box](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model#parts_of_a_box) size of the container element. The behavior is well-defined and consistent across layout modes when the container size is definite. As these three layout modes (multi-column, flex, and grid) treat cyclic percentage sizes differently, `gap` also does so. In grid layout, cyclic percentage sizes resolve against zero for determining [intrinsic size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size) contributions but resolve against the element's content box when laying out the contents. Two examples below demonstrate percentage gap values with [explicit container size](https://developer.mozilla.org/en-US/docs/Web/CSS/gap#percentage_gap_value_and_explicit_container_size) and [implicit container size](https://developer.mozilla.org/en-US/docs/Web/CSS/gap#percentage_gap_value_and_implicit_container_size) in the examples section.

Early versions of the specification called this property `grid-gap`, and to maintain compatibility with legacy websites, browsers still accept `grid-gap` as an alias for `gap`.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap): `normal`<br>- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap): `normal` |
| Applies to | multi-column elements, flex containers, grid containers |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap): as specified, with <length>s made absolute, and normal computing to zero except on multi-column elements<br>- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap): as specified, with <length>s made absolute, and normal computing to zero except on multi-column elements |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc();<br>- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc(); |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#formal_syntax)

```
gap =
  [<'row-gap'>](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)  [<'column-gap'>](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap) [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<row-gap> =
  normal                      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage [0,∞]>

<column-gap> =
  normal                      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage [0,∞]>

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#examples)

### [Flex layout](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#flex_layout)

#### HTML

html

```
<div id="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

```

#### CSS

css

```
#flexbox {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  gap: 20px 5px;
}

#flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 1 1 auto;
  width: 100px;
  height: 50px;
}

```

#### Result

### [Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#grid_layout)

#### HTML

html

```
<div id="grid">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

```

#### CSS

css

```
#grid {
  display: grid;
  height: 200px;
  grid-template: repeat(3, 1fr) / repeat(3, 1fr);
  gap: 20px 5px;
}

#grid > div {
  border: 1px solid green;
  background-color: lime;
}

```

#### Result

### [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#multi-column_layout)

#### HTML

html

```
<p class="content-box">
  This is some multi-column text with a 40px column gap created with the CSS
  <code>gap</code> property. Don't you think that's fun and exciting? I sure do!
</p>

```

#### CSS

css

```
.content-box {
  column-count: 3;
  gap: 40px;
}

```

#### Result

### [Percentage gap value and explicit container size](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#percentage_gap_value_and_explicit_container_size)

If the container has a fixed size set, then gap percentage value calculations are based on the size of the container. Thus, gap behavior is consistent across all layouts. In the following example, there are two containers, one with a grid layout and the other with a flex layout. The containers have five red 20x20px children. Both containers are explicitly set to 200px high using `height: 200px` and the gap is set with `gap: 12.5% 0`.

html

```
<span>Grid</span>
<div id="grid">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
<span>Flex</span>
<div id="flex">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

```

```
body > div {
  background-color: #cccccc;
  width: 200px;
  flex-flow: column;
}

```

css

```
#grid {
  display: inline-grid;
  height: 200px;
  gap: 12.5% 0;
}

#flex {
  display: inline-flex;
  height: 200px;
  gap: 12.5% 0;
}

#grid > div,
#flex > div {
  background-color: coral;
  width: 20px;
  height: 20px;
}

```

Now inspect the grid and flex elements using [Inspector tab in Web Developer Tools](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/open_the_inspector/index.html). In order to see the actual gaps hover mouse over `<div id="grid">` and `<div id="flex">` tags in the inspector. You will notice that the gap is the same in both cases which is 25px.

### [Percentage gap value and implicit container size](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#percentage_gap_value_and_implicit_container_size)

If size is not explicitly set on the container, then the percentage gap behaves differently in case of grid and flex layouts. In the following example the containers don't have height explicitly set.

```
<span>Grid</span>
<div id="grid">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
<span>Flex</span>
<div id="flex">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>

```

```
body > div {
  background-color: #cccccc;
  width: 200px;
}

#grid {
  display: inline-grid;
  gap: 12.5% 0;
}

#flex {
  display: inline-flex;
  gap: 12.5% 0;
  flex-flow: column;
}

#grid > div,
#flex > div {
  background-color: coral;
  width: 20px;
  height: 20px;
}

```

In case of the grid layout, percentage gap doesn't contribute to the actual height of the grid. The container's height is calculated using `0px` gap, so the actual height turns out to be 100px (20px x 5). Then the actual percentage gap is calculated using the content box's height, the gap turns out to be `12.5px` (100px x 12.5%). The gap is applied just before rendering. Thus the grid remains 100px high but it overflows due to the percentage gap added later just before rendering.

In case of the flex layout, the percentage gap always results in zero value.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#specifications)

| Specification |
| --- |
| [CSS Box Alignment Module Level 3\<br>\# gap-shorthand](https://drafts.csswg.org/css-align/#gap-shorthand) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/gap\#see_also)

- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)
- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
- [Basic concepts of grid layout: gutters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout#gutters)
- [CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment) module
- [CSS flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) module
- [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) module
- [CSS multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/gap/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/gap/index.md?plain=1 "Folder: ⁨en-us/web/css/gap⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fgap&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fgap%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fgap%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fgap%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")