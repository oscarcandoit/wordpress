---
url: https://getbootstrap.com/docs/5.1/customize/color
scraped_at: 2025-10-20T02:37:53.525Z
---

[Skip to main content](https://getbootstrap.com/docs/5.1/customize/color/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.1/customize/color/#bd-docs-nav)

[There's a newer version of Bootstrap!](https://getbootstrap.com/)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.1.3/site/content/docs/5.1/customize/color.md "View and edit this file on GitHub")

# Color

Bootstrap is supported by an extensive color system that themes our styles and components. This enables more comprehensive customization and extension for any project.

**On this page**

## Theme colors [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#theme-colors)

We use a subset of all colors to create a smaller color palette for generating color schemes, also available as Sass variables and a Sass map in Bootstrap’s `scss/_variables.scss` file.

Primary

Secondary

Success

Danger

Warning

Info

Light

Dark

All these colors are available as a Sass map, `$theme-colors`.

Copy

```scss
$theme-colors: (
  "primary":    $primary,
  "secondary":  $secondary,
  "success":    $success,
  "info":       $info,
  "warning":    $warning,
  "danger":     $danger,
  "light":      $light,
  "dark":       $dark
);

```

Check out [our Sass maps and loops docs](https://getbootstrap.com/docs/5.1/customize/sass/#maps-and-loops) for how to modify these colors.

## All colors [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#all-colors)

All Bootstrap colors are available as Sass variables and a Sass map in `scss/_variables.scss` file. To avoid increased file sizes, we don’t create text or background color classes for each of these variables. Instead, we choose a subset of these colors for a [theme palette](https://getbootstrap.com/docs/5.1/customize/color/#theme-colors).

Be sure to monitor contrast ratios as you customize colors. As shown below, we’ve added three contrast ratios to each of the main colors—one for the swatch’s current colors, one for against white, and one for against black.

**$blue**
#0d6efd


$blue-100

$blue-200

$blue-300

$blue-400

$blue-500

$blue-600

$blue-700

$blue-800

$blue-900

**$indigo**
#6610f2


$indigo-100

$indigo-200

$indigo-300

$indigo-400

$indigo-500

$indigo-600

$indigo-700

$indigo-800

$indigo-900

**$purple**
#6f42c1


$purple-100

$purple-200

$purple-300

$purple-400

$purple-500

$purple-600

$purple-700

$purple-800

$purple-900

**$pink**
#d63384


$pink-100

$pink-200

$pink-300

$pink-400

$pink-500

$pink-600

$pink-700

$pink-800

$pink-900

**$red**
#dc3545


$red-100

$red-200

$red-300

$red-400

$red-500

$red-600

$red-700

$red-800

$red-900

**$orange**
#fd7e14


$orange-100

$orange-200

$orange-300

$orange-400

$orange-500

$orange-600

$orange-700

$orange-800

$orange-900

**$yellow**
#ffc107


$yellow-100

$yellow-200

$yellow-300

$yellow-400

$yellow-500

$yellow-600

$yellow-700

$yellow-800

$yellow-900

**$green**
#198754


$green-100

$green-200

$green-300

$green-400

$green-500

$green-600

$green-700

$green-800

$green-900

**$teal**
#20c997


$teal-100

$teal-200

$teal-300

$teal-400

$teal-500

$teal-600

$teal-700

$teal-800

$teal-900

**$cyan**
#0dcaf0


$cyan-100

$cyan-200

$cyan-300

$cyan-400

$cyan-500

$cyan-600

$cyan-700

$cyan-800

$cyan-900

**$gray-500**
#adb5bd


$gray-100

$gray-200

$gray-300

$gray-400

$gray-500

$gray-600

$gray-700

$gray-800

$gray-900

**$black**
#000


**$white**
#fff


### Notes on Sass [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#notes-on-sass)

Sass cannot programmatically generate variables, so we manually created variables for every tint and shade ourselves. We specify the midpoint value (e.g., `$blue-500`) and use custom color functions to tint (lighten) or shade (darken) our colors via Sass’s `mix()` color function.

Using `mix()` is not the same as `lighten()` and `darken()`—the former blends the specified color with white or black, while the latter only adjusts the lightness value of each color. The result is a much more complete suite of colors, as [shown in this CodePen demo](https://codepen.io/emdeoh/pen/zYOQOPB).

Our `tint-color()` and `shade-color()` functions use `mix()` alongside our `$theme-color-interval` variable, which specifies a stepped percentage value for each mixed color we produce. See the `scss/_functions.scss` and `scss/_variables.scss` files for the full source code.

## Color Sass maps [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#color-sass-maps)

Bootstrap’s source Sass files include three maps to help you quickly and easily loop over a list of colors and their hex values.

- `$colors` lists all our available base ( `500`) colors
- `$theme-colors` lists all semantically named theme colors (shown below)
- `$grays` lists all tints and shades of gray

Within `scss/_variables.scss`, you’ll find Bootstrap’s color variables and Sass map. Here’s an example of the `$colors` Sass map:

Copy

```scss
$colors: (
  "blue":       $blue,
  "indigo":     $indigo,
  "purple":     $purple,
  "pink":       $pink,
  "red":        $red,
  "orange":     $orange,
  "yellow":     $yellow,
  "green":      $green,
  "teal":       $teal,
  "cyan":       $cyan,
  "white":      $white,
  "gray":       $gray-600,
  "gray-dark":  $gray-800
);

```

Add, remove, or modify values within the map to update how they’re used in many other components. Unfortunately at this time, not _every_ component utilizes this Sass map. Future updates will strive to improve upon this. Until then, plan on making use of the `${color}` variables and this Sass map.

### Example [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#example)

Here’s how you can use these in your Sass:

Copy

```scss
.alpha { color: $purple; }
.beta {
  color: $yellow-300;
  background-color: $indigo-900;
}

```

[Color](https://getbootstrap.com/docs/5.1/utilities/colors/) and [background](https://getbootstrap.com/docs/5.1/utilities/background/) utility classes are also available for setting `color` and `background-color` using the `500` color values.

## Generating utilities [Anchor](https://getbootstrap.com/docs/5.1/customize/color/\#generating-utilities)

Added in v5.1.0

Bootstrap doesn’t include `color` and `background-color` utilities for every color variable, but you can generate these yourself with our [utility API](https://getbootstrap.com/docs/5.1/utilities/api/) and our extended Sass maps added in v5.1.0.

1. To start, make sure you’ve imported our functions, variables, mixins, and utilities.
2. Use our `map-merge-multiple()` function to quickly merge multiple Sass maps together in a new map.
3. Merge this new combined map to extend any utility with a `{color}-{level}` class name.

Here’s an example that generates text color utilities (e.g., `.text-purple-500`) using the above steps.

Copy

```scss
@import "bootstrap/scss/functions";
@import "bootstrap/scss/variables";
@import "bootstrap/scss/mixins";
@import "bootstrap/scss/utilities";

$all-colors: map-merge-multiple($blues, $indigos, $purples, $pinks, $reds, $oranges, $yellows, $greens, $teals, $cyans);

$utilities: map-merge(
  $utilities,
  (
    "color": map-merge(
      map-get($utilities, "color"),
      (
        values: map-merge(
          map-get(map-get($utilities, "color"), "values"),
          (
            $all-colors
          ),
        ),
      ),
    ),
  )
);

@import "bootstrap/scss/utilities/api";

```

This will generate new `.text-{color}-{level}` utilities for every color and level. You can do the same for any other utility and property as well.