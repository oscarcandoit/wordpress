---
url: https://getbootstrap.com/docs/5.3/utilities/z-index
scraped_at: 2025-10-20T02:37:03.491Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/z-index/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/z-index/#bd-docs-nav)

Added in v5.3 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/z-index.mdx "View and edit this file on GitHub")

# Z-index

Use our low-level `z-index` utilities to quickly change the stack level of an element or component.

On this page
**On this page**

* * *

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/utilities/z-index/\#example)

Use `z-index` utilities to stack elements on top of one another. Requires a `position` value other than `static`, which can be set with custom styles or using our [position utilities](https://getbootstrap.com/docs/5.3/utilities/position/).

We call these “low-level” `z-index` utilities because of their default values of `-1` through `3`, which we use for the layout of overlapping components. High-level `z-index` values are used for overlay components like modals and tooltips.

z-3

z-2

z-1

z-0

z-n1

html

```html
<div class="z-3 position-absolute p-5 rounded-3"><span>z-3</span></div>
<div class="z-2 position-absolute p-5 rounded-3"><span>z-2</span></div>
<div class="z-1 position-absolute p-5 rounded-3"><span>z-1</span></div>
<div class="z-0 position-absolute p-5 rounded-3"><span>z-0</span></div>
<div class="z-n1 position-absolute p-5 rounded-3"><span>z-n1</span></div>
```

## Overlays [Link to this section: Overlays](https://getbootstrap.com/docs/5.3/utilities/z-index/\#overlays)

Bootstrap overlay components—dropdown, modal, offcanvas, popover, toast, and tooltip—all have their own `z-index` values to ensure a usable experience with competing “layers” of an interface.

Read about them in the [`z-index` layout page](https://getbootstrap.com/docs/5.3/layout/z-index).

## Component approach [Link to this section: Component approach](https://getbootstrap.com/docs/5.3/utilities/z-index/\#component-approach)

On some components, we use our low-level `z-index` values to manage repeating elements that overlap one another (like buttons in a button group or items in a list group).

Learn about our [`z-index` approach](https://getbootstrap.com/docs/5.3/extend/approach#z-index-scales).

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/z-index/\#css)

### Sass maps [Link to this section: Sass maps](https://getbootstrap.com/docs/5.3/utilities/z-index/\#sass-maps)

Customize this Sass map to change the available values and generated utilities.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$zindex-levels: (
  n1: -1,
  0: 0,
  1: 1,
  2: 2,
  3: 3
);

```

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/z-index/\#sass-utilities-api)

Position utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"z-index": (
  property: z-index,
  class: z,
  values: $zindex-levels,
)

```