---
url: https://getbootstrap.com/docs/5.3/components/navs-tabs
scraped_at: 2025-10-20T02:27:39.831Z
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
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav justify-content-end">
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

### Vertical [Link to this section: Vertical](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#vertical)

Stack your navigation by changing the flex item direction with the `.flex-column` utility. Need to stack them on some viewports but not others? Use the responsive versions (e.g., `.flex-sm-column`).

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav flex-column">
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

As always, vertical navigation is possible without `<ul>` s, too.

html

```html
<nav class="nav flex-column">
  <a class="nav-link active" aria-current="page" href="#">Active</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
</nav>
```

### Tabs [Link to this section: Tabs](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#tabs)

Takes the basic nav from above and adds the `.nav-tabs` class to generate a tabbed interface. Use them to create tabbable regions with our [tab JavaScript plugin](https://getbootstrap.com/docs/5.3/components/navs-tabs/#javascript-behavior).

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-tabs">
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

### Pills [Link to this section: Pills](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#pills)

Take that same HTML, but use `.nav-pills` instead:

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-pills">
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

### Underline [Link to this section: Underline](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#underline)

Take that same HTML, but use `.nav-underline` instead:

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-underline">
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

### Fill and justify [Link to this section: Fill and justify](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#fill-and-justify)

Force your `.nav`’s contents to extend the full available width with one of two modifier classes. To proportionately fill all available space with your `.nav-item` s, use `.nav-fill`. Notice that all horizontal space is occupied, but not every nav item has the same width.

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Much longer nav link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-pills nav-fill">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Much longer nav link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

When using a `<nav>`-based navigation, you can safely omit `.nav-item` as only `.nav-link` is required for styling `<a>` elements.

html

```html
<nav class="nav nav-pills nav-fill">
  <a class="nav-link active" aria-current="page" href="#">Active</a>
  <a class="nav-link" href="#">Much longer nav link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
</nav>
```

For equal-width elements, use `.nav-justified`. All horizontal space will be occupied by nav links, but unlike the `.nav-fill` above, every nav item will be the same width.

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Much longer nav link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-pills nav-justified">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Much longer nav link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

Similar to the `.nav-fill` example using a `<nav>`-based navigation.

html

```html
<nav class="nav nav-pills nav-justified">
  <a class="nav-link active" aria-current="page" href="#">Active</a>
  <a class="nav-link" href="#">Much longer nav link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
</nav>
```

## Working with flex utilities [Link to this section: Working with flex utilities](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#working-with-flex-utilities)

If you need responsive nav variations, consider using a series of [flexbox utilities](https://getbootstrap.com/docs/5.3/utilities/flex). While more verbose, these utilities offer greater customization across responsive breakpoints. In the example below, our nav will be stacked on the lowest breakpoint, then adapt to a horizontal layout that fills the available width starting from the small breakpoint.

html

```html
<nav class="nav nav-pills flex-column flex-sm-row">
  <a class="flex-sm-fill text-sm-center nav-link active" aria-current="page" href="#">Active</a>
  <a class="flex-sm-fill text-sm-center nav-link" href="#">Longer nav link</a>
  <a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>
  <a class="flex-sm-fill text-sm-center nav-link disabled" aria-disabled="true">Disabled</a>
</nav>
```

## Regarding accessibility [Link to this section: Regarding accessibility](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#regarding-accessibility)

If you’re using navs to provide a navigation bar, be sure to add a `role="navigation"` to the most logical parent container of the `<ul>`, or wrap a `<nav>` element around the whole navigation. Do not add the role to the `<ul>` itself, as this would prevent it from being announced as an actual list by assistive technologies.

Note that navigation bars, even if visually styled as tabs with the `.nav-tabs` class, should **not** be given `role="tablist"`, `role="tab"` or `role="tabpanel"` attributes. These are only appropriate for dynamic tabbed interfaces, as described in the [ARIA Authoring Practices Guide tabs pattern](https://www.w3.org/WAI/ARIA/apg/patterns/tabpanel/). See [JavaScript behavior](https://getbootstrap.com/docs/5.3/components/navs-tabs/#javascript-behavior) for dynamic tabbed interfaces in this section for an example. The `aria-current` attribute is not necessary on dynamic tabbed interfaces since our JavaScript handles the selected state by adding `aria-selected="true"` on the active tab.

## Using dropdowns [Link to this section: Using dropdowns](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#using-dropdowns)

Add dropdown menus with a little extra HTML and the [dropdowns JavaScript plugin](https://getbootstrap.com/docs/5.3/components/dropdowns#usage).

### Tabs with dropdowns [Link to this section: Tabs with dropdowns](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#tabs-with-dropdowns)

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Dropdown](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)  - [Action](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - [Another action](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - [Something else here](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - * * *

  - [Separated link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>
    <ul class="dropdown-menu">
      <li><a class="dropdown-item" href="#">Action</a></li>
      <li><a class="dropdown-item" href="#">Another action</a></li>
      <li><a class="dropdown-item" href="#">Something else here</a></li>
      <li><hr class="dropdown-divider"></li>
      <li><a class="dropdown-item" href="#">Separated link</a></li>
    </ul>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

### Pills with dropdowns [Link to this section: Pills with dropdowns](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#pills-with-dropdowns)

- [Active](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Dropdown](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)  - [Action](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - [Another action](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - [Something else here](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
  - * * *

  - [Separated link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- [Link](https://getbootstrap.com/docs/5.3/components/navs-tabs/#)
- Disabled

html

```html
<ul class="nav nav-pills">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>
    <ul class="dropdown-menu">
      <li><a class="dropdown-item" href="#">Action</a></li>
      <li><a class="dropdown-item" href="#">Another action</a></li>
      <li><a class="dropdown-item" href="#">Something else here</a></li>
      <li><hr class="dropdown-divider"></li>
      <li><a class="dropdown-item" href="#">Separated link</a></li>
    </ul>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, navs now use local CSS variables on `.nav`, `.nav-tabs`, and `.nav-pills` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

On the `.nav` base class:

[scss/\_nav.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_nav.scss)

```scss
--#{$prefix}nav-link-padding-x: #{$nav-link-padding-x};
--#{$prefix}nav-link-padding-y: #{$nav-link-padding-y};
@include rfs($nav-link-font-size, --#{$prefix}nav-link-font-size);
--#{$prefix}nav-link-font-weight: #{$nav-link-font-weight};
--#{$prefix}nav-link-color: #{$nav-link-color};
--#{$prefix}nav-link-hover-color: #{$nav-link-hover-color};
--#{$prefix}nav-link-disabled-color: #{$nav-link-disabled-color};

```

On the `.nav-tabs` modifier class:

[scss/\_nav.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_nav.scss)

```scss
--#{$prefix}nav-tabs-border-width: #{$nav-tabs-border-width};
--#{$prefix}nav-tabs-border-color: #{$nav-tabs-border-color};
--#{$prefix}nav-tabs-border-radius: #{$nav-tabs-border-radius};
--#{$prefix}nav-tabs-link-hover-border-color: #{$nav-tabs-link-hover-border-color};
--#{$prefix}nav-tabs-link-active-color: #{$nav-tabs-link-active-color};
--#{$prefix}nav-tabs-link-active-bg: #{$nav-tabs-link-active-bg};
--#{$prefix}nav-tabs-link-active-border-color: #{$nav-tabs-link-active-border-color};

```

On the `.nav-pills` modifier class:

[scss/\_nav.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_nav.scss)

```scss
--#{$prefix}nav-pills-border-radius: #{$nav-pills-border-radius};
--#{$prefix}nav-pills-link-active-color: #{$nav-pills-link-active-color};
--#{$prefix}nav-pills-link-active-bg: #{$nav-pills-link-active-bg};

```

Added in v5.3.0

On the `.nav-underline` modifier class:

[scss/\_nav.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_nav.scss)

```scss
--#{$prefix}nav-underline-gap: #{$nav-underline-gap};
--#{$prefix}nav-underline-border-width: #{$nav-underline-border-width};
--#{$prefix}nav-underline-link-active-color: #{$nav-underline-link-active-color};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$nav-link-padding-y:                .5rem;
$nav-link-padding-x:                1rem;
$nav-link-font-size:                null;
$nav-link-font-weight:              null;
$nav-link-color:                    var(--#{$prefix}link-color);
$nav-link-hover-color:              var(--#{$prefix}link-hover-color);
$nav-link-transition:               color .15s ease-in-out, background-color .15s ease-in-out, border-color .15s ease-in-out;
$nav-link-disabled-color:           var(--#{$prefix}secondary-color);
$nav-link-focus-box-shadow:         $focus-ring-box-shadow;

$nav-tabs-border-color:             var(--#{$prefix}border-color);
$nav-tabs-border-width:             var(--#{$prefix}border-width);
$nav-tabs-border-radius:            var(--#{$prefix}border-radius);
$nav-tabs-link-hover-border-color:  var(--#{$prefix}secondary-bg) var(--#{$prefix}secondary-bg) $nav-tabs-border-color;
$nav-tabs-link-active-color:        var(--#{$prefix}emphasis-color);
$nav-tabs-link-active-bg:           var(--#{$prefix}body-bg);
$nav-tabs-link-active-border-color: var(--#{$prefix}border-color) var(--#{$prefix}border-color) $nav-tabs-link-active-bg;

$nav-pills-border-radius:           var(--#{$prefix}border-radius);
$nav-pills-link-active-color:       $component-active-color;
$nav-pills-link-active-bg:          $component-active-bg;

$nav-underline-gap:                 1rem;
$nav-underline-border-width:        .125rem;
$nav-underline-link-active-color:   var(--#{$prefix}emphasis-color);

```

## JavaScript behavior [Link to this section: JavaScript behavior](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#javascript-behavior)

Use the tab JavaScript plugin—include it individually or through the compiled `bootstrap.js` file—to extend our navigational tabs and pills to create tabbable panes of local content.

- Home
- Profile
- Contact
- Disabled

This is some placeholder content the **Home tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Profile tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Contact tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Disabled tab’s** associated content.

```html
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home-tab-pane" type="button" role="tab" aria-controls="home-tab-pane" aria-selected="true">Home</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile-tab-pane" type="button" role="tab" aria-controls="profile-tab-pane" aria-selected="false">Profile</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="contact-tab" data-bs-toggle="tab" data-bs-target="#contact-tab-pane" type="button" role="tab" aria-controls="contact-tab-pane" aria-selected="false">Contact</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="disabled-tab" data-bs-toggle="tab" data-bs-target="#disabled-tab-pane" type="button" role="tab" aria-controls="disabled-tab-pane" aria-selected="false" disabled>Disabled</button>
  </li>
</ul>
<div class="tab-content" id="myTabContent">
  <div class="tab-pane fade show active" id="home-tab-pane" role="tabpanel" aria-labelledby="home-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="profile-tab-pane" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="contact-tab-pane" role="tabpanel" aria-labelledby="contact-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="disabled-tab-pane" role="tabpanel" aria-labelledby="disabled-tab" tabindex="0">...</div>
</div>

```

To help fit your needs, this works with `<ul>`-based markup, as shown above, or with any arbitrary “roll your own” markup. Note that if you’re using `<nav>`, you shouldn’t add `role="tablist"` directly to it, as this would override the element’s native role as a navigation landmark. Instead, switch to an alternative element (in the example below, a simple `<div>`) and wrap the `<nav>` around it.

This is some placeholder content the **Home tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Profile tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Contact tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Disabled tab’s** associated content.

```html
<nav>
  <div class="nav nav-tabs" id="nav-tab" role="tablist">
    <button class="nav-link active" id="nav-home-tab" data-bs-toggle="tab" data-bs-target="#nav-home" type="button" role="tab" aria-controls="nav-home" aria-selected="true">Home</button>
    <button class="nav-link" id="nav-profile-tab" data-bs-toggle="tab" data-bs-target="#nav-profile" type="button" role="tab" aria-controls="nav-profile" aria-selected="false">Profile</button>
    <button class="nav-link" id="nav-contact-tab" data-bs-toggle="tab" data-bs-target="#nav-contact" type="button" role="tab" aria-controls="nav-contact" aria-selected="false">Contact</button>
    <button class="nav-link" id="nav-disabled-tab" data-bs-toggle="tab" data-bs-target="#nav-disabled" type="button" role="tab" aria-controls="nav-disabled" aria-selected="false" disabled>Disabled</button>
  </div>
</nav>
<div class="tab-content" id="nav-tabContent">
  <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="nav-disabled" role="tabpanel" aria-labelledby="nav-disabled-tab" tabindex="0">...</div>
</div>

```

The tabs plugin also works with pills.

- Home
- Profile
- Contact
- Disabled

This is some placeholder content the **Home tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Profile tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Contact tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Disabled tab’s** associated content.

```html
<ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="pills-home-tab" data-bs-toggle="pill" data-bs-target="#pills-home" type="button" role="tab" aria-controls="pills-home" aria-selected="true">Home</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="pills-profile-tab" data-bs-toggle="pill" data-bs-target="#pills-profile" type="button" role="tab" aria-controls="pills-profile" aria-selected="false">Profile</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="pills-contact-tab" data-bs-toggle="pill" data-bs-target="#pills-contact" type="button" role="tab" aria-controls="pills-contact" aria-selected="false">Contact</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="pills-disabled-tab" data-bs-toggle="pill" data-bs-target="#pills-disabled" type="button" role="tab" aria-controls="pills-disabled" aria-selected="false" disabled>Disabled</button>
  </li>
</ul>
<div class="tab-content" id="pills-tabContent">
  <div class="tab-pane fade show active" id="pills-home" role="tabpanel" aria-labelledby="pills-home-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="pills-profile" role="tabpanel" aria-labelledby="pills-profile-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="pills-contact" role="tabpanel" aria-labelledby="pills-contact-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="pills-disabled" role="tabpanel" aria-labelledby="pills-disabled-tab" tabindex="0">...</div>
</div>

```

And with vertical pills. Ideally, for vertical tabs, you should also add `aria-orientation="vertical"` to the tab list container.

HomeProfileDisabledMessagesSettings

This is some placeholder content the **Home tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Profile tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Disabled tab’s** associated content.

This is some placeholder content the **Messages tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

This is some placeholder content the **Settings tab’s** associated content. Clicking another tab will toggle the visibility of this one for the next. The tab JavaScript swaps classes to control the content visibility and styling. You can use it with tabs, pills, and any other `.nav`-powered navigation.

```html
<div class="d-flex align-items-start">
  <div class="nav flex-column nav-pills me-3" id="v-pills-tab" role="tablist" aria-orientation="vertical">
    <button class="nav-link active" id="v-pills-home-tab" data-bs-toggle="pill" data-bs-target="#v-pills-home" type="button" role="tab" aria-controls="v-pills-home" aria-selected="true">Home</button>
    <button class="nav-link" id="v-pills-profile-tab" data-bs-toggle="pill" data-bs-target="#v-pills-profile" type="button" role="tab" aria-controls="v-pills-profile" aria-selected="false">Profile</button>
    <button class="nav-link" id="v-pills-disabled-tab" data-bs-toggle="pill" data-bs-target="#v-pills-disabled" type="button" role="tab" aria-controls="v-pills-disabled" aria-selected="false" disabled>Disabled</button>
    <button class="nav-link" id="v-pills-messages-tab" data-bs-toggle="pill" data-bs-target="#v-pills-messages" type="button" role="tab" aria-controls="v-pills-messages" aria-selected="false">Messages</button>
    <button class="nav-link" id="v-pills-settings-tab" data-bs-toggle="pill" data-bs-target="#v-pills-settings" type="button" role="tab" aria-controls="v-pills-settings" aria-selected="false">Settings</button>
  </div>
  <div class="tab-content" id="v-pills-tabContent">
    <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel" aria-labelledby="v-pills-home-tab" tabindex="0">...</div>
    <div class="tab-pane fade" id="v-pills-profile" role="tabpanel" aria-labelledby="v-pills-profile-tab" tabindex="0">...</div>
    <div class="tab-pane fade" id="v-pills-disabled" role="tabpanel" aria-labelledby="v-pills-disabled-tab" tabindex="0">...</div>
    <div class="tab-pane fade" id="v-pills-messages" role="tabpanel" aria-labelledby="v-pills-messages-tab" tabindex="0">...</div>
    <div class="tab-pane fade" id="v-pills-settings" role="tabpanel" aria-labelledby="v-pills-settings-tab" tabindex="0">...</div>
  </div>
</div>

```

### Accessibility [Link to this section: Accessibility](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#accessibility)

Dynamic tabbed interfaces, as described in the [ARIA Authoring Practices Guide tabs pattern](https://www.w3.org/WAI/ARIA/apg/patterns/tabpanel/), require `role="tablist"`, `role="tab"`, `role="tabpanel"`, and additional `aria-` attributes in order to convey their structure, functionality, and current state to users of assistive technologies (such as screen readers). As a best practice, we recommend using `<button>` elements for the tabs, as these are controls that trigger a dynamic change, rather than links that navigate to a new page or location.

In line with the ARIA Authoring Practices pattern, only the currently active tab receives keyboard focus. When the JavaScript plugin is initialized, it will set `tabindex="-1"` on all inactive tab controls. Once the currently active tab has focus, the cursor keys activate the previous/next tab. The `Home` and `End` keys activate the first and last tabs, respectively. The plugin will change the [roving `tabindex`](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/) accordingly. However, note that the JavaScript plugin does not distinguish between horizontal and vertical tab lists when it comes to cursor key interactions: regardless of the tab list’s orientation, both the up _and_ left cursor go to the previous tab, and down _and_ right cursor go to the next tab.

In general, to facilitate keyboard navigation, it’s recommended to make the tab panels themselves focusable as well, unless the first element containing meaningful content inside the tab panel is already focusable. The JavaScript plugin does not try to handle this aspect—where appropriate, you’ll need to explicitly make your tab panels focusable by adding `tabindex="0"` in your markup.

The tab JavaScript plugin **does not** support tabbed interfaces that contain dropdown menus, as these cause both usability and accessibility issues. From a usability perspective, the fact that the currently displayed tab’s trigger element is not immediately visible (as it’s inside the closed dropdown menu) can cause confusion. From an accessibility point of view, there is currently no sensible way to map this sort of construct to a standard WAI ARIA pattern, meaning that it cannot be easily made understandable to users of assistive technologies.

### Using data attributes [Link to this section: Using data attributes](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#using-data-attributes)

You can activate a tab or pill navigation without writing any JavaScript by simply specifying `data-bs-toggle="tab"` or `data-bs-toggle="pill"` on an element. Use these data attributes on `.nav-tabs` or `.nav-pills`.

```html
<!-- Nav tabs -->
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home" type="button" role="tab" aria-controls="home" aria-selected="true">Home</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile" type="button" role="tab" aria-controls="profile" aria-selected="false">Profile</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="messages-tab" data-bs-toggle="tab" data-bs-target="#messages" type="button" role="tab" aria-controls="messages" aria-selected="false">Messages</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="settings-tab" data-bs-toggle="tab" data-bs-target="#settings" type="button" role="tab" aria-controls="settings" aria-selected="false">Settings</button>
  </li>
</ul>

<!-- Tab panes -->
<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab" tabindex="0">...</div>
  <div class="tab-pane" id="profile" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">...</div>
  <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab" tabindex="0">...</div>
  <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab" tabindex="0">...</div>
</div>

```

### Via JavaScript [Link to this section: Via JavaScript](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#via-javascript)

Enable tabbable tabs via JavaScript (each tab needs to be activated individually):

```js
const triggerTabList = document.querySelectorAll('#myTab button')
triggerTabList.forEach(triggerEl => {
  const tabTrigger = new bootstrap.Tab(triggerEl)

  triggerEl.addEventListener('click', event => {
    event.preventDefault()
    tabTrigger.show()
  })
})

```

You can activate individual tabs in several ways:

```js
const triggerEl = document.querySelector('#myTab button[data-bs-target="#profile"]')
bootstrap.Tab.getInstance(triggerEl).show() // Select tab by name

const triggerFirstTabEl = document.querySelector('#myTab li:first-child button')
bootstrap.Tab.getInstance(triggerFirstTabEl).show() // Select first tab

```

### Fade effect [Link to this section: Fade effect](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#fade-effect)

To make tabs fade in, add `.fade` to each `.tab-pane`. The first tab pane must also have `.show` to make the initial content visible.

```html
<div class="tab-content">
  <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="profile" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="messages" role="tabpanel" aria-labelledby="messages-tab" tabindex="0">...</div>
  <div class="tab-pane fade" id="settings" role="tabpanel" aria-labelledby="settings-tab" tabindex="0">...</div>
</div>

```

### Methods [Link to this section: Methods](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#methods)

**All API methods are asynchronous and start a transition.** They return to the caller as soon as the transition is started, but before it ends. In addition, a method call on a transitioning component will be ignored. [Learn more in our JavaScript docs.](https://getbootstrap.com/docs/5.3/getting-started/javascript/#asynchronous-functions-and-transitions)

Activates your content as a tab element.

You can create a tab instance with the constructor, for example:

```js
const bsTab = new bootstrap.Tab('#myTab')

```

| Method | Description |
| --- | --- |
| `dispose` | Destroys an element’s tab. |
| `getInstance` | Static method which allows you to get the tab instance associated with a DOM element, you can use it like this: `bootstrap.Tab.getInstance(element)`. |
| `getOrCreateInstance` | Static method which returns a tab instance associated to a DOM element or create a new one in case it wasn’t initialized. You can use it like this: `bootstrap.Tab.getOrCreateInstance(element)`. |
| `show` | Selects the given tab and shows its associated pane. Any other tab that was previously selected becomes unselected and its associated pane is hidden. **Returns to the caller before the tab pane has actually been shown** (i.e. before the `shown.bs.tab` event occurs). |

### Events [Link to this section: Events](https://getbootstrap.com/docs/5.3/components/navs-tabs/\#events)

When showing a new tab, the events fire in the following order:

1. `hide.bs.tab` (on the current active tab)
2. `show.bs.tab` (on the to-be-shown tab)
3. `hidden.bs.tab` (on the previous active tab, the same one as for the `hide.bs.tab` event)
4. `shown.bs.tab` (on the newly-active just-shown tab, the same one as for the `show.bs.tab` event)

If no tab was already active, then the `hide.bs.tab` and `hidden.bs.tab` events will not be fired.

| Event type | Description |
| --- | --- |
| `hide.bs.tab` | This event fires when a new tab is to be shown (and thus the previous active tab is to be hidden). Use `event.target` and `event.relatedTarget` to target the current active tab and the new soon-to-be-active tab, respectively. |
| `hidden.bs.tab` | This event fires after a new tab is shown (and thus the previous active tab is hidden). Use `event.target` and `event.relatedTarget` to target the previous active tab and the new active tab, respectively. |
| `show.bs.tab` | This event fires on tab show, but before the new tab has been shown. Use `event.target` and `event.relatedTarget` to target the active tab and the previous active tab (if available) respectively. |
| `shown.bs.tab` | This event fires on tab show after a tab has been shown. Use `event.target` and `event.relatedTarget` to target the active tab and the previous active tab (if available) respectively. |

```js
const tabEl = document.querySelector('button[data-bs-toggle="tab"]')
tabEl.addEventListener('shown.bs.tab', event => {
  event.target // newly activated tab
  event.relatedTarget // previous active tab
})

```