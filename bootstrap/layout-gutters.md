---
url: https://getbootstrap.com/docs/5.3/layout/gutters
scraped_at: 2025-10-20T03:55:36.847Z
attempt: 1
---

[Skip to main content](https://getbootstrap.com/docs/5.3/layout/gutters/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/layout/gutters/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/layout/gutters.mdx "View and edit this file on GitHub")

# Gutters

Gutters are the padding between your columns, used to responsively space and align content in the Bootstrap grid system.

On this page
**On this page**

* * *

## How they work [Link to this section: How they work](https://getbootstrap.com/docs/5.3/layout/gutters/\#how-they-work)

- **Gutters are the gaps between column content, created by horizontal `padding`.** We set `padding-right` and `padding-left` on each column, and use negative `margin` to offset that at the start and end of each row to align content.

- **Gutters start at `1.5rem` ( `24px`) wide.** This allows us to match our grid to the [padding and margin spacers](https://getbootstrap.com/docs/5.3/utilities/spacing) scale.

- **Gutters can be responsively adjusted.** Use breakpoint-specific gutter classes to modify horizontal gutters, vertical gutters, and all gutters.


## Horizontal gutters [Link to this section: Horizontal gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#horizontal-gutters)

`.gx-*` classes can be used to control the horizontal gutter widths. The `.container` or `.container-fluid` parent may need to be adjusted if larger gutters are used too to avoid unwanted overflow, using a matching padding utility. For example, in the following example we’ve increased the padding with `.px-4`:

Custom column padding

Custom column padding

html

```html
<div class="container px-4 text-center">
  <div class="row gx-5">
    <div class="col">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

An alternative solution is to add a wrapper around the `.row` with the `.overflow-hidden` class:

Custom column padding

Custom column padding

html

```html
<div class="container overflow-hidden text-center">
  <div class="row gx-5">
    <div class="col">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

## Vertical gutters [Link to this section: Vertical gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#vertical-gutters)

`.gy-*` classes can be used to control the vertical gutter widths within a row when columns wrap to new lines. Like the horizontal gutters, the vertical gutters can cause some overflow below the `.row` at the end of a page. If this occurs, you add a wrapper around `.row` with the `.overflow-hidden` class:

Custom column padding

Custom column padding

Custom column padding

Custom column padding

html

```html
<div class="container overflow-hidden text-center">
  <div class="row gy-5">
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

## Horizontal & vertical gutters [Link to this section: Horizontal & vertical gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#horizontal--vertical-gutters)

Use `.g-*` classes to control the horizontal and vertical grid gutters. In the example below, we use a smaller gutter width, so there isn’t a need for the `.overflow-hidden` wrapper class.

Custom column padding

Custom column padding

Custom column padding

Custom column padding

html

```html
<div class="container text-center">
  <div class="row g-2">
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

## Row columns gutters [Link to this section: Row columns gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#row-columns-gutters)

Gutter classes can also be added to [row columns](https://getbootstrap.com/docs/5.3/layout/grid#row-columns). In the following example, we use responsive row columns and responsive gutter classes.

Row column

Row column

Row column

Row column

Row column

Row column

Row column

Row column

Row column

Row column

html

```html
<div class="container text-center">
  <div class="row row-cols-2 row-cols-lg-5 g-2 g-lg-3">
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
    <div class="col">
      <div class="p-3">Row column</div>
    </div>
  </div>
</div>
```

## No gutters [Link to this section: No gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#no-gutters)

The gutters between columns in our predefined grid classes can be removed with `.g-0`. This removes the negative `margin` s from `.row` and the horizontal `padding` from all immediate children columns.

**Need an edge-to-edge design?** Drop the parent `.container` or `.container-fluid` and add `.mx-0` to the `.row` to prevent overflow.

In practice, here’s how it looks. Note that you can continue to use this with all other predefined grid classes (including column widths, responsive tiers, reorders, and more).

.col-sm-6 .col-md-8

.col-6 .col-md-4

html

```html
<div class="row g-0 text-center">
  <div class="col-sm-6 col-md-8">.col-sm-6 .col-md-8</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>
```

## Change the gutters [Link to this section: Change the gutters](https://getbootstrap.com/docs/5.3/layout/gutters/\#change-the-gutters)

Classes are built from the `$gutters` Sass map which is inherited from the `$spacers` Sass map.

```scss
$grid-gutter-width: 1.5rem;
$gutters: (
  0: 0,
  1: $spacer * .25,
  2: $spacer * .5,
  3: $spacer,
  4: $spacer * 1.5,
  5: $spacer * 3,
);

```