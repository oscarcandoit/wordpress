---
url: https://getbootstrap.com/docs/5.3/forms/floating-labels
scraped_at: 2025-10-20T02:32:33.280Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/forms/floating-labels/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/forms/floating-labels/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/forms/floating-labels.mdx "View and edit this file on GitHub")

# Floating labels

Create beautifully simple form labels that float over your input fields.

On this page
**On this page**

* * *

## Example [Link to this section: Example](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#example)

Wrap a pair of `<input class="form-control">` and `<label>` elements in `.form-floating` to enable floating labels with Bootstrap’s textual form fields.

A non-empty `placeholder` attribute is required on each `<input>` as our CSS-only floating label implementation relies on the `:placeholder-shown` pseudo-element to detect when the input is empty. The placeholder text itself is not visible; only the `<label>` is shown to users.

Also note that the `<input>` must come first so we can utilize a sibling selector (i.e., `~`).

Email address

Password

html

```html
<div class="form-floating mb-3">
  <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">
  <label for="floatingInput">Email address</label>
</div>
<div class="form-floating">
  <input type="password" class="form-control" id="floatingPassword" placeholder="Password">
  <label for="floatingPassword">Password</label>
</div>
```

When there’s a `value` already defined, `<label>` s will automatically adjust to their floated position.

Input with value

html

```html
<form class="form-floating">
  <input type="email" class="form-control" id="floatingInputValue" placeholder="name@example.com" value="test@example.com">
  <label for="floatingInputValue">Input with value</label>
</form>
```

Form validation styles also work as expected.

Invalid input

html

```html
<form class="form-floating">
  <input type="email" class="form-control is-invalid" id="floatingInputInvalid" placeholder="name@example.com" value="test@example.com">
  <label for="floatingInputInvalid">Invalid input</label>
</form>
```

## Textareas [Link to this section: Textareas](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#textareas)

By default, `<textarea>` s with `.form-control` will be the same height as `<input>` s.

Comments

html

```html
<div class="form-floating">
  <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea"></textarea>
  <label for="floatingTextarea">Comments</label>
</div>
```

To set a custom height on your `<textarea>`, do not use the `rows` attribute. Instead, set an explicit `height` (either inline or via custom CSS).

Comments

html

```html
<div class="form-floating">
  <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea2" style="height: 100px"></textarea>
  <label for="floatingTextarea2">Comments</label>
</div>
```

## Selects [Link to this section: Selects](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#selects)

Other than `.form-control`, floating labels are only available on `.form-select` s. They work in the same way, but unlike `<input>` s, they’ll always show the `<label>` in its floated state. **Selects with `size` and `multiple` are not supported.**

Open this select menuOneTwoThreeWorks with selects

html

```html
<div class="form-floating">
  <select class="form-select" id="floatingSelect" aria-label="Floating label select example">
    <option selected>Open this select menu</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
  <label for="floatingSelect">Works with selects</label>
</div>
```

## Disabled [Link to this section: Disabled](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#disabled)

Add the `disabled` boolean attribute on an input, a textarea or a select to give it a grayed out appearance, remove pointer events, and prevent focusing.

Email address

Comments

Disabled textarea with some text insideComments

Open this select menuOneTwoThreeWorks with selects

html

```html
<div class="form-floating mb-3">
  <input type="email" class="form-control" id="floatingInputDisabled" placeholder="name@example.com" disabled>
  <label for="floatingInputDisabled">Email address</label>
</div>
<div class="form-floating mb-3">
  <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextareaDisabled" disabled></textarea>
  <label for="floatingTextareaDisabled">Comments</label>
</div>
<div class="form-floating mb-3">
  <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea2Disabled" style="height: 100px" disabled>Disabled textarea with some text inside</textarea>
  <label for="floatingTextarea2Disabled">Comments</label>
</div>
<div class="form-floating">
  <select class="form-select" id="floatingSelectDisabled" aria-label="Floating label disabled select example" disabled>
    <option selected>Open this select menu</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
  <label for="floatingSelectDisabled">Works with selects</label>
</div>
```

## Readonly plaintext [Link to this section: Readonly plaintext](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#readonly-plaintext)

Floating labels also support `.form-control-plaintext`, which can be helpful for toggling from an editable `<input>` to a plaintext value without affecting the page layout.

Empty input

Input with value

html

```html
<div class="form-floating mb-3">
  <input type="email" readonly class="form-control-plaintext" id="floatingEmptyPlaintextInput" placeholder="name@example.com">
  <label for="floatingEmptyPlaintextInput">Empty input</label>
</div>
<div class="form-floating mb-3">
  <input type="email" readonly class="form-control-plaintext" id="floatingPlaintextInput" placeholder="name@example.com" value="name@example.com">
  <label for="floatingPlaintextInput">Input with value</label>
</div>
```

## Input groups [Link to this section: Input groups](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#input-groups)

Floating labels also support `.input-group`.

@

Username

html

```html
<div class="input-group mb-3">
  <span class="input-group-text">@</span>
  <div class="form-floating">
    <input type="text" class="form-control" id="floatingInputGroup1" placeholder="Username">
    <label for="floatingInputGroup1">Username</label>
  </div>
</div>
```

When using `.input-group` and `.form-floating` along with form validation, the `-feedback` should be placed outside of the `.form-floating`, but inside of the `.input-group`. This means that the feedback will need to be shown using javascript.

@

Username

Please choose a username.


html

```html
<div class="input-group has-validation">
  <span class="input-group-text">@</span>
  <div class="form-floating is-invalid">
    <input type="text" class="form-control is-invalid" id="floatingInputGroup2" placeholder="Username" required>
    <label for="floatingInputGroup2">Username</label>
  </div>
  <div class="invalid-feedback">
    Please choose a username.
  </div>
</div>
```

## Layout [Link to this section: Layout](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#layout)

When working with the Bootstrap grid system, be sure to place form elements within column classes.

Email address

Open this select menuOneTwoThreeWorks with selects

html

```html
<div class="row g-2">
  <div class="col-md">
    <div class="form-floating">
      <input type="email" class="form-control" id="floatingInputGrid" placeholder="name@example.com" value="mdo@example.com">
      <label for="floatingInputGrid">Email address</label>
    </div>
  </div>
  <div class="col-md">
    <div class="form-floating">
      <select class="form-select" id="floatingSelectGrid">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
      <label for="floatingSelectGrid">Works with selects</label>
    </div>
  </div>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/forms/floating-labels/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$form-floating-height:                  add(3.5rem, $input-height-border);
$form-floating-line-height:             1.25;
$form-floating-padding-x:               $input-padding-x;
$form-floating-padding-y:               1rem;
$form-floating-input-padding-t:         1.625rem;
$form-floating-input-padding-b:         .625rem;
$form-floating-label-height:            1.5em;
$form-floating-label-opacity:           .65;
$form-floating-label-transform:         scale(.85) translateY(-.5rem) translateX(.15rem);
$form-floating-label-disabled-color:    $gray-600;
$form-floating-transition:              opacity .1s ease-in-out, transform .1s ease-in-out;

```