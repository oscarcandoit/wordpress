---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path
scraped_at: 2025-10-20T03:01:02.736Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS motion path

The **CSS motion path** module allows authors to animate any graphical object along a custom path.

The [CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transforms) module provides features that enable boxes to be repositioned, rotated, scaled, and skewed relative to its laid out position, without disrupting the layout of any other elements on the page. These transforms can be animated and transitioned, but only in relatively basic ways.

The features of the CSS motion path module provide offset transforms: transforms that align a point on an element to an offset distance along an offset path, optionally rotating the transformed element to follow the path direction. This module enables powerful transform possibilities, for example:

- Positioning using polar coordinates rather than limiting transformation to the standard rectangular [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) function coordinates.
- Animating an element along a defined path.

CSS motion paths allow the definition of complex 2D spatial transitions by leveraging [CSS shape functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions#shape_functions).

For example, you can define a specific path of any shape you want with the [`offset-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path) property. You can then animate an element to move along that path by animating the [`offset-distance`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance) property, and rotate it at any point with the [`offset-rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate) property.

## [Motion paths in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#motion_paths_in_action)

htmlCopy

```
<div id="heart">
  <div id="motion-demo"></div>
</div>

```

cssCopy

```
#motion-demo {
  offset-path: path(
    "M20,70 A40,40,0,0,1,100,70 A40,40,0,0,1,180,70 Q180,130,100,190 Q20,130,20,70 Z"
  );
  animation: move 3000ms infinite linear;
  width: 10px;
  height: 10px;
  background: red;
}

#heart {
  width: 200px;
  height: 200px;
  background-color: lightpink;
  clip-path: path(
    "M20,70 A40,40,0,0,1,100,70 A40,40,0,0,1,180,70 Q180,130,100,190 Q20,130,20,70 Z"
  );
}

@keyframes move {
  100% {
    offset-distance: 100%;
  }
}

```

In this example, we used [CSS masking](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking) and [CSS shapes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shapes) to clip a container with a light pink background into a heart shape. We used a [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path) function as the value of the [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path) property. Its child is a `10px` by `10px` red box that is made to follow the edge of its parent. We did this by using the same [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape) as the path, setting the box's [`offset-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path) property to the same `path()` function value. We used [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations) to change the [`offset-distance`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance) from `0%` to `100%` over three seconds.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#properties)

- [`offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset) shorthand
- [`offset-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor)
- [`offset-distance`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance)
- [`offset-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path)
- [`offset-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position)
- [`offset-rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate)

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#functions)

- [`ray()`](https://developer.mozilla.org/en-US/docs/Web/CSS/ray)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#guides)

[Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)

Step-by-step tutorial on how to create animations using CSS.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#related_concepts)

[CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transforms) module

- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [`transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
- [`translate`](https://developer.mozilla.org/en-US/docs/Web/CSS/translate)

[CSS masking](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_masking) module

- [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
- [`clip-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-rule)

[CSS shapes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shapes) module

- [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape)
- [`circle()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/circle)
- [`ellipse()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/ellipse)
- [`inset()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/inset)
- [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path)
- [`polygon()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/polygon)
- [`rect()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/rect)
- [`shape()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/shape)
- [`xywh()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/xywh)

[CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations) module

- [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) shorthand
- [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)

[CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model) module

- [`<coord-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path#coord-box)

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#specifications)

| Specification |
| --- |
| [Motion Path Module Level 1](https://drafts.fxtf.org/motion/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path\#see_also)

- [`<position>`](https://developer.mozilla.org/en-US/docs/Web/CSS/position_value)
- [`<easing-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)
- [`radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient) function
- [`prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) media query
- [`will-change`](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change) CSS property

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 11, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_motion_path/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_motion_path/index.md?plain=1 "Folder: ⁨en-us/web/css/css_motion_path⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_motion_path&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_motion_path%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_motion_path%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_motion_path%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F11ef719d1a0bd75b1600d39abd6dfbdcd835c1e2%0A*+Document+last+modified%3A+2025-10-11T03%3A06%3A53.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")