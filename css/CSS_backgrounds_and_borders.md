---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders
scraped_at: 2025-10-20T03:05:49.717Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders#search)

# CSS backgrounds and borders

The **CSS backgrounds and borders** module provides properties for adding backgrounds, borders, rounded corners, and box shadows to elements.

You can add different types of border styles, including borders made of images of any image type, from raster images to CSS gradients. Borders can be square or rounded, and a different radius can be set for each corner. Elements can be rounded whether or not they have a visible border.

Box shadows include inset and outset shadow, single or multiple shadows, and solid or allowed to fade to transparent. An outer box-shadow casts a shadow as if the border-box of the element were opaque. An inner box-shadow casts a shadow as if everything outside the padding edge were opaque. The shadow can be solid or include a spread distance with the shadow color transitioning to transparent.

The properties in this module also let you define whether cells inside a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/table) should have shared or separate borders.

### [Backgrounds, borders, and box shadows in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#backgrounds_borders_and_box_shadows_in_action)

This sample of borders, backgrounds, and box shadows consists of centered background images made of linear and radial gradients. A series of box shadows make the border appear to "pop". The element on the left has a border image set. The element on the right has a rounded dotted border.

```
<article>
  <div></div>
  <div></div>
</article>

```

```
article {
  display: flex;
  gap: 10px;
}
div {
  color: #58ade3;
  height: 320px;
  width: 240px;
  padding: 20px;
  margin: 10px;
  border: dotted 15px; /* defaults to `currentColor` */
  border-radius: 100px 0;
  background-image:
    radial-gradient(
      circle,
      transparent 60%,
      currentColor 60% 70%,
      transparent 70%
    ),
    linear-gradient(45deg, currentColor, white),
    linear-gradient(transparent, transparent);
  /* the third transparent background image was added to provide space for the background color to show through */
  background-color: currentColor;
  background-position: center;
  background-size:
    60px 60px,
    120px 120px;
  background-clip: content-box, content-box, padding-box;
  box-shadow:
    inset 5px 5px 5px rgb(0 0 0 / 0.4),
    inset -5px -5px 5px rgb(0 0 0 / 0.4),
    5px 5px 5px rgb(0 0 0 / 0.4),
    -5px -5px 5px rgb(0 0 0 / 0.4);
}
div:first-of-type {
  border-radius: 0;
  border-image-source: repeating-conic-gradient(
    from 3deg at 25% 25%,
    currentColor 0 3deg,
    transparent 3deg 6deg
  );
  border-image-slice: 30;
}

```

The background images are defined with [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image). The images are centered with [`background-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position). Different values of the [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip) property for the multiple background images are used to make the background images stay within the content box. The background color gets clipped to the padding box preventing the background from appearing through the transparent sections for the [`border-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image) and the [`dotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border). The rounded corners in the element on the right are created using the [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) property. A single [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) declaration is used to set all the shadows, both inset and outset.

Click "Play" in the example above to see or edit the code for the animation in the MDN Playground.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#properties)

- [`background-attachment`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment)
- [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip)
- [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
- [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
- [`background-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin)
- [`background-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position)
- [`background-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
- [`background-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)
- [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) shorthand
- [`background-position-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x)
- [`background-position-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-y)
- [`border-bottom-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color)
- [`border-bottom-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style)
- [`border-bottom-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width)
- [`border-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom) shorthand
- [`border-left-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color)
- [`border-left-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-style)
- [`border-left-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width)
- [`border-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left) shorthand
- [`border-right-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-color)
- [`border-right-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-style)
- [`border-right-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width)
- [`border-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right) shorthand
- [`border-top-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color)
- [`border-top-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-style)
- [`border-top-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width)
- [`border-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top) shorthand
- [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color) shorthand
- [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) shorthand
- [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) shorthand
- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) shorthand
- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius)
- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius)
- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius)
- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius)
- [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) shorthand
- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset)
- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat)
- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice)
- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source)
- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width)
- [`border-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image) shorthand
- [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)

The CSS backgrounds module level 4 also introduces the `background-position-block`, `background-position-inline`, `background-repeat-block`, `background-repeat-inline`, `background-repeat-x`, `background-repeat-y`, and `background-tbd` properties. Currently, no browsers support these features.

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#data_types)

- [`<line-style>`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-style) enumerated type

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#guides)

[Using multiple backgrounds](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Using_multiple_backgrounds)

Setting one or more backgrounds on an element.

[Resizing background images](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Resizing_background_images)

Changing the size and repeating behavior of background images.

[Scaling SVG backgrounds](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Scaling_of_SVG_backgrounds)

How SVG aspect ratio, SVG dimension values, and the CSS `background-size` property impact the scaling of SVG background images.

[Using CSS gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Using_CSS_gradients)

Creating CSS gradients and using them as background images.

[Learn CSS: background and borders](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Backgrounds_and_borders)

Learn how to implement decorative images using CSS background images.

[Learn CSS: the box model](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model)

Learn how borders and other box model properties impact the CSS box model.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#related_concepts)

- [`border-block-end-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-color)
- [`border-block-start-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-color)
- [`border-inline-end-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-color)
- [`border-inline-start-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-color)
- [`border-block-end-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-style)
- [`border-block-start-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-style)
- [`border-inline-end-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-style)
- [`border-inline-start-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-style)
- [`border-block-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-width)
- [`border-block-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-width)
- [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width)
- [`border-inline-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width)
- [`border-start-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-start-radius)
- [`border-start-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius)
- [`border-end-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-start-radius)
- [`border-end-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-end-radius)
- [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
- [`box-decoration-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)
- [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) data type
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value) data type
- [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image) data type
- [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) data type
- [`currentColor`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword) keyword

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#specifications)

| Specification |
| --- |
| [CSS Backgrounds and Borders Module Level 3](https://drafts.csswg.org/css-backgrounds/) |
| [CSS Backgrounds Module Level 4](https://drafts.csswg.org/css-backgrounds-4/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders\#see_also)

- [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
- [`backdrop-filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter)
- [`drop-shadow()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow) filter function
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Applying_color)
- [Border-image generator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Border-image_generator)
- [Border-radius generator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Border-radius_generator)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Sep 8, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_backgrounds_and_borders/index.md?plain=1 "Folder: ⁨en-us/web/css/css_backgrounds_and_borders⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_backgrounds_and_borders&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_backgrounds_and_borders%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_backgrounds_and_borders%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_backgrounds_and_borders%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F3dcdca5a04e1a40d0fe8ed0f9694c57cfb138a4f%0A*+Document+last+modified%3A+2025-09-08T13%3A59%3A31.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")