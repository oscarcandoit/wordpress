---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout
scraped_at: 2025-10-20T03:18:05.848Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout#search)

# Masonry layout

**Experimental:** **This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**

Check the [Browser compatibility table](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout#browser_compatibility) carefully before using this in production.

Level 3 of the [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) specification includes a `masonry` value for [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns) and [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows). This guide details what masonry layout is and how to use it.

Masonry layout is a layout method where one axis uses a typical strict grid layout, most often columns, and the other a masonry layout. On the masonry axis, rather than sticking to a strict grid with gaps being left after shorter items, the items in the following row rise up to completely fill the gaps.

## [Creating a masonry layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#creating_a_masonry_layout)

To create the most common masonry layout, your columns will be the grid axis and the rows the masonry axis, defined with `grid-template-columns` and `grid-template-rows`.
The child elements of this container will now lay out item by item along the rows, as they would with regular grid layout automatic placement.

As the items move onto new rows, they will display according to the masonry algorithm. Items will load into the column with the most room, causing a tightly packed layout without strict row tracks.

```
* {
  box-sizing: border-box;
}

body {
  font: 1.2em sans-serif;
}

.grid {
  padding: 10px;
  border: 2px solid #f76707;
  border-radius: 5px;
  background-color: #fff4e6;
}

.item {
  border: 2px solid #ffa94d;
  border-radius: 5px;
  background-color: #ffd8a8;
  color: #d9480f;
}

```

css

```
.grid {
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  grid-template-rows: masonry;
}

```

html

```
<div class="grid">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>

```

js

```
// prettier-ignore
const itemSizes = [\
  "2em", "3em", "1.6em", "4em", "3.2em",\
  "3em", "4.5em", "1em", "3.5em", "2.8em",\
];
const items = document.querySelectorAll(".item");
for (let i = 0; i < items.length; i++) {
  items[i].style.blockSize = itemSizes[i];
}

```

It is also possible to create a masonry layout with items loading into rows.

js

```
// prettier-ignore
const itemSizes = [\
  "2em", "3em", "1.6em", "4em", "2.2em",\
  "3em", "4.5em", "1em", "3.5em", "2.8em",\
];
const items = document.querySelectorAll(".item");
for (let i = 0; i < items.length; i++) {
  items[i].style.inlineSize = itemSizes[i];
}

```

css

```
.grid {
  display: grid;
  gap: 10px;
  grid-template-columns: masonry;
  grid-template-rows: repeat(3, 100px);
}

```

## [Controlling the grid axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#controlling_the_grid_axis)

On the grid axis, things will work just as you expect them to in grid layout. You can cause items to span multiple tracks while remaining in auto-placement, using the `span` keyword. Items may also be positioned using line-based positioning.

### [Masonry layout with spanning items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#masonry_layout_with_spanning_items)

In this example two of the items span two tracks, and the masonry items work around them.

html

```
<div class="grid">
  <div class="item"></div>
  <div class="item span-2"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item span-2"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>

```

css

```
.grid {
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  grid-template-rows: masonry;
}

.span-2 {
  grid-column-end: span 2;
}

```

This example includes an item which has positioning for columns. Items with definite placement are placed before the masonry layout happens.

html

```
<div class="grid">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item positioned">positioned.</div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>

```

css

```
.grid {
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  grid-template-rows: masonry;
}

.positioned {
  padding: 1em;
  grid-column: 2 / 4;
}

```

## [Fallbacks for masonry layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#fallbacks_for_masonry_layout)

In browsers [that do not support masonry](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout#browser_compatibility), regular grid auto-placement will be used instead.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#specifications)

| Specification |
| --- |
| [CSS Grid Layout Module Level 3\<br>\# masonry-layout](https://drafts.csswg.org/css-grid-3/#masonry-layout) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#browser_compatibility)

### [css.properties.grid-template-columns.masonry](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#css.properties.grid-template-columns.masonry)

Loading…

### [css.properties.grid-template-rows.masonry](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#css.properties.grid-template-rows.masonry)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout\#see_also)

- [`grid-auto-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow) for controlling grid auto-placement
- [Native CSS masonry layout in CSS grid](https://www.smashingmagazine.com/native-css-masonry-layout-css-grid/) via Smashing Magazine (2020)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_grid_layout/masonry_layout/index.md?plain=1 "Folder: ⁨en-us/web/css/css_grid_layout/masonry_layout⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_grid_layout%2FMasonry_layout&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_grid_layout%2Fmasonry_layout%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_grid_layout%2FMasonry_layout%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_grid_layout%2Fmasonry_layout%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F72a2f0fa7f25ba32ab8e07447a8d4bbc2f936b85%0A*+Document+last+modified%3A+2025-07-14T15%3A04%3A26.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")