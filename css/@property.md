---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/@property
scraped_at: 2025-10-20T03:18:46.765Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/@property#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/@property#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# @property


Baseline

2024


Newly available

Since ⁨July 2024⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/@property#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40property&level=low)

The **`@property`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/At-rule) is part of the [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/API/Houdini_APIs) set of APIs. It allows developers to explicitly define [CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), allowing for property type checking and constraining, setting default values, and defining whether a custom property can inherit values or not.

The `@property` rule represents a custom property registration directly in a stylesheet without having to run any JavaScript. Valid `@property` rules result in a registered custom property, which is similar to calling [`registerProperty()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/registerProperty_static "registerProperty()") with equivalent parameters.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#syntax)

cssCopy

```
@property --rotation {
  syntax: "<angle>";
  inherits: false;
  initial-value: 45deg;
}

```

The custom property name is a [`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident) that starts with `--` and is followed by a valid, user-defined identifier. It is case-sensitive.

### [Descriptors](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#descriptors)

[`syntax`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax)

A string that describes the allowed value types for the registered custom property.
May be a data type name (such as `<color>`, `<length>`, or `<number>`, etc.), with multipliers ( `+`, `#`) and combinators ( `|`), or a custom ident.
See the [syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax) descriptor page for more details.

[`inherits`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/inherits)

A boolean value that controls whether the custom property registration specified by `@property` inherits by default.

[`initial-value`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value)

A value that sets the starting value for the property.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#description)

The following conditions must be met for the `@property` rule to be valid:

- The `@property` rule must include both the [`syntax`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax) and [`inherits`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/inherits) descriptors.
If either is missing, the entire `@property` rule is invalid and ignored.
- The [`initial-value`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value) descriptor is optional if the value of the `syntax` descriptor is the universal syntax definition (that is, `syntax: "*"`).
If the `initial-value` descriptor is required but omitted, the entire `@property` rule is invalid and ignored.
- If the value of the `syntax` descriptor is not the universal syntax definition, the [`initial-value`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value) descriptor has to be a [computationally independent](https://drafts.css-houdini.org/css-properties-values-api-1/#computationally-independent) value.
This means the value can be converted into a computed value without depending on other values, except for "global" definitions independent of CSS.
For example, `10px` is computationally independent—it doesn't change when converted to a computed value. `2in` is also valid, because `1in` is always equivalent to `96px`. However, `3em` is not valid, because the value of an `em` is dependent on the parent's [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size).
- Unknown descriptors are invalid and ignored, but do not invalidate the `@property` rule.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#formal_syntax)

```
@property =
  @property <custom-property-name> { <declaration-list> }

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#examples)

### [Using `@property` to register and use a custom property](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#using_property_to_register_and_use_a_custom_property)

In this example, we define two custom properties, `--item-size` and `--item-color`, that we'll use to define the size (width and height) and background color of the three following items.

htmlCopyPlay

```
<div class="container">
  <div class="item one">Item one</div>
  <div class="item two">Item two</div>
  <div class="item three">Item three</div>
</div>

```

The following code uses the CSS `@property` at-rule to define a custom property named `--item-size`. The property sets the initial value to `40%`, limiting valid values to [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values only. This means, when used as the value for an item's size, its size will always be relative to its parent's size. The property is inheritable.

cssCopyPlay

```
@property --item-size {
  syntax: "<percentage>";
  inherits: true;
  initial-value: 40%;
}

```

We define a second custom property, `--item-color`, using [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) instead of CSS. The JavaScript [`registerProperty()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/registerProperty_static "registerProperty()") method is equivalent to `@property` at-rule. The property is defined to have an initial value of `aqua`, to accept only [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) values, and is not inherited.

jsCopyPlay

```
window.CSS.registerProperty({
  name: "--item-color",
  syntax: "<color>",
  inherits: false,
  initialValue: "aqua",
});

```

We use the two custom properties to style the items:

cssCopyPlay

```
.container {
  display: flex;
  height: 200px;
  border: 1px dashed black;

  /* set custom property values on parent */
  --item-size: 20%;
  --item-color: orange;
}

/* use custom properties to set item size and background color */
.item {
  width: var(--item-size);
  height: var(--item-size);
  background-color: var(--item-color);
}

/* set custom property values on element itself */
.two {
  --item-size: initial;
  --item-color: inherit;
}

.three {
  /* invalid values */
  --item-size: 1000px;
  --item-color: xyz;
}

```

Play

The two custom properties, `--item-size: 20%` and `--item-color: orange;` are set on the `container` parent, overriding the `40%` and `aqua` default values set when these custom properties were defined. The size is set to be inheritable; the color is not.

For item one, none of these custom properties have been set. The `--item-size` is inheritable, so the value `20%` set on its parent `container` is used. On the other hand, the property `--item-color` is not inheritable, so the value `orange` set on the parent is not considered. Instead the default initial value `aqua` is used.

For item two, CSS global keywords are set for both custom properties which are valid values for all value types and therefore valid no matter the `syntax` descriptor value. The `--item-size` is set to `initial` and uses the `initial-value: 40%;` set in the `@property` declaration. The `initial` value means the `initialValue` value for the property is used. The `--item-color` is set to `inherit`, explicitly inheriting the `orange` value from its parent even though the custom property is set to otherwise not be inherited. This is why item two is orange.

For item three, the `--item-size` value gets set to `1000px`. While `1000px` is a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value, the `@property` declaration requires the value be a `<percentage>`, so the declaration is not valid and is ignored, meaning the inheritable `20%` set on the parent is used. The `xyz` value is also invalid. As `registerProperty()` set `--item-color` to not be inherited, the default initial value of `aqua` is used and not the parent's `orange` value.

### [Animating a custom property value](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#animating_a_custom_property_value)

In this example, we define a custom property called `--progress` using `@property`: this accepts [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) values and has an initial value of `25%`. We use `--progress` to define the position value of the color stops in a [`linear-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient), specifying where a green color stops, and black starts. We then animate the value of `--progress` to `100%` over 2.5 seconds, giving the effect of animating a progress bar.

htmlCopyPlay

```
<div class="bar"></div>

```

cssCopyPlay

```
@property --progress {
  syntax: "<percentage>";
  inherits: false;
  initial-value: 25%;
}

.bar {
  display: inline-block;
  --progress: 25%;
  width: 100%;
  height: 5px;
  background: linear-gradient(
    to right,
    #00d230 var(--progress),
    black var(--progress)
  );
  animation: progressAnimation 2.5s ease infinite;
}

@keyframes progressAnimation {
  to {
    --progress: 100%;
  }
}

```

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#specifications)

| Specification |
| --- |
| [CSS Properties and Values API Level 1\<br>\# at-property-rule](https://drafts.css-houdini.org/css-properties-values-api/#at-property-rule) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/@property# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/at-rules/property.json "File: ⁨css/at-rules/property.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `@property` | Chrome – Full support<br>Chrome85<br>Chrome – Full support<br>Chrome85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge85<br>Edge – Full support<br>Edge85 (Release date: ⁨2020-08-27⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox128<br>Firefox – Full support<br>Firefox128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera71<br>Opera – Full support<br>Opera71 (Release date: ⁨2020-09-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16.4<br>Safari – Full support<br>Safari16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android85<br>Chrome Android – Full support<br>Chrome Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android128<br>Firefox for Android – Full support<br>Firefox for Android128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android60<br>Opera Android – Full support<br>Opera Android60 (Release date: ⁨2020-09-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16.4<br>Safari on iOS – Full support<br>Safari on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet14<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android85<br>WebView Android – Full support<br>WebView Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16.4<br>WebView on iOS – Full support<br>WebView on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support |
| [`inherits` descriptor](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/inherits) | Chrome – Full support<br>Chrome85<br>Chrome – Full support<br>Chrome85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge85<br>Edge – Full support<br>Edge85 (Release date: ⁨2020-08-27⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox128<br>Firefox – Full support<br>Firefox128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera71<br>Opera – Full support<br>Opera71 (Release date: ⁨2020-09-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16.4<br>Safari – Full support<br>Safari16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android85<br>Chrome Android – Full support<br>Chrome Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android128<br>Firefox for Android – Full support<br>Firefox for Android128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android60<br>Opera Android – Full support<br>Opera Android60 (Release date: ⁨2020-09-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16.4<br>Safari on iOS – Full support<br>Safari on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet14<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android85<br>WebView Android – Full support<br>WebView Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16.4<br>WebView on iOS – Full support<br>WebView on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support |
| [`initial-value` descriptor](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value) | Chrome – Full support<br>Chrome85<br>Chrome – Full support<br>Chrome85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge85<br>Edge – Full support<br>Edge85 (Release date: ⁨2020-08-27⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox128<br>Firefox – Full support<br>Firefox128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera71<br>Opera – Full support<br>Opera71 (Release date: ⁨2020-09-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16.4<br>Safari – Full support<br>Safari16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android85<br>Chrome Android – Full support<br>Chrome Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android128<br>Firefox for Android – Full support<br>Firefox for Android128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android60<br>Opera Android – Full support<br>Opera Android60 (Release date: ⁨2020-09-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16.4<br>Safari on iOS – Full support<br>Safari on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet14<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android85<br>WebView Android – Full support<br>WebView Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16.4<br>WebView on iOS – Full support<br>WebView on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support |
| [`syntax` descriptor](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax) | Chrome – Full support<br>Chrome85<br>Chrome – Full support<br>Chrome85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge85<br>Edge – Full support<br>Edge85 (Release date: ⁨2020-08-27⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox128<br>Firefox – Full support<br>Firefox128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera71<br>Opera – Full support<br>Opera71 (Release date: ⁨2020-09-15⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16.4<br>Safari – Full support<br>Safari16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android85<br>Chrome Android – Full support<br>Chrome Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android128<br>Firefox for Android – Full support<br>Firefox for Android128 (Release date: ⁨2024-07-09⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android60<br>Opera Android – Full support<br>Opera Android60 (Release date: ⁨2020-09-23⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16.4<br>Safari on iOS – Full support<br>Safari on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet14<br>Samsung Internet – Full support<br>Samsung Internet14 (Release date: ⁨2021-04-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android85<br>WebView Android – Full support<br>WebView Android85 (Release date: ⁨2020-08-25⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16.4<br>WebView on iOS – Full support<br>WebView on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/@property\#see_also)

- [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var)
- [CSS Properties and Values API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API)
- [CSS Painting API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
- [CSS Typed Object Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API)
- [Houdini APIs](https://developer.mozilla.org/en-US/docs/Web/API/Houdini_APIs)
- [Using CSS custom properties (variables)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties) guide
- [CSS custom properties for cascading variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables) module

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 20, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/@property/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/@property/index.md?plain=1 "Folder: ⁨en-us/web/css/@property⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40property&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2F%40property%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%40property%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2F%40property%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F886f2641ae90a70858c5e7d0d20959c70ee44d9d%0A*+Document+last+modified%3A+2025-08-20T01%3A23%3A27.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")