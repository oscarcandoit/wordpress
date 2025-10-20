---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
scraped_at: 2025-10-20T02:59:46.380Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# CSS reference

Use this **CSS reference** to browse an [alphabetical index](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#index) of all of the standard [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties, [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes), [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements), [data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_data_types), [functional notations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) and [at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule). You can also browse [key CSS concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#concepts) and a list of [selectors organized by type](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#selectors). Also included is a brief [DOM-CSS / CSSOM reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#dom-css_cssom).

## [Basic rule syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#basic_rule_syntax)

### [Style rule syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#style_rule_syntax)

```
style-rule ::=
    selectors-list {
      properties-list
    }

```

Where:

```
selectors-list ::=
    selector[:pseudo-class] [::pseudo-element]
    [, selectors-list]

properties-list ::=
    [property : value] [; properties-list]

```

See the index of [_selectors_](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#selectors), [_pseudo-classes_](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#pseudo), and _[pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#pseudo)_ below. The syntax for each specified _value_ depends on the data type defined for each specified _property_.

#### Style rule examples

cssCopy

```
strong {
  color: red;
}

div.menu-bar li:hover > ul {
  display: block;
}

```

For a beginner-level introduction to the syntax of selectors, see our [guide on CSS Selectors](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Basic_selectors). Be aware that any [syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax) error in a rule definition invalidates the entire rule. Invalid rules are ignored by the browser. Note that CSS rule definitions are entirely (Unicode) [text-based](https://drafts.csswg.org/css-syntax/#intro), whereas DOM-CSS / CSSOM (the rule management system) is [object-based](https://drafts.csswg.org/cssom/#introduction).

### [At-rule syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#at-rule_syntax)

As the structure of at-rules varies widely, please see [At-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule) to find the syntax of the specific one you want.

## [Index](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#index)

**Note:**
This index does not include SVG-exclusive presentation attributes, which can be used as CSS properties on [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) elements.

**Note:**
The property names in this index do **not** include the JavaScript names which do differ from the CSS standard names.

### -

- [`--*`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
- [`-webkit-line-clamp`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp)
- [`-webkit-text-fill-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-fill-color)
- [`-webkit-text-stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke)
- [`-webkit-text-stroke-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-color)
- [`-webkit-text-stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-width)

### A

- [`abs()`](https://developer.mozilla.org/en-US/docs/Web/CSS/abs)
- [`accent-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/accent-color)
- [`acos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/acos)
- [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)
- [`:active-view-transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active-view-transition)
- `:active-view-transition-type()`
- [`additive-symbols (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/additive-symbols)
- [`::after (:after)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
- [`align-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
- [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [`align-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self)
- [`alignment-baseline`](https://developer.mozilla.org/en-US/docs/Web/CSS/alignment-baseline)
- [`all`](https://developer.mozilla.org/en-US/docs/Web/CSS/all)
- [`anchor()`](https://developer.mozilla.org/en-US/docs/Web/CSS/anchor)
- [`anchor-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/anchor-name)
- `anchor-scope`
- [`anchor-size()`](https://developer.mozilla.org/en-US/docs/Web/CSS/anchor-size)
- [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle)
- [`<angle-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle-percentage)
- [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
- [`animation-composition`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition)
- [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)
- [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction)
- [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration)
- [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode)
- [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)
- [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name)
- [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state)
- [`animation-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-range)
- [`animation-range-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-range-end)
- [`animation-range-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-range-start)
- [`animation-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline)
- [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
- [`@annotation`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#annotation)
- [`:any-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)
- [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance)
- [`ascent-override (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/ascent-override)
- [`asin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/asin)
- [`aspect-ratio`](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)
- [`atan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan)
- [`atan2()`](https://developer.mozilla.org/en-US/docs/Web/CSS/atan2)
- [`attr()`](https://developer.mozilla.org/en-US/docs/Web/CSS/attr)
- [`:autofill`](https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill)

### B

- [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- [`backdrop-filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter)
- [`backface-visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility)
- [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
- [`background-attachment`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment)
- [`background-blend-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-blend-mode)
- [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip)
- [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
- [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
- [`background-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin)
- [`background-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position)
- [`background-position-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x)
- [`background-position-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-y)
- [`background-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
- [`background-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)
- [`base-palette (@font-palette-values)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/base-palette)
- `baseline-shift`
- [`<basic-shape>`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape)
- [`::before (:before)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
- [`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank)
- `bleed (@page)`
- [`<blend-mode>`](https://developer.mozilla.org/en-US/docs/Web/CSS/blend-mode)
- [`block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/block-size)
- [`blur()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/blur)
- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
- [`border-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block)
- [`border-block-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-color)
- [`border-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end)
- [`border-block-end-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-color)
- [`border-block-end-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-style)
- [`border-block-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-width)
- [`border-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start)
- [`border-block-start-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-color)
- [`border-block-start-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-style)
- [`border-block-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-width)
- [`border-block-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-style)
- [`border-block-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-width)
- [`border-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom)
- [`border-bottom-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color)
- [`border-bottom-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius)
- [`border-bottom-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius)
- [`border-bottom-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style)
- [`border-bottom-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width)
- [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse)
- [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color)
- [`border-end-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-end-radius)
- [`border-end-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-start-radius)
- [`border-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image)
- [`border-image-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset)
- [`border-image-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat)
- [`border-image-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice)
- [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source)
- [`border-image-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width)
- [`border-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline)
- [`border-inline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color)
- [`border-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end)
- [`border-inline-end-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-color)
- [`border-inline-end-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-style)
- [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width)
- [`border-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start)
- [`border-inline-start-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-color)
- [`border-inline-start-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-style)
- [`border-inline-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width)
- [`border-inline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-style)
- [`border-inline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-width)
- [`border-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left)
- [`border-left-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color)
- [`border-left-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-style)
- [`border-left-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width)
- [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [`border-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right)
- [`border-right-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-color)
- [`border-right-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-style)
- [`border-right-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width)
- [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing)
- [`border-start-end-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius)
- [`border-start-start-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-start-radius)
- [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style)
- [`border-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top)
- [`border-top-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color)
- [`border-top-left-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius)
- [`border-top-right-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius)
- [`border-top-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-style)
- [`border-top-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width)
- [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width)
- [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom)
- [`@bottom-left-corner`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page#page-margin-box-type)
- [`box-decoration-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)
- [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)
- [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
- [`break-after`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-after)
- [`break-before`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-before)
- [`break-inside`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside)
- [`brightness()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/brightness)
- [`:buffering`](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering)

### C

- [`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)
- [`calc-size()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-size)
- `cap`
- [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side)
- [`caret`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret)
- [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
- [`caret-shape`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-shape)
- `ch`
- [`@character-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#character-variant)
- [`@charset`](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset)
- [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)
- [`::checkmark`](https://developer.mozilla.org/en-US/docs/Web/CSS/::checkmark)
- [`circle()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape#circle)
- [`clamp()`](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)
- [`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear)
- [`clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
- [`clip-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-rule)
- `cm`
- [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)
- [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
- [`color-interpolation-filters`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation-filters)
- `color-mix()`
- [`color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme)
- [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count)
- [`column-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-fill)
- [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
- [`column-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule)
- [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color)
- [`column-rule-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style)
- [`column-rule-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width)
- [`column-span`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-span)
- [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width)
- [`columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/columns)
- [`conic-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/conic-gradient)
- [`contain`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain)
- [`contain-intrinsic-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-block-size)
- [`contain-intrinsic-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-height)
- [`contain-intrinsic-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-inline-size)
- [`contain-intrinsic-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-size)
- [`contain-intrinsic-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/contain-intrinsic-width)
- [`@container`](https://developer.mozilla.org/en-US/docs/Web/CSS/@container)
- [`container`](https://developer.mozilla.org/en-US/docs/Web/CSS/container)
- [`container-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/container-name)
- [`container-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/container-type)
- [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
- [`content-visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/content-visibility)
- [`contrast()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/contrast)
- [`cos()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cos)
- [`<counter>`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter)
- [`counter-increment`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-increment)
- [`counter-reset`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset)
- [`counter-set`](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-set)
- [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style)
- [`counters()`](https://developer.mozilla.org/en-US/docs/Web/CSS/counters)
- [`cross-fade()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cross-fade)
- [`cubic-bezier()`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function#cubic_b%C3%A9zier_easing_function)
- [`::cue`](https://developer.mozilla.org/en-US/docs/Web/CSS/::cue)
- `::cue()`
- [`::cue-region`](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- `::cue-region()`
- [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current)
- [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)
- [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident)
- [`cx`](https://developer.mozilla.org/en-US/docs/Web/CSS/cx)
- [`cy`](https://developer.mozilla.org/en-US/docs/Web/CSS/cy)

### D

- [`d`](https://developer.mozilla.org/en-US/docs/Web/CSS/d)
- [`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident)
- [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default)
- [`:defined`](https://developer.mozilla.org/en-US/docs/Web/CSS/:defined)
- `deg`
- [`descent-override (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/descent-override)
- [`::details-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/::details-content)
- [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension)
- [`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)
- [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction)
- [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)
- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [`<display-box>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-box)
- [`<display-inside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside)
- [`<display-internal>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal)
- [`<display-legacy>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-legacy)
- [`<display-listitem>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem)
- [`<display-outside>`](https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside)
- [`dominant-baseline`](https://developer.mozilla.org/en-US/docs/Web/CSS/dominant-baseline)
- `dpcm`
- `dpi`
- `dppx`
- [`drop-shadow()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow)

### E

- [`<easing-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)
- [`element()`](https://developer.mozilla.org/en-US/docs/Web/CSS/element)
- [`ellipse()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape#ellipse)
- `em`
- [`:empty`](https://developer.mozilla.org/en-US/docs/Web/CSS/:empty)
- [`empty-cells`](https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells)
- [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)
- [`env()`](https://developer.mozilla.org/en-US/docs/Web/CSS/env)
- `ex`
- [`exp()`](https://developer.mozilla.org/en-US/docs/Web/CSS/exp)

### F

- [`fallback (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback)
- [`field-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/field-sizing)
- [`::file-selector-button`](https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button)
- [`fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill)
- [`fill-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill-opacity)
- [`fill-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/fill-rule)
- [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
- [`<filter-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function)
- [`:first`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first)
- [`:first-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)
- [`::first-letter (:first-letter)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
- [`::first-line (:first-line)`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line)
- [`:first-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type)
- [`fit-content()`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content)
- [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value)
- [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
- [`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)
- [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)
- [`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow)
- [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)
- [`flex-shrink`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)
- [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)
- [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
- [`flood-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/flood-color)
- [`flood-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/flood-opacity)
- [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
- [`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)
- [`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)
- [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font)
- [`font-display (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display)
- [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
- [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
- [`font-family (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family)
- [`font-family (@font-palette-values)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/font-family)
- [`font-feature-settings`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings)
- [`font-feature-settings (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-feature-settings)
- [`@font-feature-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values)
- [`font-kerning`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning)
- [`font-language-override`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-language-override)
- [`font-optical-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-optical-sizing)
- [`font-palette`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-palette)
- [`@font-palette-values`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values)
- [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
- [`font-size-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size-adjust)
- [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
- [`font-style (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-style)
- [`font-synthesis`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis)
- [`font-synthesis-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-position)
- [`font-synthesis-small-caps`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-small-caps)
- [`font-synthesis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-style)
- [`font-synthesis-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-weight)
- [`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)
- [`font-variant-alternates`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-alternates)
- [`font-variant-caps`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps)
- [`font-variant-east-asian`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian)
- [`font-variant-emoji`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-emoji)
- [`font-variant-ligatures`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures)
- [`font-variant-numeric`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric)
- [`font-variant-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-position)
- [`font-variation-settings`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variation-settings)
- [`font-variation-settings (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variation-settings)
- [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
- [`font-weight (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-weight)
- `font-width`
- [`forced-color-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/forced-color-adjust)
- [`format()`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src#format)
- `fr`
- [`<frequency>`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency)
- [`<frequency-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/frequency-percentage)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen)
- [`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)

### G

- [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- `grad`
- [`<gradient>`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)
- [`::grammar-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error)
- [`grayscale()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/grayscale)
- [`grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid)
- [`grid-area`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area)
- [`grid-auto-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns)
- [`grid-auto-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow)
- [`grid-auto-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows)
- [`grid-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column)
- [`grid-column-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-end)
- [`grid-column-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-start)
- [`grid-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row)
- [`grid-row-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end)
- [`grid-row-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start)
- [`grid-template`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template)
- [`grid-template-areas`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
- [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)

### H

- `Hz`
- [`hanging-punctuation`](https://developer.mozilla.org/en-US/docs/Web/CSS/hanging-punctuation)
- `:has()`
- [`:has-slotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has-slotted)
- [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)
- `::highlight()`
- [`@historical-forms`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#historical-forms)
- [`:host`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host)
- [`:host()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function)
- `:host-context()`
- [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
- [`hsl()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl)
- [`hue-rotate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/hue-rotate)
- [`hwb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb)
- [`hyphenate-character`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphenate-character)
- [`hyphenate-limit-chars`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphenate-limit-chars)
- [`hyphens`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)
- [`hypot()`](https://developer.mozilla.org/en-US/docs/Web/CSS/hypot)

### I

- `ic`
- [`<ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ident)
- [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image)
- [`image()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image#the_image_functional_notation)
- [`image-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation)
- [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering)
- [`image-resolution`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-resolution)
- [`image-set()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/image-set)
- [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)
- `in`
- [`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range)
- [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)
- [`inherit`](https://developer.mozilla.org/en-US/docs/Web/CSS/inherit)
- [`inherits (@property)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/inherits)
- [`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial)
- [`initial-letter`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter)
- `initial-letter-align`
- [`initial-value (@property)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value)
- [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size)
- [`inset`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset)
- [`inset()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape#inset)
- [`inset-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block)
- [`inset-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-end)
- [`inset-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-start)
- [`inset-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline)
- [`inset-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline-end)
- [`inset-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline-start)
- [`<integer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)
- [`interpolate-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/interpolate-size)
- [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
- [`invert()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/invert)
- `:is()`
- [`isolation`](https://developer.mozilla.org/en-US/docs/Web/CSS/isolation)

### J

- [`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
- [`justify-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items)
- [`justify-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-self)

### K

- `kHz`
- [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)

### L

- [`lab()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lab)
- [`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)
- [`:last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)
- [`:last-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type)
- [`@layer`](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer)
- `layer()`
- `layer() (@import)`
- [`lch()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lch)
- `leader()`
- [`:left`](https://developer.mozilla.org/en-US/docs/Web/CSS/:left)
- [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left)
- [`@left-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page#page-margin-box-type)
- [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)
- [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage)
- [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
- [`light-dark()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/light-dark)
- [`lighting-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/lighting-color)
- [`line-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-break)
- [`line-clamp`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp)
- [`line-gap-override (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/line-gap-override)
- [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
- [`line-height-step`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height-step)
- [`<line-style>`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-style)
- [`linear()`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function#linear_easing_function)
- [`linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)
- [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)
- [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
- [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)
- [`list-style-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position)
- [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
- [`local()`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src#local)
- [`:local-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link)
- [`log()`](https://developer.mozilla.org/en-US/docs/Web/CSS/log)

### M

- [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
- [`margin-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block)
- [`margin-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-end)
- [`margin-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-start)
- [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom)
- [`margin-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline)
- [`margin-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end)
- [`margin-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-start)
- [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)
- [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
- [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top)
- [`margin-trim`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-trim)
- [`::marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)
- [`marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/marker)
- [`marker-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/marker-end)
- [`marker-mid`](https://developer.mozilla.org/en-US/docs/Web/CSS/marker-mid)
- [`marker-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/marker-start)
- `marks (@page)`
- [`mask`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
- [`mask-border`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border)
- [`mask-border-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-mode)
- [`mask-border-outset`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-outset)
- [`mask-border-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-repeat)
- [`mask-border-slice`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-slice)
- [`mask-border-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-source)
- [`mask-border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-width)
- [`mask-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip)
- [`mask-composite`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite)
- [`mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image)
- [`mask-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode)
- [`mask-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin)
- [`mask-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position)
- [`mask-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat)
- [`mask-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size)
- [`mask-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-type)
- [`math-depth`](https://developer.mozilla.org/en-US/docs/Web/CSS/math-depth)
- [`math-shift`](https://developer.mozilla.org/en-US/docs/Web/CSS/math-shift)
- [`math-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/math-style)
- [`matrix()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix)
- [`matrix3d()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix3d)
- [`max()`](https://developer.mozilla.org/en-US/docs/Web/CSS/max)
- [`max-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-block-size)
- [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
- [`max-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size)
- `max-lines`
- [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)
- [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
- [`min()`](https://developer.mozilla.org/en-US/docs/Web/CSS/min)
- [`min-block-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-block-size)
- [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height)
- [`min-inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size)
- [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width)
- [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax)
- [`mix-blend-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode)
- `mm`
- [`mod()`](https://developer.mozilla.org/en-US/docs/Web/CSS/mod)
- [`:modal`](https://developer.mozilla.org/en-US/docs/Web/CSS/:modal)
- `ms`
- [`:muted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted)

### N

- [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace)
- `navigation (@view-transition)`
- [`negative (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative)
- [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
- [`:nth-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
- [`:nth-last-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child)
- [`:nth-last-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type)
- [`:nth-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)
- [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number)

### O

- [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
- [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
- [`object-view-box`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-view-box)
- [`offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset)
- [`offset-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor)
- [`offset-distance`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance)
- [`offset-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path)
- [`offset-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position)
- [`offset-rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate)
- [`oklab()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklab)
- [`oklch()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch)
- [`:only-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)
- [`:only-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type)
- [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity)
- [`opacity()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/opacity)
- [`:open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:open)
- [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)
- [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order)
- [`@ornaments`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#ornaments)
- [`orphans`](https://developer.mozilla.org/en-US/docs/Web/CSS/orphans)
- [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)
- [`outline`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)
- [`outline-offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset)
- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style)
- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width)
- [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
- [`overflow-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor)
- [`overflow-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-block)
- [`overflow-clip-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin)
- [`overflow-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline)
- [`overflow-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
- [`overflow-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
- [`overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
- [`overlay`](https://developer.mozilla.org/en-US/docs/Web/CSS/overlay)
- [`override-colors (@font-palette-values)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/override-colors)
- [`overscroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior)
- [`overscroll-behavior-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block)
- [`overscroll-behavior-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-inline)
- [`overscroll-behavior-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x)
- [`overscroll-behavior-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y)

### P

- [`Pseudo-classes`](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [`Pseudo-elements`](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
- [`pad (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/pad)
- [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
- [`padding-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block)
- [`padding-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end)
- [`padding-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-start)
- [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom)
- [`padding-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline)
- [`padding-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end)
- [`padding-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start)
- [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left)
- [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right)
- [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top)
- [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page)
- [`page`](https://developer.mozilla.org/en-US/docs/Web/CSS/page)
- [`page-orientation (@page)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page/page-orientation)
- [`paint()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/paint)
- [`paint-order`](https://developer.mozilla.org/en-US/docs/Web/CSS/paint-order)
- `palette-mix()`
- `::part()`
- [`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)
- [`path()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/path)
- [`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)
- `pc`
- [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)
- [`perspective`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective)
- [`perspective()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/perspective)
- [`perspective-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin)
- `::picker()`
- [`::picker-icon`](https://developer.mozilla.org/en-US/docs/Web/CSS/::picker-icon)
- [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)
- [`place-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)
- [`place-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-items)
- [`place-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/place-self)
- [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
- [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)
- [`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)
- [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
- [`polygon()`](https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape#polygon)
- [`:popover-open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:popover-open)
- [`<position>`](https://developer.mozilla.org/en-US/docs/Web/CSS/position_value)
- [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [`position-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-anchor)
- [`position-area`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-area)
- [`@position-try`](https://developer.mozilla.org/en-US/docs/Web/CSS/@position-try)
- [`position-try`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-try)
- [`position-try-fallbacks`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-try-fallbacks)
- [`position-try-order`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-try-order)
- [`position-visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/position-visibility)
- [`pow()`](https://developer.mozilla.org/en-US/docs/Web/CSS/pow)
- [`prefix (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/prefix)
- [`print-color-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/print-color-adjust)
- [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property)
- `pt`
- `px`

### Q

- `Q`
- [`quotes`](https://developer.mozilla.org/en-US/docs/Web/CSS/quotes)

### R

- [`r`](https://developer.mozilla.org/en-US/docs/Web/CSS/r)
- `rad`
- [`radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient)
- [`range (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range)
- [`<ratio>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ratio)
- [`ray()`](https://developer.mozilla.org/en-US/docs/Web/CSS/ray)
- [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only)
- [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write)
- [`rect()`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape#rect)
- [`rem()`](https://developer.mozilla.org/en-US/docs/Web/CSS/rem)
- [`repeat()`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat)
- [`repeating-conic-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-conic-gradient)
- [`repeating-linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-linear-gradient)
- [`repeating-radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-radial-gradient)
- [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)
- [`resize`](https://developer.mozilla.org/en-US/docs/Web/CSS/resize)
- [`<resolution>`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution)
- `reversed()`
- [`revert`](https://developer.mozilla.org/en-US/docs/Web/CSS/revert)
- [`rgb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb)
- [`:right`](https://developer.mozilla.org/en-US/docs/Web/CSS/:right)
- [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right)
- [`@right-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page#page-margin-box-type)
- [`:root`](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)
- [`rotate`](https://developer.mozilla.org/en-US/docs/Web/CSS/rotate)
- [`rotate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)
- [`rotate3d()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d)
- [`rotateX()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateX)
- [`rotateY()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateY)
- [`rotateZ()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateZ)
- [`round()`](https://developer.mozilla.org/en-US/docs/Web/CSS/round)
- [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)
- [`ruby-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-align)
- `ruby-merge`
- [`ruby-overhang`](https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-overhang)
- [`ruby-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-position)
- [`rx`](https://developer.mozilla.org/en-US/docs/Web/CSS/rx)
- [`ry`](https://developer.mozilla.org/en-US/docs/Web/CSS/ry)

### S

- `s`
- [`saturate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/saturate)
- [`scale`](https://developer.mozilla.org/en-US/docs/Web/CSS/scale)
- [`scale()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale)
- [`scale3d()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale3d)
- [`scaleX()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleX)
- [`scaleY()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleY)
- [`scaleZ()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleZ)
- [`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope)
- [`@scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/@scope)
- [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
- [`scroll-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior)
- `scroll-initial-target`
- [`scroll-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin)
- [`scroll-margin-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block)
- [`scroll-margin-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-end)
- [`scroll-margin-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-start)
- [`scroll-margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-bottom)
- [`scroll-margin-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline)
- [`scroll-margin-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-end)
- [`scroll-margin-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-start)
- [`scroll-margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-left)
- [`scroll-margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-right)
- [`scroll-margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-top)
- [`::scroll-marker`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker)
- [`::scroll-marker-group`](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker-group)
- [`scroll-padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding)
- [`scroll-padding-block`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block)
- [`scroll-padding-block-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block-end)
- [`scroll-padding-block-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block-start)
- [`scroll-padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-bottom)
- [`scroll-padding-inline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline)
- [`scroll-padding-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline-end)
- [`scroll-padding-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline-start)
- [`scroll-padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-left)
- [`scroll-padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-right)
- [`scroll-padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-top)
- [`scroll-snap-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align)
- [`scroll-snap-stop`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop)
- [`scroll-snap-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type)
- `scroll-state()`
- [`scroll-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline)
- [`scroll-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-axis)
- [`scroll-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name)
- [`scrollbar-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color)
- [`scrollbar-gutter`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter)
- [`scrollbar-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-width)
- [`:seeking`](https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking)
- [`::selection`](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)
- `selector()`
- [`sepia()`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/sepia)
- [`shape-image-threshold`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-image-threshold)
- [`shape-margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-margin)
- [`shape-outside`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside)
- [`shape-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-rendering)
- [`sign()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sign)
- [`sin()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sin)
- [`size (@page)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size)
- [`size-adjust (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/size-adjust)
- [`skew()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew)
- [`skewX()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewX)
- [`skewY()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewY)
- `::slotted()`
- [`speak-as`](https://developer.mozilla.org/en-US/docs/Web/CSS/speak-as)
- [`speak-as (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as)
- [`::spelling-error`](https://developer.mozilla.org/en-US/docs/Web/CSS/::spelling-error)
- [`sqrt()`](https://developer.mozilla.org/en-US/docs/Web/CSS/sqrt)
- [`src (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src)
- [`:stalled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled)
- [`@starting-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style)
- `:state()`
- [`steps()`](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function#steps_easing_function)
- [`stop-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/stop-color)
- [`stop-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/stop-opacity)
- [`<string>`](https://developer.mozilla.org/en-US/docs/Web/CSS/string)
- [`stroke`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke)
- `stroke-color`
- [`stroke-dasharray`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dasharray)
- [`stroke-dashoffset`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-dashoffset)
- [`stroke-linecap`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linecap)
- [`stroke-linejoin`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-linejoin)
- [`stroke-miterlimit`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-miterlimit)
- [`stroke-opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-opacity)
- [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/stroke-width)
- `style()`
- [`@styleset`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#styleset)
- [`@stylistic`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#stylistic)
- [`suffix (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/suffix)
- [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)
- `supports() (@import)`
- [`@swash`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values#swash)
- [`symbols (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols)
- [`symbols()`](https://developer.mozilla.org/en-US/docs/Web/CSS/symbols)
- [`syntax (@property)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax)
- [`system (@counter-style)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/system)

### T

- [`tab-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size)
- [`table-layout`](https://developer.mozilla.org/en-US/docs/Web/CSS/table-layout)
- [`tan()`](https://developer.mozilla.org/en-US/docs/Web/CSS/tan)
- [`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
- `target-counter()`
- `target-counters()`
- [`:target-current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-current)
- [`::target-text`](https://developer.mozilla.org/en-US/docs/Web/CSS/::target-text)
- `target-text()`
- [`:target-within`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
- [`text-align-last`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last)
- [`text-anchor`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-anchor)
- [`text-box`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box)
- [`text-box-edge`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-edge)
- [`text-box-trim`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
- [`text-combine-upright`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-combine-upright)
- [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)
- [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color)
- [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line)
- [`text-decoration-skip`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip)
- [`text-decoration-skip-ink`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink)
- [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style)
- [`text-decoration-thickness`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness)
- [`<text-edge>`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-edge)
- [`text-emphasis`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis)
- [`text-emphasis-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color)
- [`text-emphasis-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position)
- [`text-emphasis-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style)
- [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)
- [`text-justify`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-justify)
- [`text-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation)
- [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)
- [`text-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering)
- [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)
- [`text-size-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust)
- [`text-spacing-trim`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-spacing-trim)
- [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
- [`text-underline-offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset)
- [`text-underline-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-position)
- [`text-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-wrap)
- [`text-wrap-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-wrap-mode)
- [`text-wrap-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-wrap-style)
- [`<time>`](https://developer.mozilla.org/en-US/docs/Web/CSS/time)
- [`<time-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/time-percentage)
- [`timeline-scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/timeline-scope)
- [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top)
- [`@top-left-corner`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page#page-margin-box-type)
- [`touch-action`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action)
- [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [`transform-box`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-box)
- [`<transform-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function)
- [`transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
- [`transform-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style)
- [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
- [`transition-behavior`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-behavior)
- [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay)
- [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration)
- [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property)
- [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
- [`translate`](https://developer.mozilla.org/en-US/docs/Web/CSS/translate)
- [`translate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate)
- [`translate3d()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d)
- [`translateX()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateX)
- [`translateY()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateY)
- [`translateZ()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateZ)
- `turn`
- [`type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/type)
- `types (@view-transition)`

### U

- [`unicode-bidi`](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
- [`unicode-range (@font-face)`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range)
- [`unset`](https://developer.mozilla.org/en-US/docs/Web/CSS/unset)
- [`<url>`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value)
- [`url()`](https://developer.mozilla.org/en-US/docs/Web/CSS/url_value#the_url_functional_notation)
- [`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid)
- [`user-select`](https://developer.mozilla.org/en-US/docs/Web/CSS/user-select)
- [`:user-valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid)

### V

- [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
- [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var)
- [`vector-effect`](https://developer.mozilla.org/en-US/docs/Web/CSS/vector-effect)
- [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
- `vh`
- [`view()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/view)
- [`view-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline)
- [`view-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-axis)
- [`view-timeline-inset`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-inset)
- [`view-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name)
- [`::view-transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/::view-transition)
- [`@view-transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/@view-transition)
- [`view-transition-class`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-transition-class)
- `::view-transition-group()`
- `::view-transition-image-pair()`
- [`view-transition-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-transition-name)
- `::view-transition-new()`
- `::view-transition-old()`
- [`visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility)
- [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)
- `vmax`
- `vmin`
- [`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked)
- `vw`

### W

- `:where()`
- [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- [`white-space-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space-collapse)
- [`widows`](https://developer.mozilla.org/en-US/docs/Web/CSS/widows)
- [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)
- [`will-change`](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change)
- [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
- [`word-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing)
- [`word-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
- [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)

### X

- [`x`](https://developer.mozilla.org/en-US/docs/Web/CSS/x)
- `:xr-overlay`
- `xywh()`

### Y

- [`y`](https://developer.mozilla.org/en-US/docs/Web/CSS/y)

### Z

- [`z-index`](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)
- [`zoom`](https://developer.mozilla.org/en-US/docs/Web/CSS/zoom)

## [Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#selectors)

The following are the various [selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors), which allow styles to be conditional based on various features of elements within the DOM.

### [Basic selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#basic_selectors)

**Basic selectors** are fundamental selectors; these are the most basic selectors that are frequently combined to create other, more complex selectors.

- [Universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors) `*`
- [Type selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors) `elementname`
- [Class selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) `.classname`
- [ID selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors) `#idname`
- [Attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) `[attr=value]`

### [Grouping selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#grouping_selectors)

[Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list) `A, B`

Specifies that both `A` and `B` elements are selected. This is a grouping method to select several matching elements.

### [Combinators](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#combinators)

Combinators are selectors that establish a relationship between two or more simple selectors, such as " `A` is a child of `B`" or " `A` is adjacent to `B`", creating a complex selector.

[Next-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Next-sibling_combinator) `A + B`

Specifies that the elements selected by both `A` and `B` have the same parent and that the element selected by `B` immediately follows the element selected by `A` horizontally.

[Subsequent-sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Subsequent-sibling_combinator) `A ~ B`

Specifies that the elements selected by both `A` and `B` share the same parent and that the element selected by `A` comes before—but not necessarily immediately before—the element selected by `B`.

[Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator) `A > B`

Specifies that the element selected by `B` is the direct child of the element selected by `A`.

[Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator) `A B`

Specifies that the element selected by `B` is a descendant of the element selected by `A`, but is not necessarily a direct child.

[Column combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Column_combinator) `A || B`Experimental

Specifies that the element selected by `B` is located within the table column specified by `A`. Elements which span multiple columns are considered to be a member of all of those columns.

### [Pseudo](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#pseudo)

[Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) `:`

Specifies a special state of the selected element(s).

[Pseudo elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) `::`

Represents entities that are not included in HTML.

See also [selectors in the Selectors specification](https://drafts.csswg.org/selectors/) and the [pseudo-element specification](https://drafts.csswg.org/css-pseudo/).

## [Concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#concepts)

### [Syntax and semantics](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#syntax_and_semantics)

- [CSS syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Syntax)
- [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule)
- [Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Cascade)
- [Comments](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Comments)
- [Descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
- [Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance)
- [Shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties)
- [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
- [Value definition syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax)
- [CSS values and units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units)
- [CSS functional notations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions)

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#values)

- [Actual value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#actual_value)
- [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value)
- [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value)
- [Resolved value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#resolved_value)
- [Specified value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#specified_value)
- [Used value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#used_value)

### [Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#layout)

- [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context)
- [Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)
- [Containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Containing_block)
- [Layout mode](https://developer.mozilla.org/en-US/docs/Glossary/Layout_mode)
- [Margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)
- [Replaced elements](https://developer.mozilla.org/en-US/docs/Glossary/Replaced_elements)
- [Stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context)
- [Visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model)

## [DOM-CSS / CSSOM](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#dom-css_cssom)

### [Major object types](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#major_object_types)

- [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets)
- [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
- [`Element.className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
- [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
- [`StyleSheetList`](https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList)
- [`CSSRuleList`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)
- [`CSSRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule)
- [`CSSStyleRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule)
- [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)

### [Important methods](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#important_methods)

- [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
- [`CSSStyleSheet.deleteRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule)

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#see_also)

- [Mozilla CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions) (prefixed with `-moz-`)
- [WebKit CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions) (mostly prefixed with `-webkit-`)

## [External Links](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference\#external_links)

- [CSS Indices (w3.org)](https://www.w3.org/TR/css/#indices)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/index.md?plain=1 "Folder: ⁨en-us/web/css/reference⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FReference&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Freference%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FReference%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Freference%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")