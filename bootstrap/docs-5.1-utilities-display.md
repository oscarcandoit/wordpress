---
url: https://getbootstrap.com/docs/5.1/utilities/display
scraped_at: 2025-10-20T02:38:31.781Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/utilities/display/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/utilities/display/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/utilities/display.md "View and edit this file on GitHub")

# Display property

Quickly and responsively toggle the display value of components and more with our display utilities. Includes support for some of the more common values, as well as some extras for controlling display when printing.

**On this page**

## How it works [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#how-it-works)

Change the value of the [`display` property](https://developer.mozilla.org/en-US/docs/Web/CSS/display) with our responsive display utility classes. We purposely support only a subset of all possible values for `display`. Classes can be combined for various effects as you need.

## Notation [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#notation)

Display utility classes that apply to all [breakpoints](https://getbootstrap.com/docs/5.1/layout/breakpoints/), from `xs` to `xxl`, have no breakpoint abbreviation in them. This is because those classes are applied from `min-width: 0;` and up, and thus are not bound by a media query. The remaining breakpoints, however, do include a breakpoint abbreviation.

As such, the classes are named using the format:

- `.d-{value}` for `xs`
- `.d-{breakpoint}-{value}` for `sm`, `md`, `lg`, `xl`, and `xxl`.

Where _value_ is one of:

- `none`
- `inline`
- `inline-block`
- `block`
- `grid`
- `table`
- `table-cell`
- `table-row`
- `flex`
- `inline-flex`

The display values can be altered by changing the `$displays` variable and recompiling the SCSS.

The media queries affect screen widths with the given breakpoint _or larger_. For example, `.d-lg-none` sets `display: none;` on `lg`, `xl`, and `xxl` screens.

## Examples [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#examples)

d-inline

d-inline

Copy

```html
<div class="d-inline p-2 bg-primary text-white">d-inline</div>
<div class="d-inline p-2 bg-dark text-white">d-inline</div>
```

d-blockd-block

Copy

```html
<span class="d-block p-2 bg-primary text-white">d-block</span>
<span class="d-block p-2 bg-dark text-white">d-block</span>
```

## Hiding elements [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#hiding-elements)

For faster mobile-friendly development, use responsive display classes for showing and hiding elements by device. Avoid creating entirely different versions of the same site, instead hide elements responsively for each screen size.

To hide elements simply use the `.d-none` class or one of the `.d-{sm,md,lg,xl,xxl}-none` classes for any responsive screen variation.

To show an element only on a given interval of screen sizes you can combine one `.d-*-none` class with a `.d-*-*` class, for example `.d-none .d-md-block .d-xl-none .d-xxl-none` will hide the element for all screen sizes except on medium and large devices.

| Screen size | Class |
| --- | --- |
| Hidden on all | `.d-none` |
| Hidden only on xs | `.d-none .d-sm-block` |
| Hidden only on sm | `.d-sm-none .d-md-block` |
| Hidden only on md | `.d-md-none .d-lg-block` |
| Hidden only on lg | `.d-lg-none .d-xl-block` |
| Hidden only on xl | `.d-xl-none .d-xxl-block` |
| Hidden only on xxl | `.d-xxl-none` |
| Visible on all | `.d-block` |
| Visible only on xs | `.d-block .d-sm-none` |
| Visible only on sm | `.d-none .d-sm-block .d-md-none` |
| Visible only on md | `.d-none .d-md-block .d-lg-none` |
| Visible only on lg | `.d-none .d-lg-block .d-xl-none` |
| Visible only on xl | `.d-none .d-xl-block .d-xxl-none` |
| Visible only on xxl | `.d-none .d-xxl-block` |

hide on lg and wider screens

hide on screens smaller than lg

Copy

```html
<div class="d-lg-none">hide on lg and wider screens</div>
<div class="d-none d-lg-block">hide on screens smaller than lg</div>
```

## Display in print [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#display-in-print)

Change the `display` value of elements when printing with our print display utility classes. Includes support for the same `display` values as our responsive `.d-*` utilities.

- `.d-print-none`
- `.d-print-inline`
- `.d-print-inline-block`
- `.d-print-block`
- `.d-print-grid`
- `.d-print-table`
- `.d-print-table-row`
- `.d-print-table-cell`
- `.d-print-flex`
- `.d-print-inline-flex`

The print and display classes can be combined.

Screen Only (Hide on print only)

Print Only (Hide on screen only)

Hide up to large on screen, but always show on print

Copy

```html
<div class="d-print-none">Screen Only (Hide on print only)</div>
<div class="d-none d-print-block">Print Only (Hide on screen only)</div>
<div class="d-none d-lg-block d-print-block">Hide up to large on screen, but always show on print</div>
```

## Sass [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#sass)

### Utilities API [Anchor](https://getbootstrap.com/docs/5.1/utilities/display/\#utilities-api)

Display utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.1/utilities/api/#using-the-api)

Copy

```scss
    "display": (
      responsive: true,
      print: true,
      property: display,
      class: d,
      values: inline inline-block block grid table table-row table-cell flex inline-flex none
    ),

```