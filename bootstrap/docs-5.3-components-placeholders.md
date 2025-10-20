---
url: https://getbootstrap.com/docs/5.3/components/placeholders
scraped_at: 2025-10-20T02:27:53.179Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/placeholders/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/placeholders/#bd-docs-nav)

Added in v5.1 [View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/placeholders.mdx "View and edit this file on GitHub")

# Placeholders

Use loading placeholders (skeleton loaders) for your components or pages to indicate something may still be loading.

On this page
**On this page**

* * *

## About [Link to this section: About](https://getbootstrap.com/docs/5.3/components/placeholders/\#about)

Placeholders can be used to enhance the experience of your application. They’re built only with HTML and CSS, meaning you don’t need any JavaScript to create them. You will, however, need some custom JavaScript to toggle their visibility. Their appearance, color, and sizing can be easily customized with our utility classes.

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/components/placeholders/\#example)

In the example below, we take a typical card component and recreate it with placeholders applied to create a “loading card”. Size and proportions are the same between the two.

Placeholder

##### Card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/placeholders/#)

Placeholder

```html
<div class="card">
  <img src="..." class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card" aria-hidden="true">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title placeholder-glow">
      <span class="placeholder col-6"></span>
    </h5>
    <p class="card-text placeholder-glow">
      <span class="placeholder col-7"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-6"></span>
      <span class="placeholder col-8"></span>
    </p>
    <a class="btn btn-primary disabled placeholder col-6" aria-disabled="true"></a>
  </div>
</div>

```

## How it works [Link to this section: How it works](https://getbootstrap.com/docs/5.3/components/placeholders/\#how-it-works)

Create placeholders with the `.placeholder` class and a grid column class (e.g., `.col-6`) to set the `width`. They can replace the text inside an element or be added as a modifier class to an existing component.

We apply additional styling to `.btn` s via `::before` to ensure the `height` is respected. You may extend this pattern for other situations as needed, or add a `&nbsp;` within the element to reflect the height when actual text is rendered in its place.

html

```html
<p aria-hidden="true">
  <span class="placeholder col-6"></span>
</p>

<a class="btn btn-primary disabled placeholder col-4" aria-disabled="true"></a>
```

The use of `aria-hidden="true"` only indicates that the element should be hidden to screen readers. The _loading_ behavior of the placeholder depends on how authors will actually use the placeholder styles, how they plan to update things, etc. Some JavaScript code may be needed to _swap_ the state of the placeholder and inform AT users of the update.

### Width [Link to this section: Width](https://getbootstrap.com/docs/5.3/components/placeholders/\#width)

You can change the `width` through grid column classes, width utilities, or inline styles.

html

```html
<span class="placeholder col-6"></span>
<span class="placeholder w-75"></span>
<span class="placeholder" style="width: 25%;"></span>
```

### Color [Link to this section: Color](https://getbootstrap.com/docs/5.3/components/placeholders/\#color)

By default, the `placeholder` uses `currentColor`. This can be overridden with a custom color or utility class.

html

```html
<span class="placeholder col-12"></span>

<span class="placeholder col-12 bg-primary"></span>
<span class="placeholder col-12 bg-secondary"></span>
<span class="placeholder col-12 bg-success"></span>
<span class="placeholder col-12 bg-danger"></span>
<span class="placeholder col-12 bg-warning"></span>
<span class="placeholder col-12 bg-info"></span>
<span class="placeholder col-12 bg-light"></span>
<span class="placeholder col-12 bg-dark"></span>
```

### Sizing [Link to this section: Sizing](https://getbootstrap.com/docs/5.3/components/placeholders/\#sizing)

The size of `.placeholder` s are based on the typographic style of the parent element. Customize them with sizing modifiers: `.placeholder-lg`, `.placeholder-sm`, or `.placeholder-xs`.

html

```html
<span class="placeholder col-12 placeholder-lg"></span>
<span class="placeholder col-12"></span>
<span class="placeholder col-12 placeholder-sm"></span>
<span class="placeholder col-12 placeholder-xs"></span>
```

### Animation [Link to this section: Animation](https://getbootstrap.com/docs/5.3/components/placeholders/\#animation)

Animate placeholders with `.placeholder-glow` or `.placeholder-wave` to better convey the perception of something being _actively_ loaded.

html

```html
<p class="placeholder-glow">
  <span class="placeholder col-12"></span>
</p>

<p class="placeholder-wave">
  <span class="placeholder col-12"></span>
</p>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/placeholders/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/placeholders/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$placeholder-opacity-max:           .5;
$placeholder-opacity-min:           .2;

```