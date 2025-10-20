---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts
scraped_at: 2025-10-20T02:59:31.202Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# Column layouts

You will often need to create a layout which has a number of columns, and CSS provides several ways to do this. Whether you use [Multi-column](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout), [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout), or [Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) layout will depend on what you are trying to achieve, and in this recipe we explore these options.

![three different styles of layouts which have two columns in the container.](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts/cookbook-multiple-columns.png)

## [Requirements](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#requirements)

There are a number of design patterns you might want to achieve with your columns:

- [A continuous thread of content broken up into newspaper-style columns](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts#a_continuous_thread_of_content_%E2%80%94_multi-column_layout).
- [A single row of items arranged as columns, with all heights being equal](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts#a_single_row_of_items_with_equal_heights_%E2%80%94_flexbox).
- [Multiple rows of columns lined up by row and column](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts#lining_items_up_in_rows_and_columns_%E2%80%94_grid_layout).

## [The recipes](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#the_recipes)

You need to choose different layout methods in order to achieve your requirements.

### [A continuous thread of content — multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#a_continuous_thread_of_content_%E2%80%94_multi-column_layout)

If you create columns using multi-column layout your text will remain as a continuous stream filling each column in turn. The columns must all be the same size, and you are unable to target an individual column or the content of an individual column.

You can control the gaps between columns with the [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap) or [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) properties, and add a rule between columns using [`column-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule).

Click "Play" in the code blocks below to edit the example in the MDN Playground:

htmlCopyPlay

```
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>
  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>
  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
  </p>
</div>

```

cssCopyPlay

```
.container {
  border: 2px solid rgb(75 70 74);
  border-radius: 0.5em;
  padding: 20px;
  font: 1.2em sans-serif;

  column-width: 10em;
  column-rule: 1px solid rgb(75 70 74);
}

```

Play

Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
daikon amaranth tatsoi tomatillo melon azuki bean garlic.


Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
Dandelion cucumber earthnut pea peanut soko zucchini.


Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
purslane kale. Celery potato scallion desert raisin horseradish spinach


In this example, we used the [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width) property to set a minimum width that the columns need to be before the browser adds an additional column. The [`columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/columns) shorthand property can be used to set the `column-width` and [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) properties, either of which can define the maximum number of columns allowed.

Use multicol when:

- You want your text to display in newspaper-like columns.
- You have a set of small items you want to break into columns.
- You do not need to target individual column boxes for styling.

### [A single row of items with equal heights — flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#a_single_row_of_items_with_equal_heights_%E2%80%94_flexbox)

Flexbox can be used to break content into columns by setting [`display: flex;`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) to make a parent element a flex-container. Just adding this one property turns all the children (child elements, pseudo-elements, and text nodes) into flex items along a single line. Setting the same [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) shorthand property with a single numeric value distributes all the available space equally, generally making all the flex items the same size as long as none have non-wrapping content forcing the item to be larger.

Margins or the `gap` property can be used to create gaps between items, but there is currently no CSS property that adds rules between flex items.

htmlCopyPlay

```
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>

  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
    carrot soko.
  </p>
</div>

```

cssCopyPlay

```
.container {
  border: 2px solid rgb(75 70 74);
  border-radius: 0.5em;
  padding: 20px 10px;
  font: 1.2em sans-serif;

  display: flex;
}

.container > * {
  padding: 10px;
  border: 2px solid rgb(95 97 110);
  border-radius: 0.5em;

  margin: 0 10px;
  flex: 1;
}

```

Play

Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
daikon amaranth tatsoi tomatillo melon azuki bean garlic.


Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
Dandelion cucumber earthnut pea peanut soko zucchini.


Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
purslane kale. Celery potato scallion desert raisin horseradish spinach
carrot soko.


To create a layout with flex items that wrap onto new rows, set the [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap) property on the container to `wrap`. Note that each flex line distributes space for that line only. Items in one line will not necessarily line up with items on other lines, as you'll see in the example below. This is why flexbox is described as one-dimensional. It is designed for controlling layout as a row or a column, but not both at the same time.

htmlCopyPlay

```
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>

  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
    carrot soko.
  </p>
</div>

```

cssCopyPlay

```
.container {
  border: 2px solid rgb(75 70 74);
  border-radius: 0.5em;
  padding: 20px 10px;
  width: 500px;
  font: 1.2em sans-serif;

  display: flex;
  flex-wrap: wrap;
}

.container > * {
  padding: 10px;
  border: 2px solid rgb(95 97 110);
  border-radius: 0.5em;

  margin: 0 10px;
  flex: 1 1 200px;
}

```

Play

Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
daikon amaranth tatsoi tomatillo melon azuki bean garlic.


Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
Dandelion cucumber earthnut pea peanut soko zucchini.


Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
purslane kale. Celery potato scallion desert raisin horseradish spinach
carrot soko.


Use flexbox:

- For single rows or columns of items.
- When you want to do alignment on the cross axis after laying out your items.
- When you are happy for wrapped items to share out space along their line only and not line up with items in other lines.

### [Lining items up in rows and columns — grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#lining_items_up_in_rows_and_columns_%E2%80%94_grid_layout)

If you want a two-dimensional grid where items line up in rows _and_ columns, then you should choose CSS grid layout. Similar to how flexbox works on the direct children of the flex container, grid layout works on the direct children of the grid container. Just set [`display: grid;`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) on the container. Properties set on this container — like [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns) and [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows) — define how the items are distributed along rows and columns.

Click "Play" in the code blocks below to edit the example in the MDN Playground:

htmlCopyPlay

```
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens.
  </p>

  <p>
    Nori grape silver beet broccoli kombu beet greens fava bean potato quandong
    celery. Bunya nuts black-eyed pea prairie turnip leek lentil turnip greens
    parsnip. .
  </p>
</div>

```

cssCopyPlay

```
.container {
  border: 2px solid rgb(75 70 74);
  border-radius: 0.5em;
  padding: 20px;
  width: 500px;
  font: 1.2em sans-serif;

  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
}

.container > * {
  padding: 10px;
  border: 2px solid rgb(95 97 110);
  border-radius: 0.5em;
  margin: 0;
}

```

Play

Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
daikon amaranth tatsoi.


Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
tatsoi pea sprouts fava bean collard greens.


Nori grape silver beet broccoli kombu beet greens fava bean potato quandong
celery. Bunya nuts black-eyed pea prairie turnip leek lentil turnip greens
parsnip. .


Use grid:

- For multiple rows or columns of items.
- When you want to be able to align the items on the block and inline axes.
- When you want items to line up in rows and columns.

## [Resources on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts\#resources_on_mdn)

- [Guide to Multi-column Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout)
- [Guide to flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout)
- [Guide to CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/layout_cookbook/column_layouts/index.md?plain=1 "Folder: ⁨en-us/web/css/layout_cookbook/column_layouts⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FLayout_cookbook%2FColumn_layouts&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Flayout_cookbook%2Fcolumn_layouts%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FLayout_cookbook%2FColumn_layouts%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Flayout_cookbook%2Fcolumn_layouts%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")