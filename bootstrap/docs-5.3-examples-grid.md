---
url: https://getbootstrap.com/docs/5.3/examples/grid
scraped_at: 2025-10-20T02:30:31.526Z
---

Toggle theme

- Light

- Dark

- Auto


# Bootstrap grid examples

Basic grid layouts to get you familiar with building within the Bootstrap grid system.

In these examples the `.themed-grid-col` class is added to the columns to add some theming. This is not a class that is available in Bootstrap by default.

## Five grid tiers

There are five tiers to the Bootstrap grid system, one for each range of devices we support. Each tier starts at a minimum viewport size and automatically applies to the larger devices unless overridden.

.col-4

.col-4

.col-4

.col-sm-4

.col-sm-4

.col-sm-4

.col-md-4

.col-md-4

.col-md-4

.col-lg-4

.col-lg-4

.col-lg-4

.col-xl-4

.col-xl-4

.col-xl-4

.col-xxl-4

.col-xxl-4

.col-xxl-4

## Three equal columns

Get three equal-width columns **starting at desktops and scaling to large desktops**. On mobile devices, tablets and below, the columns will automatically stack.

.col-md-4

.col-md-4

.col-md-4

## Three equal columns alternative

By using the `.row-cols-*` classes, you can easily create a grid with equal columns.

`.col` child of `.row-cols-md-3`

`.col` child of `.row-cols-md-3`

`.col` child of `.row-cols-md-3`

## Three unequal columns

Get three columns **starting at desktops and scaling to large desktops** of various widths. Remember, grid columns should add up to twelve for a single horizontal block. More than that, and columns start stacking no matter the viewport.

.col-md-3

.col-md-6

.col-md-3

## Two columns

Get two columns **starting at desktops and scaling to large desktops**.

.col-md-8

.col-md-4

## Full width, single column

No grid classes are necessary for full-width elements.

* * *

## Two columns with two nested columns

Per the documentation, nesting is easy—just put a row of columns within an existing column. This gives you two columns **starting at desktops and scaling to large desktops**, with another two (equal widths) within the larger column.

At mobile device sizes, tablets and down, these columns and their nested columns will stack.

.col-md-8

.col-md-6

.col-md-6

.col-md-4

* * *

## Mixed: mobile and desktop

The Bootstrap v5 grid system has six tiers of classes: xs (extra small, this class infix is not used), sm (small), md (medium), lg (large), xl (x-large), and xxl (xx-large). You can use nearly any combination of these classes to create more dynamic and flexible layouts.

Each tier of classes scales up, meaning if you plan on setting the same widths for md, lg, xl and xxl, you only need to specify md.

.col-md-8

.col-6 .col-md-4

.col-6 .col-md-4

.col-6 .col-md-4

.col-6 .col-md-4

.col-6

.col-6

* * *

## Mixed: mobile, tablet, and desktop

.col-sm-6 .col-lg-8

.col-6 .col-lg-4

.col-6 .col-sm-4

.col-6 .col-sm-4

.col-6 .col-sm-4

* * *

## Gutters

With `.gx-*` classes, the horizontal gutters can be adjusted.

`.col` with `.gx-4` gutters

`.col` with `.gx-4` gutters

`.col` with `.gx-4` gutters

`.col` with `.gx-4` gutters

`.col` with `.gx-4` gutters

`.col` with `.gx-4` gutters

Use the `.gy-*` classes to control the vertical gutters.

`.col` with `.gy-4` gutters

`.col` with `.gy-4` gutters

`.col` with `.gy-4` gutters

`.col` with `.gy-4` gutters

`.col` with `.gy-4` gutters

`.col` with `.gy-4` gutters

With `.g-*` classes, the gutters in both directions can be adjusted.

`.col` with `.g-3` gutters

`.col` with `.g-3` gutters

`.col` with `.g-3` gutters

`.col` with `.g-3` gutters

`.col` with `.g-3` gutters

`.col` with `.g-3` gutters

* * *

## Containers

Additional classes added in Bootstrap v4.4 allow containers that are 100% wide until a particular breakpoint. v5 adds a new `xxl` breakpoint.

.container

.container-sm

.container-md

.container-lg

.container-xl

.container-xxl

.container-fluid