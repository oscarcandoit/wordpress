---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius
scraped_at: 2025-10-20T03:13:07.184Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius#search)

# border-radius


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-radius&level=high)

The **`border-radius`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the corners of an element's outer border edge. You can set a single radius to make circular corners, or two radii to make elliptical corners.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#try_it)

```
border-radius: 30px;

```

```
border-radius: 25% 10%;

```

```
border-radius: 10% 30% 50% 70%;

```

```
border-radius: 10% / 50%;

```

```
border-radius: 10px 100px / 120px;

```

```
border-radius: 50% 20% / 10% 40%;

```

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box with rounded corners.
  </div>
</section>

```

```
#example-element {
  width: 80%;
  height: 80%;
  display: flex;
  justify-content: center;
  flex-direction: column;
  background-color: #5b6dcd;
  color: white;
  padding: 10px;
}

```

The radius applies to the whole [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background), even if the element has no border; the exact position of the clipping is defined by the [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip) property.

The `border-radius` property does not apply to table elements when [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) is `collapse`.

**Note:**
As with any shorthand property, individual sub-properties cannot inherit, such as in `border-radius:0 0 inherit inherit`, which would partially override existing definitions. Instead, the individual longhand properties have to be used.

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius)
- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius)
- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius)
- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#syntax)

css

```
/* The syntax of the first radius allows one to four values */
/* Radius is set for all 4 sides */
border-radius: 10px;

/* top-left-and-bottom-right | top-right-and-bottom-left */
border-radius: 10px 5%;

/* top-left | top-right-and-bottom-left | bottom-right */
border-radius: 2px 4px 2px;

/* top-left | top-right | bottom-right | bottom-left */
border-radius: 1px 0 3px 4px;

/* The syntax of the second radius allows one to four values */
/* (first radius values) / radius */
border-radius: 10px / 20px;

/* (first radius values) / top-left-and-bottom-right | top-right-and-bottom-left */
border-radius: 10px 5% / 20px 30px;

/* (first radius values) / top-left | top-right-and-bottom-left | bottom-right */
border-radius: 10px 5px 2em / 20px 25px 30%;

/* (first radius values) / top-left | top-right | bottom-right | bottom-left */
border-radius: 10px 5% / 20px 25em 30px 35em;

/* Global values */
border-radius: inherit;
border-radius: initial;
border-radius: revert;
border-radius: revert-layer;
border-radius: unset;

```

The `border-radius` property is specified as:

- one, two, three, or four [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values. This is used to set a single radius for the corners.
- followed optionally by "/" and one, two, three, or four `<length>` or `<percentage>` values. This is used to set an additional radius, so you can have elliptical corners.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#values)

|     |     |     |
| --- | --- | --- |
| _radius_ | ![A light blue rectangle with a light gray border. All 4 corners are rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/all-corner.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in each corner of the border. It is used only in the<br> one-value syntax. |
| _top-left-and-bottom-right_ | ![A light blue rectangle with a light gray border. The 2 corners on the top left and the bottom right have are rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/top-left-bottom-right.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the top-left and bottom-right corners of the element's<br> box. It is used only in the two-value syntax. |
| _top-right-and-bottom-left_ | ![A light blue rectangle with a light gray border. The 2 corners on the top right and the bottom left are rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/top-right-bottom-left.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the top-right and bottom-left corners of the element's<br> box. It is used only in the two- and three-value syntaxes. |
| _top-left_ | ![A light blue rectangle with a light gray border. The corner on the top left is rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/top-left.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the top-left corner of the element's box. It is used<br> only in the three- and four-value syntaxes. |
| _top-right_ | ![A light blue rectangle with a light gray border. The corner on the top right is rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/top-right.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the top-right corner of the element's box. It is used<br> only in the four-value syntax. |
| _bottom-right_ | ![A light blue rectangle with a light gray border. The bottom right corner is rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/bottom-right.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the bottom-right corner of the element's box. It is<br> used only in the three- and four-value syntaxes. |
| _bottom-left_ | ![A light blue rectangle with a light gray border. The bottom left corner is rounded.](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/bottom-left.png) | Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or a<br> [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) denoting a radius to use<br> for the border in the bottom-left corner of the element's box. It is<br> used only in the four-value syntax. |

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

Denotes the size of the circle radius, or the semi-major and semi-minor axes of the ellipse, using length values. Negative values are invalid.

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

Denotes the size of the circle radius, or the semi-major and semi-minor axes of the ellipse, using percentage values. Percentages for the horizontal axis refer to the width of the box; percentages for the vertical axis refer to the height of the box. Negative values are invalid.

For example:

css

```
border-radius: 1em / 5em;

/* It is equivalent to: */
border-top-left-radius: 1em 5em;
border-top-right-radius: 1em 5em;
border-bottom-right-radius: 1em 5em;
border-bottom-left-radius: 1em 5em;

```

css

```
border-radius: 4px 3px 6px / 2px 4px;

/* It is equivalent to: */
border-top-left-radius: 4px 2px;
border-top-right-radius: 3px 4px;
border-bottom-right-radius: 6px 2px;
border-bottom-left-radius: 3px 4px;

```

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius): `0`<br>- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius): `0`<br>- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius): `0`<br>- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius): `0` |
| Applies to | all elements; but User Agents are not required to apply to `table` and `inline-table` elements when [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) is `collapse`. The behavior on internal table elements is undefined for the moment.. It also applies to [`::first-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter). |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | refer to the corresponding dimension of the border box |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius): two absolute [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) s or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) s<br>- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius): two absolute [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) s or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) s<br>- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius): two absolute [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) s or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) s<br>- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius): two absolute [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) s or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) s |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc();<br>- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc();<br>- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc();<br>- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers."), [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage#interpolation "Values of the <percentage> CSS data type are interpolated as real, floating-point numbers.") or calc(); |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#formal_syntax)

```
border-radius =
  <length-percentage [0,∞]> [{1,4}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") / <length-percentage [0,∞]> [{1,4}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#examples)

### [Comparing border styles](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#comparing_border_styles)

The following example has seven [`<pre>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/pre) elements, each of which demonstrates combinations of `border` and `border-radius` styles.
The styles applied to each `<pre>` element are included as the element's contents, so you can see the CSS declarations necessary to create the associated border style:

```
<pre id="example-1">
  border: solid 10px;
  border-radius: 10px 40px 40px 10px;
</pre>

<pre id="example-2">
  border: groove 1em red;
  border-radius: 2em;
</pre>

<pre id="example-3">
  background: gold;
  border: ridge gold;
  border-radius: 13em / 3em;
</pre>

<pre id="example-4">
  border: none;
  border-radius: 40px 10px;
  background: gold;
</pre>

<pre id="example-5">
  border: none;
  border-radius: 50%;
  background: burlywood;
</pre>

<pre id="example-6">
  border: dotted;
  border-width: 10px 4px;
  border-radius: 10px 40px;
</pre>

<pre id="example-7">
  border: dashed;
  border-width: 2px 4px;
  border-radius: 40px;
</pre>

```

```
pre {
  margin: 20px;
  padding: 20px;
  width: 80%;
  height: 50px;
}

pre#example-1 {
  border: solid 10px;
  border-radius: 10px 40px 40px 10px;
}

pre#example-2 {
  border: groove 1em red;
  border-radius: 2em;
}

pre#example-3 {
  background: gold;
  border: ridge gold;
  border-radius: 13em / 3em;
}

pre#example-4 {
  border: none;
  border-radius: 40px 10px;
  background: gold;
}

pre#example-5 {
  border: none;
  border-radius: 50%;
  background: burlywood;
}

pre#example-6 {
  border: dotted;
  border-width: 10px 4px;
  border-radius: 10px 40px;
}

pre#example-7 {
  border: dashed;
  border-width: 2px 4px;
  border-radius: 40px;
}

```

### [Using `corner-shape` with `border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#using_corner-shape_with_border-radius)

When a non- `0` `border-radius` value is applied to a box corner, you can use the [`corner-shape`](https://developer.mozilla.org/en-US/docs/Web/CSS/corner-shape) property (or one of its [longhands and shorthands](https://developer.mozilla.org/en-US/docs/Web/CSS/corner-shape#corner--shape_shorthands_and_longhands)) to apply custom shapes to that corner, such as a bevel, notch, or squircle. This example demonstrates `corner-shape` usage.

#### HTML

The markup for this example contains a single [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) element.

html

```
<div></div>

```

#### CSS

We give the box some basic styles, which we've hidden for brevity. We also apply a [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow), a `border-radius` of `0 20% 50px 30%`, and a `corner-shape` of `superellipse(0.5) bevel notch squircle`.

```
body {
  font-family: "Helvetica", "Arial", sans-serif;
  width: 240px;
  margin: 20px auto;
}

div {
  width: 100%;
  height: 180px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: green;
  background-image: linear-gradient(
    to bottom,
    rgb(255 255 255 / 0),
    rgb(255 255 255 / 0.5)
  );
}

```

css

```
div {
  box-shadow: 1px 1px 3px gray;
  border-radius: 0 20% 50px 30%;
  corner-shape: superellipse(0.5) bevel notch squircle;
}

```

#### Result

The rendered result looks like this:

Note how no corner shape is applied to the top-left corner, because it has a `border-radius` of `0` set.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#specifications)

| Specification |
| --- |
| [CSS Backgrounds and Borders Module Level 3\<br>\# border-radius](https://drafts.csswg.org/css-backgrounds/#border-radius) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius\#see_also)

- Border-radius-related CSS properties: [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius), [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius), [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius), [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius), [`border-start-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-start-radius), [`border-start-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius), [`border-end-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-start-radius), [`border-end-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-end-radius)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/border-radius/index.md?plain=1 "Folder: ⁨en-us/web/css/border-radius⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-radius&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fborder-radius%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fborder-radius%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fborder-radius%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fbb52c01c1534149f1e3e4755e2576ef7828ecc0f%0A*+Document+last+modified%3A+2025-10-13T00%3A08%3A12.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")