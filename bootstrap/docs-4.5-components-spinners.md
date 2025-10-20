---
url: https://getbootstrap.com/docs/4.5/components/spinners
scraped_at: 2025-10-20T02:40:54.318Z
---

[Skip to main content](https://getbootstrap.com/docs/4.5/components/spinners/#content) [Skip to docs navigation](https://getbootstrap.com/docs/4.5/components/spinners/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

```

```

Menu

[View on GitHub](https://github.com/twbs/bootstrap/blob/v4.5.3/site/docs/4.5/components/spinners.md "View and edit this file on GitHub")

# Spinners

Indicate the loading state of a component or page with Bootstrap spinners, built entirely with HTML, CSS, and no JavaScript.

## About [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#about)

Bootstrap “spinners” can be used to show the loading state in your projects. They’re built only with HTML and CSS, meaning you don’t need any JavaScript to create them. You will, however, need some custom JavaScript to toggle their visibility. Their appearance, alignment, and sizing can be easily customized with our amazing utility classes.

For accessibility purposes, each loader here includes `role="status"` and a nested `<span class="sr-only">Loading...</span>`.

## Border spinner [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#border-spinner)

Use the border spinners for a lightweight loading indicator.

Loading...

Copy

```html
<div class="spinner-border" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

### Colors [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#colors)

The border spinner uses `currentColor` for its `border-color`, meaning you can customize the color with [text color utilities](https://getbootstrap.com/docs/4.5/utilities/colors/). You can use any of our text color utilities on the standard spinner.

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Copy

```html
<div class="spinner-border text-primary" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-secondary" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-success" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-danger" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-warning" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-info" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-light" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-border text-dark" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

**Why not use `border-color` utilities?** Each border spinner specifies a `transparent` border for at least one side, so `.border-{color}` utilities would override that.

## Growing spinner [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#growing-spinner)

If you don’t fancy a border spinner, switch to the grow spinner. While it doesn’t technically spin, it does repeatedly grow!

Loading...

Copy

```html
<div class="spinner-grow" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

Once again, this spinner is built with `currentColor`, so you can easily change its appearance with [text color utilities](https://getbootstrap.com/docs/4.5/utilities/colors/). Here it is in blue, along with the supported variants.

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Loading...

Copy

```html
<div class="spinner-grow text-primary" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-secondary" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-success" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-danger" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-warning" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-info" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-light" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow text-dark" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

## Alignment [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#alignment)

Spinners in Bootstrap are built with `rem` s, `currentColor`, and `display: inline-flex`. This means they can easily be resized, recolored, and quickly aligned.

### Margin [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#margin)

Use [margin utilities](https://getbootstrap.com/docs/4.5/utilities/spacing/) like `.m-5` for easy spacing.

Loading...

Copy

```html
<div class="spinner-border m-5" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

### Placement [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#placement)

Use [flexbox utilities](https://getbootstrap.com/docs/4.5/utilities/flex/), [float utilities](https://getbootstrap.com/docs/4.5/utilities/float/), or [text alignment](https://getbootstrap.com/docs/4.5/content/typography/) utilities to place spinners exactly where you need them in any situation.

#### Flex [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#flex)

Loading...

Copy

```html
<div class="d-flex justify-content-center">
  <div class="spinner-border" role="status">
    <span class="sr-only">Loading...</span>
  </div>
</div>
```

**Loading...**

Copy

```html
<div class="d-flex align-items-center">
  <strong>Loading...</strong>
  <div class="spinner-border ml-auto" role="status" aria-hidden="true"></div>
</div>
```

#### Floats [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#floats)

Loading...

Copy

```html
<div class="clearfix">
  <div class="spinner-border float-right" role="status">
    <span class="sr-only">Loading...</span>
  </div>
</div>
```

#### Text align [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#text-align)

Loading...

Copy

```html
<div class="text-center">
  <div class="spinner-border" role="status">
    <span class="sr-only">Loading...</span>
  </div>
</div>
```

## Size [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#size)

Add `.spinner-border-sm` and `.spinner-grow-sm` to make a smaller spinner that can quickly be used within other components.

Loading...

Loading...

Copy

```html
<div class="spinner-border spinner-border-sm" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow spinner-grow-sm" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

Or, use custom CSS or inline styles to change the dimensions as needed.

Loading...

Loading...

Copy

```html
<div class="spinner-border" style="width: 3rem; height: 3rem;" role="status">
  <span class="sr-only">Loading...</span>
</div>
<div class="spinner-grow" style="width: 3rem; height: 3rem;" role="status">
  <span class="sr-only">Loading...</span>
</div>
```

## Buttons [Anchor](https://getbootstrap.com/docs/4.5/components/spinners/\#buttons)

Use spinners within buttons to indicate an action is currently processing or taking place. You may also swap the text out of the spinner element and utilize button text as needed.

Loading...
Loading...

Copy

```html
<button class="btn btn-primary" type="button" disabled>
  <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
  <span class="sr-only">Loading...</span>
</button>
<button class="btn btn-primary" type="button" disabled>
  <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
  Loading...
</button>
```

Loading...
Loading...

Copy

```html
<button class="btn btn-primary" type="button" disabled>
  <span class="spinner-grow spinner-grow-sm" role="status" aria-hidden="true"></span>
  <span class="sr-only">Loading...</span>
</button>
<button class="btn btn-primary" type="button" disabled>
  <span class="spinner-grow spinner-grow-sm" role="status" aria-hidden="true"></span>
  Loading...
</button>
```