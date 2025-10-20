---
url: https://getbootstrap.com/docs/5.3/getting-started/rtl
scraped_at: 2025-10-20T02:33:54.229Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/getting-started/rtl/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/getting-started/rtl/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/getting-started/rtl.mdx "View and edit this file on GitHub")

# RTL

Learn how to enable support for right-to-left text in Bootstrap across our layout, components, and utilities.

On this page
**On this page**

* * *

## Get familiar [Link to this section: Get familiar](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#get-familiar)

We recommend getting familiar with Bootstrap first by reading through our [Getting Started Introduction page](https://getbootstrap.com/docs/5.3/getting-started/introduction). Once you’ve run through it, continue reading here for how to enable RTL.

You may also want to read up on [the RTLCSS project](https://rtlcss.com/), as it powers our approach to RTL.

**Bootstrap’s RTL feature is still experimental** and will evolve based on user feedback. Spotted something or have an improvement to suggest? [Open an issue](https://github.com/twbs/bootstrap/issues/new/choose), we’d love to get your insights.

## Required HTML [Link to this section: Required HTML](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#required-html)

There are two strict requirements for enabling RTL in Bootstrap-powered pages.

1. Set `dir="rtl"` on the `<html>` element.
2. Add an appropriate `lang` attribute, like `lang="ar"`, on the `<html>` element.

From there, you’ll need to include an RTL version of our CSS. For example, here’s the stylesheet for our compiled and minified CSS with RTL enabled:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.rtl.min.css" integrity="sha384-CfCrinSRH2IR6a4e6fy2q6ioOX7O6Mtm1L9vRvFZ1trBncWmMePhzvafv7oIcWiW" crossorigin="anonymous">

```

### Starter template [Link to this section: Starter template](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#starter-template)

You can see the above requirements reflected in this modified RTL starter template.

```html
<!doctype html>
<html lang="ar" dir="rtl">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.rtl.min.css" integrity="sha384-CfCrinSRH2IR6a4e6fy2q6ioOX7O6Mtm1L9vRvFZ1trBncWmMePhzvafv7oIcWiW" crossorigin="anonymous">

    <title>مرحبًا بالعالم!</title>
  </head>
  <body>
    <h1>مرحبًا بالعالم!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.min.js" integrity="sha384-G/EV+4j2dNv+tEPo3++6LCgdCROaejBqfUeNjuKAiuXbjrxilcCdDz6ZAVfHWe1Y" crossorigin="anonymous"></script>
    -->
  </body>
</html>

```

### RTL examples [Link to this section: RTL examples](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#rtl-examples)

Get started with one of our several [RTL examples](https://getbootstrap.com/docs/5.3/examples/#rtl).

## Approach [Link to this section: Approach](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#approach)

Our approach to building RTL support into Bootstrap comes with two important decisions that impact how we write and use our CSS:

1. **First, we decided to build it with the [RTLCSS](https://rtlcss.com/) project.** This gives us some powerful features for managing changes and overrides when moving from LTR to RTL. It also allows us to build two versions of Bootstrap from one codebase.

2. **Second, we’ve renamed a handful of directional classes to adopt a logical properties approach.** Most of you have already interacted with logical properties thanks to our flex utilities—they replace direction properties like `left` and `right` in favor `start` and `end`. That makes the class names and values appropriate for LTR and RTL without any overhead.


For example, instead of `.ml-3` for `margin-left`, use `.ms-3`.

Working with RTL, through our source Sass or compiled CSS, shouldn’t be much different from our default LTR though.

## Customize from source [Link to this section: Customize from source](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#customize-from-source)

When it comes to [customization](https://getbootstrap.com/docs/5.3/customize/sass), the preferred way is to take advantage of variables, maps, and mixins. This approach works the same for RTL, even if it’s post-processed from the compiled files, thanks to [how RTLCSS works](https://rtlcss.com/learn/getting-started/why-rtlcss/).

### Custom RTL values [Link to this section: Custom RTL values](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#custom-rtl-values)

Using [RTLCSS value directives](https://rtlcss.com/learn/usage-guide/value-directives/), you can make a variable output a different value for RTL. For example, to decrease the weight for `$font-weight-bold` throughout the codebase, you may use the `/*rtl: {value}*/` syntax:

```scss
$font-weight-bold: 700 #{/* rtl:600 */} !default;

```

Which would output to the following for our default CSS and RTL CSS:

```css
/* bootstrap.css */
dt {
  font-weight: 700 /* rtl:600 */;
}

/* bootstrap.rtl.css */
dt {
  font-weight: 600;
}

```

### Alternative font stack [Link to this section: Alternative font stack](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#alternative-font-stack)

In the case you’re using a custom font, be aware that not all fonts support the non-Latin alphabet. To switch from Pan-European to Arabic family, you may need to use `/*rtl:insert: {value}*/` in your font stack to modify the names of font families.

For example, to switch from `Helvetica Neue` font for LTR to `Helvetica Neue Arabic` for RTL, your Sass code could look like this:

```scss
$font-family-sans-serif:
  Helvetica Neue #{"/* rtl:insert:Arabic */"},
  // Cross-platform generic font family (default user interface font)
  system-ui,
  // Safari for macOS and iOS (San Francisco)
  -apple-system,
  // Chrome < 56 for macOS (San Francisco)
  BlinkMacSystemFont,
  // Windows
  "Segoe UI",
  // Android
  Roboto,
  // Basic web fallback
  Arial,
  // Linux
  "Noto Sans",
  // Sans serif fallback
  sans-serif,
  // Emoji fonts
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji" !default;

```

### LTR and RTL at the same time [Link to this section: LTR and RTL at the same time](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#ltr-and-rtl-at-the-same-time)

Need both LTR and RTL on the same page? Thanks to [RTLCSS String Maps](https://rtlcss.com/learn/usage-guide/string-map/), this is pretty straightforward. Wrap your `@import` s with a class, and set a custom rename rule for RTLCSS:

```scss
/* rtl:begin:options: {
  "autoRename": true,
  "stringMap":[ {\
    "name": "ltr-rtl",\
    "priority": 100,\
    "search": ["ltr"],\
    "replace": ["rtl"],\
    "options": {\
      "scope": "*",\
      "ignoreCase": false\
    }\
  } ]
} */
.ltr {
  @import "../node_modules/bootstrap/scss/bootstrap";
}
/*rtl:end:options*/

```

After running Sass then RTLCSS, each selector in your CSS files will be prepended by `.ltr`, and `.rtl` for RTL files. Now you’re able to use both files on the same page, and simply use `.ltr` or `.rtl` on your components wrappers to use one or the other direction.

**Edge cases and known limitations** to consider when working with a combined LTR and RTL implementation:

1. When switching `.ltr` and `.rtl`, make sure you add `dir` and `lang` attributes accordingly.
2. Loading both files can be a real performance bottleneck: consider some [optimization](https://getbootstrap.com/docs/5.3/customize/optimize), and maybe try to [load one of those files asynchronously](https://www.filamentgroup.com/lab/load-css-simpler/).
3. Nesting styles this way will prevent our `form-validation-state()` mixin from working as intended, thus require you tweak it a bit by yourself. [See #31223](https://github.com/twbs/bootstrap/issues/31223).

Do you want to automate this process and address several edge cases involving both directions within a single stylesheet? Then, consider using [PostCSS RTLCSS](https://github.com/elchininet/postcss-rtlcss) as a [PostCSS](https://github.com/postcss/postcss) plugin to process your source files. PostCSS RTLCSS uses [RTLCSS](https://rtlcss.com/) behind the scenes to manage the direction flipping process, but it separates the flipped declarations into rules with a different prefix for LTR and RTL, something that allows you to have both directions within the same stylesheet file. By doing this, you can switch between LTR and RTL orientations by simply changing the `dir` of the page (or even by modifying a specific class if you configure the plugin accordingly).

**Important things to take into account** when using PostCSS RTLCSS to build a combined LTR and RTL implementation:

1. It is recommended that you add the `dir` attribute to the `html` element. This way, the entire page will be affected when you change the direction. Also, make sure you add the `lang` attribute accordingly.
2. Having a single bundle with both directions will increase the size of the final stylesheet (on average, by 20%-30%): consider some [optimization](https://getbootstrap.com/docs/5.3/customize/optimize).
3. Take into account that PostCSS RTLCSS is not compatible with `/* rtl:remove */` directives because it doesn’t remove any CSS rule. You should replace your `/* rtl:remove */`, `/* rtl:begin:remove */` and `/* rtl:end:remove */` directives with `/* rtl:freeze */`, `/* rtl:begin:freeze */` and `/* rtl:end:freeze */` directives respectively. These directives will prefix the targeted rules or declarations with the current direction but will not create an RTL counterpart (same result as the `remove` ones in RTLCSS).

## The breadcrumb case [Link to this section: The breadcrumb case](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#the-breadcrumb-case)

The [breadcrumb separator](https://getbootstrap.com/docs/5.3/components/breadcrumb#dividers) is the only case requiring its own brand-new variable— namely `$breadcrumb-divider-flipped` —defaulting to `$breadcrumb-divider`.

## Additional resources [Link to this section: Additional resources](https://getbootstrap.com/docs/5.3/getting-started/rtl/\#additional-resources)

- [RTLCSS](https://rtlcss.com/)
- [RTL Styling 101](https://rtlstyling.com/posts/rtl-styling)