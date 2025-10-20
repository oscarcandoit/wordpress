---
url: https://getbootstrap.com/docs/4.2/content/reboot
scraped_at: 2025-10-20T02:38:50.802Z
---

[Skip to main content](https://getbootstrap.com/docs/4.2/content/reboot/#content) [There's a newer version of Bootstrap!](https://getbootstrap.com/)

```

```

Menu

- [Approach](https://getbootstrap.com/docs/4.2/content/reboot/#approach)
- [Page defaults](https://getbootstrap.com/docs/4.2/content/reboot/#page-defaults)
- [Native font stack](https://getbootstrap.com/docs/4.2/content/reboot/#native-font-stack)
- [Headings and paragraphs](https://getbootstrap.com/docs/4.2/content/reboot/#headings-and-paragraphs)
- [Lists](https://getbootstrap.com/docs/4.2/content/reboot/#lists)
- [Preformatted text](https://getbootstrap.com/docs/4.2/content/reboot/#preformatted-text)
- [Tables](https://getbootstrap.com/docs/4.2/content/reboot/#tables)
- [Forms](https://getbootstrap.com/docs/4.2/content/reboot/#forms)
- [Misc elements](https://getbootstrap.com/docs/4.2/content/reboot/#misc-elements)
  - [Address](https://getbootstrap.com/docs/4.2/content/reboot/#address)
  - [Blockquote](https://getbootstrap.com/docs/4.2/content/reboot/#blockquote)
  - [Inline elements](https://getbootstrap.com/docs/4.2/content/reboot/#inline-elements)
  - [Summary](https://getbootstrap.com/docs/4.2/content/reboot/#summary)
- [HTML5 \[hidden\] attribute](https://getbootstrap.com/docs/4.2/content/reboot/#html5-hidden-attribute)

# Reboot

Reboot, a collection of element-specific CSS changes in a single file, kickstart Bootstrap to provide an elegant, consistent, and simple baseline to build upon.

## Approach [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#approach)

Reboot builds upon Normalize, providing many HTML elements with somewhat opinionated styles using only element selectors. Additional styling is done only with classes. For example, we reboot some `<table>` styles for a simpler baseline and later provide `.table`, `.table-bordered`, and more.

Here are our guidelines and reasons for choosing what to override in Reboot:

- Update some browser default values to use `rem` s instead of `em` s for scalable component spacing.
- Avoid `margin-top`. Vertical margins can collapse, yielding unexpected results. More importantly though, a single direction of `margin` is a simpler mental model.
- For easier scaling across device sizes, block elements should use `rem` s for `margin` s.
- Keep declarations of `font`-related properties to a minimum, using `inherit` whenever possible.

## Page defaults [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#page-defaults)

The `<html>` and `<body>` elements are updated to provide better page-wide defaults. More specifically:

- The `box-sizing` is globally set on every element—including `*::before` and `*::after`, to `border-box`. This ensures that the declared width of element is never exceeded due to padding or border.

  - No base `font-size` is declared on the `<html>`, but `16px` is assumed (the browser default). `font-size: 1rem` is applied on the `<body>` for easy responsive type-scaling via media queries while respecting user preferences and ensuring a more accessible approach.
- The `<body>` also sets a global `font-family`, `line-height`, and `text-align`. This is inherited later by some form elements to prevent font inconsistencies.
- For safety, the `<body>` has a declared `background-color`, defaulting to `#fff`.

## Native font stack [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#native-font-stack)

The default web fonts (Helvetica Neue, Helvetica, and Arial) have been dropped in Bootstrap 4 and replaced with a “native font stack” for optimum text rendering on every device and OS. Read more about [native font stacks in this _Smashing Magazine_ article](https://www.smashingmagazine.com/2015/11/using-system-ui-fonts-practical-guide/).

Copy

```sass
$font-family-sans-serif:
  // Safari for macOS and iOS (San Francisco)
  -apple-system,
  // Chrome < 56 for macOS (San Francisco)
  BlinkMacSystemFont,
  // Windows
  "Segoe UI",
  // Android
  "Roboto",
  // Basic web fallback
  "Helvetica Neue", Arial, sans-serif,
  // Emoji fonts
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol" !default;
```

This `font-family` is applied to the `<body>` and automatically inherited globally throughout Bootstrap. To switch the global `font-family`, update `$font-family-base` and recompile Bootstrap.

## Headings and paragraphs [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#headings-and-paragraphs)

All heading elements—e.g., `<h1>`—and `<p>` are reset to have their `margin-top` removed. Headings have `margin-bottom: .5rem` added and paragraphs `margin-bottom: 1rem` for easy spacing.

| Heading | Example |
| --- | --- |
| `<h1></h1>` | h1. Bootstrap heading |
| `<h2></h2>` | h2. Bootstrap heading |
| `<h3></h3>` | h3. Bootstrap heading |
| `<h4></h4>` | h4. Bootstrap heading |
| `<h5></h5>` | h5. Bootstrap heading |
| `<h6></h6>` | h6. Bootstrap heading |

## Lists [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#lists)

All lists— `<ul>`, `<ol>`, and `<dl>`—have their `margin-top` removed and a `margin-bottom: 1rem`. Nested lists have no `margin-bottom`.

- Lorem ipsum dolor sit amet
- Consectetur adipiscing elit
- Integer molestie lorem at massa
- Facilisis in pretium nisl aliquet
- Nulla volutpat aliquam velit
  - Phasellus iaculis neque
  - Purus sodales ultricies
  - Vestibulum laoreet porttitor sem
  - Ac tristique libero volutpat at
- Faucibus porta lacus fringilla vel
- Aenean sit amet erat nunc
- Eget porttitor lorem

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem

For simpler styling, clear hierarchy, and better spacing, description lists have updated `margin` s. `<dd>` s reset `margin-left` to `0` and add `margin-bottom: .5rem`. `<dt>` s are **bolded**.

Description listsA description list is perfect for defining terms.EuismodVestibulum id ligula porta felis euismod semper eget lacinia odio sem.Donec id elit non mi porta gravida at eget metus.Malesuada portaEtiam porta sem malesuada magna mollis euismod.

## Preformatted text [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#preformatted-text)

The `<pre>` element is reset to remove its `margin-top` and use `rem` units for its `margin-bottom`.

```
.example-element {
  margin-bottom: 1rem;
}

```

## Tables [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#tables)

Tables are slightly adjusted to style `<caption>` s, collapse borders, and ensure consistent `text-align` throughout. Additional changes for borders, padding, and more come with [the `.table` class](https://getbootstrap.com/docs/4.2/content/tables/).

| Table heading | Table heading | Table heading | Table heading |
| --- | --- | --- | --- |
| Table cell | Table cell | Table cell | Table cell |
| Table cell | Table cell | Table cell | Table cell |
| Table cell | Table cell | Table cell | Table cell |

This is an example table, and this is its caption to describe the contents.


## Forms [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#forms)

Various form elements have been rebooted for simpler base styles. Here are some of the most notable changes:

- `<fieldset>` s have no borders, padding, or margin so they can be easily used as wrappers for individual inputs or groups of inputs.
- `<legend>` s, like fieldsets, have also been restyled to be displayed as a heading of sorts.
- `<label>` s are set to `display: inline-block` to allow `margin` to be applied.
- `<input>` s, `<select>` s, `<textarea>` s, and `<button>` s are mostly addressed by Normalize, but Reboot removes their `margin` and sets `line-height: inherit`, too.
- `<textarea>` s are modified to only be resizable vertically as horizontal resizing often “breaks” page layout.

These changes, and more, are demonstrated below.

Example legend

Example input

Example selectChoose...Option 1Option 2Option 3Option 4Option 5Option 6

Check this checkbox


Option one is this and that

Option two is something else that's also super long to demonstrate the wrapping of these fancy form controls.

Option three is disabled


Example textarea

Example date

Example time

Example output100

Button submit

Button submit

## Misc elements [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#misc-elements)

### Address [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#address)

The `<address>` element is updated to reset the browser default `font-style` from `italic` to `normal`. `line-height` is also now inherited, and `margin-bottom: 1rem` has been added. `<address>` s are for presenting contact information for the nearest ancestor (or an entire body of work). Preserve formatting by ending lines with `<br>`.

**Twitter, Inc.**

1355 Market St, Suite 900

San Francisco, CA 94103

P: (123) 456-7890
**Full Name**

[first.last@example.com](mailto:first.last@example.com)

### Blockquote [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#blockquote)

The default `margin` on blockquotes is `1em 40px`, so we reset that to `0 0 1rem` for something more consistent with other elements.

> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.

### Inline elements [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#inline-elements)

The `<abbr>` element receives basic styling to make it stand out amongst paragraph text.

Nulla attr vitae elit libero, a pharetra augue.

### Summary [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#summary)

The default `cursor` on summary is `text`, so we reset that to `pointer` to convey that the element can be interacted with by clicking on it.

Some details

More info about the details.

Even more details

Here are even more details about the details.

## HTML5 `[hidden]` attribute [Anchor](https://getbootstrap.com/docs/4.2/content/reboot/\#html5-hidden-attribute)

HTML5 adds [a new global attribute named `[hidden]`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden), which is styled as `display: none` by default. Borrowing an idea from [PureCSS](https://purecss.io/), we improve upon this default by making `[hidden] { display: none !important; }` to help prevent its `display` from getting accidentally overridden. While `[hidden]` isn’t natively supported by IE10, the explicit declaration in our CSS gets around that problem.

Copy

```html
<input type="text" hidden>
```

##### jQuery incompatibility

`[hidden]` is not compatible with jQuery’s `$(...).hide()` and `$(...).show()` methods. Therefore, we don’t currently especially endorse `[hidden]` over other techniques for managing the `display` of elements.

To merely toggle the visibility of an element, meaning its `display` is not modified and the element can still affect the flow of the document, use [the `.invisible` class](https://getbootstrap.com/docs/4.2/utilities/visibility/) instead.