---
url: https://getbootstrap.com/docs/5.3/helpers/screen-readers
scraped_at: 2025-10-20T02:34:42.376Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/screen-readers/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/screen-readers/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/visually-hidden.mdx "View and edit this file on GitHub")

# Visually hidden

Use these helpers to visually hide elements but keep them accessible to assistive technologies.

Visually hide an element while still allowing it to be exposed to assistive technologies (such as screen readers) with `.visually-hidden`. Use `.visually-hidden-focusable` to visually hide an element by default, but to display it when it’s focused (e.g. by a keyboard-only user). `.visually-hidden-focusable` can also be applied to a container–thanks to `:focus-within`, the container will be displayed when any child element of the container receives focus.

## Title for screen readers

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/screen-readers/#content)

A container with a [focusable element](https://getbootstrap.com/docs/5.3/helpers/screen-readers/#).

html

```html
<h2 class="visually-hidden">Title for screen readers</h2>
<a class="visually-hidden-focusable" href="#content">Skip to main content</a>
<div class="visually-hidden-focusable">A container with a <a href="#">focusable element</a>.</div>
```

Both `visually-hidden` and `visually-hidden-focusable` can also be used as mixins.

```scss
// Usage as a mixin

.visually-hidden-title {
  @include visually-hidden;
}

.skip-navigation {
  @include visually-hidden-focusable;
}

```