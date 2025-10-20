---
url: https://getbootstrap.com/docs/5.3/utilities/opacity
scraped_at: 2025-10-20T02:36:29.695Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/opacity/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/opacity/#bd-docs-nav)

Added in v5.1 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/opacity.mdx "View and edit this file on GitHub")

# Opacity

Control the opacity of elements.

The `opacity` property sets the opacity level for an element. The opacity level describes the transparency level, where `1` is not transparent at all, `.5` is 50% visible, and `0` is completely transparent.

Set the `opacity` of an element using `.opacity-{value}` utilities.

100%

75%

50%

25%

0%

```html
<div class="opacity-100">...</div>
<div class="opacity-75">...</div>
<div class="opacity-50">...</div>
<div class="opacity-25">...</div>
<div class="opacity-0">...</div>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/opacity/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/opacity/\#sass-utilities-api)

Opacity utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"opacity": (
  property: opacity,
  values: (
    0: 0,
    25: .25,
    50: .5,
    75: .75,
    100: 1,
  )
),

```