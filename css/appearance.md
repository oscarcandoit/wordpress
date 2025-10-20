---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/appearance
scraped_at: 2025-10-20T03:04:11.116Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# appearance


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2022⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fappearance&level=high)

The **`appearance`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the rendered appearance of replaced UI widget elements such as form controls. Most commonly, such elements are given native, platform-specific styling based on the operating system's theme, or a primitive appearance with styles that can be overridden using CSS.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#try_it)

- appearance: auto;

- appearance: none;

- appearance: textfield;


## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#syntax)

cssCopy

```
/* CSS Basic User Interface Module Level 4 values */
appearance: none;
appearance: auto;
appearance: menulist-button;
appearance: textfield;
appearance: base-select;

/* Global values */
appearance: inherit;
appearance: initial;
appearance: revert;
appearance: revert-layer;
appearance: unset;

/* <compat-auto> values have the same effect as 'auto' */
appearance: button;
appearance: checkbox;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#values)

The `appearance` property can be applied to all elements and pseudo-elements, but the effect of the specified value, if any, depends on the element to which it is applied.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#none)

Gives the widget a _primitive_ appearance, making it stylable via CSS, while maintaining the widget's native functionality. This value does not affect non-widgets.

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#auto)

Sets interactive widgets to render with their _OS-native_ appearance. Behaves as `none` on elements with no OS-native styling.

[`base-select`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#base-select)

Only relevant to the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/select) element and [`::picker(select)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::picker) pseudo-element, allowing them to be styled.

[`<compat-special>`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#compat-special)

Has an effect similar to `auto` on certain elements.

[`textfield`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#textfield)

Causes the appearance of certain `<input>` types to [match the appearance of the `text` type](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#try_it).

[`menulist-button`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#menulist-button)

When set on the `<select>` element, the drop-down picker's style [matches that of its default state](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#setting_the_appearance_of_a_select).

[`<compat-auto>`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#compat-auto)

Included for backwards compatibility; possible values include `button`, `checkbox`, `listbox`, `menulist`, `meter`, `progress-bar`, `push-button`, `radio`, `searchfield`, `slider-horizontal`, `square-button`, and `textarea`. The values all behave as `auto`: use `auto` instead.

**Note:**
The specification also defines a `base` value. This is not yet supported by any browser.

#### Non-standard values

Some non-standard values are also supported in some browsers:

[`slider-vertical`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#slider-vertical)

Makes the slider vertical when applied to `<input type="range">` elements. To [create a vertical slider](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_writing_modes/Vertical_controls) you should instead set the [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode) to `vertical-lr` and the [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) to `rtl`.

[`-apple-pay-button`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#-apple-pay-button)

Displays the Apple Pay logo when set on a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/button), [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a), or [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) element of type `button` or `reset`.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#description)

The `appearance` property enables displaying elements in their OS-native style based on the operating system's theme, as well as the removal of any platform-native styling with the `none` value. Setting `appearance: none`, or otherwise changing the appearance of UI widgets, does not change the element's functionality.

While most elements in a document can be fully styled by CSS, UI controls ( _widgets_) are typically rendered by the browser using the operating system's native UI styles. This _native_ appearance differs between operating systems and browsers. In this default state, widgets have limited, if any, features that can be styled with CSS. Which elements have this native UI appearance is defined in HTML.

The `appearance` property provides some control over the appearance of HTML widgets that, by default, look like native operating system controls. Most notably, the `none` value suppresses some of a widget's native appearance. This results in a _primitive_ look that can be styled via CSS while still maintaining functionality and supporting native user interactions.

Some widgets disappear completely when set to `appearance: none`. The hidden controls are still interactive, however. For example, clicking on a [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/label) associated with an `appearance: none` checkbox will toggle the checkbox's checked state.

Because `none` can cause a widget to be hidden, the `base` value is being added to provide widgets with a base appearance. When supported, the `base` value will ensure widgets maintain their native appearance while enabling CSS to be used to change a widget's styles that are not changeable by default. Unlike `none`, which can make radio buttons and checkboxes disappear, `base` gives the widget a primitive appearance with default native styles that are usable and interoperable, as well as enabling a good degree of customization via CSS. While this `base` value is not yet supported, the many `<compat-auto>` values provide similar functionality but are type-specific and not global.

The `base-select` value, which is relevant only to the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/select) element and [`::picker(select)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::picker) pseudo-element, enables [styling `<select>` elements and the select picker](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance#setting_the_appearance_of_a_select) (which contains the `<option>` elements). The picker is rendered in the top layer, similar to a popover. When `base-select` is set, the picker can be positioned relative to the select (or other elements) using [CSS anchor positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_anchor_positioning) features. In addition, the `base-select` value causes the `<select>` not to render outside the browser pane or to trigger built-in mobile operating system components. It is also no longer sized based on the width of the widest `<option>`.

### [Prefixed non-standard values](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#prefixed_non-standard_values)

Before standardization, the prefixed **`-moz-appearance`** and **`-webkit-appearance`** properties allowed elements to be shown as widgets such as buttons or checkboxes. The following non-standard values may be encountered in legacy style sheets, most commonly as values of shadow DOM component [prefixed pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#pseudo-elements).

Non-standard values

- `attachment`
- `borderless-attachment`
- `button-bevel`
- `caps-lock-indicator`
- `caret`
- `checkbox-container`
- `checkbox-label`
- `checkmenuitem`
- `color-well`
- `continuous-capacity-level-indicator`
- `default-button`
- `discrete-capacity-level-indicator`
- `inner-spin-button`
- `image-controls-button`
- `list-button`
- `listitem`
- `media-enter-fullscreen-button`
- `media-exit-fullscreen-button`
- `media-fullscreen-volume-slider`
- `media-fullscreen-volume-slider-thumb`
- `media-mute-button`
- `media-play-button`
- `media-overlay-play-button`
- `media-return-to-realtime-button`
- `media-rewind-button`
- `media-seek-back-button`
- `media-seek-forward-button`
- `media-toggle-closed-captions-button`
- `media-slider`
- `media-sliderthumb`
- `media-volume-slider-container`
- `media-volume-slider-mute-button`
- `media-volume-slider`
- `media-volume-sliderthumb`
- `media-controls-background`
- `media-controls-dark-bar-background`
- `media-controls-fullscreen-background`
- `media-controls-light-bar-background`
- `media-current-time-display`
- `media-time-remaining-display`
- `menulist-text`
- `menulist-textfield`
- `meterbar`
- `number-input`
- `progress-bar-value`
- `progressbar`
- `progressbar-vertical`
- `range`
- `range-thumb`
- `rating-level-indicator`
- `relevancy-level-indicator`
- `scale-horizontal`
- `scalethumbend`
- `scalethumb-horizontal`
- `scalethumbstart`
- `scalethumbtick`
- `scalethumb-vertical`
- `scale-vertical`
- `scrollbarthumb-horizontal`
- `scrollbarthumb-vertical`
- `scrollbartrack-horizontal`
- `scrollbartrack-vertical`
- `searchfield-decoration`
- `searchfield-results-decoration`
- `searchfield-results-button`
- `searchfield-cancel-button`
- `snapshotted-plugin-overlay`
- `sheet`
- `sliderthumb-horizontal`
- `sliderthumb-vertical`
- `textfield-multiline`

Authors are encouraged to use only standard keywords.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `none` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#formal_syntax)

```
appearance =
  none               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  base               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  base-select        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <compat-auto>      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <compat-special>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  base

<compat-auto> =
  searchfield    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  textarea       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  checkbox       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  radio          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  menulist       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  listbox        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  meter          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  progress-bar   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  button

<compat-special> =
  textfield         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  menulist-button

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#examples)

### [Basic example](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#basic_example)

This example demonstrates basic usage of the `appearance` property, altering the appearance of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) element in some browsers.

#### HTML

We include two `number` form controls along with their labels.

htmlCopyPlay

```
<p>
  <label>Enter a number: <input type="number" min="0" max="10" /></label>
</p>
<p>
  <label
    >Enter a number: <input type="number" min="0" max="10" class="text"
  /></label>
</p>

```

#### CSS

We set the element with the class of `text` to look like a text field.

cssCopyPlay

```
.text {
  appearance: textfield;
}

```

#### Results

Play

Depending on the browser, the spinner may be visually removed when the control is set to look like a text field. The `appearance` property has no effect on the functionality: for example, while there may no longer be a spinner to click on,the up and down cursor keys will still increment and decrement the value.

### [Appearance set to `none`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#appearance_set_to_none)

The following example shows how to remove the default styling from a checkbox, a radio button, and a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/select) element, and apply custom styling.

#### HTML

We include pairs of checkboxes, radio buttons, and `<select>` elements, along with their associated labels:

htmlCopyPlay

```
<label><input type="checkbox" /> Default unchecked </label>
<label><input type="checkbox" checked /> Default checked </label>

<hr />

<label><input type="radio" name="radio" /> Default unchecked </label>
<label><input type="radio" name="radio" checked /> Default checked </label>

<hr />

<label
  >Unstyled select
  <select>
    <option>Option 1</option>
    <option>Option 2</option>
  </select>
</label>

<label
  >Styled select
  <select class="none">
    <option>Option 1</option>
    <option>Option 2</option>
  </select>
</label>

```

#### CSS

We apply styles to both [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input) elements of type `checkbox`; these styles create a red square if the element is stylable. We set `appearance: none` on the [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked) UI state for all inputs ( `checkbox` and `radio`), as well as to elements with the `.none` class. This removes all the style of the radio button and checkbox, other than the margins, and allows any set styles to be applied. There are no alternative styles provided for the radio buttons or `<select>` elements for when `none` is set.

cssCopyPlay

```
[type="checkbox"] {
  width: 1em;
  height: 1em;
  display: inline-block;
  background: red;
}
input:checked,
.none {
  appearance: none;
}

```

#### Result

Play

Default unchecked  Default checked

* * *

Default unchecked  Default checked

* * *

Unstyled select
Option 1Option 2Styled select
Option 1Option 2

Setting `appearance: none` enables UI elements to be styled, but it also runs the risk of hiding the widget. The unchecked checkbox, with its `appearance` defaulting to `auto`, looks like a checkbox. Setting `appearance: none` in the `:checked` state enables it to be styled.

Like the unchecked checkbox, the unchecked radio button looks like the native UI widget, because it is. When in the checked state, with `appearance: none` applied, the radio button disappears; its functionality is retained, and only its margins affect page rendering.

### [Setting the appearance of a select](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#setting_the_appearance_of_a_select)

We can use the `appearance` property to opt-in to custom select functionality, enabling styling the `<select>` element and its picker, which represents the part of the form control that pops out of the page.

#### HTML

We include three `<select>` elements, with the same multiple [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/option) children. As with every `<select>`, we also include associated [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/label) elements. The third option has more text to demonstrate the effect of `base-select` on the width of the `<select>`:

htmlCopyPlay

```
<label for="ice-cream1"
  >Default flavor:
  <select id="ice-cream1">
    <option>Asparagus</option>
    <option>Dulce de leche</option>
    <option>Pistachio, rum raisin, and coffee</option>
  </select>
</label>
<label for="ice-cream2"
  >Base select flavor:
  <select id="ice-cream2" class="baseSelect">
    <option>Asparagus</option>
    <option>Dulce de leche</option>
    <option>Pistachio, rum raisin, and coffee</option>
  </select>
</label>
<label for="ice-cream3"
  >Menulist button flavor:
  <select id="ice-cream3" class="menulistButton">
    <option>Asparagus</option>
    <option>Dulce de leche</option>
    <option>Pistachio, rum raisin, and coffee</option>
  </select>
</label>

```

#### CSS

We select the pickers of all the `<select>` elements using the [`::picker()`](https://developer.mozilla.org/en-US/docs/Web/CSS/::picker) pseudo-element with the `select` parameter. We set the `appearance` value of all the pickers and one `<select>` element to `base-select`. We set the last `<select>` to `menulist-button`. The first `<select>` defaults to the `auto` state:

cssCopyPlay

```
.baseSelect,
::picker(select) {
  appearance: base-select;
}
.menulistButton {
  appearance: menulist-button;
}

```

cssCopyPlay

```
label {
  display: block;
}

```

We set values for the `<select>` and pickers' [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) and [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) properties to demonstrate the effects of the `appearance` values:

cssCopyPlay

```
select {
  border: 1px solid red;
  background-color: orange;
}

::picker(select) {
  background-color: yellow;
  border: none;
}

```

#### Results

Play

Default flavor:
AsparagusDulce de lechePistachio, rum raisin, and coffeeBase select flavor:
AsparagusDulce de lechePistachio, rum raisin, and coffeeMenulist button flavor:
AsparagusDulce de lechePistachio, rum raisin, and coffee

While the [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) and [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) styles are defined on all the `<select>` elements and their pickers, the `::picker(select)` styles only effect the picker where both the select and the picker have the `appearance` property set to `base-select`. The first and third selects look the same because `menulist-button` is a compatibility keyword.

Notice that, by default, the inline-size of the `<select>` is generally the inline-size of the `<option>` with the most text, and that the drop-down picker appears over the top of the rendered page when opened, making it not constrained by the surrounding page and therefore fully visible. These statements are no longer true when `base-select` is set.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#specifications)

| Specification |
| --- |
| [CSS Basic User Interface Module Level 4\<br>\# appearance-switching](https://drafts.csswg.org/css-ui/#appearance-switching) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/appearance.json "File: ⁨css/properties/appearance.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `appearance` | Chrome – Full support<br>Chrome84<br>more<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome – Full support<br>Chrome84 (Release date: ⁨2020-07-27⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge84<br>more<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Edge – Full support<br>Edge84 (Release date: ⁨2020-07-16⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox80<br>more<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-moz-⁩<br>Firefox – Full support<br>Firefox64 (Release date: ⁨2018-12-11⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Firefox – Full support<br>Firefox80 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera70<br>more<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera – Full support<br>Opera70 (Release date: ⁨2020-07-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>more<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android84<br>more<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome Android – Full support<br>Chrome Android84 (Release date: ⁨2020-07-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android80<br>more<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-moz-⁩<br>Firefox for Android – Full support<br>Firefox for Android64 (Release date: ⁨2018-12-11⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Firefox for Android – Full support<br>Firefox for Android80 (Release date: ⁨2020-08-31⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android60<br>more<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera Android – Full support<br>Opera Android60 (Release date: ⁨2020-09-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>more<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet14<br>more<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android84<br>more<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView Android – Full support<br>WebView Android84 (Release date: ⁨2020-07-27⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>more<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |
| `auto` | Chrome – Full support<br>Chrome83<br>Chrome – Full support<br>Chrome83 (Release date: ⁨2020-05-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge83<br>Edge – Full support<br>Edge83 (Release date: ⁨2020-05-21⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox80<br>Firefox – Full support<br>Firefox80 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera69<br>Opera – Full support<br>Opera69 (Release date: ⁨2020-06-24⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15.4<br>Safari – Full support<br>Safari15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android83<br>Chrome Android – Full support<br>Chrome Android83 (Release date: ⁨2020-05-19⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android80<br>Firefox for Android – Full support<br>Firefox for Android80 (Release date: ⁨2020-08-31⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android59<br>Opera Android – Full support<br>Opera Android59 (Release date: ⁨2020-06-30⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15.4<br>Safari on iOS – Full support<br>Safari on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet13<br>Samsung Internet – Full support<br>Samsung Internet13 (Release date: ⁨2020-12-02⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android83<br>WebView Android – Full support<br>WebView Android83 (Release date: ⁨2020-05-19⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.4<br>WebView on iOS – Full support<br>WebView on iOS15.4 (Release date: ⁨2022-03-14⁩)<br> <br>footnoteFull support |
| `base-select`<br>Experimental | Chrome – Full support<br>Chrome135<br>Chrome – Full support<br>Chrome135 (Release date: ⁨2025-04-01⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge135<br>Edge – Full support<br>Edge135 (Release date: ⁨2025-04-04⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera120<br>Opera – Full support<br>Opera120 (Release date: ⁨2025-07-02⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android135<br>Chrome Android – Full support<br>Chrome Android135 (Release date: ⁨2025-04-01⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android89<br>Opera Android – Full support<br>Opera Android89 (Release date: ⁨2025-04-29⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Preview browser support<br>Samsung Internet29<br>Samsung Internet – Preview browser support<br>Samsung Internet29<br>footnotePreview browser support | WebView Android – Full support<br>WebView Android135<br>WebView Android – Full support<br>WebView Android135 (Release date: ⁨2025-04-01⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| `button` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `checkbox` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `listbox` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `menulist` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `menulist-button` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox80<br>more<br>Firefox – Partial support<br>Firefox1 – 79 (Release date: ⁨2004-11-09⁩)<br> <br>footnotePartial supportfootnoteSee [bug 1481615](https://bugzil.la/1481615).<br>Firefox – Full support<br>Firefox80 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android80<br>more<br>Firefox for Android – Partial support<br>Firefox for Android4 – 79 (Release date: ⁨2011-03-29⁩)<br> <br>footnotePartial supportfootnoteSee [bug 1481615](https://bugzil.la/1481615).<br>Firefox for Android – Full support<br>Firefox for Android80 (Release date: ⁨2020-08-31⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `meter` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox54<br>more<br>Firefox – Partial support<br>Firefox1 – 53 (Release date: ⁨2004-11-09⁩)<br> <br>footnotePartial supportfootnoteDoesn't work with `<input type="checkbox">` and `<input type="radio">`.<br>Firefox – Full support<br>Firefox54 (Release date: ⁨2017-06-13⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android54<br>more<br>Firefox for Android – Partial support<br>Firefox for Android4 – 53 (Release date: ⁨2011-03-29⁩)<br> <br>footnotePartial supportfootnoteDoesn't work with `<input type="checkbox">` and `<input type="radio">`.<br>Firefox for Android – Full support<br>Firefox for Android54 (Release date: ⁨2017-06-13⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS3<br>Safari on iOS – Full support<br>Safari on iOS3 (Release date: ⁨2009-06-17⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS3<br>WebView on iOS – Full support<br>WebView on iOS3 (Release date: ⁨2009-06-17⁩)<br> <br>footnoteFull support |
| `progress-bar` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `radio` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `searchfield` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `textarea` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS2<br>Safari on iOS – Full support<br>Safari on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS2<br>WebView on iOS – Full support<br>WebView on iOS2 (Release date: ⁨2008-07-11⁩)<br> <br>footnoteFull support |
| `textfield` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari3<br>Safari – Full support<br>Safari3 (Release date: ⁨2007-10-26⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

In development. Supported in a pre-release version.In development. Supported in a pre-release version.

No supportNo support

⁨Experimental⁩. Expect behavior to change in the future.

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance\#see_also)

- [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 11, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/appearance/index.md?plain=1 "Folder: ⁨en-us/web/css/appearance⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fappearance&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fappearance%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fappearance%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fappearance%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F6eae35bc64a49865a469ca29bc40e6993b9cb8cc%0A*+Document+last+modified%3A+2025-08-11T12%3A58%3A33.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")