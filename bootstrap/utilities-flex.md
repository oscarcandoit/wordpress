---
url: https://getbootstrap.com/docs/5.3/utilities/flex
scraped_at: 2025-10-20T03:57:30.925Z
retry_attempt: 1
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/flex/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/flex/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/flex.mdx "View and edit this file on GitHub")

# Flex

Quickly manage the layout, alignment, and sizing of grid columns, navigation, components, and more with a full suite of responsive flexbox utilities. For more complex implementations, custom CSS may be necessary.

On this page
**On this page**

* * *

## Enable flex behaviors [Link to this section: Enable flex behaviors](https://getbootstrap.com/docs/5.3/utilities/flex/\#enable-flex-behaviors)

Apply `display` utilities to create a flexbox container and transform **direct children elements** into flex items. Flex containers and items are able to be modified further with additional flex properties.

I'm a flexbox container!

html

```html
<div class="d-flex p-2">I'm a flexbox container!</div>
```

I'm an inline flexbox container!

html

```html
<div class="d-inline-flex p-2">I'm an inline flexbox container!</div>
```

Responsive variations also exist for `.d-flex` and `.d-inline-flex`.

- `.d-flex`
- `.d-inline-flex`
- `.d-sm-flex`
- `.d-sm-inline-flex`
- `.d-md-flex`
- `.d-md-inline-flex`
- `.d-lg-flex`
- `.d-lg-inline-flex`
- `.d-xl-flex`
- `.d-xl-inline-flex`
- `.d-xxl-flex`
- `.d-xxl-inline-flex`

## Direction [Link to this section: Direction](https://getbootstrap.com/docs/5.3/utilities/flex/\#direction)

Set the direction of flex items in a flex container with direction utilities. In most cases you can omit the horizontal class here as the browser default is `row`. However, you may encounter situations where you needed to explicitly set this value (like responsive layouts).

Use `.flex-row` to set a horizontal direction (the browser default), or `.flex-row-reverse` to start the horizontal direction from the opposite side.

Flex item 1

Flex item 2

Flex item 3

Flex item 1

Flex item 2

Flex item 3

html

```html
<div class="d-flex flex-row mb-3">
  <div class="p-2">Flex item 1</div>
  <div class="p-2">Flex item 2</div>
  <div class="p-2">Flex item 3</div>
</div>
<div class="d-flex flex-row-reverse">
  <div class="p-2">Flex item 1</div>
  <div class="p-2">Flex item 2</div>
  <div class="p-2">Flex item 3</div>
</div>
```

Use `.flex-column` to set a vertical direction, or `.flex-column-reverse` to start the vertical direction from the opposite side.

Flex item 1

Flex item 2

Flex item 3

Flex item 1

Flex item 2

Flex item 3

html

```html
<div class="d-flex flex-column mb-3">
  <div class="p-2">Flex item 1</div>
  <div class="p-2">Flex item 2</div>
  <div class="p-2">Flex item 3</div>
</div>
<div class="d-flex flex-column-reverse">
  <div class="p-2">Flex item 1</div>
  <div class="p-2">Flex item 2</div>
  <div class="p-2">Flex item 3</div>
</div>
```

Responsive variations also exist for `flex-direction`.

- `.flex-row`
- `.flex-row-reverse`
- `.flex-column`
- `.flex-column-reverse`
- `.flex-sm-row`
- `.flex-sm-row-reverse`
- `.flex-sm-column`
- `.flex-sm-column-reverse`
- `.flex-md-row`
- `.flex-md-row-reverse`
- `.flex-md-column`
- `.flex-md-column-reverse`
- `.flex-lg-row`
- `.flex-lg-row-reverse`
- `.flex-lg-column`
- `.flex-lg-column-reverse`
- `.flex-xl-row`
- `.flex-xl-row-reverse`
- `.flex-xl-column`
- `.flex-xl-column-reverse`
- `.flex-xxl-row`
- `.flex-xxl-row-reverse`
- `.flex-xxl-column`
- `.flex-xxl-column-reverse`

## Justify content [Link to this section: Justify content](https://getbootstrap.com/docs/5.3/utilities/flex/\#justify-content)

Use `justify-content` utilities on flexbox containers to change the alignment of flex items on the main axis (the x-axis to start, y-axis if `flex-direction: column`). Choose from `start` (browser default), `end`, `center`, `between`, `around`, or `evenly`.

Justify

Content

Start

Justify

Content

End

Justify

Content

Center

Justify

Content

Between

Justify

Content

Around

Justify

Content

Evenly

```html
<div class="d-flex justify-content-start">...</div>
<div class="d-flex justify-content-end">...</div>
<div class="d-flex justify-content-center">...</div>
<div class="d-flex justify-content-between">...</div>
<div class="d-flex justify-content-around">...</div>
<div class="d-flex justify-content-evenly">...</div>

```

Responsive variations also exist for `justify-content`.

- `.justify-content-start`
- `.justify-content-end`
- `.justify-content-center`
- `.justify-content-between`
- `.justify-content-around`
- `.justify-content-evenly`
- `.justify-content-sm-start`
- `.justify-content-sm-end`
- `.justify-content-sm-center`
- `.justify-content-sm-between`
- `.justify-content-sm-around`
- `.justify-content-sm-evenly`
- `.justify-content-md-start`
- `.justify-content-md-end`
- `.justify-content-md-center`
- `.justify-content-md-between`
- `.justify-content-md-around`
- `.justify-content-md-evenly`
- `.justify-content-lg-start`
- `.justify-content-lg-end`
- `.justify-content-lg-center`
- `.justify-content-lg-between`
- `.justify-content-lg-around`
- `.justify-content-lg-evenly`
- `.justify-content-xl-start`
- `.justify-content-xl-end`
- `.justify-content-xl-center`
- `.justify-content-xl-between`
- `.justify-content-xl-around`
- `.justify-content-xl-evenly`
- `.justify-content-xxl-start`
- `.justify-content-xxl-end`
- `.justify-content-xxl-center`
- `.justify-content-xxl-between`
- `.justify-content-xxl-around`
- `.justify-content-xxl-evenly`

## Align items [Link to this section: Align items](https://getbootstrap.com/docs/5.3/utilities/flex/\#align-items)

Use `align-items` utilities on flexbox containers to change the alignment of flex items on the cross axis (the y-axis to start, x-axis if `flex-direction: column`). Choose from `start`, `end`, `center`, `baseline`, or `stretch` (browser default).

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-items-start">...</div>
<div class="d-flex align-items-end">...</div>
<div class="d-flex align-items-center">...</div>
<div class="d-flex align-items-baseline">...</div>
<div class="d-flex align-items-stretch">...</div>

```

Responsive variations also exist for `align-items`.

- `.align-items-start`
- `.align-items-end`
- `.align-items-center`
- `.align-items-baseline`
- `.align-items-stretch`
- `.align-items-sm-start`
- `.align-items-sm-end`
- `.align-items-sm-center`
- `.align-items-sm-baseline`
- `.align-items-sm-stretch`
- `.align-items-md-start`
- `.align-items-md-end`
- `.align-items-md-center`
- `.align-items-md-baseline`
- `.align-items-md-stretch`
- `.align-items-lg-start`
- `.align-items-lg-end`
- `.align-items-lg-center`
- `.align-items-lg-baseline`
- `.align-items-lg-stretch`
- `.align-items-xl-start`
- `.align-items-xl-end`
- `.align-items-xl-center`
- `.align-items-xl-baseline`
- `.align-items-xl-stretch`
- `.align-items-xxl-start`
- `.align-items-xxl-end`
- `.align-items-xxl-center`
- `.align-items-xxl-baseline`
- `.align-items-xxl-stretch`

## Align self [Link to this section: Align self](https://getbootstrap.com/docs/5.3/utilities/flex/\#align-self)

Use `align-self` utilities on flexbox items to individually change their alignment on the cross axis (the y-axis to start, x-axis if `flex-direction: column`). Choose from the same options as `align-items`: `start`, `end`, `center`, `baseline`, or `stretch` (browser default).

Flex item

Aligned flex item

Flex item

Flex item

Aligned flex item

Flex item

Flex item

Aligned flex item

Flex item

Flex item

Aligned flex item

Flex item

Flex item

Aligned flex item

Flex item

```html
<div class="align-self-start">Aligned flex item</div>
<div class="align-self-end">Aligned flex item</div>
<div class="align-self-center">Aligned flex item</div>
<div class="align-self-baseline">Aligned flex item</div>
<div class="align-self-stretch">Aligned flex item</div>

```

Responsive variations also exist for `align-self`.

- `.align-self-start`
- `.align-self-end`
- `.align-self-center`
- `.align-self-baseline`
- `.align-self-stretch`
- `.align-self-sm-start`
- `.align-self-sm-end`
- `.align-self-sm-center`
- `.align-self-sm-baseline`
- `.align-self-sm-stretch`
- `.align-self-md-start`
- `.align-self-md-end`
- `.align-self-md-center`
- `.align-self-md-baseline`
- `.align-self-md-stretch`
- `.align-self-lg-start`
- `.align-self-lg-end`
- `.align-self-lg-center`
- `.align-self-lg-baseline`
- `.align-self-lg-stretch`
- `.align-self-xl-start`
- `.align-self-xl-end`
- `.align-self-xl-center`
- `.align-self-xl-baseline`
- `.align-self-xl-stretch`
- `.align-self-xxl-start`
- `.align-self-xxl-end`
- `.align-self-xxl-center`
- `.align-self-xxl-baseline`
- `.align-self-xxl-stretch`

## Fill [Link to this section: Fill](https://getbootstrap.com/docs/5.3/utilities/flex/\#fill)

Use the `.flex-fill` class on a series of sibling elements to force them into widths equal to their content (or equal widths if their content does not surpass their border-boxes) while taking up all available horizontal space.

Flex item with a lot of content

Flex item

Flex item

html

```html
<div class="d-flex">
  <div class="p-2 flex-fill">Flex item with a lot of content</div>
  <div class="p-2 flex-fill">Flex item</div>
  <div class="p-2 flex-fill">Flex item</div>
</div>
```

Responsive variations also exist for `flex-fill`.

- `.flex-fill`
- `.flex-sm-fill`
- `.flex-md-fill`
- `.flex-lg-fill`
- `.flex-xl-fill`
- `.flex-xxl-fill`

## Grow and shrink [Link to this section: Grow and shrink](https://getbootstrap.com/docs/5.3/utilities/flex/\#grow-and-shrink)

Use `.flex-grow-*` utilities to toggle a flex item’s ability to grow to fill available space. In the example below, the `.flex-grow-1` elements uses all available space it can, while allowing the remaining two flex items their necessary space.

Flex item

Flex item

Third flex item

html

```html
<div class="d-flex">
  <div class="p-2 flex-grow-1">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="p-2">Third flex item</div>
</div>
```

Use `.flex-shrink-*` utilities to toggle a flex item’s ability to shrink if necessary. In the example below, the second flex item with `.flex-shrink-1` is forced to wrap its contents to a new line, “shrinking” to allow more space for the previous flex item with `.w-100`.

Flex item

Flex item

html

```html
<div class="d-flex">
  <div class="p-2 w-100">Flex item</div>
  <div class="p-2 flex-shrink-1">Flex item</div>
</div>
```

Responsive variations also exist for `flex-grow` and `flex-shrink`.

- `.flex-{grow|shrink}-0`
- `.flex-{grow|shrink}-1`
- `.flex-sm-{grow|shrink}-0`
- `.flex-sm-{grow|shrink}-1`
- `.flex-md-{grow|shrink}-0`
- `.flex-md-{grow|shrink}-1`
- `.flex-lg-{grow|shrink}-0`
- `.flex-lg-{grow|shrink}-1`
- `.flex-xl-{grow|shrink}-0`
- `.flex-xl-{grow|shrink}-1`
- `.flex-xxl-{grow|shrink}-0`
- `.flex-xxl-{grow|shrink}-1`

## Auto margins [Link to this section: Auto margins](https://getbootstrap.com/docs/5.3/utilities/flex/\#auto-margins)

Flexbox can do some pretty awesome things when you mix flex alignments with auto margins. Shown below are three examples of controlling flex items via auto margins: default (no auto margin), pushing two items to the right ( `.me-auto`), and pushing two items to the left ( `.ms-auto`).

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

html

```html
<div class="d-flex mb-3">
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
</div>

<div class="d-flex mb-3">
  <div class="me-auto p-2">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
</div>

<div class="d-flex mb-3">
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="ms-auto p-2">Flex item</div>
</div>
```

### With align-items [Link to this section: With align-items](https://getbootstrap.com/docs/5.3/utilities/flex/\#with-align-items)

Vertically move one flex item to the top or bottom of a container by mixing `align-items`, `flex-direction: column`, and `margin-top: auto` or `margin-bottom: auto`.

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

html

```html
<div class="d-flex align-items-start flex-column mb-3" style="height: 200px;">
  <div class="mb-auto p-2">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
</div>

<div class="d-flex align-items-end flex-column mb-3" style="height: 200px;">
  <div class="p-2">Flex item</div>
  <div class="p-2">Flex item</div>
  <div class="mt-auto p-2">Flex item</div>
</div>
```

## Wrap [Link to this section: Wrap](https://getbootstrap.com/docs/5.3/utilities/flex/\#wrap)

Change how flex items wrap in a flex container. Choose from no wrapping at all (the browser default) with `.flex-nowrap`, wrapping with `.flex-wrap`, or reverse wrapping with `.flex-wrap-reverse`.

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex flex-nowrap">
  ...
</div>

```

Flex item 1

Flex item 2

Flex item 3

Flex item 4

Flex item 5

Flex item 6

Flex item 7

Flex item 8

Flex item 9

Flex item 10

Flex item 11

Flex item 12

Flex item 13

Flex item 14

```html
<div class="d-flex flex-wrap">
  ...
</div>

```

Flex item 1

Flex item 2

Flex item 3

Flex item 4

Flex item 5

Flex item 6

Flex item 7

Flex item 8

Flex item 9

Flex item 10

Flex item 11

Flex item 12

Flex item 13

Flex item 14

```html
<div class="d-flex flex-wrap-reverse">
  ...
</div>

```

Responsive variations also exist for `flex-wrap`.

- `.flex-nowrap`
- `.flex-wrap`
- `.flex-wrap-reverse`
- `.flex-sm-nowrap`
- `.flex-sm-wrap`
- `.flex-sm-wrap-reverse`
- `.flex-md-nowrap`
- `.flex-md-wrap`
- `.flex-md-wrap-reverse`
- `.flex-lg-nowrap`
- `.flex-lg-wrap`
- `.flex-lg-wrap-reverse`
- `.flex-xl-nowrap`
- `.flex-xl-wrap`
- `.flex-xl-wrap-reverse`
- `.flex-xxl-nowrap`
- `.flex-xxl-wrap`
- `.flex-xxl-wrap-reverse`

## Order [Link to this section: Order](https://getbootstrap.com/docs/5.3/utilities/flex/\#order)

Change the _visual_ order of specific flex items with a handful of `order` utilities. We only provide options for making an item first or last, as well as a reset to use the DOM order. As `order` takes any integer value from 0 to 5, add custom CSS for any additional values needed.

First flex item

Second flex item

Third flex item

html

```html
<div class="d-flex flex-nowrap">
  <div class="order-3 p-2">First flex item</div>
  <div class="order-2 p-2">Second flex item</div>
  <div class="order-1 p-2">Third flex item</div>
</div>
```

Responsive variations also exist for `order`.

- `.order-0`
- `.order-1`
- `.order-2`
- `.order-3`
- `.order-4`
- `.order-5`
- `.order-sm-0`
- `.order-sm-1`
- `.order-sm-2`
- `.order-sm-3`
- `.order-sm-4`
- `.order-sm-5`
- `.order-md-0`
- `.order-md-1`
- `.order-md-2`
- `.order-md-3`
- `.order-md-4`
- `.order-md-5`
- `.order-lg-0`
- `.order-lg-1`
- `.order-lg-2`
- `.order-lg-3`
- `.order-lg-4`
- `.order-lg-5`
- `.order-xl-0`
- `.order-xl-1`
- `.order-xl-2`
- `.order-xl-3`
- `.order-xl-4`
- `.order-xl-5`
- `.order-xxl-0`
- `.order-xxl-1`
- `.order-xxl-2`
- `.order-xxl-3`
- `.order-xxl-4`
- `.order-xxl-5`

Additionally there are also responsive `.order-first` and `.order-last` classes that change the `order` of an element by applying `order: -1` and `order: 6`, respectively.

- `.order-first`
- `.order-last`
- `.order-sm-first`
- `.order-sm-last`
- `.order-md-first`
- `.order-md-last`
- `.order-lg-first`
- `.order-lg-last`
- `.order-xl-first`
- `.order-xl-last`
- `.order-xxl-first`
- `.order-xxl-last`

## Align content [Link to this section: Align content](https://getbootstrap.com/docs/5.3/utilities/flex/\#align-content)

Use `align-content` utilities on flexbox containers to align flex items _together_ on the cross axis. Choose from `start` (browser default), `end`, `center`, `between`, `around`, or `stretch`. To demonstrate these utilities, we’ve enforced `flex-wrap: wrap` and increased the number of flex items.

**Heads up!** This property has no effect on single rows of flex items.

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-start flex-wrap">
  ...
</div>

```

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-end flex-wrap">...</div>

```

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-center flex-wrap">...</div>

```

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-between flex-wrap">...</div>

```

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-around flex-wrap">...</div>

```

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

Flex item

```html
<div class="d-flex align-content-stretch flex-wrap">...</div>

```

Responsive variations also exist for `align-content`.

- `.align-content-start`
- `.align-content-end`
- `.align-content-center`
- `.align-content-between`
- `.align-content-around`
- `.align-content-stretch`
- `.align-content-sm-start`
- `.align-content-sm-end`
- `.align-content-sm-center`
- `.align-content-sm-between`
- `.align-content-sm-around`
- `.align-content-sm-stretch`
- `.align-content-md-start`
- `.align-content-md-end`
- `.align-content-md-center`
- `.align-content-md-between`
- `.align-content-md-around`
- `.align-content-md-stretch`
- `.align-content-lg-start`
- `.align-content-lg-end`
- `.align-content-lg-center`
- `.align-content-lg-between`
- `.align-content-lg-around`
- `.align-content-lg-stretch`
- `.align-content-xl-start`
- `.align-content-xl-end`
- `.align-content-xl-center`
- `.align-content-xl-between`
- `.align-content-xl-around`
- `.align-content-xl-stretch`
- `.align-content-xxl-start`
- `.align-content-xxl-end`
- `.align-content-xxl-center`
- `.align-content-xxl-between`
- `.align-content-xxl-around`
- `.align-content-xxl-stretch`

## Media object [Link to this section: Media object](https://getbootstrap.com/docs/5.3/utilities/flex/\#media-object)

Looking to replicate the [media object component](https://getbootstrap.com/docs/4.6/components/media-object/) from Bootstrap 4? Recreate it in no time with a few flex utilities that allow even more flexibility and customization than before.

PlaceholderImage

This is some content from a media component. You can replace this with any content and adjust it as needed.


html

```html
<div class="d-flex">
  <div class="flex-shrink-0">
    <img src="..." alt="...">
  </div>
  <div class="flex-grow-1 ms-3">
    This is some content from a media component. You can replace this with any content and adjust it as needed.
  </div>
</div>
```

And say you want to vertically center the content next to the image:

PlaceholderImage

This is some content from a media component. You can replace this with any content and adjust it as needed.


html

```html
<div class="d-flex align-items-center">
  <div class="flex-shrink-0">
    <img src="..." alt="...">
  </div>
  <div class="flex-grow-1 ms-3">
    This is some content from a media component. You can replace this with any content and adjust it as needed.
  </div>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/flex/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/flex/\#sass-utilities-api)

Flexbox utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"flex": (
  responsive: true,
  property: flex,
  values: (fill: 1 1 auto)
),
"flex-direction": (
  responsive: true,
  property: flex-direction,
  class: flex,
  values: row column row-reverse column-reverse
),
"flex-grow": (
  responsive: true,
  property: flex-grow,
  class: flex,
  values: (
    grow-0: 0,
    grow-1: 1,
  )
),
"flex-shrink": (
  responsive: true,
  property: flex-shrink,
  class: flex,
  values: (
    shrink-0: 0,
    shrink-1: 1,
  )
),
"flex-wrap": (
  responsive: true,
  property: flex-wrap,
  class: flex,
  values: wrap nowrap wrap-reverse
),
"justify-content": (
  responsive: true,
  property: justify-content,
  values: (
    start: flex-start,
    end: flex-end,
    center: center,
    between: space-between,
    around: space-around,
    evenly: space-evenly,
  )
),
"align-items": (
  responsive: true,
  property: align-items,
  values: (
    start: flex-start,
    end: flex-end,
    center: center,
    baseline: baseline,
    stretch: stretch,
  )
),
"align-content": (
  responsive: true,
  property: align-content,
  values: (
    start: flex-start,
    end: flex-end,
    center: center,
    between: space-between,
    around: space-around,
    stretch: stretch,
  )
),
"align-self": (
  responsive: true,
  property: align-self,
  values: (
    auto: auto,
    start: flex-start,
    end: flex-end,
    center: center,
    baseline: baseline,
    stretch: stretch,
  )
),
"order": (
  responsive: true,
  property: order,
  values: (
    first: -1,
    0: 0,
    1: 1,
    2: 2,
    3: 3,
    4: 4,
    5: 5,
    last: 6,
  ),
),

```