---
url: https://getbootstrap.com/docs/5.3/forms/input-group
scraped_at: 2025-10-20T02:32:43.919Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/forms/input-group/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/forms/input-group/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/forms/input-group.mdx "View and edit this file on GitHub")

# Input group

Easily extend form controls by adding text, buttons, or button groups on either side of textual inputs, custom selects, and custom file inputs.

On this page
**On this page**

* * *

## Basic example [Link to this section: Basic example](https://getbootstrap.com/docs/5.3/forms/input-group/\#basic-example)

Place one add-on or button on either side of an input. You may also place one on both sides of an input. Remember to place `<label>` s outside the input group.

@

@example.com

Your vanity URL

https://example.com/users/

Example help text goes outside the input group.

$.00

@

With textarea

html

```html
<div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1">@</span>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username" aria-describedby="basic-addon2">
  <span class="input-group-text" id="basic-addon2">@example.com</span>
</div>

<div class="mb-3">
  <label for="basic-url" class="form-label">Your vanity URL</label>
  <div class="input-group">
    <span class="input-group-text" id="basic-addon3">https://example.com/users/</span>
    <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3 basic-addon4">
  </div>
  <div class="form-text" id="basic-addon4">Example help text goes outside the input group.</div>
</div>

<div class="input-group mb-3">
  <span class="input-group-text">$</span>
  <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
  <span class="input-group-text">.00</span>
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Username" aria-label="Username">
  <span class="input-group-text">@</span>
  <input type="text" class="form-control" placeholder="Server" aria-label="Server">
</div>

<div class="input-group">
  <span class="input-group-text">With textarea</span>
  <textarea class="form-control" aria-label="With textarea"></textarea>
</div>
```

## Wrapping [Link to this section: Wrapping](https://getbootstrap.com/docs/5.3/forms/input-group/\#wrapping)

Input groups wrap by default via `flex-wrap: wrap` in order to accommodate custom form field validation within an input group. You may disable this with `.flex-nowrap`.

@

html

```html
<div class="input-group flex-nowrap">
  <span class="input-group-text" id="addon-wrapping">@</span>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="addon-wrapping">
</div>
```

## Border radius [Link to this section: Border radius](https://getbootstrap.com/docs/5.3/forms/input-group/\#border-radius)

Due to limitations of browser support at the time, `border-radius` styles can only be applied to the first and last children within the `.input-group` class. Any non-visible element in one of those positions will cause the input group to render incorrectly. This will unfortunately not be fixed until v6 most likely.

@

html

```html
<div class="input-group">
  <span class="input-group-text" id="visible-addon">@</span>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="visible-addon">
  <input type="text" class="form-control d-none" placeholder="Hidden input" aria-label="Hidden input" aria-describedby="visible-addon">
</div>
```

## Sizing [Link to this section: Sizing](https://getbootstrap.com/docs/5.3/forms/input-group/\#sizing)

Add the relative form sizing classes to the `.input-group` itself and contents within will automatically resize—no need for repeating the form control size classes on each element.

**Sizing on the individual input group elements isn’t supported.**

Small

Default

Large

html

```html
<div class="input-group input-group-sm mb-3">
  <span class="input-group-text" id="inputGroup-sizing-sm">Small</span>
  <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm">
</div>

<div class="input-group mb-3">
  <span class="input-group-text" id="inputGroup-sizing-default">Default</span>
  <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-default">
</div>

<div class="input-group input-group-lg">
  <span class="input-group-text" id="inputGroup-sizing-lg">Large</span>
  <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-lg">
</div>
```

## Checkboxes and radios [Link to this section: Checkboxes and radios](https://getbootstrap.com/docs/5.3/forms/input-group/\#checkboxes-and-radios)

Place any checkbox or radio option within an input group’s addon instead of text. We recommend adding `.mt-0` to the `.form-check-input` when there’s no visible text next to the input.

html

```html
<div class="input-group mb-3">
  <div class="input-group-text">
    <input class="form-check-input mt-0" type="checkbox" value="" aria-label="Checkbox for following text input">
  </div>
  <input type="text" class="form-control" aria-label="Text input with checkbox">
</div>

<div class="input-group">
  <div class="input-group-text">
    <input class="form-check-input mt-0" type="radio" value="" aria-label="Radio button for following text input">
  </div>
  <input type="text" class="form-control" aria-label="Text input with radio button">
</div>
```

## Multiple inputs [Link to this section: Multiple inputs](https://getbootstrap.com/docs/5.3/forms/input-group/\#multiple-inputs)

While multiple `<input>` s are supported visually, validation styles are only available for input groups with a single `<input>`.

First and last name

html

```html
<div class="input-group">
  <span class="input-group-text">First and last name</span>
  <input type="text" aria-label="First name" class="form-control">
  <input type="text" aria-label="Last name" class="form-control">
</div>
```

## Multiple addons [Link to this section: Multiple addons](https://getbootstrap.com/docs/5.3/forms/input-group/\#multiple-addons)

Multiple add-ons are supported and can be mixed with checkbox and radio input versions.

$0.00

$0.00

html

```html
<div class="input-group mb-3">
  <span class="input-group-text">$</span>
  <span class="input-group-text">0.00</span>
  <input type="text" class="form-control" aria-label="Dollar amount (with dot and two decimal places)">
</div>

<div class="input-group">
  <input type="text" class="form-control" aria-label="Dollar amount (with dot and two decimal places)">
  <span class="input-group-text">$</span>
  <span class="input-group-text">0.00</span>
</div>
```

## Button addons [Link to this section: Button addons](https://getbootstrap.com/docs/5.3/forms/input-group/\#button-addons)

Button

Button

ButtonButton

ButtonButton

html

```html
<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button" id="button-addon1">Button</button>
  <input type="text" class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username" aria-describedby="button-addon2">
  <button class="btn btn-outline-secondary" type="button" id="button-addon2">Button</button>
</div>

<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button">Button</button>
  <button class="btn btn-outline-secondary" type="button">Button</button>
  <input type="text" class="form-control" placeholder="" aria-label="Example text with two button addons">
</div>

<div class="input-group">
  <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username with two button addons">
  <button class="btn btn-outline-secondary" type="button">Button</button>
  <button class="btn btn-outline-secondary" type="button">Button</button>
</div>
```

## Buttons with dropdowns [Link to this section: Buttons with dropdowns](https://getbootstrap.com/docs/5.3/forms/input-group/\#buttons-with-dropdowns)

Dropdown

- [Action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

Dropdown

- [Action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

Dropdown

- [Action before](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action before](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

Dropdown

- [Action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

html

```html
<div class="input-group mb-3">
  <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input type="text" class="form-control" aria-label="Text input with dropdown button">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" aria-label="Text input with dropdown button">
  <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>
  <ul class="dropdown-menu dropdown-menu-end">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
</div>

<div class="input-group">
  <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action before</a></li>
    <li><a class="dropdown-item" href="#">Another action before</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input type="text" class="form-control" aria-label="Text input with 2 dropdown buttons">
  <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>
  <ul class="dropdown-menu dropdown-menu-end">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
</div>
```

## Segmented buttons [Link to this section: Segmented buttons](https://getbootstrap.com/docs/5.3/forms/input-group/\#segmented-buttons)

ActionToggle Dropdown

- [Action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

ActionToggle Dropdown

- [Action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Another action](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- [Something else here](https://getbootstrap.com/docs/5.3/forms/input-group/#)
- * * *

- [Separated link](https://getbootstrap.com/docs/5.3/forms/input-group/#)

html

```html
<div class="input-group mb-3">
  <button type="button" class="btn btn-outline-secondary">Action</button>
  <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
    <span class="visually-hidden">Toggle Dropdown</span>
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input type="text" class="form-control" aria-label="Text input with segmented dropdown button">
</div>

<div class="input-group">
  <input type="text" class="form-control" aria-label="Text input with segmented dropdown button">
  <button type="button" class="btn btn-outline-secondary">Action</button>
  <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
    <span class="visually-hidden">Toggle Dropdown</span>
  </button>
  <ul class="dropdown-menu dropdown-menu-end">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
</div>
```

## Custom forms [Link to this section: Custom forms](https://getbootstrap.com/docs/5.3/forms/input-group/\#custom-forms)

Input groups include support for custom selects and custom file inputs. Browser default versions of these are not supported.

### Custom select [Link to this section: Custom select](https://getbootstrap.com/docs/5.3/forms/input-group/\#custom-select)

OptionsChoose...OneTwoThree

Choose...OneTwoThreeOptions

ButtonChoose...OneTwoThree

Choose...OneTwoThreeButton

html

```html
<div class="input-group mb-3">
  <label class="input-group-text" for="inputGroupSelect01">Options</label>
  <select class="form-select" id="inputGroupSelect01">
    <option selected>Choose...</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
</div>

<div class="input-group mb-3">
  <select class="form-select" id="inputGroupSelect02">
    <option selected>Choose...</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
  <label class="input-group-text" for="inputGroupSelect02">Options</label>
</div>

<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button">Button</button>
  <select class="form-select" id="inputGroupSelect03" aria-label="Example select with button addon">
    <option selected>Choose...</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
</div>

<div class="input-group">
  <select class="form-select" id="inputGroupSelect04" aria-label="Example select with button addon">
    <option selected>Choose...</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
  <button class="btn btn-outline-secondary" type="button">Button</button>
</div>
```

### Custom file input [Link to this section: Custom file input](https://getbootstrap.com/docs/5.3/forms/input-group/\#custom-file-input)

Upload

Upload

Button

Button

html

```html
<div class="input-group mb-3">
  <label class="input-group-text" for="inputGroupFile01">Upload</label>
  <input type="file" class="form-control" id="inputGroupFile01">
</div>

<div class="input-group mb-3">
  <input type="file" class="form-control" id="inputGroupFile02">
  <label class="input-group-text" for="inputGroupFile02">Upload</label>
</div>

<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button" id="inputGroupFileAddon03">Button</button>
  <input type="file" class="form-control" id="inputGroupFile03" aria-describedby="inputGroupFileAddon03" aria-label="Upload">
</div>

<div class="input-group">
  <input type="file" class="form-control" id="inputGroupFile04" aria-describedby="inputGroupFileAddon04" aria-label="Upload">
  <button class="btn btn-outline-secondary" type="button" id="inputGroupFileAddon04">Button</button>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/forms/input-group/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/forms/input-group/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$input-group-addon-padding-y:           $input-padding-y;
$input-group-addon-padding-x:           $input-padding-x;
$input-group-addon-font-weight:         $input-font-weight;
$input-group-addon-color:               $input-color;
$input-group-addon-bg:                  var(--#{$prefix}tertiary-bg);
$input-group-addon-border-color:        $input-border-color;

```