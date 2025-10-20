---
url: https://getbootstrap.com/docs/5.3/content/reboot
scraped_at: 2025-10-20T02:28:28.179Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/content/reboot/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/content/reboot/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/content/reboot.mdx "View and edit this file on GitHub")

# Reboot

Reboot, a collection of element-specific CSS changes in a single file, kickstart Bootstrap to provide an elegant, consistent, and simple baseline to build upon.

On this page
**On this page**

* * *

## Approach [Link to this section: Approach](https://getbootstrap.com/docs/5.3/content/reboot/\#approach)

Reboot builds upon Normalize, providing many HTML elements with somewhat opinionated styles using only element selectors. Additional styling is done only with classes. For example, we reboot some `<table>` styles for a simpler baseline and later provide `.table`, `.table-bordered`, and more.

Here are our guidelines and reasons for choosing what to override in Reboot:

- Update some browser default values to use `rem` s instead of `em` s for scalable component spacing.
- Avoid `margin-top`. Vertical margins can collapse, yielding unexpected results. More importantly though, a single direction of `margin` is a simpler mental model.
- For easier scaling across device sizes, block elements should use `rem` s for `margin` s.
- Keep declarations of `font`-related properties to a minimum, using `inherit` whenever possible.

## CSS variables [Link to this section: CSS variables](https://getbootstrap.com/docs/5.3/content/reboot/\#css-variables)

Added in v5.2.0

With v5.1.1, we standardized our required `@import` s across all our CSS bundles (including `bootstrap.css`, `bootstrap-reboot.css`, and `bootstrap-grid.css`) to include `_root.scss`. This adds `:root` level CSS variables to all bundles, regardless of how many of them are used in that bundle. Ultimately Bootstrap 5 will continue to see more [CSS variables](https://getbootstrap.com/docs/5.3/customize/css-variables) added over time, in order to provide more real-time customization without the need to always recompile Sass. Our approach is to take our source Sass variables and transform them into CSS variables. That way, even if you don’t use CSS variables, you still have all the power of Sass. **This is still in-progress and will take time to fully implement.**

For example, consider these `:root` CSS variables for common `<body>` styles:

[scss/\_root.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_root.scss)

```scss
@if $font-size-root != null {
  --#{$prefix}root-font-size: #{$font-size-root};
}
--#{$prefix}body-font-family: #{inspect($font-family-base)};
@include rfs($font-size-base, --#{$prefix}body-font-size);
--#{$prefix}body-font-weight: #{$font-weight-base};
--#{$prefix}body-line-height: #{$line-height-base};
@if $body-text-align != null {
  --#{$prefix}body-text-align: #{$body-text-align};
}

--#{$prefix}body-color: #{$body-color};
--#{$prefix}body-color-rgb: #{to-rgb($body-color)};
--#{$prefix}body-bg: #{$body-bg};
--#{$prefix}body-bg-rgb: #{to-rgb($body-bg)};

--#{$prefix}emphasis-color: #{$body-emphasis-color};
--#{$prefix}emphasis-color-rgb: #{to-rgb($body-emphasis-color)};

--#{$prefix}secondary-color: #{$body-secondary-color};
--#{$prefix}secondary-color-rgb: #{to-rgb($body-secondary-color)};
--#{$prefix}secondary-bg: #{$body-secondary-bg};
--#{$prefix}secondary-bg-rgb: #{to-rgb($body-secondary-bg)};

--#{$prefix}tertiary-color: #{$body-tertiary-color};
--#{$prefix}tertiary-color-rgb: #{to-rgb($body-tertiary-color)};
--#{$prefix}tertiary-bg: #{$body-tertiary-bg};
--#{$prefix}tertiary-bg-rgb: #{to-rgb($body-tertiary-bg)};

```

In practice, those variables are then applied in Reboot like so:

[scss/\_reboot.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_reboot.scss)

```scss
body {
  margin: 0; // 1
  font-family: var(--#{$prefix}body-font-family);
  @include font-size(var(--#{$prefix}body-font-size));
  font-weight: var(--#{$prefix}body-font-weight);
  line-height: var(--#{$prefix}body-line-height);
  color: var(--#{$prefix}body-color);
  text-align: var(--#{$prefix}body-text-align);
  background-color: var(--#{$prefix}body-bg); // 2
  -webkit-text-size-adjust: 100%; // 3
  -webkit-tap-highlight-color: rgba($black, 0); // 4
}

```

Which allows you to make real-time customizations however you like:

```html
<body style="--bs-body-color: #333;">
  <!-- ... -->
</body>

```

## Page defaults [Link to this section: Page defaults](https://getbootstrap.com/docs/5.3/content/reboot/\#page-defaults)

The `<html>` and `<body>` elements are updated to provide better page-wide defaults. More specifically:

- The `box-sizing` is globally set on every element—including `*::before` and `*::after`, to `border-box`. This ensures that the declared width of element is never exceeded due to padding or border.

  - No base `font-size` is declared on the `<html>`, but `16px` is assumed (the browser default). `font-size: 1rem` is applied on the `<body>` for easy responsive type-scaling via media queries while respecting user preferences and ensuring a more accessible approach. This browser default can be overridden by modifying the `$font-size-root` variable.
- The `<body>` also sets a global `font-family`, `font-weight`, `line-height`, and `color`. This is inherited later by some form elements to prevent font inconsistencies.
- For safety, the `<body>` has a declared `background-color`, defaulting to `#fff`.

## Native font stack [Link to this section: Native font stack](https://getbootstrap.com/docs/5.3/content/reboot/\#native-font-stack)

Bootstrap utilizes a “native font stack” or “system font stack” for optimum text rendering on every device and OS. These system fonts have been designed specifically with today’s devices in mind, with improved rendering on screens, variable font support, and more. Read more about [native font stacks in this _Smashing Magazine_ article](https://www.smashingmagazine.com/2015/11/using-system-ui-fonts-practical-guide/).

```scss
$font-family-sans-serif:
  // Cross-platform generic font family (default user interface font)
  system-ui,
  // Safari for macOS and iOS (San Francisco)
  -apple-system,
  // Windows
  "Segoe UI",
  // Android
  Roboto,
  // older macOS and iOS
  "Helvetica Neue",
  // Linux
  "Noto Sans",
  "Liberation Sans",
  // Basic web fallback
  Arial,
  // Sans serif fallback
  sans-serif,
  // Emoji fonts
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji" !default;

```

Note that because the font stack includes emoji fonts, many common symbol/dingbat Unicode characters will be rendered as multicolored pictographs. Their appearance will vary, depending on the style used in the browser/platform’s native emoji font, and they won’t be affected by any CSS `color` styles.

This `font-family` is applied to the `<body>` and automatically inherited globally throughout Bootstrap. To switch the global `font-family`, update `$font-family-base` and recompile Bootstrap.

## Headings [Link to this section: Headings](https://getbootstrap.com/docs/5.3/content/reboot/\#headings)

All heading elements— `<h1>`— `<h6>` have their `margin-top` removed, `margin-bottom: .5rem` set, and `line-height` tightened. While headings inherit their `color` by default, you can also override it via optional CSS variable, `--bs-heading-color`.

| Heading | Example |
| --- | --- |
| `<h1></h1>` | h1. Bootstrap heading |
| `<h2></h2>` | h2. Bootstrap heading |
| `<h3></h3>` | h3. Bootstrap heading |
| `<h4></h4>` | h4. Bootstrap heading |
| `<h5></h5>` | h5. Bootstrap heading |
| `<h6></h6>` | h6. Bootstrap heading |

## Paragraphs [Link to this section: Paragraphs](https://getbootstrap.com/docs/5.3/content/reboot/\#paragraphs)

All `<p>` elements have their `margin-top` removed and `margin-bottom: 1rem` set for easy spacing.

This is an example paragraph.

html

```html
<p>This is an example paragraph.</p>
```

## Links [Link to this section: Links](https://getbootstrap.com/docs/5.3/content/reboot/\#links)

Links have a default `color` and underline applied. While links change on `:hover`, they don’t change based on whether someone `:visited` the link. They also receive no special `:focus` styles.

[This is an example link](https://getbootstrap.com/docs/5.3/content/reboot/#)

html

```html
<a href="#">This is an example link</a>
```

As of v5.3.x, link `color` is set using `rgba()` and new `-rgb` CSS variables, allowing for easy customization of link color opacity. Change the link color opacity with the `--bs-link-opacity` CSS variable:

[This is an example link](https://getbootstrap.com/docs/5.3/content/reboot/#)

html

```html
<a href="#" style="--bs-link-opacity: .5">This is an example link</a>
```

Placeholder links—those without an `href`—are targeted with a more specific selector and have their `color` and `text-decoration` reset to their default values.

This is a placeholder link

html

```html
<a>This is a placeholder link</a>
```

## Horizontal rules [Link to this section: Horizontal rules](https://getbootstrap.com/docs/5.3/content/reboot/\#horizontal-rules)

The `<hr>` element has been simplified. Similar to browser defaults, `<hr>` s are styled via `border-top`, have a default `opacity: .25`, and automatically inherit their `border-color` via `color`, including when `color` is set via the parent. They can be modified with text, border, and opacity utilities.

* * *

* * *

* * *

* * *

html

```html
<hr>

<div class="text-success">
  <hr>
</div>

<hr class="border border-danger border-2 opacity-50">
<hr class="border border-primary border-3 opacity-75">
```

## Lists [Link to this section: Lists](https://getbootstrap.com/docs/5.3/content/reboot/\#lists)

All lists— `<ul>`, `<ol>`, and `<dl>`—have their `margin-top` removed and a `margin-bottom: 1rem`. Nested lists have no `margin-bottom`. We’ve also reset the `padding-left` on `<ul>` and `<ol>` elements.

- All lists have their top margin removed
- And their bottom margin normalized
- Nested lists have no bottom margin
  - This way they have a more even appearance
  - Particularly when followed by more list items
- The left padding has also been reset

1. Here’s an ordered list
2. With a few list items
3. It has the same overall look
4. As the previous unordered list

For simpler styling, clear hierarchy, and better spacing, description lists have updated `margin` s. `<dd>` s reset `margin-left` to `0` and add `margin-bottom: .5rem`. `<dt>` s are **bolded**.

Description listsA description list is perfect for defining terms.TermDefinition for the term.A second definition for the same term.Another termDefinition for this other term.

## Inline code [Link to this section: Inline code](https://getbootstrap.com/docs/5.3/content/reboot/\#inline-code)

Wrap inline snippets of code with `<code>`. Be sure to escape HTML angle brackets.

For example, `<section>` should be wrapped as inline.

html

```html
For example, <code>&lt;section&gt;</code> should be wrapped as inline.
```

## Code blocks [Link to this section: Code blocks](https://getbootstrap.com/docs/5.3/content/reboot/\#code-blocks)

Use `<pre>` s for multiple lines of code. Once again, be sure to escape any angle brackets in the code for proper rendering. The `<pre>` element is reset to remove its `margin-top` and use `rem` units for its `margin-bottom`.

```
<p>Sample text here...</p>
<p>And another line of sample text here...</p>

```

html

```html
<pre><code>&lt;p&gt;Sample text here...&lt;/p&gt;
&lt;p&gt;And another line of sample text here...&lt;/p&gt;
</code></pre>
```

## Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/content/reboot/\#variables)

For indicating variables use the `<var>` tag.

y = mx \+ b

html

```html
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>
```

## User input [Link to this section: User input](https://getbootstrap.com/docs/5.3/content/reboot/\#user-input)

Use the `<kbd>` to indicate input that is typically entered via keyboard.

To switch directories, type `cd` followed by the name of the directory.

To edit settings, press `Ctrl + ,`

html

```html
To switch directories, type <kbd>cd</kbd> followed by the name of the directory.<br>
To edit settings, press <kbd><kbd>Ctrl</kbd> + <kbd>,</kbd></kbd>
```

## Sample output [Link to this section: Sample output](https://getbootstrap.com/docs/5.3/content/reboot/\#sample-output)

For indicating sample output from a program use the `<samp>` tag.

`This text is meant to be treated as sample output from a computer program.`

html

```html
<samp>This text is meant to be treated as sample output from a computer program.</samp>
```

## Tables [Link to this section: Tables](https://getbootstrap.com/docs/5.3/content/reboot/\#tables)

Tables are slightly adjusted to style `<caption>` s, collapse borders, and ensure consistent `text-align` throughout. Additional changes for borders, padding, and more come with [the `.table` class](https://getbootstrap.com/docs/5.3/content/tables).

| Table heading | Table heading | Table heading | Table heading |
| --- | --- | --- | --- |
| Table cell | Table cell | Table cell | Table cell |
| Table cell | Table cell | Table cell | Table cell |
| Table cell | Table cell | Table cell | Table cell |

This is an example table, and this is its caption to describe the contents.


html

```html
<table>
  <caption>
    This is an example table, and this is its caption to describe the contents.
  </caption>
  <thead>
    <tr>
      <th>Table heading</th>
      <th>Table heading</th>
      <th>Table heading</th>
      <th>Table heading</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
    </tr>
    <tr>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
    </tr>
    <tr>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
      <td>Table cell</td>
    </tr>
  </tbody>
</table>
```

## Forms [Link to this section: Forms](https://getbootstrap.com/docs/5.3/content/reboot/\#forms)

Various form elements have been rebooted for simpler base styles. Here are some of the most notable changes:

- `<fieldset>` s have no borders, padding, or margin so they can be easily used as wrappers for individual inputs or groups of inputs.
- `<legend>` s, like fieldsets, have also been restyled to be displayed as a heading of sorts.
- `<label>` s are set to `display: inline-block` to allow `margin` to be applied.
- `<input>` s, `<select>` s, `<textarea>` s, and `<button>` s are mostly addressed by Normalize, but Reboot removes their `margin` and sets `line-height: inherit`, too.
- `<textarea>` s are modified to only be resizable vertically as horizontal resizing often “breaks” page layout.
- `<button>` s and `<input>` button elements have `cursor: pointer` when `:not(:disabled)`.

These changes, and more, are demonstrated below.

Some date inputs types are [not fully supported](https://caniuse.com/input-datetime) by the latest versions of Safari and Firefox.

Example legend

Example input

Example email

Example telephone

Example url

Example number

Example search

Example range

Example file input

Example selectChoose...Option 1Option 2Option 3Option 4Option 5Option 6

Check this checkbox


Option one is this and that

Option two is something else that’s also super long to demonstrate the wrapping of these fancy form controls.

Option three is disabled


Example textarea

Example date

Example time

Example password

Example datetime-local

Example week

Example month

Example color

Example output100

Button submit

Button submit

### Pointers on buttons [Link to this section: Pointers on buttons](https://getbootstrap.com/docs/5.3/content/reboot/\#pointers-on-buttons)

Reboot includes an enhancement for `role="button"` to change the default cursor to `pointer`. Add this attribute to elements to help indicate elements are interactive. This role isn’t necessary for `<button>` elements, which get their own `cursor` change.

Non-button element button

html

```html
<span role="button" tabindex="0">Non-button element button</span>
```

## Misc elements [Link to this section: Misc elements](https://getbootstrap.com/docs/5.3/content/reboot/\#misc-elements)

### Address [Link to this section: Address](https://getbootstrap.com/docs/5.3/content/reboot/\#address)

The `<address>` element is updated to reset the browser default `font-style` from `italic` to `normal`. `line-height` is also now inherited, and `margin-bottom: 1rem` has been added. `<address>` s are for presenting contact information for the nearest ancestor (or an entire body of work). Preserve formatting by ending lines with `<br>`.

**ACME Corporation**

1123 Fictional St,

San Francisco, CA 94103

P: (123) 456-7890
**Full Name**

[first.last@example.com](mailto:first.last@example.com)

### Blockquote [Link to this section: Blockquote](https://getbootstrap.com/docs/5.3/content/reboot/\#blockquote)

The default `margin` on blockquotes is `1em 40px`, so we reset that to `0 0 1rem` for something more consistent with other elements.

> A well-known quote, contained in a blockquote element.

Someone famous in Source Title

### Inline elements [Link to this section: Inline elements](https://getbootstrap.com/docs/5.3/content/reboot/\#inline-elements)

The `<abbr>` element receives basic styling to make it stand out amongst paragraph text.


The HTML abbreviation element.


### Summary [Link to this section: Summary](https://getbootstrap.com/docs/5.3/content/reboot/\#summary)

The default `cursor` on summary is `text`, so we reset that to `pointer` to convey that the element can be interacted with by clicking on it.

Some details

More info about the details.

Even more details

Here are even more details about the details.

## HTML5 `[hidden]` attribute [Link to this section: HTML5 ](https://getbootstrap.com/docs/5.3/content/reboot/\#html5-hidden-attribute)

HTML5 adds [a new global attribute named `[hidden]`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden), which is styled as `display: none` by default. Borrowing an idea from [PureCSS](https://purecss.io/), we improve upon this default by making `[hidden] { display: none !important; }` to help prevent its `display` from getting accidentally overridden.

```html
<input type="text" hidden>

```

Since `[hidden]` is not compatible with jQuery’s `$(...).hide()` and `$(...).show()` methods, we don’t specifically endorse `[hidden]` over other techniques for managing the `display` of elements.

To merely toggle the visibility of an element, meaning its `display` is not modified and the element can still affect the flow of the document, use [the `.invisible` class](https://getbootstrap.com/docs/5.3/utilities/visibility) instead.