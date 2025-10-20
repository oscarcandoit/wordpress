---
url: https://getbootstrap.com/docs/4.2/components/carousel
scraped_at: 2025-10-20T02:41:13.538Z
---

[Skip to main content](https://getbootstrap.com/docs/4.2/components/carousel/#content) [There's a newer version of Bootstrap!](https://getbootstrap.com/)

```

```

Menu

- [How it works](https://getbootstrap.com/docs/4.2/components/carousel/#how-it-works)
- [Example](https://getbootstrap.com/docs/4.2/components/carousel/#example)
  - [Slides only](https://getbootstrap.com/docs/4.2/components/carousel/#slides-only)
  - [With controls](https://getbootstrap.com/docs/4.2/components/carousel/#with-controls)
  - [With indicators](https://getbootstrap.com/docs/4.2/components/carousel/#with-indicators)
  - [With captions](https://getbootstrap.com/docs/4.2/components/carousel/#with-captions)
  - [Crossfade](https://getbootstrap.com/docs/4.2/components/carousel/#crossfade)
  - [Individual .carousel-item interval](https://getbootstrap.com/docs/4.2/components/carousel/#individual-carousel-item-interval)
- [Usage](https://getbootstrap.com/docs/4.2/components/carousel/#usage)
  - [Via data attributes](https://getbootstrap.com/docs/4.2/components/carousel/#via-data-attributes)
  - [Via JavaScript](https://getbootstrap.com/docs/4.2/components/carousel/#via-javascript)
  - [Options](https://getbootstrap.com/docs/4.2/components/carousel/#options)
  - [Methods](https://getbootstrap.com/docs/4.2/components/carousel/#methods)
    - [.carousel(options)](https://getbootstrap.com/docs/4.2/components/carousel/#carouseloptions)
    - [.carousel('cycle')](https://getbootstrap.com/docs/4.2/components/carousel/#carouselcycle)
    - [.carousel('pause')](https://getbootstrap.com/docs/4.2/components/carousel/#carouselpause)
    - [.carousel(number)](https://getbootstrap.com/docs/4.2/components/carousel/#carouselnumber)
    - [.carousel('prev')](https://getbootstrap.com/docs/4.2/components/carousel/#carouselprev)
    - [.carousel('next')](https://getbootstrap.com/docs/4.2/components/carousel/#carouselnext)
    - [.carousel('dispose')](https://getbootstrap.com/docs/4.2/components/carousel/#carouseldispose)
  - [Events](https://getbootstrap.com/docs/4.2/components/carousel/#events)
  - [Change transition duration](https://getbootstrap.com/docs/4.2/components/carousel/#change-transition-duration)

# Carousel

A slideshow component for cycling through elements—images or slides of text—like a carousel.

## How it works [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#how-it-works)

The carousel is a slideshow for cycling through a series of content, built with CSS 3D transforms and a bit of JavaScript. It works with a series of images, text, or custom markup. It also includes support for previous/next controls and indicators.

In browsers where the [Page Visibility API](https://www.w3.org/TR/page-visibility/) is supported, the carousel will avoid sliding when the webpage is not visible to the user (such as when the browser tab is inactive, the browser window is minimized, etc.).

The animation effect of this component is dependent on the `prefers-reduced-motion` media query. See the [reduced motion section of our accessibility documentation](https://getbootstrap.com/docs/4.2/getting-started/accessibility/#reduced-motion).

Please be aware that nested carousels are not supported, and carousels are generally not compliant with accessibility standards.

Lastly, if you’re building our JavaScript from source, it [requires `util.js`](https://getbootstrap.com/docs/4.2/getting-started/javascript/#util).

## Example [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#example)

Carousels don’t automatically normalize slide dimensions. As such, you may need to use additional utilities or custom styles to appropriately size content. While carousels support previous/next controls and indicators, they’re not explicitly required. Add and customize as you see fit.

**The `.active` class needs to be added to one of the slides** otherwise the carousel will not be visible. Also be sure to set a unique id on the `.carousel` for optional controls, especially if you’re using multiple carousels on a single page. Control and indicator elements must have a `data-target` attribute (or `href` for links) that matches the id of the `.carousel` element.

### Slides only [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#slides-only)

Here’s a carousel with slides only. Note the presence of the `.d-block` and `.w-100` on carousel images to prevent browser default image alignment.

PlaceholderFirst slide

PlaceholderSecond slide

PlaceholderThird slide

Copy

```html
<div id="carouselExampleSlidesOnly" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
        <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
</div>
```

### With controls [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#with-controls)

Adding in the previous and next controls:

PlaceholderFirst slide

PlaceholderSecond slide

PlaceholderThird slide

[Previous](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleControls) [Next](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleControls)

Copy

```html
<div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

### With indicators [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#with-indicators)

You can also add the indicators to the carousel, alongside the controls, too.

PlaceholderFirst slide

PlaceholderSecond slide

PlaceholderThird slide

[Previous](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleIndicators) [Next](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleIndicators)

Copy

```html
<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

### With captions [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#with-captions)

Add captions to your slides easily with the `.carousel-caption` element within any `.carousel-item`. They can be easily hidden on smaller viewports, as shown below, with optional [display utilities](https://getbootstrap.com/docs/4.2/utilities/display/). We hide them initially with `.d-none` and bring them back on medium-sized devices with `.d-md-block`.

PlaceholderFirst slide

##### First slide label

Nulla vitae elit libero, a pharetra augue mollis interdum.

PlaceholderSecond slide

##### Second slide label

Lorem ipsum dolor sit amet, consectetur adipiscing elit.

PlaceholderThird slide

##### Third slide label

Praesent commodo cursus magna, vel scelerisque nisl consectetur.

[Previous](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleCaptions) [Next](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleCaptions)

Copy

```html
<div class="carousel-item">
  <img src="..." alt="...">
  <div class="carousel-caption d-none d-md-block">
    <h5>...</h5>
    <p>...</p>
  </div>
</div>
```

### Crossfade [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#crossfade)

Add `.carousel-fade` to your carousel to animate slides with a fade transition instead of a slide.

PlaceholderFirst slide

PlaceholderSecond slide

PlaceholderThird slide

[Previous](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleFade) [Next](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleFade)

Copy

```html
<div id="carouselExampleFade" class="carousel slide carousel-fade" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleFade" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleFade" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

### Individual `.carousel-item` interval [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#individual-carousel-item-interval)

Add `data-interval=""` to a `.carousel-item` to change the amount of time to delay between automatically cycling to the next item.

PlaceholderFirst slide

PlaceholderSecond slide

PlaceholderThird slide

[Previous](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleInterval) [Next](https://getbootstrap.com/docs/4.2/components/carousel/#carouselExampleInterval)

Copy

```html
<div id="carouselExampleInterval" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active" data-interval="10000">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item" data-interval="2000">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleInterval" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleInterval" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

## Usage [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#usage)

### Via data attributes [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#via-data-attributes)

Use data attributes to easily control the position of the carousel. `data-slide` accepts the keywords `prev` or `next`, which alters the slide position relative to its current position. Alternatively, use `data-slide-to` to pass a raw slide index to the carousel `data-slide-to="2"`, which shifts the slide position to a particular index beginning with `0`.

The `data-ride="carousel"` attribute is used to mark a carousel as animating starting at page load. **It cannot be used in combination with (redundant and unnecessary) explicit JavaScript initialization of the same carousel.**

### Via JavaScript [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#via-javascript)

Call carousel manually with:

Copy

```js
$('.carousel').carousel()
```

### Options [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#options)

Options can be passed via data attributes or JavaScript. For data attributes, append the option name to `data-`, as in `data-interval=""`.

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| interval | number | 5000 | The amount of time to delay between automatically cycling an item. If false, carousel will not automatically cycle. |
| keyboard | boolean | true | Whether the carousel should react to keyboard events. |
| pause | string \| boolean | "hover" | If set to `"hover"`, pauses the cycling of the carousel on `mouseenter` and resumes the cycling of the carousel on `mouseleave`. If set to `false`, hovering over the carousel won't pause it.<br>On touch-enabled devices, when set to `"hover"`, cycling will pause on `touchend` (once the user finished interacting with the carousel) for two intervals, before automatically resuming. Note that this is in addition to the above mouse behavior. |
| ride | string | false | Autoplays the carousel after the user manually cycles the first item. If "carousel", autoplays the carousel on load. |
| wrap | boolean | true | Whether the carousel should cycle continuously or have hard stops. |
| touch | boolean | true | Whether the carousel should support left/right swipe interactions on touchscreen devices. |

### Methods [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#methods)

#### Asynchronous methods and transitions

All API methods are **asynchronous** and start a **transition**. They return to the caller as soon as the transition is started but **before it ends**. In addition, a method call on a **transitioning component will be ignored**.

[See our JavaScript documentation for more information](https://getbootstrap.com/docs/4.2/getting-started/javascript/).

#### `.carousel(options)` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouseloptions)

Initializes the carousel with an optional options `object` and starts cycling through items.

Copy

```js
$('.carousel').carousel({
  interval: 2000
})
```

#### `.carousel('cycle')` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouselcycle)

Cycles through the carousel items from left to right.

#### `.carousel('pause')` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouselpause)

Stops the carousel from cycling through items.

#### `.carousel(number)` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouselnumber)

Cycles the carousel to a particular frame (0 based, similar to an array). **Returns to the caller before the target item has been shown** (i.e. before the `slid.bs.carousel` event occurs).

#### `.carousel('prev')` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouselprev)

Cycles to the previous item. **Returns to the caller before the previous item has been shown** (i.e. before the `slid.bs.carousel` event occurs).

#### `.carousel('next')` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouselnext)

Cycles to the next item. **Returns to the caller before the next item has been shown** (i.e. before the `slid.bs.carousel` event occurs).

#### `.carousel('dispose')` [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#carouseldispose)

Destroys an element’s carousel.

### Events [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#events)

Bootstrap’s carousel class exposes two events for hooking into carousel functionality. Both events have the following additional properties:

- `direction`: The direction in which the carousel is sliding (either `"left"` or `"right"`).
- `relatedTarget`: The DOM element that is being slid into place as the active item.
- `from`: The index of the current item
- `to`: The index of the next item

All carousel events are fired at the carousel itself (i.e. at the `<div class="carousel">`).

| Event Type | Description |
| --- | --- |
| slide.bs.carousel | This event fires immediately when the `slide` instance method is invoked. |
| slid.bs.carousel | This event is fired when the carousel has completed its slide transition. |

Copy

```js
$('#myCarousel').on('slide.bs.carousel', function () {
  // do something…
})
```

### Change transition duration [Anchor](https://getbootstrap.com/docs/4.2/components/carousel/\#change-transition-duration)

The transition duration of `.carousel-item` can be changed with the `$carousel-transition` Sass variable before compiling or custom styles if you’re using the compiled CSS. If multiple transitions are applied, make sure the transform transition is defined first (eg. `transition: transform 2s ease, opacity .5s ease-out`).