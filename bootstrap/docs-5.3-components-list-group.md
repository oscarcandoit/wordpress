---
url: https://getbootstrap.com/docs/5.3/components/list-group
scraped_at: 2025-10-20T02:27:29.832Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/list-group/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/list-group/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/list-group.mdx "View and edit this file on GitHub")

# List group

List groups are a flexible and powerful component for displaying a series of content. Modify and extend them to support just about any content within.

On this page
**On this page**

* * *

## Basic example [Link to this section: Basic example](https://getbootstrap.com/docs/5.3/components/list-group/\#basic-example)

The most basic list group is an unordered list with list items and the proper classes. Build upon it with the options that follow, or with your own CSS as needed.

- An item
- A second item
- A third item
- A fourth item
- And a fifth one

html

```html
<ul class="list-group">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
  <li class="list-group-item">A fourth item</li>
  <li class="list-group-item">And a fifth one</li>
</ul>
```

## Active items [Link to this section: Active items](https://getbootstrap.com/docs/5.3/components/list-group/\#active-items)

Add `.active` to a `.list-group-item` to indicate the current active selection.

- An active item
- A second item
- A third item
- A fourth item
- And a fifth one

html

```html
<ul class="list-group">
  <li class="list-group-item active" aria-current="true">An active item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
  <li class="list-group-item">A fourth item</li>
  <li class="list-group-item">And a fifth one</li>
</ul>
```

## Links and buttons [Link to this section: Links and buttons](https://getbootstrap.com/docs/5.3/components/list-group/\#links-and-buttons)

Use `<a>` s or `<button>` s to create _actionable_ list group items with hover, disabled, and active states by adding `.list-group-item-action`. We separate these pseudo-classes to ensure list groups made of non-interactive elements (like `<li>` s or `<div>` s) don’t provide a click or tap affordance.

Make `.list-group-item-action` instances _appear_ disabled by adding `.disabled`, and `aria-disabled="true"` to inform assistive technologies that the element is disabled. You may require additional JavaScript to fully disable links and buttons.

Be sure to **not use the standard `.btn` classes here**.

[The current link item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A second link item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A third link item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A fourth link item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A disabled link item](https://getbootstrap.com/docs/5.3/components/list-group/#)

html

```html
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
    The current link item
  </a>
  <a href="#" class="list-group-item list-group-item-action">A second link item</a>
  <a href="#" class="list-group-item list-group-item-action">A third link item</a>
  <a href="#" class="list-group-item list-group-item-action">A fourth link item</a>
  <a href="#" class="list-group-item list-group-item-action disabled" aria-disabled="true">A disabled link item</a>
</div>
```

With `<button>` s, you can also make use of the `disabled` attribute instead of the `.disabled` class. Sadly, `<a>` s don’t support the disabled attribute.

The current button
A second button itemA third button itemA fourth button itemA disabled button item

html

```html
<div class="list-group">
  <button type="button" class="list-group-item list-group-item-action active" aria-current="true">
    The current button
  </button>
  <button type="button" class="list-group-item list-group-item-action">A second button item</button>
  <button type="button" class="list-group-item list-group-item-action">A third button item</button>
  <button type="button" class="list-group-item list-group-item-action">A fourth button item</button>
  <button type="button" class="list-group-item list-group-item-action" disabled>A disabled button item</button>
</div>
```

## Flush [Link to this section: Flush](https://getbootstrap.com/docs/5.3/components/list-group/\#flush)

Add `.list-group-flush` to remove some borders and rounded corners to render list group items edge-to-edge in a parent container (e.g., cards).

- An item
- A second item
- A third item
- A fourth item
- And a fifth one

html

```html
<ul class="list-group list-group-flush">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
  <li class="list-group-item">A fourth item</li>
  <li class="list-group-item">And a fifth one</li>
</ul>
```

## Numbered [Link to this section: Numbered](https://getbootstrap.com/docs/5.3/components/list-group/\#numbered)

Add the `.list-group-numbered` modifier class (and optionally use an `<ol>` element) to opt into numbered list group items. Numbers are generated via CSS (as opposed to a `<ol>` s default browser styling) for better placement inside list group items and to allow for better customization.

Numbers are generated by `counter-reset` on the `<ol>`, and then styled and placed with a `::before` pseudo-element on the `<li>` with `counter-increment` and `content`.

1. A list item
2. A list item
3. A list item

html

```html
<ol class="list-group list-group-numbered">
  <li class="list-group-item">A list item</li>
  <li class="list-group-item">A list item</li>
  <li class="list-group-item">A list item</li>
</ol>
```

These work great with custom content as well.

1. Subheading


    Content for list item

14
2. Subheading


    Content for list item

14
3. Subheading


    Content for list item

14

html

```html
<ol class="list-group list-group-numbered">
  <li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto">
      <div class="fw-bold">Subheading</div>
      Content for list item
    </div>
    <span class="badge text-bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto">
      <div class="fw-bold">Subheading</div>
      Content for list item
    </div>
    <span class="badge text-bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto">
      <div class="fw-bold">Subheading</div>
      Content for list item
    </div>
    <span class="badge text-bg-primary rounded-pill">14</span>
  </li>
</ol>
```

## Horizontal [Link to this section: Horizontal](https://getbootstrap.com/docs/5.3/components/list-group/\#horizontal)

Add `.list-group-horizontal` to change the layout of list group items from vertical to horizontal across all breakpoints. Alternatively, choose a responsive variant `.list-group-horizontal-{sm|md|lg|xl|xxl}` to make a list group horizontal starting at that breakpoint’s `min-width`. Currently **horizontal list groups cannot be combined with flush list groups.**

**ProTip:** Want equal-width list group items when horizontal? Add `.flex-fill` to each list group item.

- An item
- A second item
- A third item

- An item
- A second item
- A third item

- An item
- A second item
- A third item

- An item
- A second item
- A third item

- An item
- A second item
- A third item

- An item
- A second item
- A third item

html

```html
<ul class="list-group list-group-horizontal">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
<ul class="list-group list-group-horizontal-sm">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
<ul class="list-group list-group-horizontal-md">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
<ul class="list-group list-group-horizontal-lg">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
<ul class="list-group list-group-horizontal-xl">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
<ul class="list-group list-group-horizontal-xxl">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
```

## Variants [Link to this section: Variants](https://getbootstrap.com/docs/5.3/components/list-group/\#variants)

**Heads up!** As of v5.3.0, the `list-group-item-variant()` Sass mixin is deprecated. List group item variants now have their CSS variables overridden in [a Sass loop](https://getbootstrap.com/docs/5.3/components/list-group/#sass-loops).

Use contextual classes to style list items with a stateful background and color.

- A simple default list group item
- A simple primary list group item
- A simple secondary list group item
- A simple success list group item
- A simple danger list group item
- A simple warning list group item
- A simple info list group item
- A simple light list group item
- A simple dark list group item

html

```html
<ul class="list-group">
  <li class="list-group-item">A simple default list group item</li>

  <li class="list-group-item list-group-item-primary">A simple primary list group item</li>
  <li class="list-group-item list-group-item-secondary">A simple secondary list group item</li>
  <li class="list-group-item list-group-item-success">A simple success list group item</li>
  <li class="list-group-item list-group-item-danger">A simple danger list group item</li>
  <li class="list-group-item list-group-item-warning">A simple warning list group item</li>
  <li class="list-group-item list-group-item-info">A simple info list group item</li>
  <li class="list-group-item list-group-item-light">A simple light list group item</li>
  <li class="list-group-item list-group-item-dark">A simple dark list group item</li>
</ul>
```

### For links and buttons [Link to this section: For links and buttons](https://getbootstrap.com/docs/5.3/components/list-group/\#for-links-and-buttons)

Contextual classes also work with `.list-group-item-action` for `<a>` and `<button>` elements. Note the addition of the hover styles here not present in the previous example. Also supported is the `.active` state; apply it to indicate an active selection on a contextual list group item.

[A simple default list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple primary list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple secondary list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple success list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple danger list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple warning list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple info list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple light list group item](https://getbootstrap.com/docs/5.3/components/list-group/#) [A simple dark list group item](https://getbootstrap.com/docs/5.3/components/list-group/#)

html

```html
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action">A simple default list group item</a>

  <a href="#" class="list-group-item list-group-item-action list-group-item-primary">A simple primary list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-secondary">A simple secondary list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-success">A simple success list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-danger">A simple danger list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-warning">A simple warning list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-info">A simple info list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-light">A simple light list group item</a>
  <a href="#" class="list-group-item list-group-item-action list-group-item-dark">A simple dark list group item</a>
</div>
```

**Accessibility tip:** Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies like screen readers. Please ensure the meaning is obvious from the content itself (e.g., the visible text with a [_sufficient_ color contrast](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#color-contrast)) or is included through alternative means, such as additional text hidden with the `.visually-hidden` class.

## With badges [Link to this section: With badges](https://getbootstrap.com/docs/5.3/components/list-group/\#with-badges)

Add badges to any list group item to show unread counts, activity, and more with the help of some [utilities](https://getbootstrap.com/docs/5.3/utilities/flex).

- A list item
14
- A second list item
2
- A third list item
1

html

```html
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A list item
    <span class="badge text-bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A second list item
    <span class="badge text-bg-primary rounded-pill">2</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A third list item
    <span class="badge text-bg-primary rounded-pill">1</span>
  </li>
</ul>
```

## Custom content [Link to this section: Custom content](https://getbootstrap.com/docs/5.3/components/list-group/\#custom-content)

Add nearly any HTML within, even for linked list groups like the one below, with the help of [flexbox utilities](https://getbootstrap.com/docs/5.3/utilities/flex).

[**List group item heading** 3 days ago\\
\\
Some placeholder content in a paragraph.\\
And some small print.](https://getbootstrap.com/docs/5.3/components/list-group/#) [**List group item heading** 3 days ago\\
\\
Some placeholder content in a paragraph.\\
And some muted small print.](https://getbootstrap.com/docs/5.3/components/list-group/#) [**List group item heading** 3 days ago\\
\\
Some placeholder content in a paragraph.\\
And some muted small print.](https://getbootstrap.com/docs/5.3/components/list-group/#)

html

```html
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small>3 days ago</small>
    </div>
    <p class="mb-1">Some placeholder content in a paragraph.</p>
    <small>And some small print.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-body-secondary">3 days ago</small>
    </div>
    <p class="mb-1">Some placeholder content in a paragraph.</p>
    <small class="text-body-secondary">And some muted small print.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-body-secondary">3 days ago</small>
    </div>
    <p class="mb-1">Some placeholder content in a paragraph.</p>
    <small class="text-body-secondary">And some muted small print.</small>
  </a>
</div>
```

## Checkboxes and radios [Link to this section: Checkboxes and radios](https://getbootstrap.com/docs/5.3/components/list-group/\#checkboxes-and-radios)

Place Bootstrap’s checkboxes and radios within list group items and customize as needed. You can use them without `<label>` s, but please remember to include an `aria-label` attribute and value for accessibility.

- [ ] First checkbox
- [ ] Second checkbox
- [ ] Third checkbox

html

```html
<ul class="list-group">
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckbox">
    <label class="form-check-label" for="firstCheckbox">First checkbox</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="secondCheckbox">
    <label class="form-check-label" for="secondCheckbox">Second checkbox</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="thirdCheckbox">
    <label class="form-check-label" for="thirdCheckbox">Third checkbox</label>
  </li>
</ul>
```

- First radio
- Second radio
- Third radio

html

```html
<ul class="list-group">
  <li class="list-group-item">
    <input class="form-check-input me-1" type="radio" name="listGroupRadio" value="" id="firstRadio" checked>
    <label class="form-check-label" for="firstRadio">First radio</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="radio" name="listGroupRadio" value="" id="secondRadio">
    <label class="form-check-label" for="secondRadio">Second radio</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="radio" name="listGroupRadio" value="" id="thirdRadio">
    <label class="form-check-label" for="thirdRadio">Third radio</label>
  </li>
</ul>
```

You can use `.stretched-link` on `<label>` s to make the whole list group item clickable.

- [ ] First checkbox
- [ ] Second checkbox
- [ ] Third checkbox

html

```html
<ul class="list-group">
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckboxStretched">
    <label class="form-check-label stretched-link" for="firstCheckboxStretched">First checkbox</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="secondCheckboxStretched">
    <label class="form-check-label stretched-link" for="secondCheckboxStretched">Second checkbox</label>
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="thirdCheckboxStretched">
    <label class="form-check-label stretched-link" for="thirdCheckboxStretched">Third checkbox</label>
  </li>
</ul>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/list-group/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/components/list-group/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, list groups now use local CSS variables on `.list-group` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

[scss/\_list-group.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_list-group.scss)

```scss
--#{$prefix}list-group-color: #{$list-group-color};
--#{$prefix}list-group-bg: #{$list-group-bg};
--#{$prefix}list-group-border-color: #{$list-group-border-color};
--#{$prefix}list-group-border-width: #{$list-group-border-width};
--#{$prefix}list-group-border-radius: #{$list-group-border-radius};
--#{$prefix}list-group-item-padding-x: #{$list-group-item-padding-x};
--#{$prefix}list-group-item-padding-y: #{$list-group-item-padding-y};
--#{$prefix}list-group-action-color: #{$list-group-action-color};
--#{$prefix}list-group-action-hover-color: #{$list-group-action-hover-color};
--#{$prefix}list-group-action-hover-bg: #{$list-group-hover-bg};
--#{$prefix}list-group-action-active-color: #{$list-group-action-active-color};
--#{$prefix}list-group-action-active-bg: #{$list-group-action-active-bg};
--#{$prefix}list-group-disabled-color: #{$list-group-disabled-color};
--#{$prefix}list-group-disabled-bg: #{$list-group-disabled-bg};
--#{$prefix}list-group-active-color: #{$list-group-active-color};
--#{$prefix}list-group-active-bg: #{$list-group-active-bg};
--#{$prefix}list-group-active-border-color: #{$list-group-active-border-color};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/list-group/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$list-group-color:                  var(--#{$prefix}body-color);
$list-group-bg:                     var(--#{$prefix}body-bg);
$list-group-border-color:           var(--#{$prefix}border-color);
$list-group-border-width:           var(--#{$prefix}border-width);
$list-group-border-radius:          var(--#{$prefix}border-radius);

$list-group-item-padding-y:         $spacer * .5;
$list-group-item-padding-x:         $spacer;
// fusv-disable
$list-group-item-bg-scale:          -80%; // Deprecated in v5.3.0
$list-group-item-color-scale:       40%; // Deprecated in v5.3.0
// fusv-enable

$list-group-hover-bg:               var(--#{$prefix}tertiary-bg);
$list-group-active-color:           $component-active-color;
$list-group-active-bg:              $component-active-bg;
$list-group-active-border-color:    $list-group-active-bg;

$list-group-disabled-color:         var(--#{$prefix}secondary-color);
$list-group-disabled-bg:            $list-group-bg;

$list-group-action-color:           var(--#{$prefix}secondary-color);
$list-group-action-hover-color:     var(--#{$prefix}emphasis-color);

$list-group-action-active-color:    var(--#{$prefix}body-color);
$list-group-action-active-bg:       var(--#{$prefix}secondary-bg);

```

### Sass mixins [Link to this section: Sass mixins](https://getbootstrap.com/docs/5.3/components/list-group/\#sass-mixins)

Deprecated in v5.3.0

[scss/mixins/\_list-group.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/mixins/_list-group.scss)

```scss
@mixin list-group-item-variant($state, $background, $color) {
  .list-group-item-#{$state} {
    color: $color;
    background-color: $background;

    &.list-group-item-action {
      &:hover,
      &:focus {
        color: $color;
        background-color: shade-color($background, 10%);
      }

      &.active {
        color: $white;
        background-color: $color;
        border-color: $color;
      }
    }
  }
}

```

### Sass loops [Link to this section: Sass loops](https://getbootstrap.com/docs/5.3/components/list-group/\#sass-loops)

Loop that generates the modifier classes with an overriding of CSS variables.

[scss/\_list-group.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_list-group.scss)

```scss
// List group contextual variants
//
// Add modifier classes to change text and background color on individual items.
// Organizationally, this must come after the `:hover` states.

@each $state in map-keys($theme-colors) {
  .list-group-item-#{$state} {
    --#{$prefix}list-group-color: var(--#{$prefix}#{$state}-text-emphasis);
    --#{$prefix}list-group-bg: var(--#{$prefix}#{$state}-bg-subtle);
    --#{$prefix}list-group-border-color: var(--#{$prefix}#{$state}-border-subtle);
    --#{$prefix}list-group-action-hover-color: var(--#{$prefix}emphasis-color);
    --#{$prefix}list-group-action-hover-bg: var(--#{$prefix}#{$state}-border-subtle);
    --#{$prefix}list-group-action-active-color: var(--#{$prefix}emphasis-color);
    --#{$prefix}list-group-action-active-bg: var(--#{$prefix}#{$state}-border-subtle);
    --#{$prefix}list-group-active-color: var(--#{$prefix}#{$state}-bg-subtle);
    --#{$prefix}list-group-active-bg: var(--#{$prefix}#{$state}-text-emphasis);
    --#{$prefix}list-group-active-border-color: var(--#{$prefix}#{$state}-text-emphasis);
  }
}

```

## JavaScript behavior [Link to this section: JavaScript behavior](https://getbootstrap.com/docs/5.3/components/list-group/\#javascript-behavior)

Use the tab JavaScript plugin—include it individually or through the compiled `bootstrap.js` file—to extend our list group to create tabbable panes of local content.

[Home](https://getbootstrap.com/docs/5.3/components/list-group/#list-home) [Profile](https://getbootstrap.com/docs/5.3/components/list-group/#list-profile) [Messages](https://getbootstrap.com/docs/5.3/components/list-group/#list-messages) [Settings](https://getbootstrap.com/docs/5.3/components/list-group/#list-settings)

Some placeholder content in a paragraph relating to "Home". And some more content, used here just to pad out and fill this tab panel. In production, you would obviously have more real content here. And not just text. It could be anything, really. Text, images, forms.

Some placeholder content in a paragraph relating to "Profile". And some more content, used here just to pad out and fill this tab panel. In production, you would obviously have more real content here. And not just text. It could be anything, really. Text, images, forms.

Some placeholder content in a paragraph relating to "Messages". And some more content, used here just to pad out and fill this tab panel. In production, you would obviously have more real content here. And not just text. It could be anything, really. Text, images, forms.

Some placeholder content in a paragraph relating to "Settings". And some more content, used here just to pad out and fill this tab panel. In production, you would obviously have more real content here. And not just text. It could be anything, really. Text, images, forms.

```html
<div class="row">
  <div class="col-4">
    <div class="list-group" id="list-tab" role="tablist">
      <a class="list-group-item list-group-item-action active" id="list-home-list" data-bs-toggle="list" href="#list-home" role="tab" aria-controls="list-home">Home</a>
      <a class="list-group-item list-group-item-action" id="list-profile-list" data-bs-toggle="list" href="#list-profile" role="tab" aria-controls="list-profile">Profile</a>
      <a class="list-group-item list-group-item-action" id="list-messages-list" data-bs-toggle="list" href="#list-messages" role="tab" aria-controls="list-messages">Messages</a>
      <a class="list-group-item list-group-item-action" id="list-settings-list" data-bs-toggle="list" href="#list-settings" role="tab" aria-controls="list-settings">Settings</a>
    </div>
  </div>
  <div class="col-8">
    <div class="tab-content" id="nav-tabContent">
      <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">...</div>
      <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">...</div>
      <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">...</div>
      <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">...</div>
    </div>
  </div>
</div>

```

### Using data attributes [Link to this section: Using data attributes](https://getbootstrap.com/docs/5.3/components/list-group/\#using-data-attributes)

You can activate a list group navigation without writing any JavaScript by simply specifying `data-bs-toggle="list"` or on an element. Use these data attributes on `.list-group-item`.

```html
<div role="tabpanel">
  <!-- List group -->
  <div class="list-group" id="myList" role="tablist">
    <a class="list-group-item list-group-item-action active" data-bs-toggle="list" href="#home" role="tab">Home</a>
    <a class="list-group-item list-group-item-action" data-bs-toggle="list" href="#profile" role="tab">Profile</a>
    <a class="list-group-item list-group-item-action" data-bs-toggle="list" href="#messages" role="tab">Messages</a>
    <a class="list-group-item list-group-item-action" data-bs-toggle="list" href="#settings" role="tab">Settings</a>
  </div>

  <!-- Tab panes -->
  <div class="tab-content">
    <div class="tab-pane active" id="home" role="tabpanel">...</div>
    <div class="tab-pane" id="profile" role="tabpanel">...</div>
    <div class="tab-pane" id="messages" role="tabpanel">...</div>
    <div class="tab-pane" id="settings" role="tabpanel">...</div>
  </div>
</div>

```

### Via JavaScript [Link to this section: Via JavaScript](https://getbootstrap.com/docs/5.3/components/list-group/\#via-javascript)

Enable tabbable list item via JavaScript (each list item needs to be activated individually):

```js
const triggerTabList = document.querySelectorAll('#myTab a')
triggerTabList.forEach(triggerEl => {
  const tabTrigger = new bootstrap.Tab(triggerEl)

  triggerEl.addEventListener('click', event => {
    event.preventDefault()
    tabTrigger.show()
  })
})

```

You can activate individual list item in several ways:

```js
const triggerEl = document.querySelector('#myTab a[href="#profile"]')
bootstrap.Tab.getInstance(triggerEl).show() // Select tab by name

const triggerFirstTabEl = document.querySelector('#myTab li:first-child a')
bootstrap.Tab.getInstance(triggerFirstTabEl).show() // Select first tab

```

### Fade effect [Link to this section: Fade effect](https://getbootstrap.com/docs/5.3/components/list-group/\#fade-effect)

To make tabs panel fade in, add `.fade` to each `.tab-pane`. The first tab pane must also have `.show` to make the initial content visible.

```html
<div class="tab-content">
  <div class="tab-pane fade show active" id="home" role="tabpanel">...</div>
  <div class="tab-pane fade" id="profile" role="tabpanel">...</div>
  <div class="tab-pane fade" id="messages" role="tabpanel">...</div>
  <div class="tab-pane fade" id="settings" role="tabpanel">...</div>
</div>

```

### Methods [Link to this section: Methods](https://getbootstrap.com/docs/5.3/components/list-group/\#methods)

**All API methods are asynchronous and start a transition.** They return to the caller as soon as the transition is started, but before it ends. In addition, a method call on a transitioning component will be ignored. [Learn more in our JavaScript docs.](https://getbootstrap.com/docs/5.3/getting-started/javascript/#asynchronous-functions-and-transitions)

Activates your content as a tab element.

You can create a tab instance with the constructor, for example:

```js
const bsTab = new bootstrap.Tab('#myTab')

```

| Method | Description |
| --- | --- |
| `dispose` | Destroys an element’s tab. |
| `getInstance` | Static method which allows you to get the tab instance associated with a DOM element, you can use it like this: `bootstrap.Tab.getInstance(element)`. |
| `getOrCreateInstance` | Static method which returns a tab instance associated to a DOM element or create a new one in case it wasn’t initialized. You can use it like this: `bootstrap.Tab.getOrCreateInstance(element)`. |
| `show` | Selects the given tab and shows its associated pane. Any other tab that was previously selected becomes unselected and its associated pane is hidden. **Returns to the caller before the tab pane has actually been shown** (i.e. before the `shown.bs.tab` event occurs). |

### Events [Link to this section: Events](https://getbootstrap.com/docs/5.3/components/list-group/\#events)

When showing a new tab, the events fire in the following order:

1. `hide.bs.tab` (on the current active tab)
2. `show.bs.tab` (on the to-be-shown tab)
3. `hidden.bs.tab` (on the previous active tab, the same one as for the `hide.bs.tab` event)
4. `shown.bs.tab` (on the newly-active just-shown tab, the same one as for the `show.bs.tab` event)

If no tab was already active, then the `hide.bs.tab` and `hidden.bs.tab` events will not be fired.

| Event type | Description |
| --- | --- |
| `hide.bs.tab` | This event fires when a new tab is to be shown (and thus the previous active tab is to be hidden). Use `event.target` and `event.relatedTarget` to target the current active tab and the new soon-to-be-active tab, respectively. |
| `hidden.bs.tab` | This event fires after a new tab is shown (and thus the previous active tab is hidden). Use `event.target` and `event.relatedTarget` to target the previous active tab and the new active tab, respectively. |
| `show.bs.tab` | This event fires on tab show, but before the new tab has been shown. Use `event.target` and `event.relatedTarget` to target the active tab and the previous active tab (if available) respectively. |
| `shown.bs.tab` | This event fires on tab show after a tab has been shown. Use `event.target` and `event.relatedTarget` to target the active tab and the previous active tab (if available) respectively. |

```js
const tabElms = document.querySelectorAll('a[data-bs-toggle="list"]')
tabElms.forEach(tabElm => {
  tabElm.addEventListener('shown.bs.tab', event => {
    event.target // newly activated tab
    event.relatedTarget // previous active tab
  })
})

```