---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
scraped_at: 2025-10-20T03:02:27.360Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout#search)

# CSS grid layout

The **CSS grid layout** module excels at dividing a page into major regions or defining the relationship in terms of size, position, and layering between parts of a control built from HTML primitives.

Like tables, grid layout enables an author to align elements into columns and rows. However, many more layouts are either possible or easier with CSS grid than they were with tables. For example, a grid container's child elements could position themselves so they actually overlap and layer, similar to CSS positioned elements.

## [Grid layout in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#grid_layout_in_action)

The example shows a three-column track grid with new rows created at a minimum of 100 pixels and a maximum of auto. Items have been placed onto the grid using line-based placement.

This sample animation uses [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display), [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns), [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows), and [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) to create the grid, and [`grid-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column) and [`grid-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row) to position items within in the grid. To view and edit the HTML and CSS used, click the 'Play' at the top right of the example.

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#properties)

- [`grid-auto-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns)
- [`grid-auto-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow)
- [`grid-auto-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows)
- [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
- [`grid-template-areas`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
- [`grid-template`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template) shorthand
- [`grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid) shorthand
- [`grid-column-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-start)
- [`grid-column-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-end)
- [`grid-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column) shorthand
- [`grid-row-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start)
- [`grid-row-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end)
- [`grid-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row) shorthand
- [`grid-area`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area) shorthand

### [Functions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#functions)

- [`repeat()`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat)
- [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax)
- [`fit-content()`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content_function)

### [Data types and values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#data_types_and_values)

- [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value) ( `fr` unit)

### [Terms and glossary definitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#terms_and_glossary_definitions)

- [Grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid)
- [Grid areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas)
- [Grid axis](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Axis)
- [Grid cell](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Cell)
- [Grid column](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column)
- [Grid container](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Container)
- [Grid lines](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Lines)
- [Grid row](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Row)
- [Grid tracks](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Tracks)
- [Gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#guides)

[Basic concepts of grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)

An overview of the various features provided in the CSS grid layout module.

[Relationship of grid layout with other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Relationship_of_grid_layout_with_other_layout_methods)

How grid layout fits together with other CSS features including flexbox, absolutely positioned elements, and `display: contents`.

[Grid layout using line-based placement](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_line-based_placement)

Grid lines and how to position items against those lines, including the `grid-area` properties, negative line numbers, spanning multiple cells, and creating grid gutters.

[Grid template areas](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_template_areas)

Placing grid items using named template areas.

[Grid layout using named grid lines](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_named_grid_lines)

Combining names and track sizes; placing grid items by defining named grid lined and template areas.

[Auto-placement in grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Auto-placement_in_grid_layout)

How grid positions items that don't have any placement properties declared.

[Aligning items in CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Box_alignment_in_grid_layout)

Aligning, justifying, and centering grid items along the two axes of a grid layout.

[Grids, logical values, and writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grids_logical_values_and_writing_modes)

A look at the interaction between CSS grid layout, box alignment and writing modes, along with CSS logical and physical properties and values.

[Grid layout and accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_and_accessibility)

A look at how CSS grid layout can both help and harm accessibility.

[Realizing common layouts using grids](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Realizing_common_layouts_using_grids)

A few different layouts demonstrating different techniques you can use when designing with CSS grid layouts, including using [`grid-template-areas`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas), a 12-column flexible grid system, and a product listing using auto-placement.

[Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid)

What subgrid does with use cases and design patterns that subgrid solves.

[Masonry layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout)

Details what masonry layout is and it is used.

[Box alignment in CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_grid_layout)

How box alignment works in the context of grid layout.

## [Related features](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#related_features)

[CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) module

- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order)

[CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment) module

- [`align-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
- [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [`align-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self)
- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
- [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- [`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
- [`justify-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items)
- [`justify-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-self)
- [`place-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)
- [`place-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-items)
- [`place-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-self)
- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)

[CSS box sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing) module

- [`aspect-ratio`](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)
- [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
- [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)
- [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
- [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)
- [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height)
- [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width)
- [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
- [`<ratio>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ratio) data type
- [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-content) value
- [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content) value
- [`fit-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content) value
- [`fit-content()`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content_function) function

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#specifications)

| Specification |
| --- |
| [CSS Grid Layout Module Level 2](https://drafts.csswg.org/css-grid/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout\#see_also)

- [CSS flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) module
- [CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) module
- [Grid by example](https://gridbyexample.com/)
- [CSS grid reference](https://tympanus.net/codrops/css_reference/grid/) via Codrops
- [Firefox DevTools: grid inspector](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_grid_layouts/index.html)
- [CSS grid playground](https://mozilladevelopers.github.io/playground/css-grid/)
- [CSS grid garden](https://cssgridgarden.com/) \- A game for learning CSS grid

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_grid_layout/index.md?plain=1 "Folder: ⁨en-us/web/css/css_grid_layout⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_grid_layout&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_grid_layout%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_grid_layout%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_grid_layout%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")