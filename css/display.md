---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/display
scraped_at: 2025-10-20T02:59:01.510Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/display#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/display#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# display


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/display#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdisplay&level=high)

The **`display`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element is treated as a [block or inline box](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout) and the layout used for its children, such as [flow layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout), [grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) or [flex](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout).

Formally, the **`display`** property sets an element's inner and outer _display types_. The outer type sets an element's participation in [flow layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout); the inner type sets the layout of children. Some values of `display` are fully defined in their own individual specifications; for example the detail of what happens when `display: flex` is declared is defined in the CSS Flexible Box Model specification.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#try_it)

- display: block;

- display: inline-block;

- display: none;

- display: flex;

- display: grid;


Apply different `display` values on the dashed orange-bordered
`div`, which contains three child elements.

Some text A.


Child 1

Child 2

Child 3

Some text B.


cssCopy

```
display: block;

```

cssCopy

```
display: inline-block;

```

cssCopy

```
display: none;

```

cssCopy

```
display: flex;

```

cssCopy

```
display: grid;

```

htmlCopy

```
<p>
  Apply different <code>display</code> values on the dashed orange-bordered
  <code>div</code>, which contains three child elements.
</p>
<section class="default-example" id="default-example">
  <div class="example-container">
    Some text A.
    <div id="example-element">
      <div class="child">Child 1</div>
      <div class="child">Child 2</div>
      <div class="child">Child 3</div>
    </div>
    Some text B.
  </div>
</section>

```

cssCopy

```
.example-container {
  width: 100%;
  height: 100%;
}

code {
  background: #88888888;
}

#example-element {
  border: 3px dashed orange;
}

.child {
  display: inline-block;
  padding: 0.5em 1em;
  background-color: #ccccff;
  border: 1px solid #ababab;
  color: black;
}

```

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#syntax)

cssCopy

```
/* precomposed values */
display: block;
display: inline;
display: inline-block;
display: flex;
display: inline-flex;
display: grid;
display: inline-grid;
display: flow-root;

/* Box suppression */
display: none;
display: contents;

/* multi-keyword syntax */
display: block flex;
display: block flow;
display: block flow-root;
display: block grid;
display: inline flex;
display: inline flow;
display: inline flow-root;
display: inline grid;

/* other values */
display: table;
display: table-row; /* all table elements have an equivalent CSS display value */
display: list-item;

/* Global values */
display: inherit;
display: initial;
display: revert;
display: revert-layer;
display: unset;

```

The CSS `display` property is specified using keyword values.

## [Grouped values](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#grouped_values)

The keyword values can be grouped into six value categories.

### [Outside](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#outside)

[`<display-outside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside)

These keywords specify the element's outer display type, which is essentially its role in flow layout:

[`block`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#block)

The element generates a block box, generating line breaks both before and after the element when in the normal flow.

[`inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline)

The element generates one or more inline boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space.

**Note:**
When browsers that support multi-keyword syntax encounter a display property that only has an **outer** value (e.g., `display: block` or `display: inline`), the inner value is set to `flow` (e.g., `display: block flow` and `display: inline flow`).

**Note:**
To be sure layouts work on older browsers, you may use single-value syntax, for example `display: inline flex` could have the following fallback

cssCopy

```
.container {
  display: inline-flex;
  display: inline flex;
}

```

See [Using the multi-keyword syntax with CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/multi-keyword_syntax_of_display) for more information.

### [Inside](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#inside)

[`<display-inside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside)

These keywords specify the element's inner display type, which defines the type of formatting context that its contents are laid out in (assuming it is a non-replaced element). When one of these keywords is used by itself as a single value, the element's outer display type defaults to `block` (with the exception of `ruby`, which defaults to `inline`).

[`flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flow)

The element lays out its contents using flow layout (block-and-inline layout).

If its outer display type is `inline`, and it is participating in a block or inline formatting context, then it generates an inline box. Otherwise it generates a block box.

Depending on the value of other properties (such as [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position), [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float), or [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)) and whether it is itself participating in a block or inline formatting context, it either establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context) (BFC) for its contents or integrates its contents into its parent formatting context.

[`flow-root`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flow-root)

The element generates a block box that establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context), defining where the formatting root lies.

[`table`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table)

These elements behave like HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/table) elements. It defines a block-level box.

[`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flex)

The element behaves like a block-level element and lays out its content according to the [flexbox model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout).

[`grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#grid)

The element behaves like a block-level element and lays out its content according to the [grid model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout).

[`ruby`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#ruby)

The element behaves like an inline-level element and lays out its content according to the ruby formatting model. It behaves like the corresponding HTML [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/ruby) elements.

**Note:**
When browsers that support multi-keyword syntax encounter a display property that only has an **inner** value (e.g., `display: flex` or `display: grid`), the outer value is set to `block` (e.g., `display: block flex` and `display: block grid`).

### [List Item](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#list_item)

[`<display-listitem>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem)

The element generates a block box for the content and a separate list-item inline box.

A single value of `list-item` will cause the element to behave like a list item.
This can be used together with [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) and [`list-style-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position).

`list-item` can also be combined with any [`<display-outside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside) keyword and the `flow` or `flow-root` [`<display-inside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside) keyword.

**Note:**
In browsers that support the multi-keyword syntax, if no inner value is specified, it will default to `flow`.
If no outer value is specified, the principal box will have an outer display type of `block`.

### [Internal](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#internal)

[`<display-internal>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal)

Some layout models such as `table` and `ruby` have a complex internal structure, with several different roles that their children and descendants can fill.
This section defines those "internal" display values, which only have meaning within that particular layout mode.

[`table-row-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-row-group)

These elements behave like [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tbody) HTML elements.

[`table-header-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-header-group)

These elements behave like [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/thead) HTML elements.

[`table-footer-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-footer-group)

These elements behave like [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tfoot) HTML elements.

[`table-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-row)

These elements behave like [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tr) HTML elements.

[`table-cell`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-cell)

These elements behave like [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/td) HTML elements.

[`table-column-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-column-group)

These elements behave like [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/colgroup) HTML elements.

[`table-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-column)

These elements behave like [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/col) HTML elements.

[`table-caption`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#table-caption)

These elements behave like [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/caption) HTML elements.

[`ruby-base`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#ruby-base)

These elements behave like [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rb) HTML elements.

[`ruby-text`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#ruby-text)

These elements behave like [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rt) HTML elements.

[`ruby-base-container`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#ruby-base-container)

These elements are generated as anonymous boxes.

[`ruby-text-container`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#ruby-text-container)

These elements behave like [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rtc) HTML elements.

### [Box](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#box)

[`<display-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-box)

These values define whether an element generates display boxes at all.

[`contents`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#contents)

These elements don't produce a specific box by themselves. They are replaced by their pseudo-box and their child boxes. Please note that the CSS Display Level 3 spec defines how the `contents` value should affect "unusual elements" — elements that aren't rendered purely by CSS box concepts such as replaced elements. See [Appendix B: Effects of display: contents on Unusual Elements](https://drafts.csswg.org/css-display/#unbox) for more details.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#none)

Turns off the display of an element so that it has no effect on layout (the document is rendered as though the element did not exist). All descendant elements also have their display turned off.
To have an element take up the space that it would normally take, but without actually rendering anything, use the [`visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility) property instead.

### [Precomposed](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#precomposed)

[`<display-legacy>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy)

CSS 2 used a single-keyword, precomposed syntax for the `display` property, requiring separate keywords for block-level and inline-level variants of the same layout mode.

[`inline-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline-block)

The element generates a block box that will be flowed with surrounding content as if it were a single inline box (behaving much like a replaced element would).

It is equivalent to `inline flow-root`.

[`inline-table`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline-table)

The `inline-table` value does not have a direct mapping in HTML. It behaves like an HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/table) element, but as an inline box, rather than a block-level box. Inside the table box is a block-level context.

It is equivalent to `inline table`.

[`inline-flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline-flex)

The element behaves like an inline-level element and lays out its content according to the flexbox model.

It is equivalent to `inline flex`.

[`inline-grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline-grid)

The element behaves like an inline-level element and lays out its content according to the grid model.

It is equivalent to `inline grid`.

### [Which syntax should you use?](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#which_syntax_should_you_use)

The [CSS display module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) describes a multi-keyword syntax for values you can use with the `display` property to explicitly define **outer** and **inner** display.
The single keyword values (precomposed `<display-legacy>` values) are supported for backward-compatibility.

For example, using two values you can specify an inline flex container as follows:

cssCopy

```
.container {
  display: inline flex;
}

```

This can also be specified using the legacy single value:

cssCopy

```
.container {
  display: inline-flex;
}

```

For more information on these changes, see the [Using the multi-keyword syntax with CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/multi-keyword_syntax_of_display) guide.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#description)

The individual pages for the different types of value that `display` can have set on it feature multiple examples of those values in action — see the [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/display#syntax) section. In addition, see the following material, which covers the various values of display in depth.

### [Multi-keyword values](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#multi-keyword_values)

- [Using the multi-keyword syntax with CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/multi-keyword_syntax_of_display)

### [CSS Flow Layout (display: block, display: inline)](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#css_flow_layout_display_block_display_inline)

- [Block and inline layout in normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_and_inline_layout_in_normal_flow)
- [Flow layout and overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout_and_overflow)
- [Flow layout and writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Flow_layout_and_writing_modes)
- [Introduction to formatting contexts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Introduction_to_formatting_contexts)
- [In flow and out of flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/In_flow_and_out_of_flow)

### [display: flex](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#display_flex)

- [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [Aligning items in a flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container)
- [Controlling ratios of flex items along the main axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Controlling_ratios_of_flex_items_along_the_main_axis)
- [Mastering wrapping of flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Mastering_wrapping_of_flex_items)
- [Ordering flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Ordering_flex_items)
- [Relationship of flexbox to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Relationship_of_flexbox_to_other_layout_methods)
- [Typical use cases of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Typical_use_cases_of_flexbox)

### [display: grid](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#display_grid)

- [Basic concepts of grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [Relationship to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Relationship_of_grid_layout_with_other_layout_methods)
- [Line-based placement](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_line-based_placement)
- [Grid template areas](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_template_areas)
- [Layout using named grid lines](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_named_grid_lines)
- [Auto-placement in grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Auto-placement_in_grid_layout)
- [Aligning items in CSS grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Box_alignment_in_grid_layout)
- [Grids, logical values and writing modes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grids_logical_values_and_writing_modes)
- [CSS grid layout and accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_and_accessibility)
- [Realizing common layouts using grids](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Realizing_common_layouts_using_grids)

### [Animating display](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#animating_display)

[Supporting browsers](https://developer.mozilla.org/en-US/docs/Web/CSS/display#browser_compatibility) animate `display` with a [discrete animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties#discrete). This generally means that the property will flip between two values 50% through animating between the two.

There is one exception, which is when animating to or from `display: none`. In this case, the browser will flip between the two values so that the animated content is shown for the entire animation duration. So for example:

- When animating `display` from `none` to `block` (or another visible `display` value), the value will flip to `block` at `0%` of the animation duration so it is visible throughout.
- When animating `display` from `block` (or another visible `display` value) to `none`, the value will flip to `none` at `100%` of the animation duration so it is visible throughout.

This behavior is useful for creating entry/exit animations where you want to for example remove a container from the DOM with `display: none`, but have it fade out with [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity) rather than disappearing immediately.

When animating `display` with [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations), you need to provide the starting `display` value in an explicit keyframe (for example using `0%` or `from`). See [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations) for an example.

When animating `display` with [CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions), two additional features are needed:

- [`@starting-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style) provides starting values for properties you want to transition from when the animated element is first shown. This is needed to avoid unexpected behavior. By default, CSS transitions are not triggered on an element's first style update or when the `display` type changes from `none` to another type.
- [`transition-behavior: allow-discrete`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-behavior) needs to be set on the [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) declaration (or the [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) shorthand) to enable `display` transitions.

For examples of transitioning the `display` property, see the [`@starting-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style#examples) and [`transition-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-behavior#examples) pages.

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#accessibility)

### [display: none](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#display_none)

Using a `display` value of `none` on an element will remove it from the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility/What_is_accessibility#accessibility_apis). This will cause the element and all its descendant elements to no longer be announced by screen reading technology.

If you want to visually hide the element, a more accessible alternative is to use [a combination of properties](https://webaim.org/techniques/css/invisiblecontent/) to remove it visually from the screen but still make it available to assistive technology such as screen readers.

While `display: none` hides content from the accessibility tree, elements that are hidden but are referenced from visible elements' `aria-describedby` or `aria-labelledby` attributes are exposed to assistive technologies.

### [display: contents](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#display_contents)

Current implementations in some browsers will remove from the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility/What_is_accessibility#accessibility_apis) any element with a `display` value of `contents` (but descendants will remain). This will cause the element itself to no longer be announced by screen reading technology. This is incorrect behavior according to the [CSS specification](https://drafts.csswg.org/css-display/#valdef-display-contents).

- [More accessible markup with display: contents \| Hidde de Vries](https://hidde.blog/more-accessible-markup-with-display-contents/)
- [Display: Contents Is Not a CSS Reset \| Adrian Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)

### [Tables](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#tables)

In some browsers, changing the `display` value of a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/table) element to `block`, `grid`, or `flex` will alter its representation in the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility/What_is_accessibility#accessibility_apis). This will cause the table to no longer be announced properly by screen reading technology.

- [Short note on what CSS display properties do to table semantics — The Paciello Group](https://www.tpgi.com/short-note-on-what-css-display-properties-do-to-table-semantics/)
- [Hidden content for better a11y \| Go Make Things](https://gomakethings.com/hidden-content-for-better-a11y/)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 \| W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `inline` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as the specified value, except for positioned and floating elements and the root element. In both cases the computed value may be a keyword other than the one specified. |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Discrete behavior except when animating to or from `none` is visible for the entire duration |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#formal_syntax)

```
display =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <display-outside>  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  <display-inside>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <display-listitem>                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <display-internal>                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <display-box>                                      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <display-legacy>                                   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <display-outside>  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <display-inside>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  math  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")

<display-outside> =
  block    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  run-in

<display-inside> =
  flow        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  flow-root   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  flex        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  grid        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby

<display-listitem> =
  <display-outside> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")      [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  flow  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  flow-root  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")   [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  list-item

<display-internal> =
  table-row-group       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-header-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-footer-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-row             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-cell            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-column-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-column          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-caption         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-base             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-text             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-base-container   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-text-container

<display-box> =
  contents   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none

<display-legacy> =
  inline-block   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-table   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-flex    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-grid

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#examples)

### [display value comparison](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#display_value_comparison)

In this example we have two block-level container elements, each one with three inline children. Below that, we have a select menu that allows you to apply different `display` values to the containers, allowing you to compare and contrast how the different values affect the element's layout, and that of their children.

We have included [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) and [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) on the containers and their children, so that it is easier to see the effect the display values are having.

#### HTML

htmlCopyPlay

```
<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<div>
  <label for="display">Choose a display value:</label>
  <select id="display">
    <option selected>block</option>
    <option>block flow</option>
    <option>inline</option>
    <option>inline flow</option>
    <option>flow</option>
    <option>flow-root</option>
    <option>block flow-root</option>
    <option>table</option>
    <option>block table</option>
    <option>flex</option>
    <option>block flex</option>
    <option>grid</option>
    <option>block grid</option>
    <option>list-item</option>
    <option>block flow list-item</option>
    <option>inline flow list-item</option>
    <option>block flow-root list-item</option>
    <option>inline flow-root list-item</option>
    <option>contents</option>
    <option>none</option>
    <option>inline-block</option>
    <option>inline flow-root</option>
    <option>inline-table</option>
    <option>inline table</option>
    <option>inline-flex</option>
    <option>inline flex</option>
    <option>inline-grid</option>
    <option>inline grid</option>
  </select>
</div>

```

#### CSS

cssCopyPlay

```
html {
  font-family: "Helvetica", "Arial", sans-serif;
  letter-spacing: 1px;
  padding-top: 10px;
}

article {
  background-color: red;
}

article span {
  background-color: black;
  color: white;
  margin: 1px;
}

article,
span {
  padding: 10px;
  border-radius: 7px;
}

article,
div {
  margin: 20px;
}

```

#### JavaScript

jsCopyPlay

```
const articles = document.querySelectorAll(".container");
const select = document.querySelector("select");

function updateDisplay() {
  articles.forEach((article) => {
    article.style.display = select.value;
  });
}

select.addEventListener("change", updateDisplay);

updateDisplay();

```

#### Result

Play

FirstSecondThirdFirstSecondThird

Choose a display value:blockblock flowinlineinline flowflowflow-rootblock flow-roottableblock tableflexblock flexgridblock gridlist-itemblock flow list-iteminline flow list-itemblock flow-root list-iteminline flow-root list-itemcontentsnoneinline-blockinline flow-rootinline-tableinline tableinline-flexinline flexinline-gridinline grid

Note that some multi-keyword values are added for illustration which have the following equivalents:

- `block` = `block flow`
- `inline` = `inline flow`
- `flow` = `block flow`
- `flow-root` = `block flow-root`
- `table` = `block table`
- `flex` = `block flex`
- `grid` = `block grid`
- `list-item` = `block flow list-item`
- `inline-block` = `inline flow-root`
- `inline-table` = `inline table`
- `inline-flex` = `inline flex`
- `inline-grid` = `inline grid`

You can find more examples in the pages for each separate display type under [Grouped values](https://developer.mozilla.org/en-US/docs/Web/CSS/display#grouped_values).

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#specifications)

| Specification |
| --- |
| [CSS Display Module Level 3\<br>\# the-display-properties](https://drafts.csswg.org/css-display/#the-display-properties) |
| [Scalable Vector Graphics (SVG) 2\<br>\# VisibilityControl](https://svgwg.org/svg2-draft/render.html#VisibilityControl) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/display# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/display.json "File: ⁨css/properties/display.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `display` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `block` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `contents` | Chrome – Full support<br>Chrome65<br>Chrome – Full support<br>Chrome65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox37<br>Firefox – Full support<br>Firefox37 (Release date: ⁨2015-03-31⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera52<br>Opera – Full support<br>Opera52 (Release date: ⁨2018-03-22⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11.1<br>Safari – Full support<br>Safari11.1 (Release date: ⁨2018-04-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android65<br>Chrome Android – Full support<br>Chrome Android65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android37<br>Firefox for Android – Full support<br>Firefox for Android37 (Release date: ⁨2015-03-31⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android47<br>Opera Android – Full support<br>Opera Android47 (Release date: ⁨2018-07-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11.3<br>Safari on iOS – Full support<br>Safari on iOS11.3 (Release date: ⁨2018-03-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet9<br>Samsung Internet – Full support<br>Samsung Internet9 (Release date: ⁨2018-09-15⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android65<br>WebView Android – Full support<br>WebView Android65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11.3<br>WebView on iOS – Full support<br>WebView on iOS11.3 (Release date: ⁨2018-03-29⁩)<br> <br>footnoteFull support |
| Specific behavior of unusual elements when `display: contents` is applied to them | Chrome – Full support<br>Chrome65<br>Chrome – Full support<br>Chrome65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox59<br>Firefox – Full support<br>Firefox59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera52<br>Opera – Full support<br>Opera52 (Release date: ⁨2018-03-22⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android65<br>Chrome Android – Full support<br>Chrome Android65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android59<br>Firefox for Android – Full support<br>Firefox for Android59 (Release date: ⁨2018-03-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android47<br>Opera Android – Full support<br>Opera Android47 (Release date: ⁨2018-07-23⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet9<br>Samsung Internet – Full support<br>Samsung Internet9 (Release date: ⁨2018-09-15⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android65<br>WebView Android – Full support<br>WebView Android65 (Release date: ⁨2018-03-06⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Elements with `display: contents` are focusable<br>Experimental | Chrome – No support<br>ChromeNo<br> <br>footnote<br>Chrome – No support<br>Chrome<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | Edge – No support<br>EdgeNo<br> <br>footnote<br>Edge – No support<br>Edge<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | Firefox – No support<br>FirefoxNo<br> <br>footnote<br>Firefox – No support<br>Firefox<br>footnote<br>footnoteSee [⁨bug 1791648⁩](https://bugzil.la/1791648)footnoteSee [⁨bug 1553549⁩](https://bugzil.la/1553549) | Opera – No support<br>OperaNo<br> <br>footnote<br>Opera – No support<br>Opera<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | Safari – No support<br>SafariNo<br> <br>footnote<br>Safari – No support<br>Safari<br>footnote<br>footnoteSee [⁨bug 255149⁩](https://webkit.org/b/255149) | Chrome Android – No support<br>Chrome AndroidNo<br> <br>footnote<br>Chrome Android – No support<br>Chrome Android<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>footnote<br>Firefox for Android – No support<br>Firefox for Android<br>footnote<br>footnoteSee [⁨bug 1791648⁩](https://bugzil.la/1791648)footnoteSee [⁨bug 1553549⁩](https://bugzil.la/1553549) | Opera Android – No support<br>Opera AndroidNo<br> <br>footnote<br>Opera Android – No support<br>Opera Android<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | Safari on iOS – No support<br>Safari on iOSNo<br> <br>footnote<br>Safari on iOS – No support<br>Safari on iOS<br>footnote<br>footnoteSee [⁨bug 255149⁩](https://webkit.org/b/255149) | Samsung Internet – No support<br>Samsung InternetNo<br> <br>footnote<br>Samsung Internet – No support<br>Samsung Internet<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | WebView Android – No support<br>WebView AndroidNo<br> <br>footnote<br>WebView Android – No support<br>WebView Android<br>footnote<br>footnoteSee [⁨bug 40866683⁩](https://crbug.com/40866683) | WebView on iOS – No support<br>WebView on iOSNo<br> <br>footnote<br>WebView on iOS – No support<br>WebView on iOS<br>footnote<br>footnoteSee [⁨bug 255149⁩](https://webkit.org/b/255149) |
| `flex` | Chrome – Full support<br>Chrome29<br>more<br>Chrome – Full support<br>Chrome21 (Release date: ⁨2012-07-31⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome – Full support<br>Chrome29 (Release date: ⁨2013-08-20⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox20<br>footnote<br>Firefox – Full support<br>Firefox20 (Release date: ⁨2013-04-02⁩)<br> <br>footnote<br>footnoteFirefox 28 added multi-line flexbox support. | Opera – Full support<br>Opera16<br>more<br>Opera – No support<br>Opera12.1 – 12.1 (Release date: ⁨2012-11-20⁩)<br> <br>unknownSupport unknown<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera – Full support<br>Opera16 (Release date: ⁨2013-08-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>more<br>Safari – Full support<br>Safari7 (Release date: ⁨2013-10-22⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android29<br>more<br>Chrome Android – Full support<br>Chrome Android25 (Release date: ⁨2013-02-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome Android – Full support<br>Chrome Android29 (Release date: ⁨2013-08-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android20<br>footnote<br>Firefox for Android – Full support<br>Firefox for Android20 (Release date: ⁨2013-04-02⁩)<br> <br>footnote<br>footnoteFirefox for Android 28 added multi-line flexbox support. | Opera Android – Full support<br>Opera Android16<br>more<br>Opera Android – No support<br>Opera Android12.1 – 12.1 (Release date: ⁨2012-10-09⁩)<br> <br>unknownSupport unknown<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera Android – Full support<br>Opera Android16 (Release date: ⁨2013-09-18⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>more<br>Safari on iOS – Full support<br>Safari on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet2<br>more<br>Samsung Internet – Full support<br>Samsung Internet1.5 (Release date: ⁨2013-09-25⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Samsung Internet – Full support<br>Samsung Internet2 (Release date: ⁨2014-10-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>more<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>more<br>WebView on iOS – Full support<br>WebView on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| `flow-root` | Chrome – Full support<br>Chrome58<br>Chrome – Full support<br>Chrome58 (Release date: ⁨2017-04-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox53<br>Firefox – Full support<br>Firefox53 (Release date: ⁨2017-04-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera45<br>Opera – Full support<br>Opera45 (Release date: ⁨2017-05-10⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari13<br>Safari – Full support<br>Safari13 (Release date: ⁨2019-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android58<br>Chrome Android – Full support<br>Chrome Android58 (Release date: ⁨2017-04-25⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android53<br>Firefox for Android – Full support<br>Firefox for Android53 (Release date: ⁨2017-04-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS13<br>Safari on iOS – Full support<br>Safari on iOS13 (Release date: ⁨2019-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet7<br>Samsung Internet – Full support<br>Samsung Internet7 (Release date: ⁨2018-03-16⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android58<br>WebView Android – Full support<br>WebView Android58 (Release date: ⁨2017-04-25⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS13<br>WebView on iOS – Full support<br>WebView on iOS13 (Release date: ⁨2019-09-19⁩)<br> <br>footnoteFull support |
| `grid` | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge16<br>more<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-ms-⁩<br>Edge – Full support<br>Edge16 (Release date: ⁨2017-10-17⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10.1<br>Safari – Full support<br>Safari10.1 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS10.3<br>Safari on iOS – Full support<br>Safari on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet6<br>footnote<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnote<br>footnoteSamsung Internet added this earlier than the corresponding Chrome version would indicate. | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS10.3<br>WebView on iOS – Full support<br>WebView on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support |
| `inline` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `inline-block` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `inline-flex` | Chrome – Full support<br>Chrome29<br>more<br>Chrome – Full support<br>Chrome21 (Release date: ⁨2012-07-31⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome – Full support<br>Chrome29 (Release date: ⁨2013-08-20⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox20<br>footnote<br>Firefox – Full support<br>Firefox20 (Release date: ⁨2013-04-02⁩)<br> <br>footnote<br>footnoteFirefox 28 added multi-line flexbox support. | Opera – Full support<br>Opera16<br>more<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera – Full support<br>Opera16 (Release date: ⁨2013-08-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>more<br>Safari – Full support<br>Safari7 (Release date: ⁨2013-10-22⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android29<br>more<br>Chrome Android – Full support<br>Chrome Android25 (Release date: ⁨2013-02-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome Android – Full support<br>Chrome Android29 (Release date: ⁨2013-08-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android20<br>footnote<br>Firefox for Android – Full support<br>Firefox for Android20 (Release date: ⁨2013-04-02⁩)<br> <br>footnote<br>footnoteFirefox for Android 28 added multi-line flexbox support. | Opera Android – Full support<br>Opera Android16<br>more<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera Android – Full support<br>Opera Android16 (Release date: ⁨2013-09-18⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>more<br>Safari on iOS – Full support<br>Safari on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet2<br>more<br>Samsung Internet – Full support<br>Samsung Internet1.5 (Release date: ⁨2013-09-25⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Samsung Internet – Full support<br>Samsung Internet2 (Release date: ⁨2014-10-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>more<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>more<br>WebView on iOS – Full support<br>WebView on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| `inline-grid` | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge16<br>more<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-ms-⁩<br>Edge – Full support<br>Edge16 (Release date: ⁨2017-10-17⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10.1<br>Safari – Full support<br>Safari10.1 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS10.3<br>Safari on iOS – Full support<br>Safari on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet6<br>footnote<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnote<br>footnoteSamsung Internet added this earlier than the corresponding Chrome version would indicate. | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS10.3<br>WebView on iOS – Full support<br>WebView on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support |
| `inline-table` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox3<br>Firefox – Full support<br>Firefox3 (Release date: ⁨2008-06-17⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| Transitionable when setting `transition-behavior: allow-discrete` | Chrome – Full support<br>Chrome117<br>Chrome – Full support<br>Chrome117 (Release date: ⁨2023-09-12⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge117<br>Edge – Full support<br>Edge117 (Release date: ⁨2023-09-15⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>footnote<br>Firefox – No support<br>Firefox<br>footnote<br>footnoteSee [⁨bug 1882408⁩](https://bugzil.la/1882408) | Opera – Full support<br>Opera103<br>Opera – Full support<br>Opera103 (Release date: ⁨2023-10-03⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18<br>Safari – Full support<br>Safari18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android117<br>Chrome Android – Full support<br>Chrome Android117 (Release date: ⁨2023-09-12⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>footnote<br>Firefox for Android – No support<br>Firefox for Android<br>footnote<br>footnoteSee [⁨bug 1882408⁩](https://bugzil.la/1882408) | Opera Android – Full support<br>Opera Android78<br>Opera Android – Full support<br>Opera Android78 (Release date: ⁨2023-10-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18<br>Safari on iOS – Full support<br>Safari on iOS18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet24<br>Samsung Internet – Full support<br>Samsung Internet24 (Release date: ⁨2024-01-25⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android117<br>WebView Android – Full support<br>WebView Android117 (Release date: ⁨2023-09-12⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18<br>WebView on iOS – Full support<br>WebView on iOS18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support |
| `@keyframe` animatable | Chrome – Full support<br>Chrome116<br>Chrome – Full support<br>Chrome116 (Release date: ⁨2023-08-15⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge116<br>Edge – Full support<br>Edge116 (Release date: ⁨2023-08-21⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>footnote<br>Firefox – No support<br>Firefox<br>footnote<br>footnoteSee [⁨bug 1834877⁩](https://bugzil.la/1834877) | Opera – Full support<br>Opera102<br>Opera – Full support<br>Opera102 (Release date: ⁨2023-08-23⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari18<br>Safari – Full support<br>Safari18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android116<br>Chrome Android – Full support<br>Chrome Android116 (Release date: ⁨2023-08-15⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>footnote<br>Firefox for Android – No support<br>Firefox for Android<br>footnote<br>footnoteSee [⁨bug 1834877⁩](https://bugzil.la/1834877) | Opera Android – Full support<br>Opera Android78<br>Opera Android – Full support<br>Opera Android78 (Release date: ⁨2023-10-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS18<br>Safari on iOS – Full support<br>Safari on iOS18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet24<br>Samsung Internet – Full support<br>Samsung Internet24 (Release date: ⁨2024-01-25⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android116<br>WebView Android – Full support<br>WebView Android116 (Release date: ⁨2023-08-15⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS18<br>WebView on iOS – Full support<br>WebView on iOS18 (Release date: ⁨2024-09-16⁩)<br> <br>footnoteFull support |
| [`list-item`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem) | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| Supported on `<legend>` | Chrome – Full support<br>Chrome71<br>Chrome – Full support<br>Chrome71 (Release date: ⁨2018-12-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox64<br>Firefox – Full support<br>Firefox64 (Release date: ⁨2018-12-11⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera58<br>Opera – Full support<br>Opera58 (Release date: ⁨2019-01-23⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android71<br>Chrome Android – Full support<br>Chrome Android71 (Release date: ⁨2018-12-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android64<br>Firefox for Android – Full support<br>Firefox for Android64 (Release date: ⁨2018-12-11⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android50<br>Opera Android – Full support<br>Opera Android50 (Release date: ⁨2019-02-18⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android71<br>WebView Android – Full support<br>WebView Android71 (Release date: ⁨2018-12-04⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `math`<br>Experimental | Chrome – Full support<br>Chrome109<br>Chrome – Full support<br>Chrome109 (Release date: ⁨2023-01-10⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge109<br>Edge – Full support<br>Edge109 (Release date: ⁨2023-01-12⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera95<br>Opera – Full support<br>Opera95 (Release date: ⁨2023-02-01⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android109<br>Chrome Android – Full support<br>Chrome Android109 (Release date: ⁨2023-01-10⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android74<br>Opera Android – Full support<br>Opera Android74 (Release date: ⁨2023-03-13⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet21<br>Samsung Internet – Full support<br>Samsung Internet21 (Release date: ⁨2023-05-19⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android109<br>WebView Android – Full support<br>WebView Android109 (Release date: ⁨2023-01-10⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Multi-keyword values | Chrome – Full support<br>Chrome115<br>Chrome – Full support<br>Chrome115 (Release date: ⁨2023-07-18⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge115<br>Edge – Full support<br>Edge115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox70<br>Firefox – Full support<br>Firefox70 (Release date: ⁨2019-10-22⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera101<br>Opera – Full support<br>Opera101 (Release date: ⁨2023-07-26⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15<br>Safari – Full support<br>Safari15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android115<br>Chrome Android – Full support<br>Chrome Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android77<br>Opera Android – Full support<br>Opera Android77 (Release date: ⁨2023-08-31⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15<br>Safari on iOS – Full support<br>Safari on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android115<br>WebView Android – Full support<br>WebView Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15<br>WebView on iOS – Full support<br>WebView on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome1<br>footnote<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnote<br>footnoteChrome 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>footnote<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnote<br>footnoteOpera 52 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>footnote<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnote<br>footnoteChrome Android 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>footnote<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnote<br>footnoteOpera Android 47 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>footnote<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnote<br>footnoteChrome 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | WebView Android – Full support<br>WebView Android4.4<br>footnote<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnote<br>footnoteWebView Android 65 stopped creating layout objects for elements inside an `<iframe>` with `display:none` applied. | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| Setting `display: none` on an `<option>` element hides it from the dropdown.<br>Non-standard | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `ruby` | Chrome – Full support<br>Chrome121<br>Chrome – Full support<br>Chrome121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | Edge – No support<br>Edge12 – 18<br>Edge – No support<br>Edge12 – 18 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteRemoved in ⁨79⁩ and later | Firefox – Full support<br>Firefox38<br>Firefox – Full support<br>Firefox38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera107<br>Opera – Full support<br>Opera107 (Release date: ⁨2024-02-07⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android121<br>Chrome Android – Full support<br>Chrome Android121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android38<br>Firefox for Android – Full support<br>Firefox for Android38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android81<br>Opera Android – Full support<br>Opera Android81 (Release date: ⁨2024-03-14⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet25<br>Samsung Internet – Full support<br>Samsung Internet25 (Release date: ⁨2024-04-24⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android121<br>WebView Android – Full support<br>WebView Android121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `ruby-base` | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>Edge12 – 18<br>Edge – No support<br>Edge12 – 18 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteRemoved in ⁨79⁩ and later | Firefox – Full support<br>Firefox38<br>Firefox – Full support<br>Firefox38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – Full support<br>Firefox for Android38<br>Firefox for Android – Full support<br>Firefox for Android38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `ruby-base-container` | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>Edge12 – 18<br>Edge – No support<br>Edge12 – 18 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteRemoved in ⁨79⁩ and later | Firefox – Full support<br>Firefox38<br>Firefox – Full support<br>Firefox38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – Full support<br>Firefox for Android38<br>Firefox for Android – Full support<br>Firefox for Android38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `ruby-text` | Chrome – Full support<br>Chrome121<br>Chrome – Full support<br>Chrome121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | Edge – No support<br>Edge12 – 18<br>Edge – No support<br>Edge12 – 18 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteRemoved in ⁨79⁩ and later | Firefox – Full support<br>Firefox38<br>Firefox – Full support<br>Firefox38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera107<br>Opera – Full support<br>Opera107 (Release date: ⁨2024-02-07⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android121<br>Chrome Android – Full support<br>Chrome Android121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android38<br>Firefox for Android – Full support<br>Firefox for Android38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android81<br>Opera Android – Full support<br>Opera Android81 (Release date: ⁨2024-03-14⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet25<br>Samsung Internet – Full support<br>Samsung Internet25 (Release date: ⁨2024-04-24⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android121<br>WebView Android – Full support<br>WebView Android121 (Release date: ⁨2024-01-23⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `ruby-text-container` | Chrome – No support<br>ChromeNo<br> <br>Chrome – No support<br>Chrome<br>footnoteNo support | Edge – No support<br>Edge12 – 18<br>Edge – No support<br>Edge12 – 18 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteRemoved in ⁨79⁩ and later | Firefox – Full support<br>Firefox38<br>Firefox – Full support<br>Firefox38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – No support<br>Chrome AndroidNo<br> <br>Chrome Android – No support<br>Chrome Android<br>footnoteNo support | Firefox for Android – Full support<br>Firefox for Android38<br>Firefox for Android – Full support<br>Firefox for Android38 (Release date: ⁨2015-05-12⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `table` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-caption` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge15<br>Edge – Full support<br>Edge15 (Release date: ⁨2017-04-05⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari4<br>Safari – Full support<br>Safari4 (Release date: ⁨2009-06-08⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS3.2<br>Safari on iOS – Full support<br>Safari on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS3.2<br>WebView on iOS – Full support<br>WebView on iOS3.2 (Release date: ⁨2010-04-03⁩)<br> <br>footnoteFull support |
| `table-cell` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-column` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-column-group` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-footer-group` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-header-group` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-row` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `table-row-group` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

No supportNo support

⁨Experimental⁩. Expect behavior to change in the future.

⁨Non-standard⁩. Check cross-browser support before using.

See implementation notes.

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/display\#see_also)

- [`visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility), [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float), [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [`grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid), [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
- SVG [`display`](https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Attribute/display) attribute
- [Block and inline layout in normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_and_inline_layout_in_normal_flow)
- [Introduction to formatting contexts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Introduction_to_formatting_contexts)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/display/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/display/index.md?plain=1 "Folder: ⁨en-us/web/css/display⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdisplay&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fdisplay%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdisplay%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fdisplay%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F40099ec4cc9464e5bf6ce88be9eb34da2a77ef4e%0A*+Document+last+modified%3A+2025-10-13T12%3A10%3A27.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")