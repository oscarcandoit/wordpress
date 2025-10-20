---
url: https://getbootstrap.com/docs/5.3/utilities/shadows
scraped_at: 2025-10-20T02:36:40.017Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/shadows/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/shadows/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/shadows.mdx "View and edit this file on GitHub")

# Shadows

Add or remove shadows to elements with box-shadow utilities.

On this page
**On this page**

* * *

## Examples [Link to this section: Examples](https://getbootstrap.com/docs/5.3/utilities/shadows/\#examples)

While shadows on components are disabled by default in Bootstrap and can be enabled via `$enable-shadows`, you can also quickly add or remove a shadow with our `box-shadow` utility classes. Includes support for `.shadow-none` and three default sizes (which have associated variables to match).

No shadow

Small shadow

Regular shadow

Larger shadow

html

```html
<div class="shadow-none p-3 mb-5 bg-body-tertiary rounded">No shadow</div>
<div class="shadow-sm p-3 mb-5 bg-body-tertiary rounded">Small shadow</div>
<div class="shadow p-3 mb-5 bg-body-tertiary rounded">Regular shadow</div>
<div class="shadow-lg p-3 mb-5 bg-body-tertiary rounded">Larger shadow</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/shadows/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/utilities/shadows/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$box-shadow:                  0 .5rem 1rem rgba($black, .15);
$box-shadow-sm:               0 .125rem .25rem rgba($black, .075);
$box-shadow-lg:               0 1rem 3rem rgba($black, .175);
$box-shadow-inset:            inset 0 1px 2px rgba($black, .075);

```

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/shadows/\#sass-utilities-api)

Shadow utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"shadow": (
  property: box-shadow,
  class: shadow,
  values: (
    null: var(--#{$prefix}box-shadow),
    sm: var(--#{$prefix}box-shadow-sm),
    lg: var(--#{$prefix}box-shadow-lg),
    none: none,
  )
),

```