---
url: https://getbootstrap.com/docs/5.3/getting-started/introduction
scraped_at: 2025-10-20T02:33:43.492Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/getting-started/introduction/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/getting-started/introduction/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/getting-started/introduction.mdx "View and edit this file on GitHub")

# Get started with Bootstrap

Bootstrap is a powerful, feature-packed frontend toolkit. Build anything—from prototype to production—in minutes.

On this page
**On this page**

* * *

## Quick start [Link to this section: Quick start](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#quick-start)

Get started by including Bootstrap’s production-ready CSS and JavaScript via CDN without the need for any build steps. See it in practice with this [Bootstrap CodePen demo](https://codepen.io/team/bootstrap/pen/qBamdLj).

1. **Create a new `index.html` file in your project root.** Include the `<meta name="viewport">` tag as well for [proper responsive behavior](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag) in mobile devices.









```html
<!doctype html>
<html lang="en">
     <head>
       <meta charset="utf-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>Bootstrap demo</title>
     </head>
     <body>
       <h1>Hello, world!</h1>
     </body>
</html>

```

2. **Include Bootstrap’s CSS and JS.** Place the `<link>` tag in the `<head>` for our CSS, and the `<script>` tag for our JavaScript bundle (including Popper for positioning dropdowns, popovers, and tooltips) before the closing `</body>`. Learn more about our [CDN links](https://getbootstrap.com/docs/5.3/getting-started/introduction/#cdn-links).









```html
<!doctype html>
<html lang="en">
     <head>
       <meta charset="utf-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>Bootstrap demo</title>
       <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">
     </head>
     <body>
       <h1>Hello, world!</h1>
       <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>
     </body>
</html>

```





You can also include [Popper](https://popper.js.org/docs/v2/) and our JS separately. If you don’t plan to use dropdowns, popovers, or tooltips, save some kilobytes by not including Popper.









```html
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.min.js" integrity="sha384-G/EV+4j2dNv+tEPo3++6LCgdCROaejBqfUeNjuKAiuXbjrxilcCdDz6ZAVfHWe1Y" crossorigin="anonymous"></script>

```

3. **Hello, world!** Open the page in your browser of choice to see your Bootstrapped page. Now you can start building with Bootstrap by creating your own [layout](https://getbootstrap.com/docs/5.3/layout/grid), adding dozens of [components](https://getbootstrap.com/docs/5.3/components/buttons), and utilizing [our official examples](https://getbootstrap.com/docs/5.3/examples).


## CDN links [Link to this section: CDN links](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#cdn-links)

As reference, here are our primary CDN links.

| Description | URL |
| --- | --- |
| CSS | `https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css` |
| JS | `https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js` |

You can also use the CDN to fetch any of our [additional builds listed in the Contents page](https://getbootstrap.com/docs/5.3/getting-started/contents).

When using CDN links, be sure to use the `integrity` attribute to verify the correct files and versions. These hashes are unique to each file and version of Bootstrap, so when you update to a new version, be sure the `integrity` attribute is also updated.

We also include a `crossorigin="anonymous"` attribute to prevent [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) errors.

## Next steps [Link to this section: Next steps](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#next-steps)

- Read a bit more about some [important global environment settings](https://getbootstrap.com/docs/5.3/getting-started/introduction/#important-globals) that Bootstrap utilizes.
- Read about what’s included in Bootstrap in our [contents section](https://getbootstrap.com/docs/5.3/getting-started/contents/) and the list of [components that require JavaScript](https://getbootstrap.com/docs/5.3/getting-started/introduction/#js-components) below.
- Need a little more power? Consider building with Bootstrap by [including the source files via package manager](https://getbootstrap.com/docs/5.3/getting-started/download#package-managers).
- Looking to use Bootstrap as a module with `<script type="module">`? Please refer to our [using Bootstrap as a module](https://getbootstrap.com/docs/5.3/getting-started/javascript#using-bootstrap-as-a-module) section.

## JS components [Link to this section: JS components](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#js-components)

Curious which components explicitly require our JavaScript and Popper? If you’re at all unsure about the general page structure, keep reading for an example page template.

- Accordions for extending our Collapse plugin
- Alerts for dismissing
- Buttons for toggling states and checkbox/radio functionality
- Carousel for all slide behaviors, controls, and indicators
- Collapse for toggling visibility of content
- Dropdowns for displaying and positioning (also requires [Popper](https://popper.js.org/docs/v2/))
- Modals for displaying, positioning, and scroll behavior
- Navbar for extending our Collapse and Offcanvas plugins to implement responsive behaviors
- Navs with the Tab plugin for toggling content panes
- Offcanvases for displaying, positioning, and scroll behavior
- Scrollspy for scroll behavior and navigation updates
- Toasts for displaying and dismissing
- Tooltips and popovers for displaying and positioning (also requires [Popper](https://popper.js.org/docs/v2/))

## Important globals [Link to this section: Important globals](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#important-globals)

Bootstrap employs a handful of important global styles and settings, all of which are almost exclusively geared towards the _normalization_ of cross browser styles. Let’s dive in.

### HTML5 doctype [Link to this section: HTML5 doctype](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#html5-doctype)

Bootstrap requires the use of the HTML5 doctype. Without it, you’ll see some funky and incomplete styling.

```html
<!doctype html>
<html lang="en">
  ...
</html>

```

### Viewport meta [Link to this section: Viewport meta](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#viewport-meta)

Bootstrap is developed _mobile first_, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, add the responsive viewport meta tag to your `<head>`.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">

```

You can see an example of this in action in the [quick start](https://getbootstrap.com/docs/5.3/getting-started/introduction/#quick-start).

### Box-sizing [Link to this section: Box-sizing](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#box-sizing)

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third-party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

```css
.selector-for-some-widget {
  box-sizing: content-box;
}

```

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot [Link to this section: Reboot](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#reboot)

For improved cross-browser rendering, we use [Reboot](https://getbootstrap.com/docs/5.3/content/reboot) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.

## Community [Link to this section: Community](https://getbootstrap.com/docs/5.3/getting-started/introduction/\#community)

Stay up-to-date on the development of Bootstrap and reach out to the community with these helpful resources.

- Read and subscribe to [The Official Bootstrap Blog](https://blog.getbootstrap.com/).
- Ask questions and explore [our GitHub Discussions](https://github.com/twbs/bootstrap/discussions).
- Discuss, ask questions, and more on [the community Discord](https://discord.gg/bZUvakRU3M) or [Bootstrap subreddit](https://www.reddit.com/r/bootstrap/).
- Chat with fellow Bootstrappers in IRC. On the `irc.libera.chat` server, in the `#bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-5`](https://stackoverflow.com/questions/tagged/bootstrap-5)).
- Developers should use the keyword `bootstrap` on packages that modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/search?q=keywords:bootstrap) or similar delivery mechanisms for maximum discoverability.

You can also follow [@getbootstrap on X](https://x.com/getbootstrap) for the latest gossip and awesome music videos.