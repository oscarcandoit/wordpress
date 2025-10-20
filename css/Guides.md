---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/Guides
scraped_at: 2025-10-20T02:59:16.042Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS guides

There are a number of methods that you can use to lay out your web pages and applications. MDN contains a number of in-depth guides to the different methods, and this page provides an overview of them all.

## [Normal flow, block, and inline layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides\#normal_flow_block_and_inline_layout)

If you are not using a flex or grid layout, then your content is laid out using normal flow, or block and inline layout. These guides will help you to understand the way this layout method works.

[Block and inline layout in normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_and_inline_layout_in_normal_flow)

An introduction to normal flow.

[In flow and out of flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/In_flow_and_out_of_flow)

How to take an item out of flow, and what that does to the layout of your document.

[Formatting contexts explained](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Introduction_to_formatting_contexts)

An introduction to creating a new formatting context.

[Flow layout and writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout_and_writing_modes)

How flow layout works if you use a different writing mode, such as vertical text.

[Flow layout and overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout_and_overflow)

Understanding and managing overflow.

[Introduction to the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)

Understanding the box model is a CSS fundamental; this guide explains how it works.

[Mastering margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)

Find out why you sometimes end up with less margin than you expect, due to margin collapsing in normal flow.

[Understanding CSS z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index)

Absolute positioning, flexbox, and grid all result in the stack (elements' relative position on the z-axis) to be manipulable via the `z-index` property. This article explains how to manage it.

## [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides\#multi-column_layout)

Multi-column layout, often referred to as multicol, takes content in normal flow, and breaks it into columns. Find out how to use this layout method in the following guides.

[Basic concepts of Multicol](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Basic_concepts)

An overview of the basic functionality of multicol.

[Styling columns](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Styling_columns)

There is a limited amount of styling opportunities for columns; this guide explains what you can do.

[Spanning and balancing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Spanning_balancing_columns)

Spanning elements across columns, and balancing the content of columns.

[Handling overflow in Multicol](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Handling_overflow_in_multicol_layout)

What happens when there is more content than available column space?

[Content breaks in Multicol](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Handling_content_breaks_in_multicol_layout)

Dealing with content breaks as the content is split into columns.

## [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides\#flexbox)

CSS Flexible Box Layout, commonly known as flexbox, is a layout model optimized for user interface design, and the layout of items in one dimension. In the flex layout model, the children of a flex container can be laid out in any direction, and can "flex" their sizes, either growing to fill unused space or shrinking to avoid overflowing the parent.

[Basic Concepts of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)

An overview of the features of Flexbox.

[Relationship of Flexbox to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Relationship_of_flexbox_to_other_layout_methods)

How Flexbox relates to other layout methods, and other CSS specifications.

[Aligning items in a flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container)

How the Box Alignment properties work with Flexbox.

[Ordering flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Ordering_flex_items)

Explaining the different ways to change the order and direction of items, and covering the potential issues in doing so.

[Controlling Ratios of flex items along the main axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Controlling_ratios_of_flex_items_along_the_main_axis)

Explaining the `flex-grow`, `flex-shrink`, and `flex-basis` properties.

[Mastering wrapping of flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Mastering_wrapping_of_flex_items)

How to create flex containers with multiple lines and control the display of the items along those lines.

[Typical use cases of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Typical_use_cases_of_flexbox)

Common design patterns that are typical Flexbox use cases.

## [Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides\#grid_layout)

CSS Grid Layout introduces a two-dimensional grid system to CSS. Grids can be used to lay out major page areas or small user interface elements.

[Basic concepts of Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)

An overview of the features of grid layout.

[Relationship of Grid Layout to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Relationship_of_grid_layout_with_other_layout_methods)

How grid relates to other methods such as alignment, sizing, and flexbox.

[Layout using line-based placement](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_line-based_placement)

How to place items by numbered lines.

[Grid template areas](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_template_areas)

How to place items using the grid-template syntax.

[Layout using named grid lines](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_named_grid_lines)

How to name lines, and place items by line name rather than number.

[Auto-placement in CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Auto-placement_in_grid_layout)

How to manage the auto-placement algorithm, and understand how the browser places items.

[Box alignment in CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Box_alignment_in_grid_layout)

How to align items, and distribute space on both axes in grid.

[CSS Grid, Logical Values and Writing Modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grids_logical_values_and_writing_modes)

How to use flow relative, rather than physical, properties and values with grid.

[CSS Grid Layout and accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_and_accessibility)

Some accessibility considerations when working with grid layout.

[Realizing common layouts using CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Realizing_common_layouts_using_grids)

Using grid to build some common layouts.

[Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid)

An explanation of the subgrid value, part of Grid Level 2.

[Masonry Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout)

An explanation of the masonry layout feature in Grid Level 3.

## [Alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides\#alignment)

[Box alignment in block layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_block_abspos_tables)

The alignment properties are specified for block and inline layout, though there is no browser support as yet.

[Box alignment in flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_flexbox)

The alignment properties first appeared with flexbox; this guide explains how they work.

[Box alignment in grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_grid_layout)

How to align items in grid layout.

[Box alignment in multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_multi-column_layout)

How alignment will work in multicol.

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/guides/index.md?plain=1 "Folder: ⁨en-us/web/css/guides⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FGuides&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fguides%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FGuides%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fguides%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")