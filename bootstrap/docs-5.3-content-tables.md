---
url: https://getbootstrap.com/docs/5.3/content/tables
scraped_at: 2025-10-20T02:28:30.954Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/content/tables/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/content/tables/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/content/tables.mdx "View and edit this file on GitHub")

# Tables

Documentation and examples for opt-in styling of tables (given their prevalent use in JavaScript plugins) with Bootstrap.

On this page
**On this page**

* * *

## Overview [Link to this section: Overview](https://getbootstrap.com/docs/5.3/content/tables/\#overview)

Due to the widespread use of `<table>` elements across third-party widgets like calendars and date pickers, Bootstrap’s tables are **opt-in**. Add the base class `.table` to any `<table>`, then extend with our optional modifier classes or custom styles. All table styles are not inherited in Bootstrap, meaning any nested tables can be styled independent from the parent.

Using the most basic table markup, here’s how `.table`-based tables look in Bootstrap.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>John</td>
      <td>Doe</td>
      <td>@social</td>
    </tr>
  </tbody>
</table>
```

## Variants [Link to this section: Variants](https://getbootstrap.com/docs/5.3/content/tables/\#variants)

Use contextual classes to color tables, table rows or individual cells.

**Heads up!** Because of the more complicated CSS used to generate our table variants, they most likely won’t see color mode adaptive styling until v6.

| Class | Heading | Heading |
| --- | --- | --- |
| Default | Cell | Cell |
| Primary | Cell | Cell |
| Secondary | Cell | Cell |
| Success | Cell | Cell |
| Danger | Cell | Cell |
| Warning | Cell | Cell |
| Info | Cell | Cell |
| Light | Cell | Cell |
| Dark | Cell | Cell |

```html
<!-- On tables -->
<table class="table-primary">...</table>
<table class="table-secondary">...</table>
<table class="table-success">...</table>
<table class="table-danger">...</table>
<table class="table-warning">...</table>
<table class="table-info">...</table>
<table class="table-light">...</table>
<table class="table-dark">...</table>

<!-- On rows -->
<tr class="table-primary">...</tr>
<tr class="table-secondary">...</tr>
<tr class="table-success">...</tr>
<tr class="table-danger">...</tr>
<tr class="table-warning">...</tr>
<tr class="table-info">...</tr>
<tr class="table-light">...</tr>
<tr class="table-dark">...</tr>

<!-- On cells (`td` or `th`) -->
<tr>
  <td class="table-primary">...</td>
  <td class="table-secondary">...</td>
  <td class="table-success">...</td>
  <td class="table-danger">...</td>
  <td class="table-warning">...</td>
  <td class="table-info">...</td>
  <td class="table-light">...</td>
  <td class="table-dark">...</td>
</tr>
```

**Accessibility tip:** Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies like screen readers. Please ensure the meaning is obvious from the content itself (e.g., the visible text with a [_sufficient_ color contrast](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#color-contrast)) or is included through alternative means, such as additional text hidden with the `.visually-hidden` class.

## Accented tables [Link to this section: Accented tables](https://getbootstrap.com/docs/5.3/content/tables/\#accented-tables)

### Striped rows [Link to this section: Striped rows](https://getbootstrap.com/docs/5.3/content/tables/\#striped-rows)

Use `.table-striped` to add zebra-striping to any table row within the `<tbody>`.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-striped">
  ...
</table>
```

### Striped columns [Link to this section: Striped columns](https://getbootstrap.com/docs/5.3/content/tables/\#striped-columns)

Use `.table-striped-columns` to add zebra-striping to any table column.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-striped-columns">
  ...
</table>
```

These classes can also be added to table variants:

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark table-striped">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark table-striped-columns">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-success table-striped">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-success table-striped-columns">
  ...
</table>
```

### Hoverable rows [Link to this section: Hoverable rows](https://getbootstrap.com/docs/5.3/content/tables/\#hoverable-rows)

Add `.table-hover` to enable a hover state on table rows within a `<tbody>`.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-hover">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark table-hover">
  ...
</table>
```

These hoverable rows can also be combined with the striped rows variant:

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-striped table-hover">
  ...
</table>
```

### Active tables [Link to this section: Active tables](https://getbootstrap.com/docs/5.3/content/tables/\#active-tables)

Highlight a table row or cell by adding a `.table-active` class.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table">
  <thead>
    ...
  </thead>
  <tbody>
    <tr class="table-active">
      ...
    </tr>
    <tr>
      ...
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>John</td>
      <td>Doe</td>
      <td class="table-active">@social</td>
    </tr>
  </tbody>
</table>

```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark">
  <thead>
    ...
  </thead>
  <tbody>
    <tr class="table-active">
      ...
    </tr>
    <tr>
      ...
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>John</td>
      <td>Doe</td>
      <td class="table-active">@social</td>
    </tr>
  </tbody>
</table>

```

## How do the variants and accented tables work? [Link to this section: How do the variants and accented tables work?](https://getbootstrap.com/docs/5.3/content/tables/\#how-do-the-variants-and-accented-tables-work)

For the accented tables ( [striped rows](https://getbootstrap.com/docs/5.3/content/tables/#striped-rows), [striped columns](https://getbootstrap.com/docs/5.3/content/tables/#striped-columns), [hoverable rows](https://getbootstrap.com/docs/5.3/content/tables/#hoverable-rows), and [active tables](https://getbootstrap.com/docs/5.3/content/tables/#active-tables)), we used some techniques to make these effects work for all our [table variants](https://getbootstrap.com/docs/5.3/content/tables/#variants):

- We start by setting the background of a table cell with the `--bs-table-bg` custom property. All table variants then set that custom property to colorize the table cells. This way, we don’t get into trouble if semi-transparent colors are used as table backgrounds.
- Then we add an inset box shadow on the table cells with `box-shadow: inset 0 0 0 9999px var(--bs-table-bg-state, var(--bs-table-bg-type, var(--bs-table-accent-bg)));` to layer on top of any specified `background-color`. It uses custom cascade to override the `box-shadow`, regardless the CSS specificity. Because we use a huge spread and no blur, the color will be monotone. Since `--bs-table-accent-bg` is set to `transparent` by default, we don’t have a default box shadow.
- When either `.table-striped`, `.table-striped-columns`, `.table-hover` or `.table-active` classes are added, either `--bs-table-bg-type` or `--bs-table-bg-state` (by default set to `initial`) are set to a semitransparent color ( `--bs-table-striped-bg`, `--bs-table-active-bg` or `--bs-table-hover-bg`) to colorize the background and override default `--bs-table-accent-bg`.
- For each table variant, we generate a `--bs-table-accent-bg` color with the highest contrast depending on that color. For example, the accent color for `.table-primary` is darker while `.table-dark` has a lighter accent color.
- Text and border colors are generated the same way, and their colors are inherited by default.

Behind the scenes it looks like this:

[scss/mixins/\_table-variants.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/mixins/_table-variants.scss)

```scss
@mixin table-variant($state, $background) {
  .table-#{$state} {
    $color: color-contrast(opaque($body-bg, $background));
    $hover-bg: mix($color, $background, percentage($table-hover-bg-factor));
    $striped-bg: mix($color, $background, percentage($table-striped-bg-factor));
    $active-bg: mix($color, $background, percentage($table-active-bg-factor));
    $table-border-color: mix($color, $background, percentage($table-border-factor));

    --#{$prefix}table-color: #{$color};
    --#{$prefix}table-bg: #{$background};
    --#{$prefix}table-border-color: #{$table-border-color};
    --#{$prefix}table-striped-bg: #{$striped-bg};
    --#{$prefix}table-striped-color: #{color-contrast($striped-bg)};
    --#{$prefix}table-active-bg: #{$active-bg};
    --#{$prefix}table-active-color: #{color-contrast($active-bg)};
    --#{$prefix}table-hover-bg: #{$hover-bg};
    --#{$prefix}table-hover-color: #{color-contrast($hover-bg)};

    color: var(--#{$prefix}table-color);
    border-color: var(--#{$prefix}table-border-color);
  }
}

```

## Table borders [Link to this section: Table borders](https://getbootstrap.com/docs/5.3/content/tables/\#table-borders)

### Bordered tables [Link to this section: Bordered tables](https://getbootstrap.com/docs/5.3/content/tables/\#bordered-tables)

Add `.table-bordered` for borders on all sides of the table and cells.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-bordered">
  ...
</table>
```

[Border color utilities](https://getbootstrap.com/docs/5.3/utilities/borders#border-color) can be added to change colors:

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-bordered border-primary">
  ...
</table>
```

### Tables without borders [Link to this section: Tables without borders](https://getbootstrap.com/docs/5.3/content/tables/\#tables-without-borders)

Add `.table-borderless` for a table without borders.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-borderless">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark table-borderless">
  ...
</table>
```

## Small tables [Link to this section: Small tables](https://getbootstrap.com/docs/5.3/content/tables/\#small-tables)

Add `.table-sm` to make any `.table` more compact by cutting all cell `padding` in half.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-sm">
  ...
</table>
```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table table-dark table-sm">
  ...
</table>
```

## Table group dividers [Link to this section: Table group dividers](https://getbootstrap.com/docs/5.3/content/tables/\#table-group-dividers)

Add a thicker border, darker between table groups— `<thead>`, `<tbody>`, and `<tfoot>`—with `.table-group-divider`. Customize the color by changing the `border-top-color` (which we don’t currently provide a utility class for at this time).

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

html

```html
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody class="table-group-divider">
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>John</td>
      <td>Doe</td>
      <td>@social</td>
    </tr>
  </tbody>
</table>
```

## Vertical alignment [Link to this section: Vertical alignment](https://getbootstrap.com/docs/5.3/content/tables/\#vertical-alignment)

Table cells of `<thead>` are always vertical aligned to the bottom. Table cells in `<tbody>` inherit their alignment from `<table>` and are aligned to the top by default. Use the [vertical align](https://getbootstrap.com/docs/5.3/utilities/vertical-align) classes to re-align where needed.

| Heading 1 | Heading 2 | Heading 3 | Heading 4 |
| --- | --- | --- | --- |
| This cell inherits `vertical-align: middle;` from the table | This cell inherits `vertical-align: middle;` from the table | This cell inherits `vertical-align: middle;` from the table | This here is some placeholder text, intended to take up quite a bit of vertical space, to demonstrate how the vertical alignment works in the preceding cells. |
| This cell inherits `vertical-align: bottom;` from the table row | This cell inherits `vertical-align: bottom;` from the table row | This cell inherits `vertical-align: bottom;` from the table row | This here is some placeholder text, intended to take up quite a bit of vertical space, to demonstrate how the vertical alignment works in the preceding cells. |
| This cell inherits `vertical-align: middle;` from the table | This cell inherits `vertical-align: middle;` from the table | This cell is aligned to the top. | This here is some placeholder text, intended to take up quite a bit of vertical space, to demonstrate how the vertical alignment works in the preceding cells. |

```html
<div class="table-responsive">
  <table class="table align-middle">
    <thead>
      <tr>
        ...
      </tr>
    </thead>
    <tbody>
      <tr>
        ...
      </tr>
      <tr class="align-bottom">
        ...
      </tr>
      <tr>
        <td>...</td>
        <td>...</td>
        <td class="align-top">This cell is aligned to the top.</td>
        <td>...</td>
      </tr>
    </tbody>
  </table>
</div>

```

## Nesting [Link to this section: Nesting](https://getbootstrap.com/docs/5.3/content/tables/\#nesting)

Border styles, active styles, and table variants are not inherited by nested tables.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| | Header | Header | Header |
| --- | --- | --- |
| A | First | Last |
| B | First | Last |
| C | First | Last | |
| 3 | John | Doe | @social |

```html
<table class="table table-striped table-bordered">
  <thead>
    ...
  </thead>
  <tbody>
    ...
    <tr>
      <td colspan="4">
        <table class="table mb-0">
          ...
        </table>
      </td>
    </tr>
    ...
  </tbody>
</table>

```

## How nesting works [Link to this section: How nesting works](https://getbootstrap.com/docs/5.3/content/tables/\#how-nesting-works)

To prevent _any_ styles from leaking to nested tables, we use the child combinator ( `>`) selector in our CSS. Since we need to target all the `td` s and `th` s in the `thead`, `tbody`, and `tfoot`, our selector would look pretty long without it. As such, we use the rather odd looking `.table > :not(caption) > * > *` selector to target all `td` s and `th` s of the `.table`, but none of any potential nested tables.

Note that if you add `<tr>` s as direct children of a table, those `<tr>` will be wrapped in a `<tbody>` by default, thus making our selectors work as intended.

## Anatomy [Link to this section: Anatomy](https://getbootstrap.com/docs/5.3/content/tables/\#anatomy)

### Table head [Link to this section: Table head](https://getbootstrap.com/docs/5.3/content/tables/\#table-head)

Similar to tables and dark tables, use the modifier classes `.table-light` or `.table-dark` to make `<thead>` s appear light or dark gray.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table">
  <thead class="table-light">
    ...
  </thead>
  <tbody>
    ...
  </tbody>
</table>

```

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

```html
<table class="table">
  <thead class="table-dark">
    ...
  </thead>
  <tbody>
    ...
  </tbody>
</table>

```

### Table foot [Link to this section: Table foot](https://getbootstrap.com/docs/5.3/content/tables/\#table-foot)

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |
| Footer | Footer | Footer | Footer |

```html
<table class="table">
  <thead>
    ...
  </thead>
  <tbody>
    ...
  </tbody>
  <tfoot>
    ...
  </tfoot>
</table>

```

### Captions [Link to this section: Captions](https://getbootstrap.com/docs/5.3/content/tables/\#captions)

A `<caption>` functions like a heading for a table. It helps users with screen readers to find a table and understand what it’s about and decide if they want to read it.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

List of users

```html
<table class="table table-sm">
  <caption>List of users</caption>
  <thead>
    ...
  </thead>
  <tbody>
    ...
  </tbody>
</table>

```

You can also put the `<caption>` on the top of the table with `.caption-top`.

| # | First | Last | Handle |
| --- | --- | --- | --- |
| 1 | Mark | Otto | @mdo |
| 2 | Jacob | Thornton | @fat |
| 3 | John | Doe | @social |

List of users

html

```html
<table class="table caption-top">
  <caption>List of users</caption>
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>John</td>
      <td>Doe</td>
      <td>@social</td>
    </tr>
  </tbody>
</table>
```

## Responsive tables [Link to this section: Responsive tables](https://getbootstrap.com/docs/5.3/content/tables/\#responsive-tables)

Responsive tables allow tables to be scrolled horizontally with ease. Make any table responsive across all viewports by wrapping a `.table` with `.table-responsive`. Or, pick a maximum breakpoint with which to have a responsive table up to by using `.table-responsive{-sm|-md|-lg|-xl|-xxl}`.

##### Vertical clipping/truncation [Link to this section: Vertical clipping/truncation](https://getbootstrap.com/docs/5.3/content/tables/\#vertical-clippingtruncation)

Responsive tables make use of `overflow-y: hidden`, which clips off any content that goes beyond the bottom or top edges of the table. In particular, this can clip off dropdown menus and other third-party widgets.

### Always responsive [Link to this section: Always responsive](https://getbootstrap.com/docs/5.3/content/tables/\#always-responsive)

Across every breakpoint, use `.table-responsive` for horizontally scrolling tables.

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

```html
<div class="table-responsive">
  <table class="table">
    ...
  </table>
</div>

```

### Breakpoint specific [Link to this section: Breakpoint specific](https://getbootstrap.com/docs/5.3/content/tables/\#breakpoint-specific)

Use `.table-responsive{-sm|-md|-lg|-xl|-xxl}` as needed to create responsive tables up to a particular breakpoint. From that breakpoint and up, the table will behave normally and not scroll horizontally.

**These tables may appear broken until their responsive styles apply at specific viewport widths.**

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

| # | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 2 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |
| 3 | Cell | Cell | Cell | Cell | Cell | Cell | Cell | Cell |

```html
<div class="table-responsive">
  <table class="table">
    ...
  </table>
</div>

<div class="table-responsive-sm">
  <table class="table">
    ...
  </table>
</div>

<div class="table-responsive-md">
  <table class="table">
    ...
  </table>
</div>

<div class="table-responsive-lg">
  <table class="table">
    ...
  </table>
</div>

<div class="table-responsive-xl">
  <table class="table">
    ...
  </table>
</div>

<div class="table-responsive-xxl">
  <table class="table">
    ...
  </table>
</div>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/content/tables/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/content/tables/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$table-cell-padding-y:        .5rem;
$table-cell-padding-x:        .5rem;
$table-cell-padding-y-sm:     .25rem;
$table-cell-padding-x-sm:     .25rem;

$table-cell-vertical-align:   top;

$table-color:                 var(--#{$prefix}emphasis-color);
$table-bg:                    var(--#{$prefix}body-bg);
$table-accent-bg:             transparent;

$table-th-font-weight:        null;

$table-striped-color:         $table-color;
$table-striped-bg-factor:     .05;
$table-striped-bg:            rgba(var(--#{$prefix}emphasis-color-rgb), $table-striped-bg-factor);

$table-active-color:          $table-color;
$table-active-bg-factor:      .1;
$table-active-bg:             rgba(var(--#{$prefix}emphasis-color-rgb), $table-active-bg-factor);

$table-hover-color:           $table-color;
$table-hover-bg-factor:       .075;
$table-hover-bg:              rgba(var(--#{$prefix}emphasis-color-rgb), $table-hover-bg-factor);

$table-border-factor:         .2;
$table-border-width:          var(--#{$prefix}border-width);
$table-border-color:          var(--#{$prefix}border-color);

$table-striped-order:         odd;
$table-striped-columns-order: even;

$table-group-separator-color: currentcolor;

$table-caption-color:         var(--#{$prefix}secondary-color);

$table-bg-scale:              -80%;

```

### Sass loops [Link to this section: Sass loops](https://getbootstrap.com/docs/5.3/content/tables/\#sass-loops)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$table-variants: (
  "primary":    shift-color($primary, $table-bg-scale),
  "secondary":  shift-color($secondary, $table-bg-scale),
  "success":    shift-color($success, $table-bg-scale),
  "info":       shift-color($info, $table-bg-scale),
  "warning":    shift-color($warning, $table-bg-scale),
  "danger":     shift-color($danger, $table-bg-scale),
  "light":      $light,
  "dark":       $dark,
);

```

### Customizing [Link to this section: Customizing](https://getbootstrap.com/docs/5.3/content/tables/\#customizing)

- The factor variables ( `$table-striped-bg-factor`, `$table-active-bg-factor` & `$table-hover-bg-factor`) are used to determine the contrast in table variants.
- Apart from the light & dark table variants, theme colors are lightened by the `$table-bg-scale` variable.