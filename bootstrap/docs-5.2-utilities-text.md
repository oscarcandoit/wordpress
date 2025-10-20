---
url: https://getbootstrap.com/docs/5.2/utilities/text
scraped_at: 2025-10-20T02:38:41.085Z
---

[Skip to main content](https://getbootstrap.com/docs/5.2/utilities/text/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.2/utilities/text/#bd-docs-nav)

Check

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.2.3/site/content/docs/5.2/utilities/text.md "View and edit this file on GitHub")

# Text

Documentation and examples for common text utilities to control alignment, wrapping, weight, and more.

On this page
**On this page**

* * *

## Text alignment [Link to this section: Text alignment](https://getbootstrap.com/docs/5.2/utilities/text/\#text-alignment)

Easily realign text to components with text alignment classes. For start, end, and center alignment, responsive classes are available that use the same viewport width breakpoints as the grid system.

Start aligned text on all viewport sizes.

Center aligned text on all viewport sizes.

End aligned text on all viewport sizes.

Start aligned text on viewports sized SM (small) or wider.

Start aligned text on viewports sized MD (medium) or wider.

Start aligned text on viewports sized LG (large) or wider.

Start aligned text on viewports sized XL (extra-large) or wider.

html

```html
<p class="text-start">Start aligned text on all viewport sizes.</p>
<p class="text-center">Center aligned text on all viewport sizes.</p>
<p class="text-end">End aligned text on all viewport sizes.</p>

<p class="text-sm-start">Start aligned text on viewports sized SM (small) or wider.</p>
<p class="text-md-start">Start aligned text on viewports sized MD (medium) or wider.</p>
<p class="text-lg-start">Start aligned text on viewports sized LG (large) or wider.</p>
<p class="text-xl-start">Start aligned text on viewports sized XL (extra-large) or wider.</p>
```

Note that we don’t provide utility classes for justified text. While, aesthetically, justified text might look more appealing, it does make word-spacing more random and therefore harder to read.

## Text wrapping and overflow [Link to this section: Text wrapping and overflow](https://getbootstrap.com/docs/5.2/utilities/text/\#text-wrapping-and-overflow)

Wrap text with a `.text-wrap` class.

This text should wrap.

html

```html
<div class="badge bg-primary text-wrap" style="width: 6rem;">
  This text should wrap.
</div>
```

Prevent text from wrapping with a `.text-nowrap` class.

This text should overflow the parent.

html

```html
<div class="text-nowrap bg-light border" style="width: 8rem;">
  This text should overflow the parent.
</div>
```

## Word break [Link to this section: Word break](https://getbootstrap.com/docs/5.2/utilities/text/\#word-break)

Prevent long strings of text from breaking your components’ layout by using `.text-break` to set `word-wrap: break-word` and `word-break: break-word`. We use `word-wrap` instead of the more common `overflow-wrap` for wider browser support, and add the deprecated `word-break: break-word` to avoid issues with flex containers.

mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm

html

```html
<p class="text-break">mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm</p>
```

Note that [breaking words isn’t possible in Arabic](https://rtlstyling.com/posts/rtl-styling#3.-line-break), which is the most used RTL language. Therefore `.text-break` is removed from our RTL compiled CSS.

## Text transform [Link to this section: Text transform](https://getbootstrap.com/docs/5.2/utilities/text/\#text-transform)

Transform text in components with text capitalization classes.

Lowercased text.

Uppercased text.

CapiTaliZed text.

html

```html
<p class="text-lowercase">Lowercased text.</p>
<p class="text-uppercase">Uppercased text.</p>
<p class="text-capitalize">CapiTaliZed text.</p>
```

Note how `.text-capitalize` only changes the first letter of each word, leaving the case of any other letters unaffected.

## Font size [Link to this section: Font size](https://getbootstrap.com/docs/5.2/utilities/text/\#font-size)

Quickly change the `font-size` of text. While our heading classes (e.g., `.h1`– `.h6`) apply `font-size`, `font-weight`, and `line-height`, these utilities _only_ apply `font-size`. Sizing for these utilities matches HTML’s heading elements, so as the number increases, their size decreases.

.fs-1 text

.fs-2 text

.fs-3 text

.fs-4 text

.fs-5 text

.fs-6 text

html

```html
<p class="fs-1">.fs-1 text</p>
<p class="fs-2">.fs-2 text</p>
<p class="fs-3">.fs-3 text</p>
<p class="fs-4">.fs-4 text</p>
<p class="fs-5">.fs-5 text</p>
<p class="fs-6">.fs-6 text</p>
```

Customize your available `font-size` s by modifying the `$font-sizes` Sass map.

## Font weight and italics [Link to this section: Font weight and italics](https://getbootstrap.com/docs/5.2/utilities/text/\#font-weight-and-italics)

Quickly change the `font-weight` or `font-style` of text with these utilities. `font-style` utilities are abbreviated as `.fst-*` and `font-weight` utilities are abbreviated as `.fw-*`.

Bold text.

Bolder weight text (relative to the parent element).

Semibold weight text.

Normal weight text.

Light weight text.

Lighter weight text (relative to the parent element).

Italic text.

Text with normal font style

html

```html
<p class="fw-bold">Bold text.</p>
<p class="fw-bolder">Bolder weight text (relative to the parent element).</p>
<p class="fw-semibold">Semibold weight text.</p>
<p class="fw-normal">Normal weight text.</p>
<p class="fw-light">Light weight text.</p>
<p class="fw-lighter">Lighter weight text (relative to the parent element).</p>
<p class="fst-italic">Italic text.</p>
<p class="fst-normal">Text with normal font style</p>
```

## Line height [Link to this section: Line height](https://getbootstrap.com/docs/5.2/utilities/text/\#line-height)

Change the line height with `.lh-*` utilities.

This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.

This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.

This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.

This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.

html

```html
<p class="lh-1">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
<p class="lh-sm">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
<p class="lh-base">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
<p class="lh-lg">This is a long paragraph written to show how the line-height of an element is affected by our utilities. Classes are applied to the element itself or sometimes the parent element. These classes can be customized as needed with our utility API.</p>
```

## Monospace [Link to this section: Monospace](https://getbootstrap.com/docs/5.2/utilities/text/\#monospace)

Change a selection to our monospace font stack with `.font-monospace`.

This is in monospace

html

```html
<p class="font-monospace">This is in monospace</p>
```

## Reset color [Link to this section: Reset color](https://getbootstrap.com/docs/5.2/utilities/text/\#reset-color)

Reset a text or link’s color with `.text-reset`, so that it inherits the color from its parent.

Muted text with a [reset link](https://getbootstrap.com/docs/5.2/utilities/text/#).

html

```html
<p class="text-muted">
  Muted text with a <a href="#" class="text-reset">reset link</a>.
</p>
```

## Text decoration [Link to this section: Text decoration](https://getbootstrap.com/docs/5.2/utilities/text/\#text-decoration)

Decorate text in components with text decoration classes.

This text has a line underneath it.

This text has a line going through it.

[This link has its text decoration removed](https://getbootstrap.com/docs/5.2/utilities/text/#)

html

```html
<p class="text-decoration-underline">This text has a line underneath it.</p>
<p class="text-decoration-line-through">This text has a line going through it.</p>
<a href="#" class="text-decoration-none">This link has its text decoration removed</a>
```

## Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.2/utilities/text/\#sass)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.2/utilities/text/\#variables)

```scss
// stylelint-disable value-keyword-case
$font-family-sans-serif:      system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", "Noto Sans", "Liberation Sans", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
$font-family-monospace:       SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
// stylelint-enable value-keyword-case
$font-family-base:            var(--#{$prefix}font-sans-serif);
$font-family-code:            var(--#{$prefix}font-monospace);

// $font-size-root affects the value of `rem`, which is used for as well font sizes, paddings, and margins
// $font-size-base affects the font size of the body text
$font-size-root:              null;
$font-size-base:              1rem; // Assumes the browser default, typically `16px`
$font-size-sm:                $font-size-base * .875;
$font-size-lg:                $font-size-base * 1.25;

$font-weight-lighter:         lighter;
$font-weight-light:           300;
$font-weight-normal:          400;
$font-weight-semibold:        600;
$font-weight-bold:            700;
$font-weight-bolder:          bolder;

$font-weight-base:            $font-weight-normal;

$line-height-base:            1.5;
$line-height-sm:              1.25;
$line-height-lg:              2;

$h1-font-size:                $font-size-base * 2.5;
$h2-font-size:                $font-size-base * 2;
$h3-font-size:                $font-size-base * 1.75;
$h4-font-size:                $font-size-base * 1.5;
$h5-font-size:                $font-size-base * 1.25;
$h6-font-size:                $font-size-base;

```

### Maps [Link to this section: Maps](https://getbootstrap.com/docs/5.2/utilities/text/\#maps)

Font-size utilities are generated from this map, in combination with our utilities API.

```scss
$font-sizes: (
  1: $h1-font-size,
  2: $h2-font-size,
  3: $h3-font-size,
  4: $h4-font-size,
  5: $h5-font-size,
  6: $h6-font-size
);

```

### Utilities API [Link to this section: Utilities API](https://getbootstrap.com/docs/5.2/utilities/text/\#utilities-api)

Font and text utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.2/utilities/api/#using-the-api)

```scss
    "font-family": (
      property: font-family,
      class: font,
      values: (monospace: var(--#{$prefix}font-monospace))
    ),
    "font-size": (
      rfs: true,
      property: font-size,
      class: fs,
      values: $font-sizes
    ),
    "font-style": (
      property: font-style,
      class: fst,
      values: italic normal
    ),
    "font-weight": (
      property: font-weight,
      class: fw,
      values: (
        light: $font-weight-light,
        lighter: $font-weight-lighter,
        normal: $font-weight-normal,
        bold: $font-weight-bold,
        semibold: $font-weight-semibold,
        bolder: $font-weight-bolder
      )
    ),
    "line-height": (
      property: line-height,
      class: lh,
      values: (
        1: 1,
        sm: $line-height-sm,
        base: $line-height-base,
        lg: $line-height-lg,
      )
    ),
    "text-align": (
      responsive: true,
      property: text-align,
      class: text,
      values: (
        start: left,
        end: right,
        center: center,
      )
    ),
    "text-decoration": (
      property: text-decoration,
      values: none underline line-through
    ),
    "text-transform": (
      property: text-transform,
      class: text,
      values: lowercase uppercase capitalize
    ),
    "white-space": (
      property: white-space,
      class: text,
      values: (
        wrap: normal,
        nowrap: nowrap,
      )
    ),
    "word-wrap": (
      property: word-wrap word-break,
      class: text,
      values: (break: break-word),
      rtl: false
    ),

```