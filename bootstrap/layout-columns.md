---
url: https://getbootstrap.com/docs/5.3/layout/columns
scraped_at: 2025-10-20T03:55:30.829Z
attempt: 1
---

[Skip to main content](https://getbootstrap.com/docs/5.3/layout/columns/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/layout/columns/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/layout/columns.mdx "View and edit this file on GitHub")

# Columns

Learn how to modify columns with a handful of options for alignment, ordering, and offsetting thanks to our flexbox grid system. Plus, see how to use column classes to manage widths of non-grid elements.

On this page
**On this page**

* * *

**Heads up!** Be sure to [read the Grid page](https://getbootstrap.com/docs/5.3/layout/grid) first before diving into how to modify and customize your grid columns.

## How they work [Link to this section: How they work](https://getbootstrap.com/docs/5.3/layout/columns/\#how-they-work)

- **Columns build on the grid’s flexbox architecture.** Flexbox means we have options for changing individual columns and [modifying groups of columns at the row level](https://getbootstrap.com/docs/5.3/layout/grid#row-columns). You choose how columns grow, shrink, or otherwise change.

- **When building grid layouts, all content goes in columns.** The hierarchy of Bootstrap’s grid goes from [container](https://getbootstrap.com/docs/5.3/layout/containers) to row to column to your content. On rare occasions, you may combine content and column, but be aware there can be unintended consequences.

- **Bootstrap includes predefined classes for creating fast, responsive layouts.** With [six breakpoints](https://getbootstrap.com/docs/5.3/layout/breakpoints) and a dozen columns at each grid tier, we have dozens of classes already built for you to create your desired layouts. This can be disabled via Sass if you wish.


## Alignment [Link to this section: Alignment](https://getbootstrap.com/docs/5.3/layout/columns/\#alignment)

Use flexbox alignment utilities to vertically and horizontally align columns.

### Vertical alignment [Link to this section: Vertical alignment](https://getbootstrap.com/docs/5.3/layout/columns/\#vertical-alignment)

Change the vertical alignment with any of the responsive `align-items-*` classes.

One of three columns


One of three columns


One of three columns


html

```html
<div class="container text-center">
  <div class="row align-items-start">
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
</div>
```

One of three columns


One of three columns


One of three columns


html

```html
<div class="container text-center">
  <div class="row align-items-center">
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
</div>
```

One of three columns


One of three columns


One of three columns


html

```html
<div class="container text-center">
  <div class="row align-items-end">
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
</div>
```

Or, change the alignment of each column individually with any of the responsive `.align-self-*` classes.

One of three columns


One of three columns


One of three columns


html

```html
<div class="container text-center">
  <div class="row">
    <div class="col align-self-start">
      One of three columns
    </div>
    <div class="col align-self-center">
      One of three columns
    </div>
    <div class="col align-self-end">
      One of three columns
    </div>
  </div>
</div>
```

### Horizontal alignment [Link to this section: Horizontal alignment](https://getbootstrap.com/docs/5.3/layout/columns/\#horizontal-alignment)

Change the horizontal alignment with any of the responsive `justify-content-*` classes.

One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


One of two columns


html

```html
<div class="container text-center">
  <div class="row justify-content-start">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-center">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-end">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-around">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-between">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-evenly">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
</div>
```

### Column wrapping [Link to this section: Column wrapping](https://getbootstrap.com/docs/5.3/layout/columns/\#column-wrapping)

If more than 12 columns are placed within a single row, each group of extra columns will, as one unit, wrap onto a new line.

.col-9

.col-4

Since 9 + 4 = 13 > 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.

.col-6

Subsequent columns continue along the new line.

html

```html
<div class="container">
  <div class="row">
    <div class="col-9">.col-9</div>
    <div class="col-4">.col-4<br>Since 9 + 4 = 13 &gt; 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.</div>
    <div class="col-6">.col-6<br>Subsequent columns continue along the new line.</div>
  </div>
</div>
```

### Column breaks [Link to this section: Column breaks](https://getbootstrap.com/docs/5.3/layout/columns/\#column-breaks)

Breaking columns to a new line in flexbox requires a small hack: add an element with `width: 100%` wherever you want to wrap your columns to a new line. Normally this is accomplished with multiple `.row` s, but not every implementation method can account for this.

.col-6 .col-sm-3

.col-6 .col-sm-3

.col-6 .col-sm-3

.col-6 .col-sm-3

html

```html
<div class="container text-center">
  <div class="row">
    <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
    <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>

    <!-- Force next columns to break to new line -->
    <div class="w-100"></div>

    <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
    <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
  </div>
</div>
```

You may also apply this break at specific breakpoints with our [responsive display utilities](https://getbootstrap.com/docs/5.3/utilities/display).

.col-6 .col-sm-4

.col-6 .col-sm-4

.col-6 .col-sm-4

.col-6 .col-sm-4

html

```html
<div class="container text-center">
  <div class="row">
    <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
    <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>

    <!-- Force next columns to break to new line at md breakpoint and up -->
    <div class="w-100 d-none d-md-block"></div>

    <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
    <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
  </div>
</div>
```

## Reordering [Link to this section: Reordering](https://getbootstrap.com/docs/5.3/layout/columns/\#reordering)

### Order classes [Link to this section: Order classes](https://getbootstrap.com/docs/5.3/layout/columns/\#order-classes)

Use `.order-` classes for controlling the **visual order** of your content. These classes are responsive, so you can set the `order` by breakpoint (e.g., `.order-1.order-md-2`). Includes support for `1` through `5` across all six grid tiers.

First in DOM, no order applied


Second in DOM, with a larger order


Third in DOM, with an order of 1


html

```html
<div class="container text-center">
  <div class="row">
    <div class="col">
      First in DOM, no order applied
    </div>
    <div class="col order-5">
      Second in DOM, with a larger order
    </div>
    <div class="col order-1">
      Third in DOM, with an order of 1
    </div>
  </div>
</div>
```

There are also responsive `.order-first` and `.order-last` classes that change the `order` of an element by applying `order: -1` and `order: 6`, respectively. These classes can also be intermixed with the numbered `.order-*` classes as needed.

First in DOM, ordered last


Second in DOM, unordered


Third in DOM, ordered first


html

```html
<div class="container text-center">
  <div class="row">
    <div class="col order-last">
      First in DOM, ordered last
    </div>
    <div class="col">
      Second in DOM, unordered
    </div>
    <div class="col order-first">
      Third in DOM, ordered first
    </div>
  </div>
</div>
```

If you need more `.order-*` classes, you can add new ones by modifying our `$utilities` Sass map. [Read our Sass maps and loops docs](https://getbootstrap.com/docs/5.3/customize/sass#maps-and-loops) or [our Modify utilities docs](https://getbootstrap.com/docs/5.3/utilities/api#modify-utilities) for details.

```scss
$utilities: map-merge(
  $utilities,
  (
    "order": map-merge(
      map-get($utilities, "order"),
      (
        values: map-merge(
          map-get(map-get($utilities, "order"), "values"),
          (
            6: 6, // Add a new `.order-{breakpoint}-6` utility
            last: 7 // Change the `.order-{breakpoint}-last` utility to use the next number
          )
        ),
      ),
    ),
  )
);

```

### Offsetting columns [Link to this section: Offsetting columns](https://getbootstrap.com/docs/5.3/layout/columns/\#offsetting-columns)

You can offset grid columns in two ways: our responsive `.offset-` grid classes and our [margin utilities](https://getbootstrap.com/docs/5.3/utilities/spacing). Grid classes are sized to match columns while margins are more useful for quick layouts where the width of the offset is variable.

#### Offset classes [Link to this section: Offset classes](https://getbootstrap.com/docs/5.3/layout/columns/\#offset-classes)

Move columns to the right using `.offset-md-*` classes. These classes increase the left margin of a column by `*` columns. For example, `.offset-md-4` moves `.col-md-4` over four columns.

.col-md-4

.col-md-4 .offset-md-4

.col-md-3 .offset-md-3

.col-md-3 .offset-md-3

.col-md-6 .offset-md-3

html

```html
<div class="container text-center">
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
  </div>
  <div class="row">
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
  </div>
  <div class="row">
    <div class="col-md-6 offset-md-3">.col-md-6 .offset-md-3</div>
  </div>
</div>
```

In addition to column clearing at responsive breakpoints, you may need to reset offsets. See this in action in [the grid example](https://getbootstrap.com/docs/5.3/examples/grid/).

.col-sm-5 .col-md-6

.col-sm-5 .offset-sm-2 .col-md-6 .offset-md-0

.col-sm-6 .col-md-5 .col-lg-6

.col-sm-6 .col-md-5 .offset-md-2 .col-lg-6 .offset-lg-0

html

```html
<div class="container text-center">
  <div class="row">
    <div class="col-sm-5 col-md-6">.col-sm-5 .col-md-6</div>
    <div class="col-sm-5 offset-sm-2 col-md-6 offset-md-0">.col-sm-5 .offset-sm-2 .col-md-6 .offset-md-0</div>
  </div>
  <div class="row">
    <div class="col-sm-6 col-md-5 col-lg-6">.col-sm-6 .col-md-5 .col-lg-6</div>
    <div class="col-sm-6 col-md-5 offset-md-2 col-lg-6 offset-lg-0">.col-sm-6 .col-md-5 .offset-md-2 .col-lg-6 .offset-lg-0</div>
  </div>
</div>
```

#### Margin utilities [Link to this section: Margin utilities](https://getbootstrap.com/docs/5.3/layout/columns/\#margin-utilities)

With the move to flexbox in v4, you can use margin utilities like `.me-auto` to force sibling columns away from one another.

.col-md-4

.col-md-4 .ms-auto

.col-md-3 .ms-md-auto

.col-md-3 .ms-md-auto

.col-auto .me-auto

.col-auto

html

```html
<div class="container text-center">
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4 ms-auto">.col-md-4 .ms-auto</div>
  </div>
  <div class="row">
    <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>
    <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>
  </div>
  <div class="row">
    <div class="col-auto me-auto">.col-auto .me-auto</div>
    <div class="col-auto">.col-auto</div>
  </div>
</div>
```

## Standalone column classes [Link to this section: Standalone column classes](https://getbootstrap.com/docs/5.3/layout/columns/\#standalone-column-classes)

The `.col-*` classes can also be used outside a `.row` to give an element a specific width. Whenever column classes are used as non-direct children of a row, the paddings are omitted.

.col-3: width of 25%

.col-sm-9: width of 75% above sm breakpoint

html

```html
<div class="col-3 p-3 mb-2">
  .col-3: width of 25%
</div>

<div class="col-sm-9 p-3">
  .col-sm-9: width of 75% above sm breakpoint
</div>
```

The classes can be used together with utilities to create responsive floated images. Make sure to wrap the content in a [`.clearfix`](https://getbootstrap.com/docs/5.3/helpers/clearfix) wrapper to clear the float if the text is shorter.

PlaceholderResponsive floated image

A paragraph of placeholder text. We’re using it here to show the use of the clearfix class. We’re adding quite a few meaningless phrases here to demonstrate how the columns interact here with the floated image.


As you can see the paragraphs gracefully wrap around the floated image. Now imagine how this would look with some actual content in here, rather than just this boring placeholder text that goes on and on, but actually conveys no tangible information at. It simply takes up space and should not really be read.


And yet, here you are, still persevering in reading this placeholder text, hoping for some more insights, or some hidden easter egg of content. A joke, perhaps. Unfortunately, there’s none of that here.


html

```html
<div class="clearfix">
  <img src="..." class="col-md-6 float-md-end mb-3 ms-md-3" alt="...">

  <p>
    A paragraph of placeholder text. We’re using it here to show the use of the clearfix class. We’re adding quite a few meaningless phrases here to demonstrate how the columns interact here with the floated image.
  </p>

  <p>
    As you can see the paragraphs gracefully wrap around the floated image. Now imagine how this would look with some actual content in here, rather than just this boring placeholder text that goes on and on, but actually conveys no tangible information at. It simply takes up space and should not really be read.
  </p>

  <p>
    And yet, here you are, still persevering in reading this placeholder text, hoping for some more insights, or some hidden easter egg of content. A joke, perhaps. Unfortunately, there’s none of that here.
  </p>
</div>
```