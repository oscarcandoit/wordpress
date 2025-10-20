---
url: https://getbootstrap.com/docs/5.1/getting-started/introduction
scraped_at: 2025-10-20T02:26:21.214Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/getting-started/introduction/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/getting-started/introduction/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/getting-started/introduction.md "View and edit this file on GitHub")

# Introduction

Get started with Bootstrap, the world’s most popular framework for building responsive, mobile-first sites, with jsDelivr and a template starter page.

**On this page**

## Quick start [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#quick-start)

Looking to quickly add Bootstrap to your project? Use jsDelivr, a free open source CDN. Using a package manager or need to download the source files? [Head to the downloads page](https://getbootstrap.com/docs/5.1/getting-started/download/).

### CSS [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#css)

Copy-paste the stylesheet `<link>` into your `<head>` before all other stylesheets to load our CSS.

Copy

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

```

### JS [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#js)

Many of our components require the use of JavaScript to function. Specifically, they require our own JavaScript plugins and [Popper](https://popper.js.org/). Place **one of the following `<script>` s** near the end of your pages, right before the closing `</body>` tag, to enable them.

#### Bundle [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#bundle)

Include every Bootstrap JavaScript plugin and dependency with one of our two bundles. Both `bootstrap.bundle.js` and `bootstrap.bundle.min.js` include [Popper](https://popper.js.org/) for our tooltips and popovers. For more information about what’s included in Bootstrap, please see our [contents](https://getbootstrap.com/docs/5.1/getting-started/contents/#precompiled-bootstrap) section.

Copy

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>

```

#### Separate [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#separate)

If you decide to go with the separate scripts solution, Popper must come first (if you’re using tooltips or popovers), and then our JavaScript plugins.

Copy

```html
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.10.2/dist/umd/popper.min.js" integrity="sha384-7+zCNj/IqJ95wo16oMtfsKbZ9ccEh31eOz1HGyDuCQ6wgnyJNSYdrPa03rtR1zdB" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.min.js" integrity="sha384-QJHtvGhmr9XOIpI6YVutG+2QOK9T+ZnN4kzFN1RtK3zEFEIsxhlmWl5/YESvpZ13" crossorigin="anonymous"></script>

```

#### Modules [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#modules)

If you use `<script type="module">`, please refer to our [using Bootstrap as a module](https://getbootstrap.com/docs/5.1/getting-started/javascript/#using-bootstrap-as-a-module) section.

#### Components [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#components)

Curious which components explicitly require our JavaScript and Popper? Click the show components link below. If you’re at all unsure about the general page structure, keep reading for an example page template.

Show components requiring JavaScript

- Alerts for dismissing
- Buttons for toggling states and checkbox/radio functionality
- Carousel for all slide behaviors, controls, and indicators
- Collapse for toggling visibility of content
- Dropdowns for displaying and positioning (also requires [Popper](https://popper.js.org/))
- Modals for displaying, positioning, and scroll behavior
- Navbar for extending our Collapse plugin to implement responsive behavior
- Offcanvases for displaying, positioning, and scroll behavior
- Toasts for displaying and dismissing
- Tooltips and popovers for displaying and positioning (also requires [Popper](https://popper.js.org/))
- Scrollspy for scroll behavior and navigation updates

## Starter template [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#starter-template)

Be sure to have your pages set up with the latest design and development standards. That means using an HTML5 doctype and including a viewport meta tag for proper responsive behaviors. Put it all together and your pages should look like this:

Copy

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.10.2/dist/umd/popper.min.js" integrity="sha384-7+zCNj/IqJ95wo16oMtfsKbZ9ccEh31eOz1HGyDuCQ6wgnyJNSYdrPa03rtR1zdB" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.min.js" integrity="sha384-QJHtvGhmr9XOIpI6YVutG+2QOK9T+ZnN4kzFN1RtK3zEFEIsxhlmWl5/YESvpZ13" crossorigin="anonymous"></script>
    -->
  </body>
</html>

```

For next steps, visit the [Layout docs](https://getbootstrap.com/docs/5.1/layout/grid/) or [our official examples](https://getbootstrap.com/docs/5.1/examples/) to start laying out your site’s content and components.

## Important globals [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#important-globals)

Bootstrap employs a handful of important global styles and settings that you’ll need to be aware of when using it, all of which are almost exclusively geared towards the _normalization_ of cross browser styles. Let’s dive in.

### HTML5 doctype [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#html5-doctype)

Bootstrap requires the use of the HTML5 doctype. Without it, you’ll see some funky incomplete styling, but including it shouldn’t cause any considerable hiccups.

Copy

```html
<!doctype html>
<html lang="en">
  ...
</html>

```

### Responsive meta tag [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#responsive-meta-tag)

Bootstrap is developed _mobile first_, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, **add the responsive viewport meta tag** to your `<head>`.

Copy

```html
<meta name="viewport" content="width=device-width, initial-scale=1">

```

You can see an example of this in action in the [starter template](https://getbootstrap.com/docs/5.1/getting-started/introduction/#starter-template).

### Box-sizing [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#box-sizing)

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third-party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

Copy

```css
.selector-for-some-widget {
  box-sizing: content-box;
}

```

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#reboot)

For improved cross-browser rendering, we use [Reboot](https://getbootstrap.com/docs/5.1/content/reboot/) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.

## Community [Anchor](https://getbootstrap.com/docs/5.1/getting-started/introduction/\#community)

Stay up to date on the development of Bootstrap and reach out to the community with these helpful resources.

- Read and subscribe to [The Official Bootstrap Blog](https://blog.getbootstrap.com/).
- Chat with fellow Bootstrappers in IRC. On the `irc.libera.chat` server, in the `#bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-5`](https://stackoverflow.com/questions/tagged/bootstrap-5)).
- Developers should use the keyword `bootstrap` on packages that modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/search?q=keywords:bootstrap) or similar delivery mechanisms for maximum discoverability.

You can also follow [@getbootstrap on Twitter](https://twitter.com/getbootstrap) for the latest gossip and awesome music videos.