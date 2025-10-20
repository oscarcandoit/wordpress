---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/shape
scraped_at: 2025-10-20T03:05:55.859Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# <shape>

**Deprecated:** This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`<shape>`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types) defines the specific form (shape) of a region. The region represents the part of an element to which the [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip) property applies.

**Note:** `<shape>` and `rect()` work in conjunction with [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip), which has been deprecated in favor of [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path). When possible, use `clip-path` and the [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape) data type instead.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#syntax)

The `<shape>` data type is specified using the `rect()` function, which produces a region in the form of a rectangle.

`rect()`

cssCopy

```
rect(top, right, bottom, left)

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#values)

![A graph showing top, right, bottom, and left, as described below. These define the rectangle's shape. The upper left corner is defined by the top and left values. The bottom right corner is defined by the bottom and right values.](https://developer.mozilla.org/en-US/docs/Web/CSS/shape/rect.png)

[_top_](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#top)

Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) representing the offset for the top of the rectangle relative to the top border of the element's box.

[_right_](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#right)

Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) representing the offset for the right of the rectangle relative to the left border of the element's box.

[_bottom_](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#bottom)

Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) representing the offset for the bottom of the rectangle relative to the top border of the element's box.

[_left_](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#left)

Is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) representing the offset for the left of the rectangle relative to the left border of the element's box.

## [Interpolation](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#interpolation)

When animated, values of the `<shape>` data type are interpolated over their `top`, `right`, `bottom`, and `left` components, each treated as a real, floating-point number. The speed of the interpolation is determined by the [easing function](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function) associated with the animation.

## [Example](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#example)

### [Example demonstrating correct use of the rect() function](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#example_demonstrating_correct_use_of_the_rect_function)

cssCopy

```
img.clip04 {
  clip: rect(10px, 20px, 20px, 10px);
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#specifications)

| Specification |
| --- |
| [Cascading Style Sheets Level 2\<br>\# value-def-shape](https://drafts.csswg.org/css2/#value-def-shape) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/shape\#see_also)

- Related CSS property: [`clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/shape/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/shape/index.md?plain=1 "Folder: ⁨en-us/web/css/shape⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fshape&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fshape%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fshape%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fshape%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")