---
url: https://getbootstrap.com/docs/5.3/helpers/stacks
scraped_at: 2025-10-20T02:34:44.904Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/stacks/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/stacks/#bd-docs-nav)

Added in v5.1 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/stacks.mdx "View and edit this file on GitHub")

# Stacks

Shorthand helpers that build on top of our flexbox utilities to make component layout faster and easier than ever.

On this page
**On this page**

* * *

Stacks offer a shortcut for applying a number of flexbox properties to quickly and easily create layouts in Bootstrap. All credit for the concept and implementation goes to the open source [Pylon project](https://almonk.github.io/pylon/).

**Heads up!** Support for gap utilities with flexbox isn’t available in Safari prior to 14.5, so consider verifying your intended browser support. Grid layout should have no issues. [Read more](https://caniuse.com/flexbox-gap).

## Vertical [Link to this section: Vertical](https://getbootstrap.com/docs/5.3/helpers/stacks/\#vertical)

Use `.vstack` to create vertical layouts. Stacked items are full-width by default. Use `.gap-*` utilities to add space between items.

First item

Second item

Third item

html

```html
<div class="vstack gap-3">
  <div class="p-2">First item</div>
  <div class="p-2">Second item</div>
  <div class="p-2">Third item</div>
</div>
```

## Horizontal [Link to this section: Horizontal](https://getbootstrap.com/docs/5.3/helpers/stacks/\#horizontal)

Use `.hstack` for horizontal layouts. Stacked items are vertically centered by default and only take up their necessary width. Use `.gap-*` utilities to add space between items.

First item

Second item

Third item

html

```html
<div class="hstack gap-3">
  <div class="p-2">First item</div>
  <div class="p-2">Second item</div>
  <div class="p-2">Third item</div>
</div>
```

Using horizontal margin utilities like `.ms-auto` as spacers:

First item

Second item

Third item

html

```html
<div class="hstack gap-3">
  <div class="p-2">First item</div>
  <div class="p-2 ms-auto">Second item</div>
  <div class="p-2">Third item</div>
</div>
```

And with [vertical rules](https://getbootstrap.com/docs/5.3/helpers/vertical-rule):

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

## Examples [Link to this section: Examples](https://getbootstrap.com/docs/5.3/helpers/stacks/\#examples)

Use `.vstack` to stack buttons and other elements:

Save changesCancel

html

```html
<div class="vstack gap-2 col-md-5 mx-auto">
  <button type="button" class="btn btn-secondary">Save changes</button>
  <button type="button" class="btn btn-outline-secondary">Cancel</button>
</div>
```

Create an inline form with `.hstack`:

Submit

Reset

html

```html
<div class="hstack gap-3">
  <input class="form-control me-auto" type="text" placeholder="Add your item here..." aria-label="Add your item here...">
  <button type="button" class="btn btn-secondary">Submit</button>
  <div class="vr"></div>
  <button type="button" class="btn btn-outline-danger">Reset</button>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/helpers/stacks/\#css)

[scss/helpers/\_stacks.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/helpers/_stacks.scss)

```scss
.hstack {
  display: flex;
  flex-direction: row;
  align-items: center;
  align-self: stretch;
}

.vstack {
  display: flex;
  flex: 1 1 auto;
  flex-direction: column;
  align-self: stretch;
}

```