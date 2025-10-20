---
url: https://getbootstrap.com/docs/5.3/utilities/sizing
scraped_at: 2025-10-20T02:36:47.307Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/sizing/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/sizing/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/sizing.mdx "View and edit this file on GitHub")

# Sizing

Easily make an element as wide or as tall with our width and height utilities.

On this page
**On this page**

* * *

## Relative to the parent [Link to this section: Relative to the parent](https://getbootstrap.com/docs/5.3/utilities/sizing/\#relative-to-the-parent)

Width and height utilities are generated from the utility API in `_utilities.scss`. Includes support for `25%`, `50%`, `75%`, `100%`, and `auto` by default. Modify those values as you need to generate different utilities here.

Width 25%

Width 50%

Width 75%

Width 100%

Width auto

html

```html
<div class="w-25 p-3">Width 25%</div>
<div class="w-50 p-3">Width 50%</div>
<div class="w-75 p-3">Width 75%</div>
<div class="w-100 p-3">Width 100%</div>
<div class="w-auto p-3">Width auto</div>
```

Height 25%

Height 50%

Height 75%

Height 100%

Height auto

html

```html
<div style="height: 100px;">
  <div class="h-25 d-inline-block" style="width: 120px;">Height 25%</div>
  <div class="h-50 d-inline-block" style="width: 120px;">Height 50%</div>
  <div class="h-75 d-inline-block" style="width: 120px;">Height 75%</div>
  <div class="h-100 d-inline-block" style="width: 120px;">Height 100%</div>
  <div class="h-auto d-inline-block" style="width: 120px;">Height auto</div>
</div>
```

You can also use `max-width: 100%;` and `max-height: 100%;` utilities as needed.

Max-width 100%

html

```html
<div style="width: 50%; height: 100px;">
  <div class="mw-100" style="width: 200%;">Max-width 100%</div>
</div>
```

Max-height 100%

html

```html
<div style="height: 100px;">
  <div class="mh-100" style="width: 100px; height: 200px;">Max-height 100%</div>
</div>
```

## Relative to the viewport [Link to this section: Relative to the viewport](https://getbootstrap.com/docs/5.3/utilities/sizing/\#relative-to-the-viewport)

You can also use utilities to set the width and height relative to the viewport.

```html
<div class="min-vw-100">Min-width 100vw</div>
<div class="min-vh-100">Min-height 100vh</div>
<div class="vw-100">Width 100vw</div>
<div class="vh-100">Height 100vh</div>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/sizing/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/sizing/\#sass-utilities-api)

Sizing utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"width": (
  property: width,
  class: w,
  values: (
    25: 25%,
    50: 50%,
    75: 75%,
    100: 100%,
    auto: auto
  )
),
"max-width": (
  property: max-width,
  class: mw,
  values: (100: 100%)
),
"viewport-width": (
  property: width,
  class: vw,
  values: (100: 100vw)
),
"min-viewport-width": (
  property: min-width,
  class: min-vw,
  values: (100: 100vw)
),
"height": (
  property: height,
  class: h,
  values: (
    25: 25%,
    50: 50%,
    75: 75%,
    100: 100%,
    auto: auto
  )
),
"max-height": (
  property: max-height,
  class: mh,
  values: (100: 100%)
),
"viewport-height": (
  property: height,
  class: vh,
  values: (100: 100vh)
),
"min-viewport-height": (
  property: min-height,
  class: min-vh,
  values: (100: 100vh)
),

```