---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions
scraped_at: 2025-10-20T03:00:59.370Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# Firefox (-moz-) vendor-prefixed CSS extensions

A [vendor prefix](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix) is used to indicate that a feature is specific to a certain browser.
Firefox supports several extensions to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), which are prefixed with `-moz-`.

## [-moz-prefixed properties without standard equivalents](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#-moz-prefixed_properties_without_standard_equivalents)

**Note:**
These extensions are mostly experimental or deprecated but kept for backward compatibility.
You should avoid using them on production websites.

- [`-moz-float-edge`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-float-edge)Deprecated
- [`-moz-force-broken-image-icon`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-force-broken-image-icon)Deprecated: Use `alt` text instead.
- [`-moz-orient`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-orient)
- `-moz-osx-font-smoothing`: A similar [`font-smooth`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-smooth) equivalent exists.
- [`-moz-user-focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-user-focus)Deprecated
- [`-moz-user-input`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-user-input)Deprecated
- `-moz-user-modify`: A non-prefixed [`user-modify`](https://developer.mozilla.org/en-US/docs/Web/CSS/user-modify) equivalent exists, but the HTML [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/contenteditable) attribute is recommended instead.

## [-moz-prefixed properties with standard equivalents](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#-moz-prefixed_properties_with_standard_equivalents)

The following properties were implemented first using the `-moz-` vendor prefix, but are now supported in Firefox using the standard (non-prefixed) syntax.
Support for the prefixed version is typically dropped eventually, so use the standard property instead.

### [A](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#a)

- [`-moz-animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)Deprecated: Prefixed version still supported.
- [`-moz-animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)Deprecated: Prefixed version still supported.
- [`-moz-animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction)Deprecated: Prefixed version still supported.
- [`-moz-animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration)Deprecated: Prefixed version still supported.
- [`-moz-animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode)Deprecated: Prefixed version still supported.
- [`-moz-animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)Deprecated: Prefixed version still supported.
- [`-moz-animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name)Deprecated: Prefixed version still supported.
- [`-moz-animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state)Deprecated: Prefixed version still supported.
- [`-moz-animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)Deprecated: Prefixed version still supported.
- `-moz-appearance`: The prefixed version of [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) is still supported.

### [B](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#b)

- [`-moz-backface-visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility)Deprecated: Prefixed version still supported.
- `-moz-background-clip`Deprecated: Not supported; use [`background-clip`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip).
- `-moz-background-origin`Deprecated: Not supported; use [`background-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin).
- `-moz-box-align`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items).
- `-moz-background-inline-policy`Deprecated: Not supported; use [`box-decoration-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break).
- `-moz-box-direction`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction).
- `-moz-box-flex`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow).
- `-moz-box-ordinal-group`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order).
- `-moz-box-orient`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction).
- `-moz-box-pack`Deprecated: Use [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout) with [`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content).
- `-moz-background-size`Deprecated: Not supported; use [`background-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size).
- `-moz-border-end`Deprecated: Not supported; use [`border-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end).
- `-moz-border-end-color`Deprecated: Not supported; use [`border-inline-end-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-color).
- `-moz-border-end-style`Deprecated: Not supported; use [`border-inline-end-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-style).
- `-moz-border-end-width`Deprecated: Not supported; use [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width).
- `-moz-border-image`Deprecated: Not supported; use [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width).
- `-moz-border-start`Deprecated: Not supported; use [`border-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start).
- `-moz-border-start-color`Deprecated: Not supported; use [`border-inline-start-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-color).
- `-moz-border-start-style`Deprecated: Not supported; use [`border-inline-start-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-style).
- `-moz-border-start-width`Deprecated: Not supported; use [`border-inline-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width).
- [`-moz-box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)Deprecated: Prefixed version still supported.

### [C](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#c)

- `-moz-column-count`Deprecated: Not supported; use [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count).
- `-moz-column-fill`Deprecated: Not supported; use [`column-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-fill).
- `-moz-column-gap`Deprecated: Not supported; use [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap).
- `-moz-column-width`Deprecated: Not supported; use [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width).
- `-moz-column-rule`Deprecated: Not supported; use [`column-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule).
- `-moz-column-rule-width`Deprecated: Not supported; use [`column-rule-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width).
- `-moz-column-rule-style`Deprecated: Not supported; use [`column-rule-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style).
- `-moz-column-rule-color`Deprecated: Not supported; use [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color).

### [F–M](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#f%E2%80%93m)

- [`-moz-font-feature-settings`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings)Deprecated: Prefixed version still supported.
- [`-moz-font-language-override`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-language-override)Deprecated: Prefixed version still supported.
- [`-moz-hyphens`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)Deprecated: Prefixed version still supported.
- `-moz-margin-end`Deprecated: Not supported; use [`margin-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end).
- `-moz-margin-start`Deprecated: Not supported; use [`margin-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-start).

### [O-P](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#o-p)

- `-moz-opacity`Deprecated: Not supported; use [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity).
- `-moz-outline`Deprecated: Not supported; use [`outline`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline).
- `-moz-outline-color`Deprecated: Not supported; use [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color).
- `-moz-outline-offset`Deprecated: Not supported; use [`outline-offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset).
- `-moz-outline-style`Deprecated: Not supported; use [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style).
- `-moz-outline-width`Deprecated: Not supported; use [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width).
- `-moz-padding-end`Deprecated: Not supported; use [`padding-inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end).
- `-moz-padding-start`Deprecated: Not supported; use [`padding-inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start).
- [`-moz-perspective`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective)Deprecated: Prefixed version still supported.
- [`-moz-perspective-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin)Deprecated: Prefixed version still supported.

### [T–Z](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#t%E2%80%93z)

- `-moz-tab-size`: Use [`tab-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size)
- `-moz-text-align-last`Deprecated: Not supported; use [`text-align-last`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last).
- `-moz-text-decoration-color`Deprecated: Not supported; use [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color).
- `-moz-text-decoration-line`Deprecated: Not supported; use [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line).
- `-moz-text-decoration-style`Deprecated: Not supported; use [`text-decoration-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style).
- `-moz-text-size-adjust`: See [`text-size-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust)Experimental.
- [`-moz-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)Deprecated: Prefixed version still supported.
- [`-moz-transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)Deprecated: Prefixed version still supported.
- [`-moz-transform-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style)Deprecated: Prefixed version still supported.
- `-moz-transition`Deprecated: Not supported; use [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition).
- `-moz-transition-delay`Deprecated: Not supported; use [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay).
- `-moz-transition-duration`Deprecated: Not supported; use [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration).
- `-moz-transition-property`Deprecated: Not supported; use [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property).
- `-moz-transition-timing-function`Deprecated: Not supported; use [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function).
- `-moz-user-select`: Use [`user-select`](https://developer.mozilla.org/en-US/docs/Web/CSS/user-select).

## [-moz-prefixed property values](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#-moz-prefixed_property_values)

### [Global values](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#global_values)

- `-moz-initial`: See [`initial`](https://developer.mozilla.org/en-US/docs/Web/CSS/initial).

### [background-image](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#background-image)

**Property:** [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)

- `-moz-linear-gradient`Deprecated: Use [`linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient).
- `-moz-radial-gradient`Deprecated: Use [`radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient).
- `-moz-element`Deprecated: Use [`element()`](https://developer.mozilla.org/en-US/docs/Web/CSS/element).
- [`-moz-image-rect()`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-rect)Deprecated

### [order-style and outline-style](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#order-style_and_outline-style)

**Properties:** [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) and [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style).

- `-moz-bg-inset`Deprecated
- `-moz-bg-outset`Deprecated
- `-moz-bg-solid`Deprecated

### [<color> keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#color_keywords)

**Type:** [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)

- `-moz-activehyperlinktext`
- `-moz-hyperlinktext`
- `-moz-visitedhyperlinktext`
- `-moz-buttonhoverface`
- `-moz-buttonhovertext`
- `-moz-default-background-color`
- `-moz-default-color`
- `-moz-cellhighlight`
- `-moz-cellhighlighttext`
- `-moz-field`
- `-moz-fieldtext`
- `-moz-dialog`
- `-moz-dialogtext`
- `-moz-menuhover`
- `-moz-menuhovertext`

### [empty-cells](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#empty-cells)

**Property:** [`empty-cells`](https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells)

- `-moz-show-background` (default value in quirks mode)

### [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#font-family)

**Property:** [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)

- `-moz-fixed`

### [image-rendering](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#image-rendering)

**Property:** [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering)

- `-moz-crisp-edges`Deprecated: Use [`crisp-edges`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering#crisp-edges).

### [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#length)

**Type:** [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

- `-moz-calc`Deprecated: Use [`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc).

### [list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#list-style-type)

**Property:** [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)

Several vendor-prefixed values for `list-style-type` are now supported as standard values without a `-moz-` prefix, except for those in the following list.
See [Browser Compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type#browser_compatibility) for details.

- `-moz-ethiopic-halehame`
- `-moz-ethiopic-halehame-am`
- `-moz-ethiopic-halehame-ti-er`
- `-moz-ethiopic-halehame-ti-et`
- `-moz-hangul`
- `-moz-hangul-consonant`
- `-moz-urdu`

### [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#text-align)

**Property:** [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

- `-moz-center`Deprecated: Use [`text-align: center`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).
- `-moz-left`Deprecated: Use [`text-align: left`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).
- `-moz-right`Deprecated: Use [`text-align: right`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).

### [width, min-width, and max-width](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#width_min-width_and_max-width)

**Properties:** [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), and [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)

- `-moz-min-content`: See [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-content).
- `-moz-fit-content`: See [`fit-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content).
- `-moz-max-content`: See [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content).
- `-moz-available`: See [`stretch`](https://developer.mozilla.org/en-US/docs/Web/CSS/width#stretch).

## [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#pseudo-classes)

- `:-moz-any`Deprecated: Use [`:is`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is).
- `:-moz-any-link`Deprecated: Use [`:any-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link).
- [`:-moz-broken`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-broken)Deprecated
- [`:-moz-drag-over`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-drag-over)
- [`:-moz-first-node`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-first-node)
- `:-moz-full-screen`Deprecated: Not supported; use [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen).
- `:-moz-full-screen-ancestor`Deprecated: Not supported; use [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen).
- [`:-moz-handler-blocked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-handler-blocked)
- [`:-moz-handler-crashed`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-handler-crashed)
- [`:-moz-handler-disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-handler-disabled)
- [`:-moz-last-node`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-last-node)
- [`:-moz-loading`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-loading)
- [`:-moz-locale-dir(ltr)`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-locale-dir_ltr)
- [`:-moz-locale-dir(rtl)`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-locale-dir_rtl)
- `:-moz-native-anonymous`
- `:-moz-placeholder`Deprecated: Use [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown).
- [`:-moz-only-whitespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-only-whitespace)
- `:-moz-read-only`Deprecated: Use [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only).
- `:-moz-read-write`Deprecated: Use [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write).
- [`:-moz-submit-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-submit-invalid): See [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).
- [`:-moz-suppressed`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-suppressed)
- `:-moz-ui-invalid`Deprecated: Use [`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid).
- `:-moz-ui-valid`Deprecated: Use [`:user-valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid).
- [`:-moz-user-disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-user-disabled)
- [`:-moz-window-inactive`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-window-inactive)

## [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#pseudo-elements)

- `::-moz-canvas`
- `::-moz-cell-content`
- [`::-moz-color-swatch`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-color-swatch)
- [`::-moz-focus-inner`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-focus-inner)
- `::-moz-focus-outer`
- `::-moz-inline-table`
- [`::-moz-list-bullet`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-list-bullet)
- [`::-moz-list-number`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-list-number)
- [`::-moz-meter-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-meter-bar)
- `::-moz-pagebreak`
- `::-moz-pagecontent`
- `::-moz-placeholder`Deprecated: Use [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder).
- [`::-moz-progress-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-progress-bar)
- [`::-moz-range-progress`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-range-progress)
- [`::-moz-range-thumb`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-range-thumb)
- [`::-moz-range-track`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-range-track)
- `::-moz-scrolled-canvas`
- `::-moz-scrolled-content`
- `::-moz-selection`Deprecated: Use [`::selection`](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection).
- `::-moz-svg-foreign-content`
- `::-moz-table`
- `::-moz-table-cell`
- `::-moz-table-column`
- `::-moz-table-column-group`
- `::-moz-table-outer`
- `::-moz-table-row`
- `::-moz-table-row-group`
- `::-moz-viewport`
- `::-moz-viewport-scroll`

## [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#at-rules)

- [`@-moz-document`](https://developer.mozilla.org/en-US/docs/Web/CSS/@document)

## [Media features](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#media_features)

- [`-moz-device-pixel-ratio`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/-moz-device-pixel-ratio)Deprecated
- `-moz-platform`
- `-moz-windows-glass`

## [Other](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#other)

- `-moz-alt-content`: See [Firefox bug 11011](https://bugzil.la/11011)

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions\#see_also)

- [WebKit (-webkit-) vendor-prefixed CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions)
- [Vendor Prefix](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix) glossary entry

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/mozilla_extensions/index.md?plain=1 "Folder: ⁨en-us/web/css/mozilla_extensions⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FMozilla_Extensions&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fmozilla_extensions%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2FMozilla_Extensions%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fmozilla_extensions%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")