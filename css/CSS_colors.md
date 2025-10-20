---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors
scraped_at: 2025-10-20T02:58:42.267Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS colors

The **CSS colors** module defines colors, color types, color blending, opacity, and how you can apply these colors and effects to HTML content.

While this module has only two CSS properties, [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) and [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity), over 20 CSS and SVG properties, CSS images, at-rules, and @media rules depend on these two properties.

## [Colors in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#colors_in_action)

The color syntax converter below shows the values of the currently selected color in [red-green-blue](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb) (RGB), [hexadecimal](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color) (HEX), [hue, saturation, and lightness](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl) (HSL), and [hue, whiteness, and blackness](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb) (HWB) CSS color formats. All the RGB, HEX, HSL, and HWB color values here, while written differently, represent the same color value.

Color syntax converter

| RGB | rgb(186 218 85) |
| HEX | #bada55 |
| HSL | hsl(74 64.3% 59.4%) |
| HWB | hwb(74 33.3% 14.5%) |
| color() | color(srgb 0.73 0.85 0.33) |

Current color values:


Select a color:

Select an opacity:

Selecting a color via the [color picker](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input/color) and an opacity via the [slider](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input/range) updates the RGB, HEX, HSL, and HWB values. When you choose a new color or opacity value, the color of the background and the slider update via the CSS properties [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) and [`accent-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/accent-color), respectively.

To see the code for this color syntax converter, [view the source on GitHub](https://github.com/mdn/css-examples/blob/main/modules/colors.html).

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#properties)

- [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
- [`dynamic-range-limit`](https://developer.mozilla.org/en-US/docs/Web/CSS/dynamic-range-limit)
- [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity)

### [At-rules and descriptors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#at-rules_and_descriptors)

The CSS colors module also introduces the [`@color-profile`](https://developer.mozilla.org/en-US/docs/Web/CSS/@color-profile) at-rule, along with its `components`, `rendering-intent` and `src` descriptors. Currently, no browsers support these features.

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#functions)

- Color functions:
  - [`rgb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb)
  - [`hsl()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl)
  - [`hwb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb)
  - [`lab()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lab)
  - [`lch()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lch)
  - [`oklab()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklab)
  - [`oklch()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch)
  - [`color()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color)
- [`color-mix()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix)
- [`contrast-color()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/contrast-color)
- [`light-dark()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/light-dark)
- [`dynamic-range-limit-mix()`](https://developer.mozilla.org/en-US/docs/Web/CSS/dynamic-range-limit-mix)

The CSS color modules also introduce the [`device-cmyk()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/device-cmyk), `contrast-color()`, and `hdr-color()` functions. Currently, no browsers support these features.

### [Data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#data_types)

- [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)
- [`<color-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors#functions)
- [`<hex-color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color)
- [`<named-color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color)
- [`<alpha-value>`](https://developer.mozilla.org/en-US/docs/Web/CSS/alpha-value)
- [`<hue>`](https://developer.mozilla.org/en-US/docs/Web/CSS/hue)
- [`<system-color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/system-color)
- [`<colorspace-params>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color#using_predefined_color_spaces_with_color)

### [Glossary terms and keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#glossary_terms_and_keywords)

- [color space](https://developer.mozilla.org/en-US/docs/Glossary/Color_space)
- [`currentColor`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword)
- [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
- [RGB](https://developer.mozilla.org/en-US/docs/Glossary/RGB)
- [`transparent`](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color#transparent)

### [Interfaces](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#interfaces)

The CSS color module also introduces the `CSSColorProfileRule` interface. Currently, no browsers support this feature.

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#guides)

[Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Applying_color)

A guide to using CSS to apply color to a variety of types of content, including all CSS properties that accept `<color>` as a value.

[CSS color values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Color_values)

An overview of color spaces and the different `<color>` functional notations available in CSS.

[Using color wisely](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Using_color_wisely)

Color theory and resources, including finding the right colors to create an accessible color palette, contrast, and printing in color.

[Using relative colors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Relative_colors)

This article explains relative CSS color syntax, shows what the different options are, and looks at some illustrative examples.

[Color format converter](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Color_format_converter)

A tool that lets you enter or pick a color and copy its corresponding value in any CSS [color format](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value).

[Understanding color and luminance](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Colors_and_Luminance)

Color perception and using colors with color insensitive (color blind) users, reduced vision users and users with vestibular disorders or other neurological disorders in mind.

[WCAG 1.4.1: Color contrast](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable/Color_contrast)

Explanation of contrast requirements between background and foreground content to ensure legibility.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#related_concepts)

- CSS properties that are part of other specifications:
  - [`accent-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/accent-color)
  - [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
  - [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
  - [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color)
  - [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)
  - [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
  - [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
  - [`color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme)
  - [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color)
  - [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)
  - [`scrollbar-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color)
  - [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)
  - [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color)
  - [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)
  - [`-webkit-tap-highlight-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-tap-highlight-color)
- SVG color properties that are part of other specifications:
  - [`fill`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/fill)
  - [`flood-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/flood-color)
  - [`lighting-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/lighting-color)
  - [`stop-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stop-color)
  - [`stroke`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/stroke)
- SVG [`color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/color) attribute
- [Color wheel](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel) glossary term
- [Interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation) glossary term
- The [`@font-palette-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values) at-rule [`override-colors`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/override-colors) descriptor
- The [`@color-profile`](https://developer.mozilla.org/en-US/docs/Web/CSS/@color-profile) at-rule
- The [`color-gamut`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-gamut) @media feature
- The [`forced-colors`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/forced-colors) @media feature

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#specifications)

| Specification |
| --- |
| [CSS Color Module Level 4](https://drafts.csswg.org/css-color/) |
| [CSS Color Module Level 5](https://drafts.csswg.org/css-color-5/) |
| [CSS Color HDR Module Level 1](https://drafts.csswg.org/css-color-hdr/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors\#see_also)

- [CSS color adjustment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_color_adjustment) module and the [`print-color-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/print-color-adjust) property.
- [CSS images](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images) module, which is where CSS [`<gradient>`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient) images are defined.
- The [`VideoColorSpace`](https://developer.mozilla.org/en-US/docs/Web/API/VideoColorSpace) interface
- The SVG [`<feColorMatrix>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/feColorMatrix) element
- [Canvas API: applying styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors#colors)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 3, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_colors/index.md?plain=1 "Folder: ⁨en-us/web/css/css_colors⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_colors&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_colors%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_colors%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_colors%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F54ac1367cb817a0079c30d2e36b5cbafc0a01431%0A*+Document+last+modified%3A+2025-10-03T13%3A03%3A00.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")