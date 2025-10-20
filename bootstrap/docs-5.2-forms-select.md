---
url: https://getbootstrap.com/docs/5.2/forms/select
scraped_at: 2025-10-20T02:39:20.396Z
---

[Skip to main content](https://getbootstrap.com/docs/5.2/forms/select/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.2/forms/select/#bd-docs-nav)

Check

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.2.3/site/content/docs/5.2/forms/select.md "View and edit this file on GitHub")

# Select

Customize the native `<select>` s with custom CSS that changes the element’s initial appearance.

On this page
**On this page**

* * *

## Default [Link to this section: Default](https://getbootstrap.com/docs/5.2/forms/select/\#default)

Custom `<select>` menus need only a custom class, `.form-select` to trigger the custom styles. Custom styles are limited to the `<select>`’s initial appearance and cannot modify the `<option>` s due to browser limitations.

Open this select menuOneTwoThree

html

```html
<select class="form-select" aria-label="Default select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

## Sizing [Link to this section: Sizing](https://getbootstrap.com/docs/5.2/forms/select/\#sizing)

You may also choose from small and large custom selects to match our similarly sized text inputs.

Open this select menuOneTwoThreeOpen this select menuOneTwoThree

html

```html
<select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>

<select class="form-select form-select-sm" aria-label=".form-select-sm example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

The `multiple` attribute is also supported:

Open this select menuOneTwoThree

html

```html
<select class="form-select" multiple aria-label="multiple select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

As is the `size` attribute:

Open this select menuOneTwoThree

html

```html
<select class="form-select" size="3" aria-label="size 3 select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

## Disabled [Link to this section: Disabled](https://getbootstrap.com/docs/5.2/forms/select/\#disabled)

Add the `disabled` boolean attribute on a select to give it a grayed out appearance and remove pointer events.

Open this select menuOneTwoThree

html

```html
<select class="form-select" aria-label="Disabled select example" disabled>
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

## Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.2/forms/select/\#sass)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.2/forms/select/\#variables)

```scss
$form-select-padding-y:             $input-padding-y;
$form-select-padding-x:             $input-padding-x;
$form-select-font-family:           $input-font-family;
$form-select-font-size:             $input-font-size;
$form-select-indicator-padding:     $form-select-padding-x * 3; // Extra padding for background-image
$form-select-font-weight:           $input-font-weight;
$form-select-line-height:           $input-line-height;
$form-select-color:                 $input-color;
$form-select-bg:                    $input-bg;
$form-select-disabled-color:        null;
$form-select-disabled-bg:           $gray-200;
$form-select-disabled-border-color: $input-disabled-border-color;
$form-select-bg-position:           right $form-select-padding-x center;
$form-select-bg-size:               16px 12px; // In pixels because image dimensions
$form-select-indicator-color:       $gray-800;
$form-select-indicator:             url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'><path fill='none' stroke='#{$form-select-indicator-color}' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='m2 5 6 6 6-6'/></svg>");

$form-select-feedback-icon-padding-end: $form-select-padding-x * 2.5 + $form-select-indicator-padding;
$form-select-feedback-icon-position:    center right $form-select-indicator-padding;
$form-select-feedback-icon-size:        $input-height-inner-half $input-height-inner-half;

$form-select-border-width:        $input-border-width;
$form-select-border-color:        $input-border-color;
$form-select-border-radius:       $input-border-radius;
$form-select-box-shadow:          $box-shadow-inset;

$form-select-focus-border-color:  $input-focus-border-color;
$form-select-focus-width:         $input-focus-width;
$form-select-focus-box-shadow:    0 0 0 $form-select-focus-width $input-btn-focus-color;

$form-select-padding-y-sm:        $input-padding-y-sm;
$form-select-padding-x-sm:        $input-padding-x-sm;
$form-select-font-size-sm:        $input-font-size-sm;
$form-select-border-radius-sm:    $input-border-radius-sm;

$form-select-padding-y-lg:        $input-padding-y-lg;
$form-select-padding-x-lg:        $input-padding-x-lg;
$form-select-font-size-lg:        $input-font-size-lg;
$form-select-border-radius-lg:    $input-border-radius-lg;

$form-select-transition:          $input-transition;

```