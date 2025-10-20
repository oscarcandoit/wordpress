---
url: https://getbootstrap.com/docs/5.3/content/images
scraped_at: 2025-10-20T02:28:25.149Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/content/images/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/content/images/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/content/images.mdx "View and edit this file on GitHub")

# Images

Documentation and examples for opting images into responsive behavior (so they never become wider than their parent) and add lightweight styles to them—all via classes.

On this page
**On this page**

* * *

## Responsive images [Link to this section: Responsive images](https://getbootstrap.com/docs/5.3/content/images/\#responsive-images)

Images in Bootstrap are made responsive with `.img-fluid`. This applies `max-width: 100%;` and `height: auto;` to the image so that it scales with the parent width.

PlaceholderResponsive image

html

```html
<img src="..." class="img-fluid" alt="...">
```

## Image thumbnails [Link to this section: Image thumbnails](https://getbootstrap.com/docs/5.3/content/images/\#image-thumbnails)

In addition to our [border-radius utilities](https://getbootstrap.com/docs/5.3/utilities/borders), you can use `.img-thumbnail` to give an image a rounded 1px border appearance.

A generic square placeholder image with a white border around it, making it resemble a photograph taken with an old instant camera200x200

html

```html
<img src="..." class="img-thumbnail" alt="...">
```

## Aligning images [Link to this section: Aligning images](https://getbootstrap.com/docs/5.3/content/images/\#aligning-images)

Align images with the [helper float classes](https://getbootstrap.com/docs/5.3/utilities/float) or [text alignment classes](https://getbootstrap.com/docs/5.3/utilities/text#text-alignment). `block`-level images can be centered using [the `.mx-auto` margin utility class](https://getbootstrap.com/docs/5.3/utilities/spacing#horizontal-centering).

Placeholder200x200Placeholder200x200

html

```html
<img src="..." class="rounded float-start" alt="...">
<img src="..." class="rounded float-end" alt="...">
```

Placeholder200x200

html

```html
<img src="..." class="rounded mx-auto d-block" alt="...">
```

Placeholder200x200

html

```html
<div class="text-center">
  <img src="..." class="rounded" alt="...">
</div>
```

## Picture [Link to this section: Picture](https://getbootstrap.com/docs/5.3/content/images/\#picture)

If you are using the `<picture>` element to specify multiple `<source>` elements for a specific `<img>`, make sure to add the `.img-*` classes to the `<img>` and not to the `<picture>` tag.

```html
<picture>
  <source srcset="..." type="image/svg+xml">
  <img src="..." class="img-fluid img-thumbnail" alt="...">
</picture>

```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/content/images/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/content/images/\#sass-variables)

Variables are available for image thumbnails.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$thumbnail-padding:                 .25rem;
$thumbnail-bg:                      var(--#{$prefix}body-bg);
$thumbnail-border-width:            var(--#{$prefix}border-width);
$thumbnail-border-color:            var(--#{$prefix}border-color);
$thumbnail-border-radius:           var(--#{$prefix}border-radius);
$thumbnail-box-shadow:              var(--#{$prefix}box-shadow-sm);

```