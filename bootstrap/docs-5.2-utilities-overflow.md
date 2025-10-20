---
url: https://getbootstrap.com/docs/5.2/utilities/overflow
scraped_at: 2025-10-20T02:42:24.820Z
---

[Skip to main content](https://getbootstrap.com/docs/5.2/utilities/overflow/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.2/utilities/overflow/#bd-docs-nav)

Check

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.2.3/site/content/docs/5.2/utilities/overflow.md "View and edit this file on GitHub")

# Overflow

Use these shorthand utilities for quickly configuring how content overflows an element.

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

Using Sass variables, you may customize the overflow utilities by changing the `$overflows` variable in `_variables.scss`.

## Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.2/utilities/overflow/\#sass)

### Utilities API [Link to this section: Utilities API](https://getbootstrap.com/docs/5.2/utilities/overflow/\#utilities-api)

Overflow utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.2/utilities/api/#using-the-api)

```scss
    "overflow": (
      property: overflow,
      values: auto hidden visible scroll,
    ),

```