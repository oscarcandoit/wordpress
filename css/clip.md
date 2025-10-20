---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/clip
scraped_at: 2025-10-20T03:01:11.443Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/clip#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/clip#search)

# clip

**Deprecated:** This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](https://developer.mozilla.org/en-US/docs/Web/CSS/clip#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning:**
Authors are encouraged to use the [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path) property instead.

The **`clip`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a visible portion of an element. The `clip` property applies only to absolutely positioned elements — that is, elements with [`position:absolute`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) or [`position:fixed`](https://developer.mozilla.org/en-US/docs/Web/CSS/position).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#syntax)

css

```
/* Keyword value */
clip: auto;

/* <shape> values */
clip: rect(1px, 10em, 3rem, 2ch);

/* Global values */
clip: inherit;
clip: initial;
clip: revert;
clip: revert-layer;
clip: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#values)

[`rect()`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip#rect)

A rectangle defined using a `rect()` function of the form `rect(<top>, <right>, <bottom>, <left>)`. The `<top>` and `<bottom>` values are offsets from the _inside top border edge_ of the box, while `<right>` and `<left>` are offsets from the _inside left border edge_ of the box — that is, the extent of the padding box.

The `<top>`, `<right>`, `<bottom>`, and `<left>` values may be either a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) or `auto`. If any side's value is `auto`, the element is clipped to that side's _inside border edge_.

**Note:**
The `rect()` [`<shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape) function used in the deprecated `clip` property is different from the CSS [`rect()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/rect) function used to define a CSS [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape).

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip#auto)

The element does not clip (default). This is different from `rect(auto, auto, auto, auto)`, which clips to the element's inside border edges.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | absolutely positioned elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | `auto` if specified as `auto`, otherwise a rectangle with four values, each of which is `auto` if specified as `auto` or the computed length otherwise |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | a [rectangle](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#interpolation "Values of the <shape> CSS data type which are rectangles are interpolated over their top, right, bottom and left component, each treated as a real, floating-point number.") |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#formal_syntax)

```
clip =
  <rect()>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

<rect()> =
  rect(  [<top>](https://developer.mozilla.org/en-US/docs/Web/CSS/top) , [<right>](https://developer.mozilla.org/en-US/docs/Web/CSS/right) , [<bottom>](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom) , [<left>](https://developer.mozilla.org/en-US/docs/Web/CSS/left) )

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#examples)

### [Clipping an image](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#clipping_an_image)

html

```
<p class="dotted-border">
  <img src="macarons.png" alt="Original graphic" />
  <img id="top-left" src="macarons.png" alt="Graphic clipped to upper left" />
  <img id="middle" src="macarons.png" alt="Graphic clipped towards middle" />
  <img
    id="bottom-right"
    src="macarons.png"
    alt="Graphic clipped to bottom right" />
</p>

```

css

```
.dotted-border {
  border: dotted;
  position: relative;
  width: 390px;
  height: 400px;
}

#top-left,
#middle,
#bottom-right {
  position: absolute;
  top: 0;
}

#top-left {
  left: 400px;
  clip: rect(0, 130px, 90px, 0);
}

#middle {
  left: 270px;
  clip: rect(100px, 260px, 190px, 130px);
}

#bottom-right {
  left: 140px;
  clip: rect(200px, 390px, 290px, 260px);
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#specifications)

| Specification |
| --- |
| [CSS Masking Module Level 1\<br>\# clip-property](https://drafts.fxtf.org/css-masking/#clip-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/clip\#see_also)

- [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
- [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [`mask`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
- [`shape-image-threshold`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-image-threshold)
- [`shape-outside`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/clip/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/clip/index.md?plain=1 "Folder: ⁨en-us/web/css/clip⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fclip&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fclip%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fclip%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fclip%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")