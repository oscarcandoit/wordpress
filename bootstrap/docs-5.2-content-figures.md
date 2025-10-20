---
url: https://getbootstrap.com/docs/5.2/content/figures
scraped_at: 2025-10-20T02:41:55.854Z
---

[Skip to main content](https://getbootstrap.com/docs/5.2/content/figures/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.2/content/figures/#bd-docs-nav)

Check

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.2.3/site/content/docs/5.2/content/figures.md "View and edit this file on GitHub")

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

Aligning the figure’s caption is easy with our [text utilities](https://getbootstrap.com/docs/5.2/utilities/text/#text-alignment).

Placeholder400x300A caption for the above image.

html

```html
<figure class="figure">
  <img src="..." class="figure-img img-fluid rounded" alt="...">
  <figcaption class="figure-caption text-end">A caption for the above image.</figcaption>
</figure>
```

## Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.2/content/figures/\#sass)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.2/content/figures/\#variables)

```scss
$figure-caption-font-size:          $small-font-size;
$figure-caption-color:              $gray-600;

```