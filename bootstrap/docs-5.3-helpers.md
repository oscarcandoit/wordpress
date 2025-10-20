---
url: https://getbootstrap.com/docs/5.3/helpers
scraped_at: 2025-10-20T02:34:05.044Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/clearfix.mdx "View and edit this file on GitHub")

# Clearfix

Quickly and easily clear floated content within a container by adding a clearfix utility.

Easily clear `float` s by adding `.clearfix` **to the parent element**. Can also be used as a mixin.

Use in HTML:

```html
<div class="clearfix">...</div>

```

The mixin source code:

[scss/mixins/\_clearfix.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/mixins/_clearfix.scss)

```scss
@mixin clearfix() {
  &::after {
    display: block;
    clear: both;
    content: "";
  }
}

```

Use the mixin in SCSS:

```scss
.element {
  @include clearfix;
}

```

The following example shows how the clearfix can be used. Without the clearfix the wrapping div would not span around the buttons which would cause a broken layout.

Example Button floated leftExample Button floated right

html

```html
<div class="bg-info clearfix">
  <button type="button" class="btn btn-secondary float-start">Example Button floated left</button>
  <button type="button" class="btn btn-secondary float-end">Example Button floated right</button>
</div>
```