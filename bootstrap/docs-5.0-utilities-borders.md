---
url: https://getbootstrap.com/docs/5.0/utilities/borders
scraped_at: 2025-10-20T02:39:01.246Z
---

[Skip to main content](https://getbootstrap.com/docs/5.0/utilities/borders/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.0/utilities/borders/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.0.2/site/content/docs/5.0/utilities/borders.md "View and edit this file on GitHub")

# Borders

Use border utilities to quickly style the border and border-radius of an element. Great for images, buttons, or any other element.

**On this page**

## Border [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#border)

Use border utilities to add or remove an element’s borders. Choose from all borders or one at a time.

### Additive [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#additive)

Copy

```html
<span class="border"></span>
<span class="border-top"></span>
<span class="border-end"></span>
<span class="border-bottom"></span>
<span class="border-start"></span>
```

### Subtractive [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#subtractive)

Copy

```html
<span class="border-0"></span>
<span class="border-top-0"></span>
<span class="border-end-0"></span>
<span class="border-bottom-0"></span>
<span class="border-start-0"></span>
```

## Border color [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#border-color)

Change the border color using utilities built on our theme colors.

Copy

```html
<span class="border border-primary"></span>
<span class="border border-secondary"></span>
<span class="border border-success"></span>
<span class="border border-danger"></span>
<span class="border border-warning"></span>
<span class="border border-info"></span>
<span class="border border-light"></span>
<span class="border border-dark"></span>
<span class="border border-white"></span>
```

## Border-width [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#border-width)

Copy

```html
<span class="border border-1"></span>
<span class="border border-2"></span>
<span class="border border-3"></span>
<span class="border border-4"></span>
<span class="border border-5"></span>
```

## Border-radius [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#border-radius)

Add classes to an element to easily round its corners.

Example rounded image75x75Example top rounded image75x75Example right rounded image75x75Example bottom rounded image75x75Example left rounded image75x75Completely round image75x75Rounded pill image150x75

Copy

```html
<img src="..." class="rounded" alt="...">
<img src="..." class="rounded-top" alt="...">
<img src="..." class="rounded-end" alt="...">
<img src="..." class="rounded-bottom" alt="...">
<img src="..." class="rounded-start" alt="...">
<img src="..." class="rounded-circle" alt="...">
<img src="..." class="rounded-pill" alt="...">
```

### Sizes [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#sizes)

Use the scaling classes for larger or smaller rounded corners. Sizes range from `0` to `3`, and can be configured by modifying the utilities API.

Example non-rounded image75x75Example small rounded image75x75Example default rounded image75x75Example large rounded image75x75

Copy

```html
<img src="..." class="rounded-0" alt="...">
<img src="..." class="rounded-1" alt="...">
<img src="..." class="rounded-2" alt="...">
<img src="..." class="rounded-3" alt="...">
```

## Sass [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#sass)

### Variables [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#variables)

Copy

```scss
$border-width:                1px;
$border-widths: (
  1: 1px,
  2: 2px,
  3: 3px,
  4: 4px,
  5: 5px
);

$border-color:                $gray-300;

```

Copy

```scss
$border-radius:               .25rem;
$border-radius-sm:            .2rem;
$border-radius-lg:            .3rem;
$border-radius-pill:          50rem;

```

### Mixins [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#mixins)

Copy

```scss
@mixin border-radius($radius: $border-radius, $fallback-border-radius: false) {
  @if $enable-rounded {
    border-radius: valid-radius($radius);
  }
  @else if $fallback-border-radius != false {
    border-radius: $fallback-border-radius;
  }
}

@mixin border-top-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-top-left-radius: valid-radius($radius);
    border-top-right-radius: valid-radius($radius);
  }
}

@mixin border-end-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-top-right-radius: valid-radius($radius);
    border-bottom-right-radius: valid-radius($radius);
  }
}

@mixin border-bottom-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-bottom-right-radius: valid-radius($radius);
    border-bottom-left-radius: valid-radius($radius);
  }
}

@mixin border-start-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-top-left-radius: valid-radius($radius);
    border-bottom-left-radius: valid-radius($radius);
  }
}

@mixin border-top-start-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-top-left-radius: valid-radius($radius);
  }
}

@mixin border-top-end-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-top-right-radius: valid-radius($radius);
  }
}

@mixin border-bottom-end-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-bottom-right-radius: valid-radius($radius);
  }
}

@mixin border-bottom-start-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-bottom-left-radius: valid-radius($radius);
  }
}

```

### Utilities API [Anchor](https://getbootstrap.com/docs/5.0/utilities/borders/\#utilities-api)

Border utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.0/utilities/api/#using-the-api)

Copy

```scss
    "border": (
      property: border,
      values: (
        null: $border-width solid $border-color,
        0: 0,
      )
    ),
    "border-top": (
      property: border-top,
      values: (
        null: $border-width solid $border-color,
        0: 0,
      )
    ),
    "border-end": (
      property: border-right,
      class: border-end,
      values: (
        null: $border-width solid $border-color,
        0: 0,
      )
    ),
    "border-bottom": (
      property: border-bottom,
      values: (
        null: $border-width solid $border-color,
        0: 0,
      )
    ),
    "border-start": (
      property: border-left,
      class: border-start,
      values: (
        null: $border-width solid $border-color,
        0: 0,
      )
    ),
    "border-color": (
      property: border-color,
      class: border,
      values: map-merge($theme-colors, ("white": $white))
    ),
    "border-width": (
      property: border-width,
      class: border,
      values: $border-widths
    ),

```

Copy

```scss
    "rounded": (
      property: border-radius,
      class: rounded,
      values: (
        null: $border-radius,
        0: 0,
        1: $border-radius-sm,
        2: $border-radius,
        3: $border-radius-lg,
        circle: 50%,
        pill: $border-radius-pill
      )
    ),
    "rounded-top": (
      property: border-top-left-radius border-top-right-radius,
      class: rounded-top,
      values: (null: $border-radius)
    ),
    "rounded-end": (
      property: border-top-right-radius border-bottom-right-radius,
      class: rounded-end,
      values: (null: $border-radius)
    ),
    "rounded-bottom": (
      property: border-bottom-right-radius border-bottom-left-radius,
      class: rounded-bottom,
      values: (null: $border-radius)
    ),
    "rounded-start": (
      property: border-bottom-left-radius border-top-left-radius,
      class: rounded-start,
      values: (null: $border-radius)
    ),

```