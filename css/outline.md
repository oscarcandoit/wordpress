---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/outline
scraped_at: 2025-10-20T03:17:43.318Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# outline


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨March 2023⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline&level=high)

The **`outline`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) sets most of the outline properties in a single declaration.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#try_it)

- outline: solid;

- outline: dashedred;

- outline: 1remsolid;

- outline: thickdouble #32a1ce;

- outline: 8pxridgergb(170 50 220 / 0.6);



border-radius: 2rem;


cssCopy

```
outline: solid;

```

cssCopy

```
outline: dashed red;

```

cssCopy

```
outline: 1rem solid;

```

cssCopy

```
outline: thick double #32a1ce;

```

cssCopy

```
outline: 8px ridge rgb(170 50 220 / 0.6);
border-radius: 2rem;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box with an outline around it.
  </div>
</section>

```

cssCopy

```
#example-element {
  padding: 0.75rem;
  width: 80%;
  height: 100px;
}

```

## [Constituent properties](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#constituent_properties)

This property is a shorthand for the following CSS properties:

- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width)
- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style)
- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#syntax)

cssCopy

```
/* style */
outline: solid;

/* style | color */
outline: dashed #ff6666;

/* width | style */
outline: thick inset;

/* width | style | color*/
outline: 3px solid green;

/* Global values */
outline: inherit;
outline: initial;
outline: revert;
outline: revert-layer;
outline: unset;

```

The `outline` property may be specified using one, two, or three of the values listed below. The order of the values does not matter. As with all shorthand properties, any omitted sub-values will be set to their [initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value).

**Note:**
The outline will be invisible for many elements if its style is not defined. This is because the style defaults to `none`. A notable exception is `input` elements, which are given default styling by browsers.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#values)

[`<'outline-width'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#outline-width)

Sets the thickness of the outline. Defaults to `medium` if absent. See [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width).

[`<'outline-style'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#outline-style)

Sets the style of the outline. Defaults to `none` if absent. See [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style).

[`<'outline-color'>`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline#outline-color)

Sets the color of the outline. Defaults to `invert` for browsers supporting it, `currentColor` for the others. See [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color).

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#description)

Outline is a line outside of the element's [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border). Unlike other areas of the box, outlines don't take up space, so they don't affect the layout of the document in any way.

There are a few properties that affect an outline's appearance. It is possible to change the style, color, and width using the `outline` property, the distance from the border using the [`outline-offset`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset) property, and corner angles using the [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) property.

An outline is not required to be rectangular: While dealing with multiline text, some browsers will draw an outline for each line box separately, while others will wrap the whole text with a single outline.

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#accessibility)

Assigning `outline` a value of `0` or `none` will remove the browser's default focus style. If an element can be interacted with it must have a visible focus indicator. Provide obvious focus styling if the default focus style is removed.

- [How to Design Useful and Usable Focus Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/)
- WCAG 2.1: [Understanding Success Criterion 2.4.7: Focus Visible](https://www.w3.org/WAI/WCAG21/Understanding/focus-visible.html)

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | as each of the properties of the shorthand:<br>- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width): `medium`<br>- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style): `none`<br>- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color): `auto` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as each of the properties of the shorthand:<br>- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width): an absolute length; if the keyword `none` is specified, the computed value is `0`<br>- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style): as specified<br>- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color): For the keyword `auto`, the computed value is `currentcolor`. For the color value, if the value is translucent, the computed value will be the `rgba()` corresponding one. If it isn't, it will be the `rgb()` corresponding one. The `transparent` keyword maps to `rgba(0,0,0,0)`. |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | as each of the properties of the shorthand:<br>- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width): a [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length#interpolation "Values of the <length> CSS data type are interpolated as real, floating-point numbers.")<br>- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style): by computed value type<br>- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color): a [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#interpolation "Values of the <color> CSS data type are interpolated on each of their red, green, blue components, each handled as a real, floating-point number. Note that interpolation of colors happens in the alpha-premultiplied sRGBA color space to prevent unexpected grey colors to appear.") |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#formal_syntax)

```
outline =
  [<'outline-width'>](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width)   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'outline-style'>](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style)   [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")
  [<'outline-color'>](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)

<outline-width> =
  <line-width>

<outline-style> =
  auto                   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <outline-line-style>

<outline-color> =
  auto         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <image-1D>

<line-width> =
  [<length \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  thin             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  medium           [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  thick

<image-1D> =
  <stripes()>

<stripes()> =
  stripes( <color-stripe> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma") )

<color-stripe> =
  [<color>](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)                             [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <length-percentage>  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  [<flex>](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#examples)

### [Using outline to set a focus style](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#using_outline_to_set_a_focus_style)

#### HTML

htmlCopyPlay

```
<a href="#">This link has a special focus style.</a>

```

#### CSS

cssCopyPlay

```
a {
  border: 1px solid;
  border-radius: 3px;
  display: inline-block;
  margin: 10px;
  padding: 5px;
}

a:focus {
  outline: 4px dotted #ee7733;
  outline-offset: 4px;
  background: #ffffaa;
}

```

#### Result

Play

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#specifications)

| Specification |
| --- |
| [CSS Basic User Interface Module Level 4\<br>\# outline](https://drafts.csswg.org/css-ui/#outline) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/outline# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/outline.json "File: ⁨css/properties/outline.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `outline` | Chrome – Full support<br>Chrome94<br>more<br>Chrome – Partial support<br>Chrome1 – 93 (Release date: ⁨2008-12-11⁩)<br> <br>footnotePartial supportfootnoteBefore Chrome 94, `outline` does not follow the shape of `border-radius`.<br>Chrome – Full support<br>Chrome94 (Release date: ⁨2021-09-21⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge94<br>more<br>Edge – Partial support<br>Edge12 – 93 (Release date: ⁨2015-07-29⁩)<br> <br>footnotePartial supportfootnoteBefore Edge 94, `outline` does not follow the shape of `border-radius`.<br>Edge – Full support<br>Edge94 (Release date: ⁨2021-09-24⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox88<br>more<br>Firefox – No support<br>Firefox1 – 3.5 (Release date: ⁨2004-11-09⁩)<br> <br>prefix<br>footnoteRemoved in ⁨3.6⁩ and laterprefixImplemented with the vendor prefix: ⁨-moz-⁩<br>Firefox – Partial support<br>Firefox1.5 – 87 (Release date: ⁨2005-11-29⁩)<br> <br>footnotePartial supportfootnoteBefore Firefox 88, `outline` does not follow the shape of `border-radius`.<br>Firefox – Full support<br>Firefox88 (Release date: ⁨2021-04-19⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera80<br>more<br>Opera – Partial support<br>Opera7 – 79 (Release date: ⁨2003-01-28⁩)<br> <br>footnotePartial supportfootnoteBefore Opera 80, `outline` does not follow the shape of `border-radius`.<br>Opera – Full support<br>Opera80 (Release date: ⁨2021-10-05⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16.4<br>more<br>Safari – Partial support<br>Safari1.2 – 16.3 (Release date: ⁨2004-02-02⁩)<br> <br>footnotePartial supportfootnoteBefore Safari 16.4, `outline` does not follow the shape of `border-radius`. See [bug 20807](https://webkit.org/b/20807).<br>Safari – Full support<br>Safari16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android94<br>more<br>Chrome Android – Partial support<br>Chrome Android18 – 93 (Release date: ⁨2012-06-27⁩)<br> <br>footnotePartial supportfootnoteBefore Chrome Android 94, `outline` does not follow the shape of `border-radius`.<br>Chrome Android – Full support<br>Chrome Android94 (Release date: ⁨2021-09-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android88<br>more<br>Firefox for Android – Partial support<br>Firefox for Android4 – 87 (Release date: ⁨2011-03-29⁩)<br> <br>footnotePartial supportfootnoteBefore Firefox for Android 88, `outline` does not follow the shape of `border-radius`.<br>Firefox for Android – Full support<br>Firefox for Android88 (Release date: ⁨2021-04-19⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16.4<br>more<br>Safari on iOS – Partial support<br>Safari on iOS1 – 16.3 (Release date: ⁨2007-06-29⁩)<br> <br>footnotePartial supportfootnoteBefore Safari on iOS 16.4, `outline` does not follow the shape of `border-radius`. See [bug 20807](https://webkit.org/b/20807).<br>Safari on iOS – Full support<br>Safari on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android94<br>more<br>WebView Android – Partial support<br>WebView Android1 – 93 (Release date: ⁨2008-09-23⁩)<br> <br>footnotePartial supportfootnoteBefore Chrome 94, `outline` does not follow the shape of `border-radius`.<br>WebView Android – Full support<br>WebView Android94 (Release date: ⁨2021-09-21⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16.4<br>more<br>WebView on iOS – Partial support<br>WebView on iOS1 – 16.3 (Release date: ⁨2007-06-29⁩)<br> <br>footnotePartial supportfootnoteBefore WebView on iOS 16.4, `outline` does not follow the shape of `border-radius`. See [bug 20807](https://webkit.org/b/20807).<br>WebView on iOS – Full support<br>WebView on iOS16.4 (Release date: ⁨2023-03-27⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/outline\#see_also)

- [`outline-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width)
- [`outline-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style)
- [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color)
- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Aug 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/outline/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/outline/index.md?plain=1 "Folder: ⁨en-us/web/css/outline⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Foutline%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Foutline%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Foutline%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F06639598f7805417a0331fe403304af9c7ecc2de%0A*+Document+last+modified%3A+2025-08-13T02%3A06%3A22.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")