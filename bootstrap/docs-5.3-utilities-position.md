---
url: https://getbootstrap.com/docs/5.3/utilities/position
scraped_at: 2025-10-20T02:36:37.315Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/position/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/position/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/position.mdx "View and edit this file on GitHub")

# Position

Use these shorthand utilities for quickly configuring the position of an element.

On this page
**On this page**

* * *

## Position values [Link to this section: Position values](https://getbootstrap.com/docs/5.3/utilities/position/\#position-values)

Quick positioning classes are available, though they are not responsive.

```html
<div class="position-static">...</div>
<div class="position-relative">...</div>
<div class="position-absolute">...</div>
<div class="position-fixed">...</div>
<div class="position-sticky">...</div>

```

## Arrange elements [Link to this section: Arrange elements](https://getbootstrap.com/docs/5.3/utilities/position/\#arrange-elements)

Arrange elements easily with the edge positioning utilities. The format is `{property}-{position}`.

Where _property_ is one of:

- `top` \- for the vertical `top` position
- `start` \- for the horizontal `left` position (in LTR)
- `bottom` \- for the vertical `bottom` position
- `end` \- for the horizontal `right` position (in LTR)

Where _position_ is one of:

- `0` \- for `0` edge position
- `50` \- for `50%` edge position
- `100` \- for `100%` edge position

(You can add more position values by adding entries to the `$position-values` Sass map variable.)

html

```html
<div class="position-relative">
  <div class="position-absolute top-0 start-0"></div>
  <div class="position-absolute top-0 end-0"></div>
  <div class="position-absolute top-50 start-50"></div>
  <div class="position-absolute bottom-50 end-50"></div>
  <div class="position-absolute bottom-0 start-0"></div>
  <div class="position-absolute bottom-0 end-0"></div>
</div>
```

## Center elements [Link to this section: Center elements](https://getbootstrap.com/docs/5.3/utilities/position/\#center-elements)

In addition, you can also center the elements with the transform utility class `.translate-middle`.

This class applies the transformations `translateX(-50%)` and `translateY(-50%)` to the element which, in combination with the edge positioning utilities, allows you to absolute center an element.

html

```html
<div class="position-relative">
  <div class="position-absolute top-0 start-0 translate-middle"></div>
  <div class="position-absolute top-0 start-50 translate-middle"></div>
  <div class="position-absolute top-0 start-100 translate-middle"></div>
  <div class="position-absolute top-50 start-0 translate-middle"></div>
  <div class="position-absolute top-50 start-50 translate-middle"></div>
  <div class="position-absolute top-50 start-100 translate-middle"></div>
  <div class="position-absolute top-100 start-0 translate-middle"></div>
  <div class="position-absolute top-100 start-50 translate-middle"></div>
  <div class="position-absolute top-100 start-100 translate-middle"></div>
</div>
```

By adding `.translate-middle-x` or `.translate-middle-y` classes, elements can be positioned only in horizontal or vertical direction.

html

```html
<div class="position-relative">
  <div class="position-absolute top-0 start-0"></div>
  <div class="position-absolute top-0 start-50 translate-middle-x"></div>
  <div class="position-absolute top-0 end-0"></div>
  <div class="position-absolute top-50 start-0 translate-middle-y"></div>
  <div class="position-absolute top-50 start-50 translate-middle"></div>
  <div class="position-absolute top-50 end-0 translate-middle-y"></div>
  <div class="position-absolute bottom-0 start-0"></div>
  <div class="position-absolute bottom-0 start-50 translate-middle-x"></div>
  <div class="position-absolute bottom-0 end-0"></div>
</div>
```

## Examples [Link to this section: Examples](https://getbootstrap.com/docs/5.3/utilities/position/\#examples)

Here are some real life examples of these classes:

Mails +99 unread messages

Marker

Alerts unread messages

html

```html
<button type="button" class="btn btn-primary position-relative">
  Mails <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill text-bg-secondary">+99 <span class="visually-hidden">unread messages</span></span>
</button>

<div class="position-relative py-2 px-4 text-bg-secondary border border-secondary rounded-pill">
  Marker <svg width="1em" height="1em" viewBox="0 0 16 16" class="position-absolute top-100 start-50 translate-middle mt-1" fill="var(--bs-secondary)" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M7.247 11.14L2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z"/></svg>
</div>

<button type="button" class="btn btn-primary position-relative">
  Alerts <span class="position-absolute top-0 start-100 translate-middle badge border border-light rounded-circle bg-danger p-2"><span class="visually-hidden">unread messages</span></span>
</button>
```

You can use these classes with existing components to create new ones. Remember that you can extend its functionality by adding entries to the `$position-values` variable.

123

html

```html
<div class="position-relative m-4">
  <div class="progress" role="progressbar" aria-label="Progress" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" style="height: 1px;">
    <div class="progress-bar" style="width: 50%"></div>
  </div>
  <button type="button" class="position-absolute top-0 start-0 translate-middle btn btn-sm btn-primary rounded-pill" style="width: 2rem; height:2rem;">1</button>
  <button type="button" class="position-absolute top-0 start-50 translate-middle btn btn-sm btn-primary rounded-pill" style="width: 2rem; height:2rem;">2</button>
  <button type="button" class="position-absolute top-0 start-100 translate-middle btn btn-sm btn-secondary rounded-pill" style="width: 2rem; height:2rem;">3</button>
</div>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/position/\#css)

### Sass maps [Link to this section: Sass maps](https://getbootstrap.com/docs/5.3/utilities/position/\#sass-maps)

Default position utility values are declared in a Sass map, then used to generate our utilities.

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$position-values: (
  0: 0,
  50: 50%,
  100: 100%
);

```

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/position/\#sass-utilities-api)

Position utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"position": (
  property: position,
  values: static relative absolute fixed sticky
),
"top": (
  property: top,
  values: $position-values
),
"bottom": (
  property: bottom,
  values: $position-values
),
"start": (
  property: left,
  class: start,
  values: $position-values
),
"end": (
  property: right,
  class: end,
  values: $position-values
),
"translate-middle": (
  property: transform,
  class: translate-middle,
  values: (
    null: translate(-50%, -50%),
    x: translateX(-50%),
    y: translateY(-50%),
  )
),

```