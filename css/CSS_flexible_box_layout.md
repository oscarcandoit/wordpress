---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout
scraped_at: 2025-10-20T03:05:59.330Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout#search)

# CSS flexible box layout

The **CSS flexible box layout** module defines a CSS box model optimized for user interface design, and the layout of items in one dimension. In the flex layout model, the children of a flex container can be laid out in any direction, and can "flex" their sizes, either growing to fill unused space or shrinking to avoid overflowing the parent. Both horizontal and vertical alignment of the children can be easily manipulated.

## [Flexible box layout in action](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#flexible_box_layout_in_action)

In the following example, a container has been set to `display: flex`, which means that the three child items become flex items. The value of `justify-content` has been set to `space-between` in order to space the items out evenly on the main axis. An equal amount of space is placed between each item with the left and right items being flush with the edges of the flex container. You can also see that the items are stretching on the cross axis, due to the default value of `align-items` being `stretch`. The items stretch to the height of the flex container, making them each appear as tall as the tallest item.

htmlCopy

```
<div class="box">
  <div>One</div>
  <div>Two</div>
  <div>Three <br />has <br />extra <br />text</div>
</div>

```

cssCopy

```
body {
  font-family: sans-serif;
}

.box {
  border: 2px dotted rgb(96 139 168);
  display: flex;
  justify-content: space-between;
}

.box > * {
  border: 2px solid rgb(96 139 168);
  border-radius: 5px;
  background-color: rgb(96 139 168 / 0.2);
  padding: 1em;
}

```

## [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#reference)

### [Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#properties)

- [`align-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
- [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [`align-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self)
- [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
- [`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)
- [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)
- [`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow)
- [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)
- [`flex-shrink`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)
- [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)
- [`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)

### [Glossary terms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#glossary_terms)

- [Flexbox](https://developer.mozilla.org/en-US/docs/Glossary/Flexbox)
- [Flex container](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Container)
- [Flex item](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Item)
- [Main axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)
- [Cross axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis)
- [Flex](https://developer.mozilla.org/en-US/docs/Glossary/Flex)

## [Guides](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#guides)

[Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)

An overview of the features of Flexbox.

[Relationship of flexbox to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Relationship_of_flexbox_to_other_layout_methods)

How Flexbox relates to other layout methods and other CSS specifications.

[Aligning items in a flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container)

How the box alignment properties work with Flexbox.

[Ordering flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Ordering_flex_items)

Explaining the different ways to change the order and direction of items, and covering the potential issues in doing so.

[Controlling ratios of flex items along the main axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Controlling_ratios_of_flex_items_along_the_main_axis)

Explaining the flex-grow, flex-shrink and flex-basis properties.

[Mastering wrapping of flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Mastering_wrapping_of_flex_items)

How to create flex containers with multiple lines and control the display of the items in those lines.

[Typical use cases of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Typical_use_cases_of_flexbox)

Common design patterns that are typical Flexbox use cases.

[CSS layout: flexbox](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox)

Learn how to use flexbox layout to create web layouts.

[Box alignment in flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_flexbox)

Details features of [CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment) which are specific to flexbox.

## [Related concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#related_concepts)

[CSS display module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display)

- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order)

[CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment) module

- [`align-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
- [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [`align-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self)
- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
- [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- [`justify-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items)
- [`place-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)
- [`place-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-items)
- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)

[CSS box sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing) module

- [`aspect-ratio`](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)
- [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content) value
- [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-content) value
- [`fit-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content) value
- [intrinsic size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size) glossary term

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#specifications)

| Specification |
| --- |
| [CSS Flexible Box Layout Module Level 1](https://drafts.csswg.org/css-flexbox/) |

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout\#see_also)

- [CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) module
- [CSS writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes) module
- [Using the multi-keyword syntax with CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/multi-keyword_syntax_of_display)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/css_flexible_box_layout/index.md?plain=1 "Folder: ⁨en-us/web/css/css_flexible_box_layout⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_flexible_box_layout&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fcss_flexible_box_layout%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FCSS_flexible_box_layout%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fcss_flexible_box_layout%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")