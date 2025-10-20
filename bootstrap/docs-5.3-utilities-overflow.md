---
url: https://getbootstrap.com/docs/5.3/utilities/overflow
scraped_at: 2025-10-20T02:36:34.415Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/overflow/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/overflow/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/overflow.mdx "View and edit this file on GitHub")

# Overflow

Use these shorthand utilities for quickly configuring how content overflows an element.

On this page
**On this page**

* * *

## Overflow [Link to this section: Overflow](https://getbootstrap.com/docs/5.3/utilities/overflow/\#overflow)

Adjust the `overflow` property on the fly with four default values and classes. These classes are not responsive by default.

This is an example of using `.overflow-auto` on an element with set width and height dimensions. By design, this content will vertically scroll.

This is an example of using `.overflow-hidden` on an element with set width and height dimensions.

This is an example of using `.overflow-visible` on an element with set width and height dimensions.

This is an example of using `.overflow-scroll` on an element with set width and height dimensions.

```html
<div class="overflow-auto">...</div>
<div class="overflow-hidden">...</div>
<div class="overflow-visible">...</div>
<div class="overflow-scroll">...</div>

```

### `overflow-x` [Link to this section: undefined](https://getbootstrap.com/docs/5.3/utilities/overflow/\#overflow-x)

Adjust the `overflow-x` property to affect the overflow of content horizontally.

`.overflow-x-auto` example on an element

with set width and height dimensions.

`.overflow-x-hidden` example

on an element with set width and height dimensions.

`.overflow-x-visible` example

on an element with set width and height dimensions.

`.overflow-x-scroll` example on an element

with set width and height dimensions.

```html
<div class="overflow-x-auto">...</div>
<div class="overflow-x-hidden">...</div>
<div class="overflow-x-visible">...</div>
<div class="overflow-x-scroll">...</div>

```

### `overflow-y` [Link to this section: undefined](https://getbootstrap.com/docs/5.3/utilities/overflow/\#overflow-y)

Adjust the `overflow-y` property to affect the overflow of content vertically.

`.overflow-y-auto` example on an element with set width and height dimensions.

`.overflow-y-hidden` example on an element with set width and height dimensions.

`.overflow-y-visible` example on an element with set width and height dimensions.

`.overflow-y-scroll` example on an element with set width and height dimensions.

```html
<div class="overflow-y-auto">...</div>
<div class="overflow-y-hidden">...</div>
<div class="overflow-y-visible">...</div>
<div class="overflow-y-scroll">...</div>

```

Using Sass variables, you may customize the overflow utilities by changing the `$overflows` variable in `_variables.scss`.

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/overflow/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/overflow/\#sass-utilities-api)

Overflow utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"overflow": (
  property: overflow,
  values: auto hidden visible scroll,
),
"overflow-x": (
  property: overflow-x,
  values: auto hidden visible scroll,
),
"overflow-y": (
  property: overflow-y,
  values: auto hidden visible scroll,
),

```