---
url: https://getbootstrap.com/docs/5.1/content/images
scraped_at: 2025-10-20T02:41:16.429Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/content/images/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/content/images/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/content/images.md "View and edit this file on GitHub")

# Images

Documentation and examples for opting images into responsive behavior (so they never become wider than their parent) and add lightweight styles to them—all via classes.

**On this page**

## Responsive images [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#responsive-images)

Images in Bootstrap are made responsive with `.img-fluid`. This applies `max-width: 100%;` and `height: auto;` to the image so that it scales with the parent width.

PlaceholderResponsive image

Copy

```html
<img src="..." class="img-fluid" alt="...">
```

## Image thumbnails [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#image-thumbnails)

In addition to our [border-radius utilities](https://getbootstrap.com/docs/5.1/utilities/borders/), you can use `.img-thumbnail` to give an image a rounded 1px border appearance.

A generic square placeholder image with a white border around it, making it resemble a photograph taken with an old instant camera200x200

Copy

```html
<img src="..." class="img-thumbnail" alt="...">
```

## Aligning images [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#aligning-images)

Align images with the [helper float classes](https://getbootstrap.com/docs/5.1/utilities/float/) or [text alignment classes](https://getbootstrap.com/docs/5.1/utilities/text/#text-alignment). `block`-level images can be centered using [the `.mx-auto` margin utility class](https://getbootstrap.com/docs/5.1/utilities/spacing/#horizontal-centering).

Placeholder200x200Placeholder200x200

Copy

```html
<img src="..." class="rounded float-start" alt="...">
<img src="..." class="rounded float-end" alt="...">
```

Placeholder200x200

Copy

```html
<img src="..." class="rounded mx-auto d-block" alt="...">
```

Placeholder200x200

Copy

```html
<div class="text-center">
  <img src="..." class="rounded" alt="...">
</div>
```

## Picture [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#picture)

If you are using the `<picture>` element to specify multiple `<source>` elements for a specific `<img>`, make sure to add the `.img-*` classes to the `<img>` and not to the `<picture>` tag.

Copy

```html
<picture>
  <source srcset="..." type="image/svg+xml">
  <img src="..." class="img-fluid img-thumbnail" alt="...">
</picture>

```

## Sass [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#sass)

### Variables [Anchor](https://getbootstrap.com/docs/5.1/content/images/\#variables)

Variables are available for image thumbnails.

Copy

```scss
$thumbnail-padding:                 .25rem;
$thumbnail-bg:                      $body-bg;
$thumbnail-border-width:            $border-width;
$thumbnail-border-color:            $gray-300;
$thumbnail-border-radius:           $border-radius;
$thumbnail-box-shadow:              $box-shadow-sm;

```