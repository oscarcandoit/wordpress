---
url: https://getbootstrap.com/docs/5.0/helpers/ratio
scraped_at: 2025-10-20T02:40:00.479Z
---

[Skip to main content](https://getbootstrap.com/docs/5.0/helpers/ratio/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.0/helpers/ratio/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.0.2/site/content/docs/5.0/helpers/ratio.md "View and edit this file on GitHub")

# Ratios

Use generated pseudo elements to make an element maintain the aspect ratio of your choosing. Perfect for responsively handling video or slideshow embeds based on the width of the parent.

**On this page**

## About [Anchor](https://getbootstrap.com/docs/5.0/helpers/ratio/\#about)

Use the ratio helper to manage the aspect ratios of external content like `<iframe>` s, `<embed>` s, `<video>` s, and `<object>` s. These helpers also can be used on any standard HTML child element (e.g., a `<div>` or `<img>`). Styles are applied from the parent `.ratio` class directly to the child.

Aspect ratios are declared in a Sass map and included in each class via CSS variable, which also allows [custom aspect ratios](https://getbootstrap.com/docs/5.0/helpers/ratio/#custom-ratios).

**Pro-Tip!** You don’t need `frameborder="0"` on your `<iframe>` s as we override that for you in [Reboot](https://getbootstrap.com/docs/5.0/content/reboot/).

## Example [Anchor](https://getbootstrap.com/docs/5.0/helpers/ratio/\#example)

Wrap any embed, like an `<iframe>`, in a parent element with `.ratio` and an aspect ratio class. The immediate child element is automatically sized thanks to our universal selector `.ratio > *`.

REO Speedwagon - Can't Fight This Feeling (Official HD Video) - YouTube

[Photo image of RSpwagonVEVO](https://www.youtube.com/channel/UCLLXuGtdhCmVYY2nqGx20Cg?embeds_referring_euri=https%3A%2F%2Fgetbootstrap.com%2F)

RSpwagonVEVO

[REO Speedwagon - Can't Fight This Feeling (Official HD Video)](https://www.youtube.com/watch?v=zpOULjyy-n8)

RSpwagonVEVO

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

Copy

```html
<div class="ratio ratio-16x9">
  <iframe src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" title="YouTube video" allowfullscreen></iframe>
</div>
```

## Aspect ratios [Anchor](https://getbootstrap.com/docs/5.0/helpers/ratio/\#aspect-ratios)

Aspect ratios can be customized with modifier classes. By default the following ratio classes are provided:

1x1

4x3

16x9

21x9

Copy

```html
<div class="ratio ratio-1x1">
  <div>1x1</div>
</div>
<div class="ratio ratio-4x3">
  <div>4x3</div>
</div>
<div class="ratio ratio-16x9">
  <div>16x9</div>
</div>
<div class="ratio ratio-21x9">
  <div>21x9</div>
</div>
```

## Custom ratios [Anchor](https://getbootstrap.com/docs/5.0/helpers/ratio/\#custom-ratios)

Each `.ratio-*` class includes a CSS custom property (or CSS variable) in the selector. You can override this CSS variable to create custom aspect ratios on the fly with some quick math on your part.

For example, to create a 2x1 aspect ratio, set `--bs-aspect-ratio: 50%` on the `.ratio`.

2x1

Copy

```html
<div class="ratio" style="--bs-aspect-ratio: 50%;">
  <div>2x1</div>
</div>
```

This CSS variable makes it easy to modify the aspect ratio across breakpoints. The following is 4x3 to start, but changes to a custom 2x1 at the medium breakpoint.

Copy

```scss
.ratio-4x3 {
  @include media-breakpoint-up(md) {
    --bs-aspect-ratio: 50%; // 2x1
  }
}

```

4x3, then 2x1

Copy

```html
<div class="ratio ratio-4x3">
  <div>4x3, then 2x1</div>
</div>
```

## Sass map [Anchor](https://getbootstrap.com/docs/5.0/helpers/ratio/\#sass-map)

Within `_variables.scss`, you can change the aspect ratios you want to use. Here’s our default `$ratio-aspect-ratios` map. Modify the map as you like and recompile your Sass to put them to use.

Copy

```scss
$aspect-ratios: (
  "1x1": 100%,
  "4x3": calc(3 / 4 * 100%),
  "16x9": calc(9 / 16 * 100%),
  "21x9": calc(9 / 21 * 100%)
);

```