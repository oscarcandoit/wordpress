---
url: https://getbootstrap.com/docs/5.3/helpers/focus-ring
scraped_at: 2025-10-20T02:34:27.942Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#bd-docs-nav)

Added in v5.3 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/focus-ring.mdx "View and edit this file on GitHub")

# Focus ring

Utility classes that allows you to add and modify custom focus ring styles to elements and components.

On this page
**On this page**

* * *

The `.focus-ring` helper removes the default `outline` on `:focus`, replacing it with a `box-shadow` that can be more broadly customized. The new shadow is made up of a series of CSS variables, inherited from the `:root` level, that can be modified for any element or component.

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/helpers/focus-ring/\#example)

Click directly on the link below to see the focus ring in action, or into the example below and then press `Tab`.

[Custom focus ring](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

html

```html
<a href="#" class="d-inline-flex focus-ring py-1 px-2 text-decoration-none border rounded-2">
  Custom focus ring
</a>
```

## Customize [Link to this section: Customize](https://getbootstrap.com/docs/5.3/helpers/focus-ring/\#customize)

Modify the styling of a focus ring with our CSS variables, Sass variables, utilities, or custom styles.

### CSS variables [Link to this section: CSS variables](https://getbootstrap.com/docs/5.3/helpers/focus-ring/\#css-variables)

Modify the `--bs-focus-ring-*` CSS variables as needed to change the default appearance.

[Green focus ring](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

html

```html
<a href="#" class="d-inline-flex focus-ring py-1 px-2 text-decoration-none border rounded-2" style="--bs-focus-ring-color: rgba(var(--bs-success-rgb), .25)">
  Green focus ring
</a>
```

`.focus-ring` sets styles via global CSS variables that can be overridden on any parent element, as shown above. These variables are generated from their Sass variable counterparts.

[scss/\_root.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_root.scss)

```scss
--#{$prefix}focus-ring-width: #{$focus-ring-width};
--#{$prefix}focus-ring-opacity: #{$focus-ring-opacity};
--#{$prefix}focus-ring-color: #{$focus-ring-color};

```

By default, there is no `--bs-focus-ring-x`, `--bs-focus-ring-y`, or `--bs-focus-ring-blur`, but we provide CSS variables with fallbacks to initial `0` values. Modify them to change the default appearance.

[Blurry offset focus ring](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

html

```html
<a href="#" class="d-inline-flex focus-ring py-1 px-2 text-decoration-none border rounded-2" style="--bs-focus-ring-x: 10px; --bs-focus-ring-y: 10px; --bs-focus-ring-blur: 4px">
  Blurry offset focus ring
</a>
```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/helpers/focus-ring/\#sass-variables)

Customize the focus ring Sass variables to modify all usage of the focus ring styles across your Bootstrap-powered project.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$focus-ring-width:      .25rem;
$focus-ring-opacity:    .25;
$focus-ring-color:      rgba($primary, $focus-ring-opacity);
$focus-ring-blur:       0;
$focus-ring-box-shadow: 0 0 $focus-ring-blur $focus-ring-width $focus-ring-color;

```

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/helpers/focus-ring/\#sass-utilities-api)

In addition to `.focus-ring`, we have several `.focus-ring-*` utilities to modify the helper class defaults. Modify the color with any of our [theme colors](https://getbootstrap.com/docs/5.3/customize/color#theme-colors). Note that the light and dark variants may not be visible on all background colors given current color mode support.

[Primary focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Secondary focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Success focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Danger focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Warning focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Info focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Light focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

[Dark focus](https://getbootstrap.com/docs/5.3/helpers/focus-ring/#)

html

```html
<p><a href="#" class="d-inline-flex focus-ring focus-ring-primary py-1 px-2 text-decoration-none border rounded-2">Primary focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-secondary py-1 px-2 text-decoration-none border rounded-2">Secondary focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-success py-1 px-2 text-decoration-none border rounded-2">Success focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-danger py-1 px-2 text-decoration-none border rounded-2">Danger focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-warning py-1 px-2 text-decoration-none border rounded-2">Warning focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-info py-1 px-2 text-decoration-none border rounded-2">Info focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-light py-1 px-2 text-decoration-none border rounded-2">Light focus</a></p>
<p><a href="#" class="d-inline-flex focus-ring focus-ring-dark py-1 px-2 text-decoration-none border rounded-2">Dark focus</a></p>
```

Focus ring utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"focus-ring": (
  css-var: true,
  css-variable-name: focus-ring-color,
  class: focus-ring,
  values: map-loop($theme-colors-rgb, rgba-css-var, "$key", "focus-ring")
),

```