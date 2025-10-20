---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap
scraped_at: 2025-10-20T03:18:41.977Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap#search)

# column-gap


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolumn-gap&level=high)

The **`column-gap`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the size of the gap ( [gutter](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)) between an element's columns.

Initially a part of [Multi-column Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout), the definition of `column-gap` has been broadened to include multiple layout methods. Now specified in [CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment), it may be used in multi-column, flexible box, and grid layouts.

Early versions of the specification called this property `grid-column-gap`, and to maintain compatibility with legacy websites, browsers will still accept `grid-column-gap` as an alias for `column-gap`.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#try_it)

- column-gap: 0;

- column-gap: 10%;

- column-gap: 1em;

- column-gap: 20px;


## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#syntax)

cssCopy

```
/* Keyword value */
column-gap: normal;

/* <length> values */
column-gap: 3px;
column-gap: 2.5em;

/* <percentage> value */
column-gap: 3%;

/* Global values */
column-gap: inherit;
column-gap: initial;
column-gap: revert;
column-gap: revert-layer;
column-gap: unset;

```

The `column-gap` property is specified as one of the values listed below.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#values)

[`normal`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap#normal)

The browser's default spacing is used between columns. For multi-column layout this is specified as `1em`. For all other layout types it is 0.

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

The size of the gap between columns, defined as a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length). The [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) property's value must be non-negative.

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

The size of the gap between columns, defined as a [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). The [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) property's value must be non-negative.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `normal` |
| Applies to | multi-column elements, flex containers, grid containers |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | refer to corresponding dimension of the content area |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, with <length>s made absolute, and normal computing to zero except on multi-column elements |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc(); |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#formal_syntax)

```
column-gap =
  normal                      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <length-percentage [0,∞]>

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#examples)

### [Flex layout](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#flex_layout)

In this example, a flex container contains six flex items of two different widths ( `200px` and `300px`), creating flex items that are not laid out as a grid. The `column-gap` property is used to add horizontal space between the adjacent flex items.

#### HTML

htmlCopy

```
<div class="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

```

#### CSS

To create a flex container, we set its [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property value to `flex`. We then use the [`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow) shorthand property to set the [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) to row (the default) and [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap) to `wrap`, allowing the flex items to flow onto new lines if needed. By default, flex items stretch to be as tall as their container. By setting a [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), even the empty flex items will be `100px` tall.

To better demonstrate the `column-gap` property, the flex items in this example have two different width values. The width of the flex items is set within the `<div>` flex items. We use the [`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis) component of the [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) shorthand property to make all the flex items `200px` wide. We then target every third flex item by using the [`:nth-of-type(3n)`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type) selector, widening them to `300px`.

The `column-gap` value is set as `20px` on the flex container to create a `20px` gap between the adjacent flex items in each row.

cssCopy

```
.flexbox {
  display: flex;
  flex-flow: row wrap;
  height: 100px;
  column-gap: 20px;
}

.flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 200px;
}
div:nth-of-type(3n) {
  flex: 300px;
}

```

#### Result

**Note:**
While there is horizontal space between adjacent flex items in each flex row, there is no space between the rows. To set vertical space between flex rows, you can specify a non-zero value for the [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap) property. The [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) shorthand property is also available to set both the `row-gap` and `column-gap` in one declaration, in that order.

### [Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#grid_layout)

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
</div>

```

#### CSS

css

```
#grid {
  display: grid;
  height: 100px;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px;
  column-gap: 20px;
}

#grid > div {
  border: 1px solid green;
  background-color: lime;
}

```

#### Result

### [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#multi-column_layout)

#### HTML

html

```
<p class="content-box">
  This is some multi-column text with a 40px column gap created with the CSS
  `column-gap` property. Don't you think that's fun and exciting? I sure do!
</p>

```

#### CSS

css

```
.content-box {
  column-count: 3;
  column-gap: 40px;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#specifications)

| Specification |
| --- |
| [CSS Box Alignment Module Level 3\<br>\# column-row-gap](https://drafts.csswg.org/css-align/#column-row-gap) |
| [CSS Grid Layout Module Level 2\<br>\# gutters](https://drafts.csswg.org/css-grid/#gutters) |
| [CSS Multi-column Layout Module Level 1\<br>\# column-gap](https://drafts.csswg.org/css-multicol/#column-gap) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap\#see_also)

- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)
- [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- [Basic concepts of grid layout: gutters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout#gutters)
- [Styling Columns](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Styling_columns)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/column-gap/index.md?plain=1 "Folder: ⁨en-us/web/css/column-gap⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolumn-gap&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcolumn-gap%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fcolumn-gap%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcolumn-gap%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")