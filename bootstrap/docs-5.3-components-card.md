---
url: https://getbootstrap.com/docs/5.3/components/card
scraped_at: 2025-10-20T02:27:14.750Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/card/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/card/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/card.mdx "View and edit this file on GitHub")

# Cards

Bootstrap’s cards provide a flexible and extensible content container with multiple variants and options.

On this page
**On this page**

* * *

## About [Link to this section: About](https://getbootstrap.com/docs/5.3/components/card/\#about)

A **card** is a flexible and extensible content container. It includes options for headers and footers, a wide variety of content, contextual background colors, and powerful display options. If you’re familiar with Bootstrap 3, cards replace our old panels, wells, and thumbnails. Similar functionality to those components is available as modifier classes for cards.

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/components/card/\#example)

Cards are built with as little markup and styles as possible, but still manage to deliver a ton of control and customization. Built with flexbox, they offer easy alignment and mix well with other Bootstrap components. They have no `margin` by default, so use [spacing utilities](https://getbootstrap.com/docs/5.3/utilities/spacing) as needed.

Below is an example of a basic card with mixed content and a fixed width. Cards have no fixed width to start, so they’ll naturally fill the full width of its parent element. This is easily customized with our various [sizing options](https://getbootstrap.com/docs/5.3/components/card/#sizing).

PlaceholderImage cap

##### Card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## Content types [Link to this section: Content types](https://getbootstrap.com/docs/5.3/components/card/\#content-types)

Cards support a wide variety of content, including images, text, list groups, links, and more. Below are examples of what’s supported.

### Body [Link to this section: Body](https://getbootstrap.com/docs/5.3/components/card/\#body)

The building block of a card is the `.card-body`. Use it whenever you need a padded section within a card.

This is some text within a card body.


html

```html
<div class="card">
  <div class="card-body">
    This is some text within a card body.
  </div>
</div>
```

### Titles, text, and links [Link to this section: Titles, text, and links](https://getbootstrap.com/docs/5.3/components/card/\#titles-text-and-links)

Card titles are used by adding `.card-title` to a `<h*>` tag. In the same way, links are added and placed next to each other by adding `.card-link` to an `<a>` tag.

Subtitles are used by adding a `.card-subtitle` to a `<h*>` tag. If the `.card-title` and the `.card-subtitle` items are placed in a `.card-body` item, the card title and subtitle are aligned nicely.

##### Card title

###### Card subtitle

Some quick example text to build on the card title and make up the bulk of the card’s content.

[Card link](https://getbootstrap.com/docs/5.3/components/card/#) [Another link](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
```

### Images [Link to this section: Images](https://getbootstrap.com/docs/5.3/components/card/\#images)

`.card-img-top` and `.card-img-bottom` respectively set the top and bottom corners rounded to match the card’s borders. With `.card-text`, text can be added to the card. Text within `.card-text` can also be styled with the standard HTML tags.

PlaceholderImage cap

Some quick example text to build on the card title and make up the bulk of the card’s content.

html

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
```

### List groups [Link to this section: List groups](https://getbootstrap.com/docs/5.3/components/card/\#list-groups)

Create lists of content in a card with a flush list group.

- An item
- A second item
- A third item

html

```html
<div class="card" style="width: 18rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
</div>
```

Featured


- An item
- A second item
- A third item

html

```html
<div class="card" style="width: 18rem;">
  <div class="card-header">
    Featured
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
</div>
```

- An item
- A second item
- A third item

Card footer


html

```html
<div class="card" style="width: 18rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
  <div class="card-footer">
    Card footer
  </div>
</div>
```

### Kitchen sink [Link to this section: Kitchen sink](https://getbootstrap.com/docs/5.3/components/card/\#kitchen-sink)

Mix and match multiple content types to create the card you need, or throw everything in there. Shown below are image styles, blocks, text styles, and a list group—all wrapped in a fixed-width card.

PlaceholderImage cap

##### Card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

- An item
- A second item
- A third item

[Card link](https://getbootstrap.com/docs/5.3/components/card/#) [Another link](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
  <div class="card-body">
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
```

### Header and footer [Link to this section: Header and footer](https://getbootstrap.com/docs/5.3/components/card/\#header-and-footer)

Add an optional header and/or footer within a card.

Featured


##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

Card headers can be styled by adding `.card-header` to `<h*>` elements.

##### Featured

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card">
  <h5 class="card-header">Featured</h5>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

Quote


> A well-known quote, contained in a blockquote element.

Someone famous in Source Title

html

```html
<div class="card">
  <div class="card-header">
    Quote
  </div>
  <div class="card-body">
    <figure>
      <blockquote class="blockquote">
        <p>A well-known quote, contained in a blockquote element.</p>
      </blockquote>
      <figcaption class="blockquote-footer">
        Someone famous in <cite title="Source Title">Source Title</cite>
      </figcaption>
    </figure>
  </div>
</div>
```

Featured


##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

2 days ago


html

```html
<div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-body-secondary">
    2 days ago
  </div>
</div>
```

## Sizing [Link to this section: Sizing](https://getbootstrap.com/docs/5.3/components/card/\#sizing)

Cards assume no specific `width` to start, so they’ll be 100% wide unless otherwise stated. You can change this as needed with custom CSS, grid classes, grid Sass mixins, or utilities.

### Using grid markup [Link to this section: Using grid markup](https://getbootstrap.com/docs/5.3/components/card/\#using-grid-markup)

Using the grid, wrap cards in columns and rows as needed.

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="row">
  <div class="col-sm-6 mb-3 mb-sm-0">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Special title treatment</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Special title treatment</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
</div>
```

### Using utilities [Link to this section: Using utilities](https://getbootstrap.com/docs/5.3/components/card/\#using-utilities)

Use our handful of [available sizing utilities](https://getbootstrap.com/docs/5.3/utilities/sizing) to quickly set a card’s width.

##### Card title

With supporting text below as a natural lead-in to additional content.

[Button](https://getbootstrap.com/docs/5.3/components/card/#)

##### Card title

With supporting text below as a natural lead-in to additional content.

[Button](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card w-75 mb-3">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>

<div class="card w-50">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>
```

### Using custom CSS [Link to this section: Using custom CSS](https://getbootstrap.com/docs/5.3/components/card/\#using-custom-css)

Use custom CSS in your stylesheets or as inline styles to set a width.

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## Text alignment [Link to this section: Text alignment](https://getbootstrap.com/docs/5.3/components/card/\#text-alignment)

You can quickly change the text alignment of any card—in its entirety or specific parts—with our [text align classes](https://getbootstrap.com/docs/5.3/utilities/text#text-alignment).

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card mb-3" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-center mb-3" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-end" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## Navigation [Link to this section: Navigation](https://getbootstrap.com/docs/5.3/components/card/\#navigation)

Add some navigation to a card’s header (or block) with Bootstrap’s [nav components](https://getbootstrap.com/docs/5.3/components/navs-tabs).

- [Active](https://getbootstrap.com/docs/5.3/components/card/#)
- [Link](https://getbootstrap.com/docs/5.3/components/card/#)
- Disabled

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs">
      <li class="nav-item">
        <a class="nav-link active" aria-current="true" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

- [Active](https://getbootstrap.com/docs/5.3/components/card/#)
- [Link](https://getbootstrap.com/docs/5.3/components/card/#)
- Disabled

##### Special title treatment

With supporting text below as a natural lead-in to additional content.

[Go somewhere](https://getbootstrap.com/docs/5.3/components/card/#)

html

```html
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-pills card-header-pills">
      <li class="nav-item">
        <a class="nav-link active" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## Images [Link to this section: Images](https://getbootstrap.com/docs/5.3/components/card/\#images-1)

Cards include a few options for working with images. Choose from appending “image caps” at either end of a card, overlaying images with card content, or simply embedding the image in a card.

### Image caps [Link to this section: Image caps](https://getbootstrap.com/docs/5.3/components/card/\#image-caps)

Similar to headers and footers, cards can include top and bottom “image caps”—images at the top or bottom of a card.

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

PlaceholderImage cap

html

```html
<div class="card mb-3">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
  </div>
</div>
<div class="card">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
  </div>
  <img src="..." class="card-img-bottom" alt="...">
</div>
```

### Image overlays [Link to this section: Image overlays](https://getbootstrap.com/docs/5.3/components/card/\#image-overlays)

Turn an image into a card background and overlay your card’s text. Depending on the image, you may or may not need additional styles or utilities.

PlaceholderCard image

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

html

```html
<div class="card text-bg-dark">
  <img src="..." class="card-img" alt="...">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small>Last updated 3 mins ago</small></p>
  </div>
</div>
```

Note that content should not be larger than the height of the image. If content is larger than the image the content will be displayed outside the image.

## Horizontal [Link to this section: Horizontal](https://getbootstrap.com/docs/5.3/components/card/\#horizontal)

Using a combination of grid and utility classes, cards can be made horizontal in a mobile-friendly and responsive way. In the example below, we remove the grid gutters with `.g-0` and use `.col-md-*` classes to make the card horizontal at the `md` breakpoint. Further adjustments may be needed depending on your card content.

PlaceholderImage

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

html

```html
<div class="card mb-3" style="max-width: 540px;">
  <div class="row g-0">
    <div class="col-md-4">
      <img src="..." class="img-fluid rounded-start" alt="...">
    </div>
    <div class="col-md-8">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
        <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
      </div>
    </div>
  </div>
</div>
```

## Card styles [Link to this section: Card styles](https://getbootstrap.com/docs/5.3/components/card/\#card-styles)

Cards include various options for customizing their backgrounds, borders, and color.

### Background and color [Link to this section: Background and color](https://getbootstrap.com/docs/5.3/components/card/\#background-and-color)

Added in v5.2.0

Set a `background-color` with contrasting foreground `color` with [our `.text-bg-{color}` helpers](https://getbootstrap.com/docs/5.3/helpers/color-background). Previously it was required to manually pair your choice of [`.text-{color}`](https://getbootstrap.com/docs/5.3/utilities/colors) and [`.bg-{color}`](https://getbootstrap.com/docs/5.3/utilities/background) utilities for styling, which you still may use if you prefer.

Header

##### Primary card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Secondary card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Success card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Danger card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Warning card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Info card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Light card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Dark card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

html

```html
<div class="card text-bg-primary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Primary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-secondary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Secondary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-success mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Success card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-danger mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Danger card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-warning mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Warning card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-info mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Info card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-light mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Light card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card text-bg-dark mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Dark card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
```

**Accessibility tip:** Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies like screen readers. Please ensure the meaning is obvious from the content itself (e.g., the visible text with a [_sufficient_ color contrast](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#color-contrast)) or is included through alternative means, such as additional text hidden with the `.visually-hidden` class.

### Border [Link to this section: Border](https://getbootstrap.com/docs/5.3/components/card/\#border)

Use [border utilities](https://getbootstrap.com/docs/5.3/utilities/borders) to change just the `border-color` of a card. Note that you can put `.text-{color}` classes on the parent `.card` or a subset of the card’s contents as shown below.

Header

##### Primary card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Secondary card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Success card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Danger card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Warning card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Info card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Light card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Header

##### Dark card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

html

```html
<div class="card border-primary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body text-primary">
    <h5 class="card-title">Primary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-secondary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body text-secondary">
    <h5 class="card-title">Secondary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-success mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body text-success">
    <h5 class="card-title">Success card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-danger mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body text-danger">
    <h5 class="card-title">Danger card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-warning mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Warning card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-info mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Info card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-light mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Light card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
<div class="card border-dark mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Dark card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
</div>
```

### Mixins utilities [Link to this section: Mixins utilities](https://getbootstrap.com/docs/5.3/components/card/\#mixins-utilities)

You can also change the borders on the card header and footer as needed, and even remove their `background-color` with `.bg-transparent`.

Header

##### Success card title

Some quick example text to build on the card title and make up the bulk of the card’s content.

Footer

html

```html
<div class="card border-success mb-3" style="max-width: 18rem;">
  <div class="card-header bg-transparent border-success">Header</div>
  <div class="card-body text-success">
    <h5 class="card-title">Success card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
  </div>
  <div class="card-footer bg-transparent border-success">Footer</div>
</div>
```

## Card layout [Link to this section: Card layout](https://getbootstrap.com/docs/5.3/components/card/\#card-layout)

In addition to styling the content within cards, Bootstrap includes a few options for laying out series of cards. For the time being, **these layout options are not yet responsive**.

### Card groups [Link to this section: Card groups](https://getbootstrap.com/docs/5.3/components/card/\#card-groups)

Use card groups to render cards as a single, attached element with equal width and height columns. Card groups start off stacked and use `display: flex;` to become attached with uniform dimensions starting at the `sm` breakpoint.

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This card has supporting text below as a natural lead-in to additional content.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.

Last updated 3 mins ago

html

```html
<div class="card-group">
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
      <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
    </div>
  </div>
</div>
```

When using card groups with footers, their content will automatically line up.

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This card has supporting text below as a natural lead-in to additional content.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.

Last updated 3 mins ago

html

```html
<div class="card-group">
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    </div>
    <div class="card-footer">
      <small class="text-body-secondary">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
    </div>
    <div class="card-footer">
      <small class="text-body-secondary">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
    </div>
    <div class="card-footer">
      <small class="text-body-secondary">Last updated 3 mins ago</small>
    </div>
  </div>
</div>
```

### Grid cards [Link to this section: Grid cards](https://getbootstrap.com/docs/5.3/components/card/\#grid-cards)

Use the Bootstrap grid system and its [`.row-cols` classes](https://getbootstrap.com/docs/5.3/layout/grid#row-columns) to control how many grid columns (wrapped around your cards) you show per row. For example, here’s `.row-cols-1` laying out the cards on one column, and `.row-cols-md-2` splitting four cards to equal width across multiple rows, from the medium breakpoint up.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

html

```html
<div class="row row-cols-1 row-cols-md-2 g-4">
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
</div>
```

Change it to `.row-cols-3` and you’ll see the fourth card wrap.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

html

```html
<div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
</div>
```

When you need equal height, add `.h-100` to the cards. If you want equal heights by default, you can set `$card-height: 100%` in Sass.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

PlaceholderImage cap

##### Card title

This is a short card.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content.

PlaceholderImage cap

##### Card title

This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

html

```html
<div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a short card.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
</div>
```

Just like with card groups, card footers will automatically line up.

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This card has supporting text below as a natural lead-in to additional content.

Last updated 3 mins ago

PlaceholderImage cap

##### Card title

This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.

Last updated 3 mins ago

html

```html
<div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
      <div class="card-footer">
        <small class="text-body-secondary">Last updated 3 mins ago</small>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      </div>
      <div class="card-footer">
        <small class="text-body-secondary">Last updated 3 mins ago</small>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="..." class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
      </div>
      <div class="card-footer">
        <small class="text-body-secondary">Last updated 3 mins ago</small>
      </div>
    </div>
  </div>
</div>
```

### Masonry [Link to this section: Masonry](https://getbootstrap.com/docs/5.3/components/card/\#masonry)

In `v4` we used a CSS-only technique to mimic the behavior of [Masonry](https://masonry.desandro.com/)-like columns, but this technique came with lots of unpleasant [side effects](https://github.com/twbs/bootstrap/pull/28922). If you want to have this type of layout in `v5`, you can just make use of Masonry plugin. **Masonry is not included in Bootstrap**, but we’ve made a [demo example](https://getbootstrap.com/docs/5.3/examples/masonry) to help you get started.

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/card/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/components/card/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, cards now use local CSS variables on `.card` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

[scss/\_card.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_card.scss)

```scss
--#{$prefix}card-spacer-y: #{$card-spacer-y};
--#{$prefix}card-spacer-x: #{$card-spacer-x};
--#{$prefix}card-title-spacer-y: #{$card-title-spacer-y};
--#{$prefix}card-title-color: #{$card-title-color};
--#{$prefix}card-subtitle-color: #{$card-subtitle-color};
--#{$prefix}card-border-width: #{$card-border-width};
--#{$prefix}card-border-color: #{$card-border-color};
--#{$prefix}card-border-radius: #{$card-border-radius};
--#{$prefix}card-box-shadow: #{$card-box-shadow};
--#{$prefix}card-inner-border-radius: #{$card-inner-border-radius};
--#{$prefix}card-cap-padding-y: #{$card-cap-padding-y};
--#{$prefix}card-cap-padding-x: #{$card-cap-padding-x};
--#{$prefix}card-cap-bg: #{$card-cap-bg};
--#{$prefix}card-cap-color: #{$card-cap-color};
--#{$prefix}card-height: #{$card-height};
--#{$prefix}card-color: #{$card-color};
--#{$prefix}card-bg: #{$card-bg};
--#{$prefix}card-img-overlay-padding: #{$card-img-overlay-padding};
--#{$prefix}card-group-margin: #{$card-group-margin};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/card/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$card-spacer-y:                     $spacer;
$card-spacer-x:                     $spacer;
$card-title-spacer-y:               $spacer * .5;
$card-title-color:                  null;
$card-subtitle-color:               null;
$card-border-width:                 var(--#{$prefix}border-width);
$card-border-color:                 var(--#{$prefix}border-color-translucent);
$card-border-radius:                var(--#{$prefix}border-radius);
$card-box-shadow:                   null;
$card-inner-border-radius:          subtract($card-border-radius, $card-border-width);
$card-cap-padding-y:                $card-spacer-y * .5;
$card-cap-padding-x:                $card-spacer-x;
$card-cap-bg:                       rgba(var(--#{$prefix}body-color-rgb), .03);
$card-cap-color:                    null;
$card-height:                       null;
$card-color:                        null;
$card-bg:                           var(--#{$prefix}body-bg);
$card-img-overlay-padding:          $spacer;
$card-group-margin:                 $grid-gutter-width * .5;

```