---
url: https://getbootstrap.com/docs/5.2/components/pagination
scraped_at: 2025-10-20T02:41:03.924Z
---

[Skip to main content](https://getbootstrap.com/docs/5.2/components/pagination/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.2/components/pagination/#bd-docs-nav)

Check

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.2.3/site/content/docs/5.2/components/pagination.md "View and edit this file on GitHub")

# Pagination

Documentation and examples for showing pagination to indicate a series of related content exists across multiple pages.

On this page
**On this page**

* * *

## Overview [Link to this section: Overview](https://getbootstrap.com/docs/5.2/components/pagination/\#overview)

We use a large block of connected links for our pagination, making links hard to miss and easily scalable—all while providing large hit areas. Pagination is built with list HTML elements so screen readers can announce the number of available links. Use a wrapping `<nav>` element to identify it as a navigation section to screen readers and other assistive technologies.

In addition, as pages likely have more than one such navigation section, it’s advisable to provide a descriptive `aria-label` for the `<nav>` to reflect its purpose. For example, if the pagination component is used to navigate between a set of search results, an appropriate label could be `aria-label="Search results pages"`.

html

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

## Working with icons [Link to this section: Working with icons](https://getbootstrap.com/docs/5.2/components/pagination/\#working-with-icons)

Looking to use an icon or symbol in place of text for some pagination links? Be sure to provide proper screen reader support with `aria` attributes.

html

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </a>
    </li>
  </ul>
</nav>
```

## Disabled and active states [Link to this section: Disabled and active states](https://getbootstrap.com/docs/5.2/components/pagination/\#disabled-and-active-states)

Pagination links are customizable for different circumstances. Use `.disabled` for links that appear un-clickable and `.active` to indicate the current page.

While the `.disabled` class uses `pointer-events: none` to _try_ to disable the link functionality of `<a>` s, that CSS property is not yet standardized and doesn’t account for keyboard navigation. As such, you should always add `tabindex="-1"` on disabled links and use custom JavaScript to fully disable their functionality.

html

```html
<nav aria-label="...">
  <ul class="pagination">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item active" aria-current="page">
      <a class="page-link" href="#">2</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

You can optionally swap out active or disabled anchors for `<span>`, or omit the anchor in the case of the prev/next arrows, to remove click functionality and prevent keyboard focus while retaining intended styles.

html

```html
<nav aria-label="...">
  <ul class="pagination">
    <li class="page-item disabled">
      <span class="page-link">Previous</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item active" aria-current="page">
      <span class="page-link">2</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

## Sizing [Link to this section: Sizing](https://getbootstrap.com/docs/5.2/components/pagination/\#sizing)

Fancy larger or smaller pagination? Add `.pagination-lg` or `.pagination-sm` for additional sizes.

html

```html
<nav aria-label="...">
  <ul class="pagination pagination-lg">
    <li class="page-item active" aria-current="page">
      <span class="page-link">1</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
  </ul>
</nav>
```

html

```html
<nav aria-label="...">
  <ul class="pagination pagination-sm">
    <li class="page-item active" aria-current="page">
      <span class="page-link">1</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
  </ul>
</nav>
```

## Alignment [Link to this section: Alignment](https://getbootstrap.com/docs/5.2/components/pagination/\#alignment)

Change the alignment of pagination components with [flexbox utilities](https://getbootstrap.com/docs/5.2/utilities/flex/). For example, with `.justify-content-center`:

html

```html
<nav aria-label="Page navigation example">
  <ul class="pagination justify-content-center">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

Or with `.justify-content-end`:

html

```html
<nav aria-label="Page navigation example">
  <ul class="pagination justify-content-end">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.2/components/pagination/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.2/components/pagination/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, pagination now uses local CSS variables on `.pagination` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

```scss
  --#{$prefix}pagination-padding-x: #{$pagination-padding-x};
  --#{$prefix}pagination-padding-y: #{$pagination-padding-y};
  @include rfs($pagination-font-size, --#{$prefix}pagination-font-size);
  --#{$prefix}pagination-color: #{$pagination-color};
  --#{$prefix}pagination-bg: #{$pagination-bg};
  --#{$prefix}pagination-border-width: #{$pagination-border-width};
  --#{$prefix}pagination-border-color: #{$pagination-border-color};
  --#{$prefix}pagination-border-radius: #{$pagination-border-radius};
  --#{$prefix}pagination-hover-color: #{$pagination-hover-color};
  --#{$prefix}pagination-hover-bg: #{$pagination-hover-bg};
  --#{$prefix}pagination-hover-border-color: #{$pagination-hover-border-color};
  --#{$prefix}pagination-focus-color: #{$pagination-focus-color};
  --#{$prefix}pagination-focus-bg: #{$pagination-focus-bg};
  --#{$prefix}pagination-focus-box-shadow: #{$pagination-focus-box-shadow};
  --#{$prefix}pagination-active-color: #{$pagination-active-color};
  --#{$prefix}pagination-active-bg: #{$pagination-active-bg};
  --#{$prefix}pagination-active-border-color: #{$pagination-active-border-color};
  --#{$prefix}pagination-disabled-color: #{$pagination-disabled-color};
  --#{$prefix}pagination-disabled-bg: #{$pagination-disabled-bg};
  --#{$prefix}pagination-disabled-border-color: #{$pagination-disabled-border-color};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.2/components/pagination/\#sass-variables)

```scss
$pagination-padding-y:              .375rem;
$pagination-padding-x:              .75rem;
$pagination-padding-y-sm:           .25rem;
$pagination-padding-x-sm:           .5rem;
$pagination-padding-y-lg:           .75rem;
$pagination-padding-x-lg:           1.5rem;

$pagination-font-size:              $font-size-base;

$pagination-color:                  var(--#{$prefix}link-color);
$pagination-bg:                     $white;
$pagination-border-radius:          $border-radius;
$pagination-border-width:           $border-width;
$pagination-margin-start:           ($pagination-border-width * -1);
$pagination-border-color:           $gray-300;

$pagination-focus-color:            var(--#{$prefix}link-hover-color);
$pagination-focus-bg:               $gray-200;
$pagination-focus-box-shadow:       $input-btn-focus-box-shadow;
$pagination-focus-outline:          0;

$pagination-hover-color:            var(--#{$prefix}link-hover-color);
$pagination-hover-bg:               $gray-200;
$pagination-hover-border-color:     $gray-300;

$pagination-active-color:           $component-active-color;
$pagination-active-bg:              $component-active-bg;
$pagination-active-border-color:    $pagination-active-bg;

$pagination-disabled-color:         $gray-600;
$pagination-disabled-bg:            $white;
$pagination-disabled-border-color:  $gray-300;

$pagination-transition:              color .15s ease-in-out, background-color .15s ease-in-out, border-color .15s ease-in-out, box-shadow .15s ease-in-out;

$pagination-border-radius-sm:       $border-radius-sm;
$pagination-border-radius-lg:       $border-radius-lg;

```

### Sass mixins [Link to this section: Sass mixins](https://getbootstrap.com/docs/5.2/components/pagination/\#sass-mixins)

```scss
@mixin pagination-size($padding-y, $padding-x, $font-size, $border-radius) {
  --#{$prefix}pagination-padding-x: #{$padding-x};
  --#{$prefix}pagination-padding-y: #{$padding-y};
  @include rfs($font-size, --#{$prefix}pagination-font-size);
  --#{$prefix}pagination-border-radius: #{$border-radius};
}

```