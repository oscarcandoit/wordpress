---
url: https://getbootstrap.com/docs/5.3/forms/overview
scraped_at: 2025-10-20T02:32:51.417Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/forms/overview/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/forms/overview/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/forms/overview.mdx "View and edit this file on GitHub")

# Forms

Examples and usage guidelines for form control styles, layout options, and custom components for creating a wide variety of forms.

On this page
**On this page**

* * *

[**Form control** Style textual inputs and textareas with support for multiple states.](https://getbootstrap.com/docs/5.3/forms/form-control/)

[**Select** Improve browser default select elements with a custom initial appearance.](https://getbootstrap.com/docs/5.3/forms/select/)

[**Checks & radios** Use our custom radio buttons and checkboxes in forms for selecting input options.](https://getbootstrap.com/docs/5.3/forms/checks-radios/)

[**Range** Replace browser default range inputs with our custom version.](https://getbootstrap.com/docs/5.3/forms/range/)

[**Input group** Attach labels and buttons to your inputs for increased semantic value.](https://getbootstrap.com/docs/5.3/forms/input-group/)

[**Floating labels** Create beautifully simple form labels that float over your input fields.](https://getbootstrap.com/docs/5.3/forms/floating-labels/)

[**Layout** Create inline, horizontal, or complex grid-based layouts with your forms.](https://getbootstrap.com/docs/5.3/forms/layout/)

[**Validation** Validate your forms with custom or native validation behaviors and styles.](https://getbootstrap.com/docs/5.3/forms/validation/)

## Overview [Link to this section: Overview](https://getbootstrap.com/docs/5.3/forms/overview/\#overview)

Bootstrap’s form controls expand on [our Rebooted form styles](https://getbootstrap.com/docs/5.3/content/reboot#forms) with classes. Use these classes to opt into their customized displays for a more consistent rendering across browsers and devices.

Be sure to use an appropriate `type` attribute on all inputs (e.g., `email` for email address or `number` for numerical information) to take advantage of newer input controls like email verification, number selection, and more.

Here’s a quick example to demonstrate Bootstrap’s form styles. Keep reading for documentation on required classes, form layout, and more.

Email address

We'll never share your email with anyone else.

Password

Check me out

Submit

html

```html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

## Disabled forms [Link to this section: Disabled forms](https://getbootstrap.com/docs/5.3/forms/overview/\#disabled-forms)

Add the `disabled` boolean attribute on an input to prevent user interactions and make it appear lighter.

```html
<input class="form-control" id="disabledInput" type="text" placeholder="Disabled input here..." disabled>

```

Add the `disabled` attribute to a `<fieldset>` to disable all the controls within. Browsers treat all native form controls ( `<input>`, `<select>`, and `<button>` elements) inside a `<fieldset disabled>` as disabled, preventing both keyboard and mouse interactions on them.

However, if your form also includes custom button-like elements such as `<a class="btn btn-*">...</a>`, these will only be given a style of `pointer-events: none`, meaning they are still focusable and operable using the keyboard. In this case, you must manually modify these controls by adding `tabindex="-1"` to prevent them from receiving focus and `aria-disabled="disabled"` to signal their state to assistive technologies.

Disabled fieldset example

Disabled input

Disabled select menuDisabled select

Can’t check this


Submit

html

```html
<form>
  <fieldset disabled>
    <legend>Disabled fieldset example</legend>
    <div class="mb-3">
      <label for="disabledTextInput" class="form-label">Disabled input</label>
      <input type="text" id="disabledTextInput" class="form-control" placeholder="Disabled input">
    </div>
    <div class="mb-3">
      <label for="disabledSelect" class="form-label">Disabled select menu</label>
      <select id="disabledSelect" class="form-select">
        <option>Disabled select</option>
      </select>
    </div>
    <div class="mb-3">
      <div class="form-check">
        <input class="form-check-input" type="checkbox" id="disabledFieldsetCheck" disabled>
        <label class="form-check-label" for="disabledFieldsetCheck">
          Can’t check this
        </label>
      </div>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </fieldset>
</form>
```

## Accessibility [Link to this section: Accessibility](https://getbootstrap.com/docs/5.3/forms/overview/\#accessibility)

Ensure that all form controls have an appropriate accessible name so that their purpose can be conveyed to users of assistive technologies. The simplest way to achieve this is to use a `<label>` element, or—in the case of buttons—to include sufficiently descriptive text as part of the `<button>...</button>` content.

For situations where it’s not possible to include a visible `<label>` or appropriate text content, there are alternative ways of still providing an accessible name, such as:

- `<label>` elements hidden using the `.visually-hidden` class
- Pointing to an existing element that can act as a label using `aria-labelledby`
- Providing a `title` attribute
- Explicitly setting the accessible name on an element using `aria-label`

If none of these are present, assistive technologies may resort to using the `placeholder` attribute as a fallback for the accessible name on `<input>` and `<textarea>` elements. The examples in this section provide a few suggested, case-specific approaches.

While using visually hidden content ( `.visually-hidden`, `aria-label`, and even `placeholder` content, which disappears once a form field has content) will benefit assistive technology users, a lack of visible label text may still be problematic for certain users. Some form of visible label is generally the best approach, both for accessibility and usability.

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/forms/overview/\#css)

Many form variables are set at a general level to be re-used and extended by individual form components. You’ll see these most often as `$input-btn-*` and `$input-*` variables.

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/forms/overview/\#sass-variables)

`$input-btn-*` variables are shared global variables between our [buttons](https://getbootstrap.com/docs/5.3/components/buttons) and our form components. You’ll find these frequently reassigned as values to other component-specific variables.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$input-btn-padding-y:         .375rem;
$input-btn-padding-x:         .75rem;
$input-btn-font-family:       null;
$input-btn-font-size:         $font-size-base;
$input-btn-line-height:       $line-height-base;

$input-btn-focus-width:         $focus-ring-width;
$input-btn-focus-color-opacity: $focus-ring-opacity;
$input-btn-focus-color:         $focus-ring-color;
$input-btn-focus-blur:          $focus-ring-blur;
$input-btn-focus-box-shadow:    $focus-ring-box-shadow;

$input-btn-padding-y-sm:      .25rem;
$input-btn-padding-x-sm:      .5rem;
$input-btn-font-size-sm:      $font-size-sm;

$input-btn-padding-y-lg:      .5rem;
$input-btn-padding-x-lg:      1rem;
$input-btn-font-size-lg:      $font-size-lg;

$input-btn-border-width:      var(--#{$prefix}border-width);

```