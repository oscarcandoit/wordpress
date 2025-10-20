---
url: https://getbootstrap.com/docs/5.3/helpers/vertical-rule
scraped_at: 2025-10-20T02:35:07.905Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/#bd-docs-nav)

Added in v5.1 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/vertical-rule.mdx "View and edit this file on GitHub")

# Vertical rule

Use the custom vertical rule helper to create vertical dividers like the `<hr>` element.

On this page
**On this page**

* * *

## How it works [Link to this section: How it works](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/\#how-it-works)

Vertical rules are inspired by the `<hr>` element, allowing you to create vertical dividers in common layouts. They’re styled just like `<hr>` elements:

- They’re `1px` wide
- They have `min-height` of `1em`
- Their color is set via `currentColor` and `opacity`

Customize them with additional styles as needed.

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/\#example)

html

```html
<div class="vr"></div>
```

Vertical rules scale their height in flex layouts:

html

```html
<div class="d-flex" style="height: 200px;">
  <div class="vr"></div>
</div>
```

## With stacks [Link to this section: With stacks](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/\#with-stacks)

They can also be used in [stacks](https://getbootstrap.com/docs/5.3/helpers/stacks):

First item

Second item

Third item

html

```html
<div class="hstack gap-3">
  <div class="p-2">First item</div>
  <div class="p-2 ms-auto">Second item</div>
  <div class="vr"></div>
  <div class="p-2">Third item</div>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/\#sass-variables)

Customize the vertical rule Sass variable to change its width.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$vr-border-width:             var(--#{$prefix}border-width);

```