---
url: https://getbootstrap.com/docs/5.1/utilities/sizing
scraped_at: 2025-10-20T02:39:56.398Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/utilities/sizing/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/utilities/sizing/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/utilities/sizing.md "View and edit this file on GitHub")

# Sizing

Easily make an element as wide or as tall with our width and height utilities.

**On this page**

## Relative to the parent [Anchor](https://getbootstrap.com/docs/5.1/utilities/sizing/\#relative-to-the-parent)

Width and height utilities are generated from the utility API in `_utilities.scss`. Includes support for `25%`, `50%`, `75%`, `100%`, and `auto` by default. Modify those values as you need to generate different utilities here.

Width 25%

Width 50%

Width 75%

Width 100%

Width auto

Copy

```html
<div class="w-25 p-3" style="background-color: #eee;">Width 25%</div>
<div class="w-50 p-3" style="background-color: #eee;">Width 50%</div>
<div class="w-75 p-3" style="background-color: #eee;">Width 75%</div>
<div class="w-100 p-3" style="background-color: #eee;">Width 100%</div>
<div class="w-auto p-3" style="background-color: #eee;">Width auto</div>
```

Height 25%

Height 50%

Height 75%

Height 100%

Height auto

Copy

```html
<div style="height: 100px; background-color: rgba(255,0,0,0.1);">
  <div class="h-25 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 25%</div>
  <div class="h-50 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 50%</div>
  <div class="h-75 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 75%</div>
  <div class="h-100 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 100%</div>
  <div class="h-auto d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height auto</div>
</div>
```

You can also use `max-width: 100%;` and `max-height: 100%;` utilities as needed.

PlaceholderMax-width 100%

Copy

```html
<img src="..." class="mw-100" alt="...">
```

Max-height 100%

Copy

```html
<div style="height: 100px; background-color: rgba(255,0,0,.1);">
  <div class="mh-100" style="width: 100px; height: 200px; background-color: rgba(0,0,255,.1);">Max-height 100%</div>
</div>
```

## Relative to the viewport [Anchor](https://getbootstrap.com/docs/5.1/utilities/sizing/\#relative-to-the-viewport)

You can also use utilities to set the width and height relative to the viewport.

Copy

```html
<div class="min-vw-100">Min-width 100vw</div>
<div class="min-vh-100">Min-height 100vh</div>
<div class="vw-100">Width 100vw</div>
<div class="vh-100">Height 100vh</div>

```

## Sass [Anchor](https://getbootstrap.com/docs/5.1/utilities/sizing/\#sass)

### Utilities API [Anchor](https://getbootstrap.com/docs/5.1/utilities/sizing/\#utilities-api)

Sizing utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.1/utilities/api/#using-the-api)

Copy

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