---
url: https://getbootstrap.com/docs/5.3/migration
scraped_at: 2025-10-20T02:35:51.042Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/migration/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/migration/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/migration.mdx "View and edit this file on GitHub")

# Migrating to v5

Track and review changes to the Bootstrap source files, documentation, and components to help you migrate from v4 to v5.

On this page
**On this page**

* * *

## v5.3.6 [Link to this section: v5.3.6](https://getbootstrap.com/docs/5.3/migration/\#v536)

### Dependencies [Link to this section: Dependencies](https://getbootstrap.com/docs/5.3/migration/\#dependencies)

- Migrated from Hugo to Astro for building our documentation

## v5.3.0 [Link to this section: v5.3.0](https://getbootstrap.com/docs/5.3/migration/\#v530)

If you’re migrating from our previous alpha releases of v5.3.0, please review their changes in addition to this section.

### Helpers [Link to this section: Helpers](https://getbootstrap.com/docs/5.3/migration/\#helpers)

- [Colored links](https://getbootstrap.com/docs/5.3/helpers/colored-links) once again have `!important` so they work better with our newly added link utilities.

### Utilities [Link to this section: Utilities](https://getbootstrap.com/docs/5.3/migration/\#utilities)

- Added new `.d-inline-grid` [display utility](https://getbootstrap.com/docs/5.3/utilities/display).

## v5.3.0-alpha2 [Link to this section: v5.3.0-alpha2](https://getbootstrap.com/docs/5.3/migration/\#v530-alpha2)

If you’re migrating from our previous alpha release of v5.3.0, please review the changes listed below.

### CSS variables [Link to this section: CSS variables](https://getbootstrap.com/docs/5.3/migration/\#css-variables)

- Removed several duplicate and unused root CSS variables.

### Color modes [Link to this section: Color modes](https://getbootstrap.com/docs/5.3/migration/\#color-modes)

- Dark mode colors are now derived from our theme colors (e.g., `$primary`) in Sass, rather than color specific tints or shades (e.g., `$blue-300`). This allows for a more automated dark mode when customizing the default theme colors.

- Added Sass maps for generating theme colors for dark mode text, subtle background, and subtle border.

- [Snippet examples](https://getbootstrap.com/docs/5.3/examples/#snippets) are now ready for dark mode with updated markup and reduced custom styles.

- Added `color-scheme: dark` to dark mode CSS to change OS level controls like scrollbars

- Form validation `border-color` and text `color` states now respond to dark mode, thanks to new Sass and CSS variables.

- Dropped recently added form control background CSS variables and reassigned the Sass variables to use CSS variables instead. This simplifies the styling across color modes and avoids an issue where form controls in dark mode wouldn’t update properly.

- Our `box-shadow` s will once again always stay dark instead of inverting to white when in dark mode.

- Improved HTML and JavaScript for our color mode toggle script. The selector for changing the active SVG has been improved, and the markup made more accessible with ARIA attributes.

- Improved docs code syntax colors and more across light and dark modes.


### Typography [Link to this section: Typography](https://getbootstrap.com/docs/5.3/migration/\#typography)

- We no longer set a color for `$headings-color-dark` or `--bs-heading-color` for dark mode. To avoid several problems of headings within components appearing the wrong color, we’ve set the Sass variable to `null` and added a `null` check like we use on the default light mode.

### Components [Link to this section: Components](https://getbootstrap.com/docs/5.3/migration/\#components)

- Cards now have a `color` set on them to improve rendering across color modes.

- Added new `.nav-underline` variant for our navigation with a simpler bottom border under the active nav link. [See the docs for an example.](https://getbootstrap.com/docs/5.3/components/navs-tabs#underline)

- Navs now have new `:focus-visible` styles that better match our custom button focus styles.


### Helpers [Link to this section: Helpers](https://getbootstrap.com/docs/5.3/migration/\#helpers-1)

- Added new `.icon-link` helper to quickly place and align Bootstrap Icons alongside a textual link. Icon links support our new link utilities, too.

- Added new focus ring helper for removing the default `outline` and setting a custom `box-shadow` focus ring.


### Utilities [Link to this section: Utilities](https://getbootstrap.com/docs/5.3/migration/\#utilities-1)

- Renamed Sass and CSS variables `${color}-text` to `${color}-text-emphasis` to match their associated utilities.

- Added new `.link-body-emphasis` helper alongside our [colored links](https://getbootstrap.com/docs/5.3/helpers/colored-links). This creates a colored link using our color mode responsive emphasis color.

- Added new link utilities for link color opacity, underline offset, underline color, and underline opacity. [Explore the new links utilities.](https://getbootstrap.com/docs/5.3/utilities/link)

- CSS variable based `border-width` utilities have been reverted to set their property directly (as was done prior to v5.2.0). This avoids inheritance issues across nested elements, including tables.

- Added new `.border-black` utility to match our `.text-black` and `.bg-black` utilities.

- Deprecated The `.text-muted` utility and `$text-muted` Sass variable have been deprecated and replaced with `.text-body-secondary` and `$body-secondary-color`.


### Docs [Link to this section: Docs](https://getbootstrap.com/docs/5.3/migration/\#docs)

- Examples are now displayed with the appropriate light or dark color mode as dictated by the setting in our docs. Each example has an individual color mode picker.

- Improved included JavaScript for live Toast demo.

- Added `twbs/examples` repo contents to the top of the Examples page.


### Tooling [Link to this section: Tooling](https://getbootstrap.com/docs/5.3/migration/\#tooling)

- Added SCSS testing via True to help test our utilities API and other customizations.

- Replaced instances of our bootstrap-npm-starter project with the newer and more complete [twbs/examples repo](https://github.com/twbs/examples).


* * *

For a complete list of changes, [see the v5.3.0-alpha2 project on GitHub](https://github.com/orgs/twbs/projects/13).

## v5.3.0-alpha1 [Link to this section: v5.3.0-alpha1](https://getbootstrap.com/docs/5.3/migration/\#v530-alpha1)

* * *

### Color modes! [Link to this section: Color modes!](https://getbootstrap.com/docs/5.3/migration/\#color-modes-1)

Learn more by reading the new [color modes documentation](https://getbootstrap.com/docs/5.3/customize/color-modes).

- **Global support for light (default) and dark color modes.** Set color mode globally on the `:root` element, on groups of elements and components with a wrapper class, or directly on components, with `data-bs-theme="light|dark"`. Also included is a new `color-mode()` mixin that can output a ruleset with the `data-bs-theme` selector or a media query, depending on your preference.

Deprecated Color modes replace dark variants for components, so `.btn-close-white`, `.carousel-dark`, `.dropdown-menu-dark`, and `.navbar-dark` are deprecated.

- **New extended color system.** We’ve added new theme colors (but not in `$theme-colors`) for a more nuanced, system-wide color palette with new secondary, tertiary, and emphasis colors for `color` and `background-color`. These new colors are available as Sass variables, CSS variables, and utilities.

- We’ve also expanded our theme color Sass variables, CSS variables, and utilities to include text emphasis, subtle background colors, and subtle border colors. These are available as Sass variables, CSS variables, and utilities.

- Adds new `_variables-dark.scss` stylesheet to house dark-mode specific overrides. This stylesheet should be imported immediately after the existing `_variables.scss` file in your import stack.









```diff
diff --git a/scss/bootstrap.scss b/scss/bootstrap.scss
index 8f8296def..449d70487 100644
  --- a/scss/bootstrap.scss
+++ b/scss/bootstrap.scss
@@ -6,6 +6,7 @@
// Configuration
@import "functions";
@import "variables";
+@import "variables-dark";
@import "maps";
@import "mixins";
@import "utilities";

```


### CSS variables [Link to this section: CSS variables](https://getbootstrap.com/docs/5.3/migration/\#css-variables-1)

- Restores CSS variables for breakpoints, though we don’t use them in our media queries as they’re not supported. However, these can be useful in JS-specific contexts.

- Per the color modes update, we’ve added new utilities for new Sass CSS variables `secondary` and `tertiary` text and background colors, plus `{color}-bg-subtle`, `{color}-border-subtle`, and `{color}-text-emphasis` for our theme colors. These new colors are available through Sass and CSS variables (but not our color maps) with the express goal of making it easier to customize across multiple colors modes like light and dark.

- Adds additional variables for alerts, `.btn-close`, and `.offcanvas`.

- The `--bs-heading-color` variable is back with an update and dark mode support. First, we now check for a `null` value on the associated Sass variable, `$headings-color`, before trying to output the CSS variable, so by default it’s not present in our compiled CSS. Second, we use the CSS variable with a fallback value, `inherit`, allowing the original behavior to persist, but also allowing for overrides.

- Converts links to use CSS variables for styling `color`, but not `text-decoration`. Colors are now set with `--bs-link-color-rgb` and `--bs-link-opacity` as `rgba()` color, allowing you to customize the translucency with ease. The `a:hover` pseudo-class now overrides `--bs-link-color-rgb` instead of explicitly setting the `color` property.

- `--bs-border-width` is now being used in more components for greater control over default global styling.

- Adds new root CSS variables for our `box-shadow` s, including `--bs-box-shadow`, `--bs-box-shadow-sm`, `--bs-box-shadow-lg`, and `--bs-box-shadow-inset`.


### Components [Link to this section: Components](https://getbootstrap.com/docs/5.3/migration/\#components-1)

#### Alert [Link to this section: Alert](https://getbootstrap.com/docs/5.3/migration/\#alert)

- Alert variants are now styled via CSS variables.

- Deprecated The `alert-variant()` mixin is now deprecated. We now [use a Sass loop](https://getbootstrap.com/docs/5.3/components/alerts#sass-loops) directly to modify the component’s default CSS variables for each variant.


#### List group [Link to this section: List group](https://getbootstrap.com/docs/5.3/migration/\#list-group)

- List group item variants are now styled via CSS variables.

- Deprecated The `list-group-item-variant()` mixin is now deprecated. We now [use a Sass loop](https://getbootstrap.com/docs/5.3/components/list-group#sass-loops) directly to modify the component’s default CSS variables for each variant.


#### Dropdowns [Link to this section: Dropdowns](https://getbootstrap.com/docs/5.3/migration/\#dropdowns)

- Deprecated The `.dropdown-menu-dark` class has been deprecated and replaced with `data-bs-theme="dark"` on the dropdown or any parent element. [See the docs for an example.](https://getbootstrap.com/docs/5.3/components/dropdowns#dark-dropdowns)

#### Close button [Link to this section: Close button](https://getbootstrap.com/docs/5.3/migration/\#close-button)

- Deprecated The `.btn-close-white` class has been deprecated and replaced with `data-bs-theme="dark"` on the close button or any parent element. [See the docs for an example.](https://getbootstrap.com/docs/5.3/components/close-button#dark-variant)

#### Navbar [Link to this section: Navbar](https://getbootstrap.com/docs/5.3/migration/\#navbar)

- Deprecated The `.navbar-dark` class has been deprecated and replaced with `data-bs-theme="dark"` on the navbar or any parent element. [See the docs for updated examples.](https://getbootstrap.com/docs/5.3/components/navbar#color-schemes)

### Progress bars [Link to this section: Progress bars](https://getbootstrap.com/docs/5.3/migration/\#progress-bars)

The markup for [progress bars](https://getbootstrap.com/docs/5.3/components/progress) has been updated in v5.3.0. Due to the placement of `role` and various `aria-` attributes on the inner `.progress-bar` element, **some screen readers were not announcing zero value progress bars**. Now, `role="progressbar"` and the relevant `aria-*` attributes are on the outer `.progress` element, leaving the `.progress-bar` purely for the visual presentation of the bar and optional label.

While we recommend adopting the new markup for improved compatibility with all screen readers, note that the legacy progress bar structure will continue to work as before.

```html
<!-- Previous markup -->
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-label="Basic example" style="width: 25%" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>

<!-- New markup -->
<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 25%"></div>
</div>

```

We’ve also introduced a new `.progress-stacked` class to more logically wrap [multiple progress bars](https://getbootstrap.com/docs/5.3/components/progress#multiple-bars) into a single stacked progress bar.

```html
<!-- Previous markup -->
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-label="Segment one" style="width: 15%" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100"></div>
  <div class="progress-bar bg-success" role="progressbar" aria-label="Segment two" style="width: 30%" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100"></div>
  <div class="progress-bar bg-info" role="progressbar" aria-label="Segment three" style="width: 20%" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100"></div>
</div>

<!-- New markup -->
<div class="progress-stacked">
  <div class="progress" role="progressbar" aria-label="Segment one" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100" style="width: 15%">
    <div class="progress-bar"></div>
  </div>
  <div class="progress" role="progressbar" aria-label="Segment two" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="width: 30%">
    <div class="progress-bar bg-success"></div>
  </div>
  <div class="progress" role="progressbar" aria-label="Segment three" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">
    <div class="progress-bar bg-info"></div>
  </div>
</div>

```

### Forms [Link to this section: Forms](https://getbootstrap.com/docs/5.3/migration/\#forms)

- `.form-control` is now styled with CSS variables to support color modes. This includes the addition of two new root CSS variables for the default and disabled form control backgrounds.

- `.form-check` and `.form-switch` components are now built with CSS variables for setting the `background-image`. The usage here differs from other components in that the various focus, active, etc states for each component aren’t set on the base class. Instead, the states override one variable (e.g., `--bs-form-switch-bg`).

- Floating form labels now have a `background-color` to fix support for `<textarea>` elements. Additional changes have been made to also support disabled states and more.

- Fixed display of date and time inputs in WebKit based browsers.


### Utilities [Link to this section: Utilities](https://getbootstrap.com/docs/5.3/migration/\#utilities-2)

- Deprecated `.text-muted` will be replaced by `.text-body-secondary` in v6.

With the addition of the expanded theme colors and variables, the `.text-muted` variables and utility have been deprecated with v5.3.0. Its default value has also been reassigned to the new `--bs-secondary-color` CSS variable to better support color modes. It will be removed in v6.0.0.

- Adds new `.overflow-x`, `.overflow-y`, and several `.object-fit-*` utilities. _The object-fit property is used to specify how an `<img>` or `<video>` should be resized to fit its container, giving us a responsive alternative to using `background-image` for a resizable fill/fit image._

- Adds new `.fw-medium` utility.

- Added new [`.z-*` utilities](https://getbootstrap.com/docs/5.3/utilities/z-index) for `z-index`.

- [Box shadow utilities](https://getbootstrap.com/docs/5.3/utilities/shadows) (and Sass variables) have been updated for dark mode. They now use `--bs-body-color-rgb` to generate the `rgba()` color values, allowing them to easily adapt to color modes based on the specified foreground color.


For a complete list of changes, [see the v5.3.0 project on GitHub](https://github.com/twbs/bootstrap/projects/).

## v5.2.0 [Link to this section: v5.2.0](https://getbootstrap.com/docs/5.3/migration/\#v520)

* * *

### Refreshed design [Link to this section: Refreshed design](https://getbootstrap.com/docs/5.3/migration/\#refreshed-design)

Bootstrap v5.2.0 features a subtle design update for a handful of components and properties across the project, **most notably through refined `border-radius` values on buttons and form controls**. Our documentation also has been updated with a new homepage, simpler docs layout that no longer collapses sections of the sidebar, and more prominent examples of [Bootstrap Icons](https://icons.getbootstrap.com/).

### More CSS variables [Link to this section: More CSS variables](https://getbootstrap.com/docs/5.3/migration/\#more-css-variables)

**We’ve updated all our components to use CSS variables.** While Sass still underpins everything, each component has been updated to include CSS variables on the component base classes (e.g., `.btn`), allowing for more real-time customization of Bootstrap. In subsequent releases, we'll continue to expand our use of CSS variables into our layout, forms, helpers, and utilities. Read more about CSS variables in each component on their respective documentation pages.

Our CSS variable usage will be somewhat incomplete until Bootstrap 6. While we’d love to fully implement these across the board, they do run the risk of causing breaking changes. For example, setting `$alert-border-width: var(--bs-border-width)` in our source code breaks potential Sass in your own code if you were doing `$alert-border-width * 2` for some reason.

As such, wherever possible, we will continue to push towards more CSS variables, but please recognize our implementation may be slightly limited in v5.

### New `_maps.scss` [Link to this section: New ](https://getbootstrap.com/docs/5.3/migration/\#new-_mapsscss)

**Bootstrap v5.2.0 introduced a new Sass file with `_maps.scss`.** It pulls out several Sass maps from `_variables.scss` to fix an issue where updates to an original map were not applied to secondary maps that extend them. For example, updates to `$theme-colors` were not being applied to other theme maps that relied on `$theme-colors`, breaking key customization workflows. In short, Sass has a limitation where once a default variable or map has been _used_, it cannot be updated. _There’s a similar shortcoming with CSS variables when they’re used to compose other CSS variables._

This is why variable customizations in Bootstrap have to come after `@import "functions"`, but before `@import "variables"` and the rest of our import stack. The same applies to Sass maps—you must override the defaults before they get used. The following maps have been moved to the new `_maps.scss`:

- `$theme-colors-rgb`
- `$utilities-colors`
- `$utilities-text`
- `$utilities-text-colors`
- `$utilities-bg`
- `$utilities-bg-colors`
- `$negative-spacers`
- `$gutters`

Your custom Bootstrap CSS builds should now look something like this with a separate maps import.

```diff
  // Functions come first
  @import "functions";

  // Optional variable overrides here
+ $custom-color: #df711b;
+ $custom-theme-colors: (
+   "custom": $custom-color
+ );

  // Variables come next
  @import "variables";

+ // Optional Sass map overrides here
+ $theme-colors: map-merge($theme-colors, $custom-theme-colors);
+
+ // Followed by our default maps
+ @import "maps";
+
  // Rest of our imports
  @import "mixins";
  @import "utilities";
  @import "root";
  @import "reboot";
  // etc

```

### New utilities [Link to this section: New utilities](https://getbootstrap.com/docs/5.3/migration/\#new-utilities)

- Expanded [`font-weight` utilities](https://getbootstrap.com/docs/5.3/utilities/text#font-weight-and-italics) to include `.fw-semibold` for semibold fonts.
- Expanded [`border-radius` utilities](https://getbootstrap.com/docs/5.3/utilities/borders#sizes) to include two new sizes, `.rounded-4` and `.rounded-5`, for more options.

### Additional changes [Link to this section: Additional changes](https://getbootstrap.com/docs/5.3/migration/\#additional-changes)

- **Introduced new `$enable-container-classes` option. —** Now when opting into the experimental CSS Grid layout, `.container-*` classes will still be compiled, unless this option is set to `false`. Containers also now keep their gutter values.

- **Offcanvas component now has [responsive variations](https://getbootstrap.com/docs/5.3/components/offcanvas#responsive).** The original `.offcanvas` class remains unchanged—it hides content across all viewports. To make it responsive, change that `.offcanvas` class to any `.offcanvas-{sm|md|lg|xl|xxl}` class.

- **Thicker table dividers are now opt-in. —** We’ve removed the thicker and more difficult to override border between table groups and moved it to an optional class you can apply, `.table-group-divider`. [See the table docs for an example.](https://getbootstrap.com/docs/5.3/content/tables#table-group-dividers)

- **[Scrollspy has been rewritten](https://github.com/twbs/bootstrap/pull/33421) to use the Intersection Observer API**, which means you no longer need relative parent wrappers, deprecates `offset` config, and more. Look for your Scrollspy implementations to be more accurate and consistent in their nav highlighting.

- **Popovers and tooltips now use CSS variables.** Some CSS variables have been updated from their Sass counterparts to reduce the number of variables. As a result, three variables have been deprecated in this release: `$popover-arrow-color`, `$popover-arrow-outer-color`, and `$tooltip-arrow-color`.

- **Added new `.text-bg-{color}` helpers.** Instead of setting individual `.text-*` and `.bg-*` utilities, you can now use [the `.text-bg-*` helpers](https://getbootstrap.com/docs/5.3/helpers/color-background) to set a `background-color` with contrasting foreground `color`.

- Added `.form-check-reverse` modifier to flip the order of labels and associated checkboxes/radios.

- Added [striped columns](https://getbootstrap.com/docs/5.3/content/tables#striped-columns) support to tables via the new `.table-striped-columns` class.


For a complete list of changes, [see the v5.2.0 project on GitHub](https://github.com/twbs/bootstrap/projects/32).

## v5.1.0 [Link to this section: v5.1.0](https://getbootstrap.com/docs/5.3/migration/\#v510)

* * *

- **Added experimental support for [CSS Grid layout](https://getbootstrap.com/docs/5.3/layout/css-grid). —** This is a work in progress, and is not yet ready for production use, but you can opt into the new feature via Sass. To enable it, disable the default grid, by setting `$enable-grid-classes: false` and enable the CSS Grid by setting `$enable-cssgrid: true`.

- **Updated navbars to support offcanvas. —** Add [offcanvas drawers in any navbar](https://getbootstrap.com/docs/5.3/components/navbar#offcanvas) with the responsive `.navbar-expand-*` classes and some offcanvas markup.

- **Added new [placeholder component](https://getbootstrap.com/docs/5.3/components/placeholders/). —** Our newest component, a way to provide temporary blocks in lieu of real content to help indicate that something is still loading in your site or app.

- **Collapse plugin now supports [horizontal collapsing](https://getbootstrap.com/docs/5.3/components/collapse#horizontal). —** Add `.collapse-horizontal` to your `.collapse` to collapse the `width` instead of the `height`. Avoid browser repainting by setting a `min-height` or `height`.

- **Added new stack and vertical rule helpers. —** Quickly apply multiple flexbox properties to quickly create custom layouts with [stacks](https://getbootstrap.com/docs/5.3/helpers/stacks/). Choose from horizontal ( `.hstack`) and vertical ( `.vstack`) stacks. Add vertical dividers similar to `<hr>` elements with the [new `.vr` helpers](https://getbootstrap.com/docs/5.3/helpers/vertical-rule/).

- **Added new global `:root` CSS variables. —** Added several new CSS variables to the `:root` level for controlling `<body>` styles. More are in the works, including across our utilities and components, but for now read up [CSS variables in the Customize section](https://getbootstrap.com/docs/5.3/customize/css-variables/).

- **Overhauled color and background utilities to use CSS variables, and added new [text opacity](https://getbootstrap.com/docs/5.3/utilities/text#opacity) and [background opacity](https://getbootstrap.com/docs/5.3/utilities/background#opacity) utilities. —** `.text-*` and `.bg-*` utilities are now built with CSS variables and `rgba()` color values, allowing you to easily customize any utility with new opacity utilities.

- **Added new snippet examples based to show how to customize our components. —** Pull ready to use customized components and other common design patterns with our new [Snippets examples](https://getbootstrap.com/docs/5.3/examples/#snippets). Includes [footers](https://getbootstrap.com/docs/5.3/examples/footers/), [dropdowns](https://getbootstrap.com/docs/5.3/examples/dropdowns/), [list groups](https://getbootstrap.com/docs/5.3/examples/list-groups/), and [modals](https://getbootstrap.com/docs/5.3/examples/modals/).

- **Removed unused positioning styles from popovers and tooltips** as these are handled solely by Popper. `$tooltip-margin` has been deprecated and set to `null` in the process.


Want more information? [Read the v5.1.0 blog post.](https://blog.getbootstrap.com/2021/08/04/bootstrap-5-1-0/)

## v5.0.0 [Link to this section: v5.0.0](https://getbootstrap.com/docs/5.3/migration/\#v500)

* * *

**Hey there!** Changes to our first major release of Bootstrap 5, v5.0.0, are documented below. They don’t reflect the additional changes shown above.

### Dependencies [Link to this section: Dependencies](https://getbootstrap.com/docs/5.3/migration/\#dependencies-1)

- Dropped jQuery.
- Upgraded from Popper v1.x to Popper v2.x.
- Replaced Libsass with Dart Sass as our Sass compiler given Libsass was deprecated.
- Migrated from Jekyll to Hugo for building our documentation

### Browser support [Link to this section: Browser support](https://getbootstrap.com/docs/5.3/migration/\#browser-support)

- Dropped Internet Explorer 10 and 11
- Dropped Microsoft Edge < 16 (Legacy Edge)
- Dropped Firefox < 60
- Dropped Safari < 12
- Dropped iOS Safari < 12
- Dropped Chrome < 60

* * *

### Documentation changes [Link to this section: Documentation changes](https://getbootstrap.com/docs/5.3/migration/\#documentation-changes)

- Redesigned homepage, docs layout, and footer.
- Added [new Parcel guide](https://getbootstrap.com/docs/5.3/getting-started/parcel).
- Added [new Customize section](https://getbootstrap.com/docs/5.3/customize/overview/), replacing [v4’s Theming page](https://getbootstrap.com/docs/4.6/getting-started/theming/), with new details on Sass, global configuration options, color schemes, CSS variables, and more.
- Reorganized all form documentation into [new Forms section](https://getbootstrap.com/docs/5.3/forms/overview/), breaking apart the content into more focused pages.
- Similarly, updated [the Layout section](https://getbootstrap.com/docs/5.3/layout/breakpoints), to flesh out grid content more clearly.
- Renamed “Navs” component page to "Navs & Tabs".
- Renamed “Checks” page to "Checks & radios".
- Redesigned the navbar and added a new subnav to make it easier to get around our sites and docs versions.
- Added new keyboard shortcut for the search field: `Ctrl + /`.

### Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.3/migration/\#sass)

- We’ve ditched the default Sass map merges to make it easier to remove redundant values. Keep in mind you now have to define all values in the Sass maps like `$theme-colors`. Check out how to deal with [Sass maps](https://getbootstrap.com/docs/5.3/customize/sass#maps-and-loops).

- Breaking Renamed `color-yiq()` function and related variables to `color-contrast()` as it’s no longer related to YIQ color space. [See #30168.](https://github.com/twbs/bootstrap/pull/30168/)
  - `$yiq-contrasted-threshold` is renamed to `$min-contrast-ratio`.
  - `$yiq-text-dark` and `$yiq-text-light` are respectively renamed to `$color-contrast-dark` and `$color-contrast-light`.
- Breaking Media query mixins parameters have changed for a more logical approach.
  - `media-breakpoint-down()` uses the breakpoint itself instead of the next breakpoint (e.g., `media-breakpoint-down(lg)` instead of `media-breakpoint-down(md)` targets viewports smaller than `lg`).
  - Similarly, the second parameter in `media-breakpoint-between()` also uses the breakpoint itself instead of the next breakpoint (e.g., `media-breakpoint-between(sm, lg)` instead of `media-breakpoint-between(sm, md)` targets viewports between `sm` and `lg`).
- Breaking Removed print styles and `$enable-print-styles` variable. Print display classes are still around. [See #28339](https://github.com/twbs/bootstrap/pull/28339).

- Breaking Dropped `color()`, `theme-color()`, and `gray()` functions in favor of variables. [See #29083](https://github.com/twbs/bootstrap/pull/29083).

- Breaking Renamed `theme-color-level()` function to `color-level()` and now accepts any color you want instead of only `$theme-color` colors. [See #29083](https://github.com/twbs/bootstrap/pull/29083) **Watch out:** `color-level()` was later on dropped in `v5.0.0-alpha3`.

- Breaking Renamed `$enable-prefers-reduced-motion-media-query` and `$enable-pointer-cursor-for-buttons` to `$enable-reduced-motion` and `$enable-button-pointers` for brevity.

- Breaking Removed the `bg-gradient-variant()` mixin. Use the `.bg-gradient` class to add gradients to elements instead of the generated `.bg-gradient-*` classes.

- Breaking **Removed previously deprecated mixins:**
  - `hover`, `hover-focus`, `plain-hover-focus`, and `hover-focus-active`
  - `float()`
  - `form-control-mixin()`
  - `nav-divider()`
  - `retina-img()`
  - `text-hide()` (also dropped the associated utility class, `.text-hide`)
  - `visibility()`
  - `form-control-focus()`
- Breaking Renamed `scale-color()` function to `shift-color()` to avoid collision with Sass’s own color scaling function.

- `box-shadow` mixins now allow `null` values and drop `none` from multiple arguments. [See #30394](https://github.com/twbs/bootstrap/pull/30394).

- The `border-radius()` mixin now has a default value.


### Color system [Link to this section: Color system](https://getbootstrap.com/docs/5.3/migration/\#color-system)

- The color system which worked with `color-level()` and `$theme-color-interval` was removed in favor of a new color system. All `lighten()` and `darken()` functions in our codebase are replaced by `tint-color()` and `shade-color()`. These functions will mix the color with either white or black instead of changing its lightness by a fixed amount. The `shift-color()` will either tint or shade a color depending on whether its weight parameter is positive or negative. [See #30622](https://github.com/twbs/bootstrap/pull/30622) for more details.

- Added new tints and shades for every color, providing nine separate colors for each base color, as new Sass variables.

- Improved color contrast. Bumped color contrast ratio from 3:1 to 4.5:1 and updated blue, green, cyan, and pink colors to ensure WCAG 2.2 AA contrast. Also changed our color contrast color from `$gray-900` to `$black`.

- To support our color system, we’ve added new custom `tint-color()` and `shade-color()` functions to mix our colors appropriately.


### Grid updates [Link to this section: Grid updates](https://getbootstrap.com/docs/5.3/migration/\#grid-updates)

- **New breakpoint!** Added new `xxl` breakpoint for `1400px` and up. No changes to all other breakpoints.

- **Improved gutters.** Gutters are now set in rems, and are narrower than v4 ( `1.5rem`, or about `24px`, down from `30px`). This aligns our grid system’s gutters with our spacing utilities.
  - Added new [gutter class](https://getbootstrap.com/docs/5.3/layout/gutters) ( `.g-*`, `.gx-*`, and `.gy-*`) to control horizontal/vertical gutters, horizontal gutters, and vertical gutters.
  - Breaking Renamed `.no-gutters` to `.g-0` to match new gutter utilities.
- Columns no longer have `position: relative` applied, so you may have to add `.position-relative` to some elements to restore that behavior.

- Breaking Dropped several `.order-*` classes that often went unused. We now only provide `.order-0` to `.order-5` out of the box.

- Breaking Dropped the `.media` component as it can be easily replicated with utilities. [See #28265](https://github.com/twbs/bootstrap/pull/28265) and the [flex utilities page for an example](https://getbootstrap.com/docs/5.3/utilities/flex#media-object).

- Breaking `bootstrap-grid.css` now only applies `box-sizing: border-box` to the column instead of resetting the global box-sizing. This way, our grid styles can be used in more places without interference.

- `$enable-grid-classes` no longer disables the generation of container classes anymore. [See #29146.](https://github.com/twbs/bootstrap/pull/29146)

- Updated the `make-col` mixin to default to equal columns without a specified size.


### Content, Reboot, etc [Link to this section: Content, Reboot, etc](https://getbootstrap.com/docs/5.3/migration/\#content-reboot-etc)

- **[RFS](https://getbootstrap.com/docs/5.3/getting-started/rfs) is now enabled by default.** Headings using the `font-size()` mixin will automatically adjust their `font-size` to scale with the viewport. _This feature was previously opt-in with v4._

- Breaking Overhauled our display typography to replace our `$display-*` variables and with a `$display-font-sizes` Sass map. Also removed the individual `$display-*-weight` variables for a single `$display-font-weight` and adjusted `font-size` s.

- Added two new `.display-*` heading sizes, `.display-5` and `.display-6`.

- **Links are underlined by default** (not just on hover), unless they’re part of specific components.

- **Redesigned tables** to refresh their styles and rebuild them with CSS variables for more control over styling.

- Breaking Nested tables do not inherit styles anymore.

- Breaking `.thead-light` and `.thead-dark` are dropped in favor of the `.table-*` variant classes which can be used for all table elements ( `thead`, `tbody`, `tfoot`, `tr`, `th` and `td`).

- Breaking The `table-row-variant()` mixin is renamed to `table-variant()` and accepts only 2 parameters: `$color` (color name) and `$value` (color code). The border color and accent colors are automatically calculated based on the table factor variables.

- Split table cell padding variables into `-y` and `-x`.

- Breaking Dropped `.pre-scrollable` class. [See #29135](https://github.com/twbs/bootstrap/pull/29135)

- Breaking `.text-*` utilities do not add hover and focus states to links anymore. `.link-*` helper classes can be used instead. [See #29267](https://github.com/twbs/bootstrap/pull/29267)

- Breaking Dropped `.text-justify` class. [See #29793](https://github.com/twbs/bootstrap/pull/29793)

- Breaking ~~`<hr>` elements now use `height` instead of `border` to better support the `size` attribute. This also enables use of padding utilities to create thicker dividers (e.g., `<hr class="py-1">`).~~

- Reset default horizontal `padding-left` on `<ul>` and `<ol>` elements from browser default `40px` to `2rem`.

- Added `$enable-smooth-scroll`, which applies `scroll-behavior: smooth` globally—except for users asking for reduced motion through `prefers-reduced-motion` media query. [See #31877](https://github.com/twbs/bootstrap/pull/31877)


### RTL [Link to this section: RTL](https://getbootstrap.com/docs/5.3/migration/\#rtl)

- Horizontal direction specific variables, utilities, and mixins have all been renamed to use logical properties like those found in flexbox layouts—e.g., `start` and `end` in lieu of `left` and `right`.

### Forms [Link to this section: Forms](https://getbootstrap.com/docs/5.3/migration/\#forms-1)

- **Added new floating forms!** We’ve promoted the Floating labels example to fully supported form components. [See the new Floating labels page.](https://getbootstrap.com/docs/5.3/forms/floating-labels)

- Breaking **Consolidated native and custom form elements.** Checkboxes, radios, selects, and other inputs that had native and custom classes in v4 have been consolidated. Now nearly all our form elements are entirely custom, most without the need for custom HTML.
  - `.custom-control.custom-checkbox` is now `.form-check`.
  - `.custom-control.custom-radio` is now `.form-check`.
  - `.custom-control.custom-switch` is now `.form-check.form-switch`.
  - `.custom-select` is now `.form-select`.
  - `.custom-file` and `.form-control-file` have been replaced by custom styles on top of `.form-control`.
  - `.custom-range` is now `.form-range`.
  - Dropped native `.form-control-file` and `.form-control-range`.
- Breaking Dropped `.input-group-append` and `.input-group-prepend`. You can now just add buttons and `.input-group-text` as direct children of the input groups.

- The longstanding [Missing border radius on input group with validation feedback bug](https://github.com/twbs/bootstrap/issues/25110) is finally fixed by adding an additional `.has-validation` class to input groups with validation.

- Breaking **Dropped form-specific layout classes for our grid system.** Use our grid and utilities instead of `.form-group`, `.form-row`, or `.form-inline`.

- Breaking Form labels now require `.form-label`.

- Breaking `.form-text` no longer sets `display`, allowing you to create inline or block help text as you wish just by changing the HTML element.

- Form controls no longer used fixed `height` when possible, instead deferring to `min-height` to improve customization and compatibility with other components.

- Validation icons are no longer applied to `<select>` s with `multiple`.

- Rearranged source Sass files under `scss/forms/`, including input group styles.


* * *

### Components [Link to this section: Components](https://getbootstrap.com/docs/5.3/migration/\#components-2)

- Unified `padding` values for alerts, breadcrumbs, cards, dropdowns, list groups, modals, popovers, and tooltips to be based on our `$spacer` variable. [See #30564](https://github.com/twbs/bootstrap/pull/30564).

#### Accordion [Link to this section: Accordion](https://getbootstrap.com/docs/5.3/migration/\#accordion)

- Added [new accordion component](https://getbootstrap.com/docs/5.3/components/accordion).

#### Alerts [Link to this section: Alerts](https://getbootstrap.com/docs/5.3/migration/\#alerts)

- Alerts now have [examples with icons](https://getbootstrap.com/docs/5.3/components/alerts#icons).

- Removed custom styles for `<hr>` s in each alert since they already use `currentColor`.


#### Badges [Link to this section: Badges](https://getbootstrap.com/docs/5.3/migration/\#badges)

- Breaking Dropped all `.badge-*` color classes for background utilities (e.g., use `.bg-primary` instead of `.badge-primary`).

- Breaking Dropped `.badge-pill`—use the `.rounded-pill` utility instead.

- Breaking Removed hover and focus styles for `<a>` and `<button>` elements.

- Increased default padding for badges from `.25em`/ `.5em` to `.35em`/ `.65em`.


- Simplified the default appearance of breadcrumbs by removing `padding`, `background-color`, and `border-radius`.

- Added new CSS custom property `--bs-breadcrumb-divider` for easy customization without needing to recompile CSS.


#### Buttons [Link to this section: Buttons](https://getbootstrap.com/docs/5.3/migration/\#buttons)

- Breaking **[Toggle buttons](https://getbootstrap.com/docs/5.3/forms/checks-radios#toggle-buttons), with checkboxes or radios, no longer require JavaScript and have new markup.** We no longer require a wrapping element, add `.btn-check` to the `<input>`, and pair it with any `.btn` classes on the `<label>`. [See #30650](https://github.com/twbs/bootstrap/pull/30650). _The docs for this has moved from our Buttons page to the new Forms section._

- Breaking **Dropped `.btn-block` for utilities.** Instead of using `.btn-block` on the `.btn`, wrap your buttons with `.d-grid` and a `.gap-*` utility to space them as needed. Switch to responsive classes for even more control over them. [Read the docs for some examples.](https://getbootstrap.com/docs/5.3/components/buttons#block-buttons)

- Updated our `button-variant()` and `button-outline-variant()` mixins to support additional parameters.

- Updated buttons to ensure increased contrast on hover and active states.

- Disabled buttons now have `pointer-events: none;`.


#### Card [Link to this section: Card](https://getbootstrap.com/docs/5.3/migration/\#card)

- Breaking Dropped `.card-deck` in favor of our grid. Wrap your cards in column classes and add a parent `.row-cols-*` container to recreate card decks (but with more control over responsive alignment).

- Breaking Dropped `.card-columns` in favor of Masonry. [See #28922](https://github.com/twbs/bootstrap/pull/28922).

- Breaking Replaced the `.card` based accordion with a [new Accordion component](https://getbootstrap.com/docs/5.3/components/accordion).


#### Carousel [Link to this section: Carousel](https://getbootstrap.com/docs/5.3/migration/\#carousel)

- Added new [`.carousel-dark` variant](https://getbootstrap.com/docs/5.3/components/carousel#dark-variant) for dark text, controls, and indicators (great for lighter backgrounds).

- Replaced chevron icons for carousel controls with new SVGs from [Bootstrap Icons](https://icons.getbootstrap.com/).


#### Close button [Link to this section: Close button](https://getbootstrap.com/docs/5.3/migration/\#close-button-1)

- Breaking Renamed `.close` to `.btn-close` for a less generic name.

- Close buttons now use a `background-image` (embedded SVG) instead of a `&times;` in the HTML, allowing for easier customization without the need to touch your markup.

- Added new `.btn-close-white` variant that uses `filter: invert(1)` to enable higher contrast dismiss icons against darker backgrounds.


#### Collapse [Link to this section: Collapse](https://getbootstrap.com/docs/5.3/migration/\#collapse)

- Removed scroll anchoring for accordions.

#### Dropdowns [Link to this section: Dropdowns](https://getbootstrap.com/docs/5.3/migration/\#dropdowns-1)

- Added new `.dropdown-menu-dark` variant and associated variables for on-demand dark dropdowns.

- Added new variable for `$dropdown-padding-x`.

- Darkened the dropdown divider for improved contrast.

- Breaking All the events for the dropdown are now triggered on the dropdown toggle button and then bubbled up to the parent element.

- Dropdown menus now have a `data-bs-popper="static"` attribute set when the positioning of the dropdown is static, or dropdown is in the navbar. This is added by our JavaScript and helps us use custom position styles without interfering with Popper’s positioning.

- Breaking Dropped `flip` option for dropdown plugin in favor of native Popper configuration. You can now disable the flipping behavior by passing an empty array for [`fallbackPlacements`](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements) option in [flip](https://popper.js.org/docs/v2/modifiers/flip/) modifier.

- Dropdown menus can now be clickable with a new `autoClose` option to handle the [auto close behavior](https://getbootstrap.com/docs/5.3/components/dropdowns#auto-close-behavior). You can use this option to accept the click inside or outside the dropdown menu to make it interactive.

- Dropdowns now support `.dropdown-item` s wrapped in `<li>` s.


#### Jumbotron [Link to this section: Jumbotron](https://getbootstrap.com/docs/5.3/migration/\#jumbotron)

- Breaking Dropped the jumbotron component as it can be replicated with utilities. [See our new Jumbotron example for a demo.](https://getbootstrap.com/docs/5.3/examples/jumbotron)

#### List group [Link to this section: List group](https://getbootstrap.com/docs/5.3/migration/\#list-group-1)

- Added new [`.list-group-numbered` modifier](https://getbootstrap.com/docs/5.3/components/list-group#numbered) to list groups.

#### Navs and tabs [Link to this section: Navs and tabs](https://getbootstrap.com/docs/5.3/migration/\#navs-and-tabs)

- Added new `null` variables for `font-size`, `font-weight`, `color`, and `:hover` `color` to the `.nav-link` class.

#### Navbars [Link to this section: Navbars](https://getbootstrap.com/docs/5.3/migration/\#navbars)

- Breaking Navbars now require a container within (to drastically simplify spacing requirements and CSS required).
- Breaking The `.active` class can no longer be applied to `.nav-item` s, it must be applied directly on `.nav-link` s.

#### Offcanvas [Link to this section: Offcanvas](https://getbootstrap.com/docs/5.3/migration/\#offcanvas)

- Added the new [offcanvas component](https://getbootstrap.com/docs/5.3/components/offcanvas).

#### Pagination [Link to this section: Pagination](https://getbootstrap.com/docs/5.3/migration/\#pagination)

- Pagination links now have customizable `margin-left` that are dynamically rounded on all corners when separated from one another.

- Added `transition` s to pagination links.


#### Popovers [Link to this section: Popovers](https://getbootstrap.com/docs/5.3/migration/\#popovers)

- Breaking Renamed `.arrow` to `.popover-arrow` in our default popover template.

- Renamed `whiteList` option to `allowList`.


#### Spinners [Link to this section: Spinners](https://getbootstrap.com/docs/5.3/migration/\#spinners)

- Spinners now honor `prefers-reduced-motion: reduce` by slowing down animations. [See #31882](https://github.com/twbs/bootstrap/pull/31882).

- Improved spinner vertical alignment.


#### Toasts [Link to this section: Toasts](https://getbootstrap.com/docs/5.3/migration/\#toasts)

- Toasts can now be [positioned](https://getbootstrap.com/docs/5.3/components/toasts#placement) in a `.toast-container` with the help of [positioning utilities](https://getbootstrap.com/docs/5.3/utilities/position).

- Changed default toast duration to 5 seconds.

- Removed `overflow: hidden` from toasts and replaced with proper `border-radius` s with `calc()` functions.


#### Tooltips [Link to this section: Tooltips](https://getbootstrap.com/docs/5.3/migration/\#tooltips)

- Breaking Renamed `.arrow` to `.tooltip-arrow` in our default tooltip template.

- Breaking The default value for the `fallbackPlacements` is changed to `['top', 'right', 'bottom', 'left']` for better placement of popper elements.

- Breaking Renamed `whiteList` option to `allowList`.


### Utilities [Link to this section: Utilities](https://getbootstrap.com/docs/5.3/migration/\#utilities-3)

- Breaking Renamed several utilities to use logical property names instead of directional names with the addition of RTL support:
  - Renamed `.float-left` and `.float-right` to `.float-start` and `.float-end`.
  - Renamed `.border-left` and `.border-right` to `.border-start` and `.border-end`.
  - Renamed `.rounded-left` and `.rounded-right` to `.rounded-start` and `.rounded-end`.
  - Renamed `.ml-*` and `.mr-*` to `.ms-*` and `.me-*`.
  - Renamed `.pl-*` and `.pr-*` to `.ps-*` and `.pe-*`.
  - Renamed `.text-*-left` and `.text-*-right` to `.text-*-start` and `.text-*-end`.
- Breaking Disabled negative margins by default.

- Added new `.bg-body` class for quickly setting the `<body>`’s background to additional elements.

- Added new [position utilities](https://getbootstrap.com/docs/5.3/utilities/position#arrange-elements) for `top`, `right`, `bottom`, and `left`. Values include `0`, `50%`, and `100%` for each property.

- Added new `.translate-middle-x` & `.translate-middle-y` utilities to horizontally or vertically center absolute/fixed positioned elements.

- Added new [`border-width` utilities](https://getbootstrap.com/docs/5.3/utilities/borders#border-width).

- Breaking Renamed `.text-monospace` to `.font-monospace`.

- Breaking Removed `.text-hide` as it’s an antiquated method for hiding text that shouldn’t be used anymore.

- Added `.fs-*` utilities for `font-size` utilities (with RFS enabled). These use the same scale as HTML’s default headings (1-6, large to small), and can be modified via Sass map.

- Breaking Renamed `.font-weight-*` utilities as `.fw-*` for brevity and consistency.

- Breaking Renamed `.font-italic` utility to `.fst-italic` for brevity and consistency with new `.fst-normal` utility.

- Added `.d-grid` to display utilities and new `gap` utilities ( `.gap`) for CSS Grid and flexbox layouts.

- Breaking Removed `.rounded-sm` and `rounded-lg`, and introduced a new scale of classes, `.rounded-0` to `.rounded-3`. [See #31687](https://github.com/twbs/bootstrap/pull/31687).

- Added new `line-height` utilities: `.lh-1`, `.lh-sm`, `.lh-base` and `.lh-lg`. See [here](https://getbootstrap.com/docs/5.3/utilities/text#line-height).

- Moved the `.d-none` utility in our CSS to give it more weight over other display utilities.

- Extended the `.visually-hidden-focusable` helper to also work on containers, using `:focus-within`.


### Helpers [Link to this section: Helpers](https://getbootstrap.com/docs/5.3/migration/\#helpers-2)

- Breaking **Responsive embed helpers have been renamed to [ratio helpers](https://getbootstrap.com/docs/5.3/helpers/ratio)** with new class names and improved behaviors, as well as a helpful CSS variable.
  - Classes have been renamed to change `by` to `x` in the aspect ratio. For example, `.ratio-16by9` is now `.ratio-16x9`.
  - We’ve dropped the `.embed-responsive-item` and element group selector in favor of a simpler `.ratio > *` selector. No more class is needed, and the ratio helper now works with any HTML element.
  - The `$embed-responsive-aspect-ratios` Sass map has been renamed to `$aspect-ratios` and its values have been simplified to include the class name and the percentage as the `key: value` pair.
  - CSS variables are now generated and included for each value in the Sass map. Modify the `--bs-aspect-ratio` variable on the `.ratio` to create any [custom aspect ratio](https://getbootstrap.com/docs/5.3/helpers/ratio#custom-ratios).
- Breaking **"Screen reader" classes are now ["visually hidden" classes](https://getbootstrap.com/docs/5.3/helpers/visually-hidden).**
  - Changed the Sass file from `scss/helpers/_screenreaders.scss` to `scss/helpers/_visually-hidden.scss`
  - Renamed `.sr-only` and `.sr-only-focusable` to `.visually-hidden` and `.visually-hidden-focusable`
  - Renamed `sr-only()` and `sr-only-focusable()` mixins to `visually-hidden()` and `visually-hidden-focusable()`.
- `bootstrap-utilities.css` now also includes our helpers. Helpers don’t need to be imported in custom builds anymore.


### JavaScript [Link to this section: JavaScript](https://getbootstrap.com/docs/5.3/migration/\#javascript)

- **Dropped jQuery dependency** and rewrote plugins to be in regular JavaScript.

- Breaking Data attributes for all JavaScript plugins are now namespaced to help distinguish Bootstrap functionality from third parties and your own code. For example, we use `data-bs-toggle` instead of `data-toggle`.

- **All plugins can now accept a CSS selector as the first argument.** You can either pass a DOM element or any valid CSS selector to create a new instance of the plugin:









```js
const modal = new bootstrap.Modal('#myModal')
const dropdown = new bootstrap.Dropdown('[data-bs-toggle="dropdown"]')

```

- `popperConfig` can be passed as a function that accepts the Bootstrap’s default Popper config as an argument, so that you can merge this default configuration in your way. **Applies to dropdowns, popovers, and tooltips.**

- The default value for the `fallbackPlacements` is changed to `['top', 'right', 'bottom', 'left']` for better placement of Popper elements. **Applies to dropdowns, popovers, and tooltips.**

- Removed underscore from public static methods like `_getInstance()` → `getInstance()`.

- Removed `util.js`, with its functionality now integrated into individual plugins. If you previously included `util.js` manually, you can safely remove it, as it is no longer needed. Each plugin now contains only the utilities it requires, enhancing modularity and reducing dependencies.