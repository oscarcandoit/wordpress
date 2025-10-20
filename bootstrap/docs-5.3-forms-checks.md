---
url: https://getbootstrap.com/docs/5.3/forms/checks
scraped_at: 2025-10-20T02:32:30.282Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/forms/checks-radios/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/forms/checks-radios/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/forms/checks-radios.mdx "View and edit this file on GitHub")

# Checks and radios

Create consistent cross-browser and cross-device checkboxes and radios with our completely rewritten checks component.

On this page
**On this page**

* * *

## Approach [Link to this section: Approach](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#approach)

Browser default checkboxes and radios are replaced with the help of `.form-check`, a series of classes for both input types that improves the layout and behavior of their HTML elements, that provide greater customization and cross browser consistency. Checkboxes are for selecting one or several options in a list, while radios are for selecting one option from many.

Structurally, our `<input>` s and `<label>` s are sibling elements as opposed to an `<input>` within a `<label>`. This is slightly more verbose as you must specify `id` and `for` attributes to relate the `<input>` and `<label>`. We use the sibling selector ( `~`) for all our `<input>` states, like `:checked` or `:disabled`. When combined with the `.form-check-label` class, we can easily style the text for each item based on the `<input>`’s state.

Our checks use custom Bootstrap icons to indicate checked or indeterminate states.

## Checks [Link to this section: Checks](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#checks)

Default checkbox


Checked checkbox


html

```html
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkDefault">
  <label class="form-check-label" for="checkDefault">
    Default checkbox
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkChecked" checked>
  <label class="form-check-label" for="checkChecked">
    Checked checkbox
  </label>
</div>
```

### Indeterminate [Link to this section: Indeterminate](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#indeterminate)

Checkboxes can utilize the `:indeterminate` pseudo class when manually set via JavaScript (there is no available HTML attribute for specifying it).

Indeterminate checkbox


html

```html
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkIndeterminate">
  <label class="form-check-label" for="checkIndeterminate">
    Indeterminate checkbox
  </label>
</div>
```

### Disabled [Link to this section: Disabled](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#disabled)

Add the `disabled` attribute and the associated `<label>` s are automatically styled to match with a lighter color to help indicate the input’s state.

Disabled indeterminate checkbox


Disabled checkbox


Disabled checked checkbox


html

```html
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkIndeterminateDisabled" disabled>
  <label class="form-check-label" for="checkIndeterminateDisabled">
    Disabled indeterminate checkbox
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkDisabled" disabled>
  <label class="form-check-label" for="checkDisabled">
    Disabled checkbox
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkCheckedDisabled" checked disabled>
  <label class="form-check-label" for="checkCheckedDisabled">
    Disabled checked checkbox
  </label>
</div>
```

## Radios [Link to this section: Radios](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#radios)

Default radio


Default checked radio


html

```html
<div class="form-check">
  <input class="form-check-input" type="radio" name="radioDefault" id="radioDefault1">
  <label class="form-check-label" for="radioDefault1">
    Default radio
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="radioDefault" id="radioDefault2" checked>
  <label class="form-check-label" for="radioDefault2">
    Default checked radio
  </label>
</div>
```

### Disabled [Link to this section: Disabled](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#disabled-1)

Add the `disabled` attribute and the associated `<label>` s are automatically styled to match with a lighter color to help indicate the input’s state.

Disabled radio


Disabled checked radio


html

```html
<div class="form-check">
  <input class="form-check-input" type="radio" name="radioDisabled" id="radioDisabled" disabled>
  <label class="form-check-label" for="radioDisabled">
    Disabled radio
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="radioDisabled" id="radioCheckedDisabled" checked disabled>
  <label class="form-check-label" for="radioCheckedDisabled">
    Disabled checked radio
  </label>
</div>
```

## Switches [Link to this section: Switches](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#switches)

A switch has the markup of a custom checkbox but uses the `.form-switch` class to render a toggle switch. Consider using `role="switch"` to more accurately convey the nature of the control to assistive technologies that support this role. In older assistive technologies, it will simply be announced as a regular checkbox as a fallback. Switches also support the `disabled` attribute.

Default switch checkbox input

Checked switch checkbox input

Disabled switch checkbox input

Disabled checked switch checkbox input

html

```html
<div class="form-check form-switch">
  <input class="form-check-input" type="checkbox" role="switch" id="switchCheckDefault">
  <label class="form-check-label" for="switchCheckDefault">Default switch checkbox input</label>
</div>
<div class="form-check form-switch">
  <input class="form-check-input" type="checkbox" role="switch" id="switchCheckChecked" checked>
  <label class="form-check-label" for="switchCheckChecked">Checked switch checkbox input</label>
</div>
<div class="form-check form-switch">
  <input class="form-check-input" type="checkbox" role="switch" id="switchCheckDisabled" disabled>
  <label class="form-check-label" for="switchCheckDisabled">Disabled switch checkbox input</label>
</div>
<div class="form-check form-switch">
  <input class="form-check-input" type="checkbox" role="switch" id="switchCheckCheckedDisabled" checked disabled>
  <label class="form-check-label" for="switchCheckCheckedDisabled">Disabled checked switch checkbox input</label>
</div>
```

### Native switches [Link to this section: Native switches](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#native-switches)

Progressively enhance your switches for mobile Safari (iOS 17.4+) by adding a `switch` attribute to your input to enable haptic feedback when toggling switches, just like native iOS switches. There are no style changes attached to using this attribute in Bootstrap as all our switches use custom styles.

Native switch haptics


html

```html
<div class="form-check form-switch">
  <input class="form-check-input" type="checkbox" value="" id="checkNativeSwitch" switch>
  <label class="form-check-label" for="checkNativeSwitch">
    Native switch haptics
  </label>
</div>
```

Be sure to read more about [the switch attribute on the WebKit blog](https://webkit.org/blog/15054/an-html-switch-control/). Safari 17.4+ on macOS and iOS both have native-style switches in HTML while other browsers simply fall back to the standard checkbox appearance. Applying the attribute to a non-Bootstrap checkbox in more recent versions of Safari will render a native switch.

## Default (stacked) [Link to this section: Default (stacked)](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#default-stacked)

By default, any number of checkboxes and radios that are immediate sibling will be vertically stacked and appropriately spaced with `.form-check`.

Default checkbox


Disabled checkbox


html

```html
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="defaultCheck1">
  <label class="form-check-label" for="defaultCheck1">
    Default checkbox
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="defaultCheck2" disabled>
  <label class="form-check-label" for="defaultCheck2">
    Disabled checkbox
  </label>
</div>
```

Default radio


Second default radio


Disabled radio


html

```html
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios1" value="option1" checked>
  <label class="form-check-label" for="exampleRadios1">
    Default radio
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios2" value="option2">
  <label class="form-check-label" for="exampleRadios2">
    Second default radio
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios3" value="option3" disabled>
  <label class="form-check-label" for="exampleRadios3">
    Disabled radio
  </label>
</div>
```

## Inline [Link to this section: Inline](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#inline)

Group checkboxes or radios on the same horizontal row by adding `.form-check-inline` to any `.form-check`.

1

2

3 (disabled)

html

```html
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="option1">
  <label class="form-check-label" for="inlineCheckbox1">1</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="option2">
  <label class="form-check-label" for="inlineCheckbox2">2</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="option3" disabled>
  <label class="form-check-label" for="inlineCheckbox3">3 (disabled)</label>
</div>
```

1

2

3 (disabled)

html

```html
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1">
  <label class="form-check-label" for="inlineRadio1">1</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option2">
  <label class="form-check-label" for="inlineRadio2">2</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option3" disabled>
  <label class="form-check-label" for="inlineRadio3">3 (disabled)</label>
</div>
```

## Reverse [Link to this section: Reverse](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#reverse)

Put your checkboxes, radios, and switches on the opposite side with the `.form-check-reverse` modifier class.

Reverse checkbox


Disabled reverse checkbox


Reverse switch checkbox input

html

```html
<div class="form-check form-check-reverse">
  <input class="form-check-input" type="checkbox" value="" id="reverseCheck1">
  <label class="form-check-label" for="reverseCheck1">
    Reverse checkbox
  </label>
</div>
<div class="form-check form-check-reverse">
  <input class="form-check-input" type="checkbox" value="" id="reverseCheck2" disabled>
  <label class="form-check-label" for="reverseCheck2">
    Disabled reverse checkbox
  </label>
</div>

<div class="form-check form-switch form-check-reverse">
  <input class="form-check-input" type="checkbox" id="switchCheckReverse">
  <label class="form-check-label" for="switchCheckReverse">Reverse switch checkbox input</label>
</div>
```

## Without labels [Link to this section: Without labels](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#without-labels)

Omit the wrapping `.form-check` for checkboxes and radios that have no label text. Remember to still provide some form of accessible name for assistive technologies (for instance, using `aria-label`). See the [forms overview accessibility](https://getbootstrap.com/docs/5.3/forms/overview/#accessibility) section for details.

html

```html
<div>
  <input class="form-check-input" type="checkbox" id="checkboxNoLabel" value="" aria-label="...">
</div>

<div>
  <input class="form-check-input" type="radio" name="radioNoLabel" id="radioNoLabel1" value="" aria-label="...">
</div>
```

## Toggle buttons [Link to this section: Toggle buttons](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#toggle-buttons)

Create button-like checkboxes and radio buttons by using `.btn` styles rather than `.form-check-label` on the `<label>` elements. These toggle buttons can further be grouped in a [button group](https://getbootstrap.com/docs/5.3/components/button-group) if needed.

### Checkbox toggle buttons [Link to this section: Checkbox toggle buttons](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#checkbox-toggle-buttons)

Single toggleCheckedDisabled

html

```html
<input type="checkbox" class="btn-check" id="btn-check" autocomplete="off">
<label class="btn btn-primary" for="btn-check">Single toggle</label>

<input type="checkbox" class="btn-check" id="btn-check-2" checked autocomplete="off">
<label class="btn btn-primary" for="btn-check-2">Checked</label>

<input type="checkbox" class="btn-check" id="btn-check-3" autocomplete="off" disabled>
<label class="btn btn-primary" for="btn-check-3">Disabled</label>
```

Single toggleCheckedDisabled

html

```html
<input type="checkbox" class="btn-check" id="btn-check-4" autocomplete="off">
<label class="btn" for="btn-check-4">Single toggle</label>

<input type="checkbox" class="btn-check" id="btn-check-5" checked autocomplete="off">
<label class="btn" for="btn-check-5">Checked</label>

<input type="checkbox" class="btn-check" id="btn-check-6" autocomplete="off" disabled>
<label class="btn" for="btn-check-6">Disabled</label>
```

Visually, these checkbox toggle buttons are identical to the [button plugin toggle buttons](https://getbootstrap.com/docs/5.3/components/buttons#button-plugin). However, they are conveyed differently by assistive technologies: the checkbox toggles will be announced by screen readers as “checked“/“not checked“ (since, despite their appearance, they are fundamentally still checkboxes), whereas the button plugin toggle buttons will be announced as “button“/“button pressed“. The choice between these two approaches will depend on the type of toggle you are creating, and whether or not the toggle will make sense to users when announced as a checkbox or as an actual button.

### Radio toggle buttons [Link to this section: Radio toggle buttons](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#radio-toggle-buttons)

CheckedRadioDisabledRadio

html

```html
<input type="radio" class="btn-check" name="options" id="option1" autocomplete="off" checked>
<label class="btn btn-secondary" for="option1">Checked</label>

<input type="radio" class="btn-check" name="options" id="option2" autocomplete="off">
<label class="btn btn-secondary" for="option2">Radio</label>

<input type="radio" class="btn-check" name="options" id="option3" autocomplete="off" disabled>
<label class="btn btn-secondary" for="option3">Disabled</label>

<input type="radio" class="btn-check" name="options" id="option4" autocomplete="off">
<label class="btn btn-secondary" for="option4">Radio</label>
```

CheckedRadioDisabledRadio

html

```html
<input type="radio" class="btn-check" name="options-base" id="option5" autocomplete="off" checked>
<label class="btn" for="option5">Checked</label>

<input type="radio" class="btn-check" name="options-base" id="option6" autocomplete="off">
<label class="btn" for="option6">Radio</label>

<input type="radio" class="btn-check" name="options-base" id="option7" autocomplete="off" disabled>
<label class="btn" for="option7">Disabled</label>

<input type="radio" class="btn-check" name="options-base" id="option8" autocomplete="off">
<label class="btn" for="option8">Radio</label>
```

### Outlined styles [Link to this section: Outlined styles](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#outlined-styles)

Different variants of `.btn`, such as the various outlined styles, are supported.

Single toggle

Checked

Checked success radioDanger radio

html

```html
<input type="checkbox" class="btn-check" id="btn-check-outlined" autocomplete="off">
<label class="btn btn-outline-primary" for="btn-check-outlined">Single toggle</label><br>

<input type="checkbox" class="btn-check" id="btn-check-2-outlined" checked autocomplete="off">
<label class="btn btn-outline-secondary" for="btn-check-2-outlined">Checked</label><br>

<input type="radio" class="btn-check" name="options-outlined" id="success-outlined" autocomplete="off" checked>
<label class="btn btn-outline-success" for="success-outlined">Checked success radio</label>

<input type="radio" class="btn-check" name="options-outlined" id="danger-outlined" autocomplete="off">
<label class="btn btn-outline-danger" for="danger-outlined">Danger radio</label>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#css)

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/forms/checks-radios/\#sass-variables)

Variables for checks:

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$form-check-input-width:                  1em;
$form-check-min-height:                   $font-size-base * $line-height-base;
$form-check-padding-start:                $form-check-input-width + .5em;
$form-check-margin-bottom:                .125rem;
$form-check-label-color:                  null;
$form-check-label-cursor:                 null;
$form-check-transition:                   null;

$form-check-input-active-filter:          brightness(90%);

$form-check-input-bg:                     $input-bg;
$form-check-input-border:                 var(--#{$prefix}border-width) solid var(--#{$prefix}border-color);
$form-check-input-border-radius:          .25em;
$form-check-radio-border-radius:          50%;
$form-check-input-focus-border:           $input-focus-border-color;
$form-check-input-focus-box-shadow:       $focus-ring-box-shadow;

$form-check-input-checked-color:          $component-active-color;
$form-check-input-checked-bg-color:       $component-active-bg;
$form-check-input-checked-border-color:   $form-check-input-checked-bg-color;
$form-check-input-checked-bg-image:       url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'><path fill='none' stroke='#{$form-check-input-checked-color}' stroke-linecap='round' stroke-linejoin='round' stroke-width='3' d='m6 10 3 3 6-6'/></svg>");
$form-check-radio-checked-bg-image:       url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'><circle r='2' fill='#{$form-check-input-checked-color}'/></svg>");

$form-check-input-indeterminate-color:          $component-active-color;
$form-check-input-indeterminate-bg-color:       $component-active-bg;
$form-check-input-indeterminate-border-color:   $form-check-input-indeterminate-bg-color;
$form-check-input-indeterminate-bg-image:       url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'><path fill='none' stroke='#{$form-check-input-indeterminate-color}' stroke-linecap='round' stroke-linejoin='round' stroke-width='3' d='M6 10h8'/></svg>");

$form-check-input-disabled-opacity:        .5;
$form-check-label-disabled-opacity:        $form-check-input-disabled-opacity;
$form-check-btn-check-disabled-opacity:    $btn-disabled-opacity;

$form-check-inline-margin-end:    1rem;

```

Variables for switches:

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$form-switch-color:               rgba($black, .25);
$form-switch-width:               2em;
$form-switch-padding-start:       $form-switch-width + .5em;
$form-switch-bg-image:            url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'><circle r='3' fill='#{$form-switch-color}'/></svg>");
$form-switch-border-radius:       $form-switch-width;
$form-switch-transition:          background-position .15s ease-in-out;

$form-switch-focus-color:         $input-focus-border-color;
$form-switch-focus-bg-image:      url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'><circle r='3' fill='#{$form-switch-focus-color}'/></svg>");

$form-switch-checked-color:       $component-active-color;
$form-switch-checked-bg-image:    url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'><circle r='3' fill='#{$form-switch-checked-color}'/></svg>");
$form-switch-checked-bg-position: right center;

```