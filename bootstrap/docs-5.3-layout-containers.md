---
url: https://getbootstrap.com/docs/5.3/layout/containers
scraped_at: 2025-10-20T02:35:34.027Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/layout/containers/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/layout/containers/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/layout/containers.mdx "View and edit this file on GitHub")

# Containers

Containers are a fundamental building block of Bootstrap that contain, pad, and align your content within a given device or viewport.

On this page
**On this page**

* * *

## How they work [Link to this section: How they work](https://getbootstrap.com/docs/5.3/layout/containers/\#how-they-work)

Containers are the most basic layout element in Bootstrap and are **required when using our default grid system**. Containers are used to contain, pad, and (sometimes) center the content within them. While containers _can_ be nested, most layouts do not require a nested container.

Bootstrap comes with three different containers:

- `.container`, which sets a `max-width` at each responsive breakpoint
- `.container-{breakpoint}`, which is `width: 100%` until the specified breakpoint
- `.container-fluid`, which is `width: 100%` at all breakpoints

The table below illustrates how each container’s `max-width` compares to the original `.container` and `.container-fluid` across each breakpoint.

See them in action and compare them in our [Grid example](https://getbootstrap.com/docs/5.3/examples/grid/#containers).

|  | Extra small<br><576px | Small<br>≥576px | Medium<br>≥768px | Large<br>≥992px | X-Large<br>≥1200px | XX-Large<br>≥1400px |
| --- | --- | --- | --- | --- | --- | --- |
| `.container` | 100% | 540px | 720px | 960px | 1140px | 1320px |
| `.container-sm` | 100% | 540px | 720px | 960px | 1140px | 1320px |
| `.container-md` | 100% | 100% | 720px | 960px | 1140px | 1320px |
| `.container-lg` | 100% | 100% | 100% | 960px | 1140px | 1320px |
| `.container-xl` | 100% | 100% | 100% | 100% | 1140px | 1320px |
| `.container-xxl` | 100% | 100% | 100% | 100% | 100% | 1320px |
| `.container-fluid` | 100% | 100% | 100% | 100% | 100% | 100% |

## Default container [Link to this section: Default container](https://getbootstrap.com/docs/5.3/layout/containers/\#default-container)

Our default `.container` class is a responsive, fixed-width container, meaning its `max-width` changes at each breakpoint.

```html
<div class="container">
  <!-- Content here -->
</div>

```

## Responsive containers [Link to this section: Responsive containers](https://getbootstrap.com/docs/5.3/layout/containers/\#responsive-containers)

Responsive containers allow you to specify a class that is 100% wide until the specified breakpoint is reached, after which we apply `max-width` s for each of the higher breakpoints. For example, `.container-sm` is 100% wide to start until the `sm` breakpoint is reached, where it will scale up with `md`, `lg`, `xl`, and `xxl`.

```html
<div class="container-sm">100% wide until small breakpoint</div>
<div class="container-md">100% wide until medium breakpoint</div>
<div class="container-lg">100% wide until large breakpoint</div>
<div class="container-xl">100% wide until extra large breakpoint</div>
<div class="container-xxl">100% wide until extra extra large breakpoint</div>

```

## Fluid containers [Link to this section: Fluid containers](https://getbootstrap.com/docs/5.3/layout/containers/\#fluid-containers)

Use `.container-fluid` for a full width container, spanning the entire width of the viewport.

```html
<div class="container-fluid">
  ...
</div>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/layout/containers/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/layout/containers/\#sass-variables)

As shown above, Bootstrap generates a series of predefined container classes to help you build the layouts you desire. You may customize these predefined container classes by modifying the Sass map (found in `_variables.scss`) that powers them:

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px,
  xxl: 1320px
);

```

For more information and examples on how to modify our Sass maps and variables, please refer to [the Sass section of the Grid documentation](https://getbootstrap.com/docs/5.3/layout/grid#css).

### Sass mixins [Link to this section: Sass mixins](https://getbootstrap.com/docs/5.3/layout/containers/\#sass-mixins)

In addition to customizing the Sass, you can also create your own containers with our Sass mixin.

```scss
// Source mixin
@mixin make-container($padding-x: $container-padding-x) {
  width: 100%;
  padding-right: $padding-x;
  padding-left: $padding-x;
  margin-right: auto;
  margin-left: auto;
}

// Usage
.custom-container {
  @include make-container();
}

```