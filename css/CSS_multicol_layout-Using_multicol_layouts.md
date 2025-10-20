---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts
scraped_at: 2025-10-20T03:14:29.058Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts#search)

# Using multi-column layouts

The properties defined in the **CSS multi-column layout module** extend the _block layout mode_, enabling the easy definition of multiple columns of text. People have trouble reading text if lines are too long. If it takes too long for the eyes to move from the end of one line to the beginning of the next, readers can lose track of which line they were on. To provide for a better user experience when reading text making use of a large screen, you should limit the width of text by using columns of text placed side by side, just as newspapers do.

## [Using columns](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#using_columns)

### [Column count and width](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#column_count_and_width)

Two CSS properties control whether and how many columns will appear: [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) and [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width).

The `column-count` property sets the number of columns to a particular number. E.g.,

## [Example 1](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_1)

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html)

html

```
<div id="col">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua.
  </p>
  <p>
    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
    aliquip ex ea commodo consequat.
  </p>
  <p>
    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore
    eu fugiat nulla pariatur.
  </p>
  <p>
    Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia
    deserunt mollit anim id est laborum.
  </p>
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css)

css

```
#col {
  column-count: 2;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#result)

The content will be displayed in two columns:

The `column-width` property sets the minimum desired column width. If `column-count` is not also set, then the browser will automatically make as many columns as fit in the available width.

## [Example 2](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_2)

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html_2)

html

```
<div id="wid">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
  proident, sunt in culpa qui officia deserunt mollit anim id est laborum
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css_2)

css

```
#wid {
  column-width: 100px;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#result_2)

In a multi-column block, content automatically flows from one column into the next as needed. All HTML, CSS, and DOM functionality is supported within columns, as are editing and printing.

### [The columns shorthand](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#the_columns_shorthand)

You can use either [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) or [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width). Because values for these properties do not overlap, it is often convenient to use the shorthand [`columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/columns).

## [Example 3](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_3)

In this example, the CSS declaration `column-width: 12em` is replaced by `columns: 12em`.

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html_3)

html

```
<div id="col_short">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
  proident, sunt in culpa qui officia deserunt mollit anim id est laborum
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css_3)

css

```
#col_short {
  columns: 12em;
}

```

## [Example 4](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_4)

In this example, the CSS declaration `column-count: 4` is replaced by `columns: 4`.

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html_4)

html

```
<div id="columns_4">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
  proident, sunt in culpa qui officia deserunt mollit anim id est laborum
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css_4)

css

```
#columns_4 {
  columns: 4;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#result_3)

## [Example 5](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_5)

The two CSS declarations `column-width: 8em` and `column-count: 12` can be replaced by `columns: 12 8em`. The `column-count` portion of the shorthand is the maximum number of columns that will be present. The `column-width` is the minimum width each column should be.

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html_5)

html

```
<div id="columns_12">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
  proident, sunt in culpa qui officia deserunt mollit anim id est laborum
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css_5)

css

```
#columns_12 {
  columns: 12 8em;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#result_4)

Assuming a default `1em` gap between columns, if the container is wider than `103ems` (12 columns \* `8em` width each + 7 `1em` gaps), there will be 12 columns, each with a width of `8ems` or more. If the container is less than `103ems` wide, there will be fewer than 12 columns. If the container is less than `17ems` wide ( `8em` column + `8em` column + `1em` gap), the content will be displayed as a single column with no column gap.

### [Height balancing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#height_balancing)

CSS columns require that the column heights must be balanced: that is, the browser automatically sets the maximum column height so that the heights of the content in each column are approximately equal. Firefox does this.

However, in some situations it is also useful to set the maximum height of the columns explicitly, and then lay out content starting at the first column and creating as many columns as necessary, possibly overflowing to the right. Therefore, if the height is constrained, by setting the CSS [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) or [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties on a multi-column block, each column is allowed to grow to that height and no further before adding new column. This mode is also much more efficient for layout.

### [Column Gaps](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#column_gaps)

There is a gap between columns. The recommended default is `1em`. This size can be changed by applying the [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap) property to the multi-column block:

## [Example 6](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#example_6)

### [HTML](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#html_6)

html

```
<div id="column_gap">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
  consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
  cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
  proident, sunt in culpa qui officia deserunt mollit anim id est laborum
</div>

```

### [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#css_6)

css

```
#column_gap {
  column-count: 5;
  column-gap: 2em;
}

```

### [Result](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Using_multicol_layouts\#result_5)