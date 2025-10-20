---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/d
scraped_at: 2025-10-20T03:00:48.715Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/d#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/d#search)

# d

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/d#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fd&level=not)

The **`d`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a path to be drawn by the SVG [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path) element. If present, it overrides the element's [`d`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/d) attribute.

**Note:**
The `d` property only applies to [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path) elements nested in an [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/svg). It doesn't apply to other SVG elements nor to HTML elements or pseudo-elements.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#syntax)

css

```
/* Default */
d: none;

/* Basic usage */
d: path("m 5,5 h 35 L 20,30 z");
d: path("M 0,25 l 50,150 l 200,50 z");
d: path("M 10,5 l 90,0 -80,80 0,-60 80,80 -90,0 z");

/* Global values */
d: inherit;
d: initial;
d: revert;
d: revert-layer;
d: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#values)

The value is either a [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path) function with a single [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string) parameter or the keyword `none`.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/d#none)

No path is drawn.

[`path(<string>)`](https://developer.mozilla.org/en-US/docs/Web/CSS/d#pathstring)

A `path()` function with a quoted [data string](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/d) parameter. The data string defines an [SVG path](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path). The SVG path data string contains [path commands](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/d#path_commands) that implicitly use pixel units. An empty path is considered invalid.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `none` |
| Applies to | [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/path) element in [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/svg) |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | yes, as specified for [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape), otherwise no |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#formal_syntax)

```
d =
  none       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<string>](https://developer.mozilla.org/en-US/docs/Web/CSS/string)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#examples)

### [Specifying path data](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#specifying_path_data)

This example demonstrates the basic use case of `d`, and how the CSS `d` property takes precedence over the `d` attribute.

#### HTML

We include two identical `<path>` elements in an SVG; their `d` attribute values are `"m 5,5 h 90 v 90 h -90 v -90 z"`, which creates a `90px` square.

html

```
<svg>
  <path d="m 5,5 h 90 v 90 h -90 v -90 z" />
  <path d="m 5,5 h 90 v 90 h -90 v -90 z" />
</svg>

```

#### CSS

With CSS, we style both paths, providing a black [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke) and semi-opaque red [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill). We then use the `d` property to override the value of the SVG [`d`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/d) attribute for the last path only. The browser renders SVG images as `300px` wide and `150px` tall by default.

css

```
svg {
  border: 1px solid;
}

path {
  fill: #ff333388;
  stroke: black;
}

path:last-of-type {
  d: path(
    "M10,30 A20,20 0,0,1 50,30 A20,20 0,0,1 90,30 Q90,60 50,90 Q10,60 10,30 z"
  );
}

```

#### Results

The second `<path>` is a heart, as defined in the CSS `d` property's `path()` function value. The unstyled `<path>`'s path remained a square, as defined in its SVG `d` attribute value.

### [Animating data paths](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#animating_data_paths)

This example demonstrates animating the `d` attribute value.

#### HTML

We create a `<svg>` containing a single `<path>` element.

html

```
<svg>
  <path />
</svg>

```

#### CSS

We use the `d` attribute to define a heart with a line through it. We use CSS to define the [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill), [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke), and [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width) of that path, and add a two-second [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition). We add a [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) style that contains a slightly different [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path) function; the path has the same number of data points as the default state, making the path animatable.

css

```
svg {
  border: 1px solid;
}

path {
  d: path(
    "M10,30 A20,20 0,0,1 50,30 A20,20 0,0,1 90,30 Q90,60 50,90 Q10,60 10,30 z M90,5 L5,90"
  );
  transition: all 2s;
  fill: none;
  stroke: red;
  stroke-width: 3px;
}

svg:hover path {
  d: path(
    "M10,30 A20,20 0,0,1 50,30 A20,20 0,0,1 90,30 Q90,60 50,90 Q10,60 10,30 z M5,5 L90,90"
  );
  stroke: black;
}

```

#### Results

To view the animation, hover over the SVG.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#specifications)

| Specification |
| --- |
| [Scalable Vector Graphics (SVG) 2\<br>\# TheDProperty](https://svgwg.org/svg2-draft/paths.html#TheDProperty) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/d\#see_also)

- SVG [`d`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/d) attribute
- [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill)
- [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke)
- [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path) function
- [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape) data type
- [Overview of CSS shapes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shapes/Overview_of_shapes)
- [CSS shapes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shapes) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/d/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/d/index.md?plain=1 "Folder: ⁨en-us/web/css/d⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fd&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fd%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fd%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fd%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")