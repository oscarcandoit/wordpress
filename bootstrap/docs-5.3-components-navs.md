---
url: https://getbootstrap.com/docs/5.3/components/navs
scraped_at: 2025-10-20T02:27:44.224Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/navs-tabs/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/navs-tabs/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/navs-tabs.mdx "View and edit this file on GitHub")

# Navs and tabs

Documentation and examples for how to use Bootstrap’s included navigation components.

On this page
**On this page**

* * *

## Base nav [Link to this section: Base nav](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#base-nav)

Navigation available in Bootstrap share general markup and styles, from the base `.nav` class to the active and disabled states. Swap modifier classes to switch between each style.

The base `.nav` component is built with flexbox and provide a strong foundation for building all types of navigation components. It includes some style overrides (for working with lists), some link padding for larger hit areas, and basic disabled styling.

The base `.nav` component does not include any `.active` state. The following examples include the class, mainly to demonstrate that this particular class does not trigger any special styling.

To convey the active state to assistive technologies, use the `aria-current` attribute — using the `page` value for current page, or `true` for the current item in a set.

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

Classes are used throughout, so your markup can be super flexible. Use `<ul>` s like above, `<ol>` if the order of your items is important, or roll your own with a `<nav>` element. Because the `.nav` uses `display: flex`, the nav links behave the same as nav items would, but without the extra markup.

html

```html
<nav class="nav">
  <a class="nav-link active" aria-current="page" href="#">Active</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
</nav>
```

## Available styles [Link to this section: Available styles](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#available-styles)

Change the style of `.nav` s component with modifiers and utilities. Mix and match as needed, or build your own.

### Horizontal alignment [Link to this section: Horizontal alignment](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#horizontal-alignment)

Change the horizontal alignment of your nav with [flexbox utilities](https://getbootstrap.com/docs/5.3/utilities/flex#justify-content). By default, navs are left-aligned, but you can easily change them to center or right-aligned.

Centered with `.justify-content-center`:

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav justify-content-center">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

Right-aligned with `.justify-content-end`:

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)