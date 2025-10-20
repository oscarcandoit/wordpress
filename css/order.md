---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/order
scraped_at: 2025-10-20T03:15:56.906Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/order#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/order#search)

# order


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨September 2015⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/order#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Forder&level=high)

The **`order`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending `order` value and then by their source code order. Items not given an explicit `order` value are assigned the default value of `0`.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#try_it)

```
order: 0;

```

```
order: 3;

```

```
order: -1;

```

```
order: 2;

```

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">Box 1:</div>
  <div style="order: 1">Box 2: <code>order: 1;</code></div>
  <div style="order: 2">Box 3: <code>order: 2;</code></div>
  <div style="order: 2">Box 4: <code>order: 2;</code></div>
  <div style="order: 3">Box 5: <code>order: 3;</code></div>
</section>

```

```
.default-example {
  max-height: 300px;
  display: flex;
  flex-flow: column;
}

.default-example > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
  margin: 0.5rem;
  padding: 0.5rem;
  flex: 1;
}

#example-element {
  background-color: rgb(255 0 200 / 0.2);
  border: 3px solid rebeccapurple;
}

#example-element::after {
  content: attr(style);
  outline: 2px dashed;
  font-family: monospace;
}

```

In the above demo, select the options on the left-hand side to change the value of the pink box's `order` property. The light blue boxes have been given fixed `order` values.

Bear in mind the effect of source order. For example, when `order: 2;` is selected, the pink box is placed before the two blue boxes with `order: 2;`. This is because the pink box appears before the blue boxes in the source code.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#syntax)

css

```
/* <integer> values */
order: 5;
order: -5;

/* Global values */
order: inherit;
order: initial;
order: revert;
order: revert-layer;
order: unset;

```

Since `order` is only meant to affect the _visual order_ of elements and not their logical or tab order, it must not be used on non-visual media such as [speech](https://drafts.csswg.org/css-speech/).

Defined in the [CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) module, this property impacts only grid and flex items. When `order` is set on an element whose parent's [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property is not creating a flex or grid container, it has no effect.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#values)

[`<integer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)

Represents the ordinal group to be used by the item.

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#accessibility)

Using the `order` property will create a disconnect between the visual presentation of content and DOM order. This will adversely affect low vision users navigating with the aid of assistive technology such as a screen reader. If the visual order differs from the DOM order, your users will have different experiences depending on how they access your content.

- [Flexbox & the keyboard navigation disconnect](https://tink.uk/flexbox-the-keyboard-navigation-disconnect/) via Tink (2016)
- [Source Order Matters](https://adrianroselli.com/2015/09/source-order-matters.html) via Adrian Roselli (2015)
- [Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.3_%E2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.2 \| W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-sequence.html)

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `0` |
| Applies to | Flex items, grid items, and absolutely-positioned flex and grid container children |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | an [integer](https://developer.mozilla.org/en-US/docs/Web/CSS/integer#interpolation "Values of the <integer> CSS data type are interpolated via integer discrete steps. The calculation is done as if they were real, floating-point numbers and the discrete value is obtained using the floor function.") |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#formal_syntax)

```
order =
  [<integer>](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#examples)

### [Ordering items in a flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#ordering_items_in_a_flex_container)

In this example, we create a classic two-sidebar layout.

#### HTML

We include a header, a footer, and a main content area. The main content includes an article and two side bars. Note their order! We'll use the CSS `order` property to change their visual order.

html

```
<header>Header</header>
<main>
  <article>Article</article>
  <nav>Nav</nav>
  <aside>Aside</aside>
</main>
<footer>Footer</footer>

```

#### CSS

We style the main area using [flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) module features; by setting [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) to `flex`, the [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/main) element becomes a flex container. By default, this creates flex items of equal vertical size. The sidebars are both given an absolute [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), while the [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/article) will consume all the [positive free space](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Controlling_ratios_of_flex_items_along_the_main_axis#positive_and_negative_free_space) with a [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow) factor set via the [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) shorthand.

We then set different `order` property values on each of the flex container's three children; this means the CSS is defining that component's visual order rather than it appearing in the order declared in the HTML.

css

```
main {
  display: flex;
  text-align: center;
}
main > article {
  flex: 1;
  order: 2;
}
main > nav {
  width: 200px;
  order: 1;
}
main > aside {
  width: 200px;
  order: 3;
}

```

#### Result

The `<article>` appears first in the source order but visually rendered in the center.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#specifications)

| Specification |
| --- |
| [CSS Display Module Level 3\<br>\# order-property](https://drafts.csswg.org/css-display/#order-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/order\#see_also)

- [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [Ordering flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Ordering_flex_items)
- [CSS grid layout and accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_and_accessibility)
- [CSS display](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display) module
- [Reading order](https://developer.mozilla.org/en-US/docs/Glossary/Reading_order)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/order/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/order/index.md?plain=1 "Folder: ⁨en-us/web/css/order⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Forder&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Forder%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Forder%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Forder%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")