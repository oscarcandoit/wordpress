---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal
scraped_at: 2025-10-20T03:10:58.702Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#search)

# <display-internal>

Some layout models such as `table` and `ruby` have a complex internal structure, with several different roles that their children and descendants can fill. This page defines those "internal" display values, which only have meaning within that particular layout mode.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#syntax)

Valid `<display-internal>` values:

[`table-row-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-row-group)

These elements behave like [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tbody) HTML elements.

[`table-header-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-header-group)

These elements behave like [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/thead) HTML elements.

[`table-footer-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-footer-group)

These elements behave like [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tfoot) HTML elements.

[`table-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-row)

These elements behave like [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/tr) HTML elements.

[`table-cell`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-cell)

These elements behave like [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/td) HTML elements.

[`table-column-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-column-group)

These elements behave like [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/colgroup) HTML elements.

[`table-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-column)

These elements behave like [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/col) HTML elements.

[`table-caption`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#table-caption)

These elements behave like [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/caption) HTML elements.

[`ruby-base`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#ruby-base)

These elements behave like [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rb) HTML elements.

[`ruby-text`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#ruby-text)

These elements behave like [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rt) HTML elements.

[`ruby-base-container`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#ruby-base-container)

These elements are generated as anonymous boxes.

[`ruby-text-container`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal#ruby-text-container)

These elements behave like [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/rtc) HTML elements.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#formal_syntax)

```
<display-internal> =
  table-row-group       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-header-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-footer-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-row             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-cell            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-column-group    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-column          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  table-caption         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-base             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-text             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-base-container   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ruby-text-container

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#examples)

### [CSS tables example](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css_tables_example)

The following example demonstrates laying out a form using CSS table layout.

#### HTML

htmlCopy

```
<main>
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" name="name" />
  </div>
  <div>
    <label for="age">Age</label>
    <input type="text" id="age" name="age" />
  </div>
</main>

```

#### CSS

cssCopy

```
main {
  display: table;
}

div {
  display: table-row;
}

label,
input {
  display: table-cell;
  margin: 5px;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#specifications)

This feature does not appear to be defined in any specification.

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#browser_compatibility)

### [css.properties.display.table-row-group](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-row-group)

Loading…

### [css.properties.display.table-header-group](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-header-group)

Loading…

### [css.properties.display.table-footer-group](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-footer-group)

Loading…

### [css.properties.display.table-row](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-row)

Loading…

### [css.properties.display.table-cell](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-cell)

Loading…

### [css.properties.display.table-column-group](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-column-group)

Loading…

### [css.properties.display.table-column](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-column)

Loading…

### [css.properties.display.table-caption](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.table-caption)

Loading…

### [css.properties.display.ruby-base](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.ruby-base)

Loading…

### [css.properties.display.ruby-text](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.ruby-text)

Loading…

### [css.properties.display.ruby-base-container](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.ruby-base-container)

Loading…

### [css.properties.display.ruby-text-container](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#css.properties.display.ruby-text-container)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal\#see_also)

- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
  - [`<display-outside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside)
  - [`<display-inside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside)
  - [`<display-listitem>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem)
  - [`<display-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-box)
  - [`<display-legacy>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/display-internal/index.md?plain=1 "Folder: ⁨en-us/web/css/display-internal⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdisplay-internal&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fdisplay-internal%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fdisplay-internal%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fdisplay-internal%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")