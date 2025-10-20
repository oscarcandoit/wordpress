---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/zoom
scraped_at: 2025-10-20T03:05:26.166Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#search)

# zoom


Baseline

2024


Newly available

Since ⁨May 2024⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fzoom&level=low)

The **`zoom`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property can be used to control the magnification level of an element.
[`transform: scale()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale) can be used as an alternative to this property.

The `zoom` CSS property scales the targeted element, which can affect the page layout.
When scaling, the zoomed element scales from `top` and `center` when using the default [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode).

In contrast, an element scaled using [`scale()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale) will not cause layout recalculation or move other elements on the page.
If using `scale()` makes the contents larger than the containing element, then [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) comes into effect.
Additionally, elements adjusted using `scale()` transform from the `center` by default; this can be changed with the [`transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin) CSS property.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#syntax)

css

```
/* <percentage> values */
zoom: 50%;
zoom: 200%;

/* <number> values */
zoom: 1.1;
zoom: 0.7;

/* Non-standard keyword values */
zoom: normal;
zoom: reset;

/* Global values */
zoom: inherit;
zoom: initial;
zoom: revert;
zoom: revert-layer;
zoom: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#values)

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

Zoom factor. `100%` is equivalent to `normal`. Values larger than `100%` zoom in. Values smaller than `100%` zoom out.

[`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number)

Zoom factor. Equivalent to the corresponding percentage ( `1.0` = `100%` = `normal`). Values larger than `1.0` zoom in. Values smaller than `1.0` zoom out.

Two non-standard keyword values are not recommended. Check [browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#browser_compatibility) data:

[`normal`](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#normal)

Render the element at its normal size; equal to `zoom: 1`. Use the global [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset) keyword value instead.

[`reset`](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom#reset)

Resets the value to `zoom: 1` and prevents the element from being (de)magnified if the user applies non-pinch-based zooming (e.g., by pressing `Ctrl` \- `-` or `Ctrl` \+ `+` keyboard shortcuts) to the document.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `1` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| Percentages | Converted to [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified, but with [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) converted to the equivalent [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#formal_syntax)

```
zoom =
  [<number \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#examples)

### [Resizing paragraphs](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#resizing_paragraphs)

In this example the paragraph elements are zoomed, on hovering a paragraph the `zoom` value is `unset`.

#### HTML

html

```
<p class="small">Small</p>
<p class="normal">Normal</p>
<p class="big">Big</p>

```

#### CSS

```
body {
  display: flex;
  align-items: center;
  justify-content: space-around;
  height: 100vh;
}

```

css

```
.small {
  zoom: 75%;
}
.normal {
  zoom: normal;
}
.big {
  zoom: 2.5;
}
p:hover {
  zoom: unset;
}

```

#### Result

### [Resizing elements](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#resizing_elements)

In this example the `div` elements are zoomed using the `normal`, `<percentage>`, and `<number>` values.

#### HTML

html

```
<div id="a" class="circle"></div>
<div id="b" class="circle"></div>
<div id="c" class="circle"></div>

```

#### CSS

css

```
div.circle {
  width: 25px;
  height: 25px;
  border-radius: 100%;
  vertical-align: middle;
  display: inline-block;
}
div#a {
  background-color: gold;
  zoom: normal; /* circle is 25px diameter */
}
div#b {
  background-color: green;
  zoom: 200%; /* circle is 50px diameter */
}
div#c {
  background-color: blue;
  zoom: 2.9; /* circle is 72.5px diameter */
}

```

#### Result

### [Creating a zoom control](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#creating_a_zoom_control)

In this example a `select` field is used to change the zoom level of the element.

#### HTML

In this first block, of HTML, a `select` field is defined with the different `zoom` values to be used.

html

```
<section class="controls">
  <label for="zoom"
    >Zoom level
    <select name="zoom" id="zoom">
      <option value="0.5">Extra Small</option>
      <option value="0.75">Small</option>
      <option value="normal" selected>Normal</option>
      <option value="1.5">Large</option>
      <option value="2">Extra Large</option>
    </select>
  </label>
</section>

```

In this second block a **not supported** message is added that will be hidden if the browser supports `zoom`.

html

```
<p class="zoom-notice">CSS zoom is not supported</p>

```

The final block just defines the content that will be zoomed.

html

```
<section class="content">
  <h1>This is the heading</h1>
  <p>
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Placeat inventore
    ea eveniet, fugiat in consequatur molestiae nostrum repellendus nam
    provident repellat officiis facilis alias facere obcaecati quos sunt
    voluptas! Iste.
  </p>
  <p>
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Placeat inventore
    ea eveniet, fugiat in consequatur molestiae nostrum repellendus nam
    provident repellat officiis facilis alias facere obcaecati quos sunt
    voluptas! Iste.
  </p>
</section>

```

#### CSS

In this first block, of CSS, we are setting the starting value for the `--zoom-level` using [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) and then using that as the value for `zoom` on the content block.

css

```
html {
  --zoom-level: normal;
}
.content {
  max-width: 60ch;
  margin: auto;
  zoom: var(--zoom-level);
}

```

```
.controls,
.zoom-notice {
  display: flex;
  justify-content: space-around;
}
.zoom-notice {
  color: red;
}

```

In this final CSS block we are checking to see if the browser supports `zoom` and if so setting the **not supported** message to `display: none;`.

css

```
@supports (zoom: 1) {
  .zoom-notice {
    display: none;
  }
}

```

#### JavaScript

This JavaScript watches for a change in the select field and sets the new value for `--zoom-level` on the content `section`, e.g., `style="--zoom-level: 1.5;"`.

js

```
const zoomControl = document.querySelector("#zoom");
const content = document.querySelector(".content");
const updateZoom = () => {
  content.style = `--zoom-level: ${zoomControl.value}`;
};
zoomControl.addEventListener("change", updateZoom);

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#specifications)

| Specification |
| --- |
| [CSS Viewport Module Level 1\<br>\# zoom-property](https://drafts.csswg.org/css-viewport/#zoom-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom\#see_also)

- [`zoom` entry in CSS-Tricks' CSS Almanac](https://css-tricks.com/almanac/properties/z/zoom/)
- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [`scale`](https://developer.mozilla.org/en-US/docs/Web/CSS/scale)
- [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset) keyword
- [Legacy `zoom` property](https://css-tricks.com/almanac/properties/z/zoom/) via CSS-Tricks (2013)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/zoom/index.md?plain=1 "Folder: ⁨en-us/web/css/zoom⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fzoom&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fzoom%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fzoom%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fzoom%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")