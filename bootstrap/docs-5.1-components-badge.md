---
url: https://getbootstrap.com/docs/5.1/components/badge
scraped_at: 2025-10-20T02:41:49.875Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/components/badge/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/components/badge/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/components/badge.md "View and edit this file on GitHub")

# Badges

Documentation and examples for badges, our small count and labeling component.

**On this page**

## Examples [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#examples)

Badges scale to match the size of the immediate parent element by using relative font sizing and `em` units. As of v5, badges no longer have focus or hover styles for links.

### Headings [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#headings)

# Example heading New

## Example heading New

### Example heading New

#### Example heading New

##### Example heading New

###### Example heading New

Copy

```html
<h1>Example heading <span class="badge bg-secondary">New</span></h1>
<h2>Example heading <span class="badge bg-secondary">New</span></h2>
<h3>Example heading <span class="badge bg-secondary">New</span></h3>
<h4>Example heading <span class="badge bg-secondary">New</span></h4>
<h5>Example heading <span class="badge bg-secondary">New</span></h5>
<h6>Example heading <span class="badge bg-secondary">New</span></h6>
```

### Buttons [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#buttons)

Badges can be used as part of links or buttons to provide a counter.

Notifications 4

Copy

```html
<button type="button" class="btn btn-primary">
  Notifications <span class="badge bg-secondary">4</span>
</button>
```

Note that depending on how they are used, badges may be confusing for users of screen readers and similar assistive technologies. While the styling of badges provides a visual cue as to their purpose, these users will simply be presented with the content of the badge. Depending on the specific situation, these badges may seem like random additional words or numbers at the end of a sentence, link, or button.

Unless the context is clear (as with the “Notifications” example, where it is understood that the “4” is the number of notifications), consider including additional context with a visually hidden piece of additional text.

### Positioned [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#positioned)

Use utilities to modify a `.badge` and position it in the corner of a link or button.

Inbox

99+
unread messages

Copy

```html
<button type="button" class="btn btn-primary position-relative">
  Inbox
  <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
    99+
    <span class="visually-hidden">unread messages</span>
  </span>
</button>
```

You can also replace the `.badge` class with a few more utilities without a count for a more generic indicator.

Profile
New alerts

Copy

```html
<button type="button" class="btn btn-primary position-relative">
  Profile
  <span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">
    <span class="visually-hidden">New alerts</span>
  </span>
</button>
```

## Background colors [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#background-colors)

Use our background utility classes to quickly change the appearance of a badge. Please note that when using Bootstrap’s default `.bg-light`, you’ll likely need a text color utility like `.text-dark` for proper styling. This is because background utilities do not set anything but `background-color`.

PrimarySecondarySuccessDangerWarningInfoLightDark

Copy

```html
<span class="badge bg-primary">Primary</span>
<span class="badge bg-secondary">Secondary</span>
<span class="badge bg-success">Success</span>
<span class="badge bg-danger">Danger</span>
<span class="badge bg-warning text-dark">Warning</span>
<span class="badge bg-info text-dark">Info</span>
<span class="badge bg-light text-dark">Light</span>
<span class="badge bg-dark">Dark</span>
```

##### Conveying meaning to assistive technologies

Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies – such as screen readers. Ensure that information denoted by the color is either obvious from the content itself (e.g. the visible text), or is included through alternative means, such as additional text hidden with the `.visually-hidden` class.

## Pill badges [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#pill-badges)

Use the `.rounded-pill` utility class to make badges more rounded with a larger `border-radius`.

PrimarySecondarySuccessDangerWarningInfoLightDark

Copy

```html
<span class="badge rounded-pill bg-primary">Primary</span>
<span class="badge rounded-pill bg-secondary">Secondary</span>
<span class="badge rounded-pill bg-success">Success</span>
<span class="badge rounded-pill bg-danger">Danger</span>
<span class="badge rounded-pill bg-warning text-dark">Warning</span>
<span class="badge rounded-pill bg-info text-dark">Info</span>
<span class="badge rounded-pill bg-light text-dark">Light</span>
<span class="badge rounded-pill bg-dark">Dark</span>
```

## Sass [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#sass)

### Variables [Anchor](https://getbootstrap.com/docs/5.1/components/badge/\#variables)

Copy

```scss
$badge-font-size:                   .75em;
$badge-font-weight:                 $font-weight-bold;
$badge-color:                       $white;
$badge-padding-y:                   .35em;
$badge-padding-x:                   .65em;
$badge-border-radius:               $border-radius;

```