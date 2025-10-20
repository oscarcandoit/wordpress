---
url: https://getbootstrap.com/docs/5.3/content/figures
scraped_at: 2025-10-20T02:28:21.961Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/content/figures/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/content/figures/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/content/figures.mdx "View and edit this file on GitHub")

# Figures

Documentation and examples for displaying related images and text with the figure component in Bootstrap.

On this page
**On this page**

* * *

Anytime you need to display a piece of content—like an image with an optional caption, consider using a `<figure>`.

Use the included `.figure`, `.figure-img` and `.figure-caption` classes to provide some baseline styles for the HTML5 `<figure>` and `<figcaption>` elements. Images in figures have no explicit size, so be sure to add the `.img-fluid` class to your `<img>` to make it responsive.

Placeholder400x300A caption for the above image.

html

```html
<figure class="figure">
  <img src="..." class="figure-img img-fluid rounded" alt="...">
  <figcaption class="figure-caption">A caption for the above image.</figcaption>
</figure>
```

Aligning the figure’s caption is easy with our [text utilities](https://getbootstrap.com/docs/5.3/utilities/text#text-alignment).

Placeholder400x300A caption for the above image.

html

```html
<figure class="figure">
  <img src="..." class="figure-img img-fluid rounded" alt="...">
  <figcaption class="figure-caption text-end">A caption for the above image.</figcaption>
</figure>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/content/figures/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/content/figures/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$figure-caption-font-size:          $small-font-size;
$figure-caption-color:              var(--#{$prefix}secondary-color);

```