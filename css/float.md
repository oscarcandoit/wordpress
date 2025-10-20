---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/float
scraped_at: 2025-10-20T03:08:23.658Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/float#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/float#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# float


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/float#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffloat&level=high)

The **`float`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property places an element on the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the page, though still remaining a part of the flow (in contrast to [absolute positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position#absolute_positioning)).

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#try_it)

- float: none;

- float: left;

- float: right;

- float: inline-start;

- float: inline-end;


cssCopy

```
float: none;

```

cssCopy

```
float: left;

```

cssCopy

```
float: right;

```

cssCopy

```
float: inline-start;

```

cssCopy

```
float: inline-end;

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">Float me</div>
    As much mud in the streets as if the waters had but newly retired from the
    face of the earth, and it would not be wonderful to meet a Megalosaurus,
    forty feet long or so, waddling like an elephantine lizard up Holborn Hill.
  </div>
</section>

```

cssCopy

```
.example-container {
  border: 1px solid #c5c5c5;
  padding: 0.75em;
  text-align: left;
  width: 80%;
  line-height: normal;
}

#example-element {
  border: solid 10px #efac09;
  background-color: #040d46;
  color: white;
  padding: 1em;
  width: 40%;
}

```

A _floating element_ is one where the computed value of `float` is not `none`.

As `float` implies the use of the block layout, it modifies the computed value of the [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) values, in some cases:

| Specified value | Computed value |
| --- | --- |
| `inline` | `block` |
| `inline-block` | `block` |
| `inline-table` | `table` |
| `table-row` | `block` |
| `table-row-group` | `block` |
| `table-column` | `block` |
| `table-column-group` | `block` |
| `table-cell` | `block` |
| `table-caption` | `block` |
| `table-header-group` | `block` |
| `table-footer-group` | `block` |
| `inline-flex` | `flex` |
| `inline-grid` | `grid` |
| _other_ | _unchanged_ |

**Note:**
When accessing a CSS property in JavaScript through the [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) object, single-word property names are used as is. Although `float` is a reserved keyword in JavaScript, the CSS `float` property is accessed as `float` in modern browsers. In older browsers, you must use `cssFloat` to access the `float` property. (This is similar to how the "class" attribute is accessed as "className" and the "for" attribute of a `<label>` element is accessed as "htmlFor".)

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#syntax)

cssCopy

```
/* Keyword values */
float: left;
float: right;
float: none;
float: inline-start;
float: inline-end;

/* Global values */
float: inherit;
float: initial;
float: revert;
float: revert-layer;
float: unset;

```

The `float` property is specified as a single keyword, chosen from the list of values below.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#values)

[`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/float#left)

The element must float on the left side of its containing block.

[`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/float#right)

The element must float on the right side of its containing block.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/float#none)

The element must not float.

[`inline-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/float#inline-start)

The element must float on the start side of its containing block. That is the left side with `ltr` scripts, and the right side with `rtl` scripts.

[`inline-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/float#inline-end)

The element must float on the end side of its containing block. That is the right side with `ltr` scripts, and the left side with `rtl` scripts.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `none` |
| Applies to | all elements, but has no effect if the value of [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) is `none`. |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#formal_syntax)

```
float =
  block-start       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  block-end         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-start      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline-end        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  snap-block        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <snap-block()>    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  snap-inline       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <snap-inline()>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  left              [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  right             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  top               [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  bottom            [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none              [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  footnote

<snap-block()> =
  snap-block(  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length) , [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  start  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  end  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  near  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<snap-inline()> =
  snap-inline(  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length) , [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  left  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  right  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  near  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#examples)

### [How floated elements are positioned](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#how_floated_elements_are_positioned)

As mentioned above, when an element is floated, it is taken out of the normal flow of the document (though still remaining part of it). It is shifted to the left, or right, until it touches the edge of its containing box, _or another floated element_.

In this example, there are three colored squares. Two are floated left, and one is floated right. Note that the second "left" square is placed to the right of the first. Additional squares would continue to stack to the right, until they filled the containing box, after which they would wrap to the next line.

A floated element is at least as tall as its tallest nested floated children. We gave the parent `width: 100%` and floated it to ensure it is tall enough to encompass its floated children, and to make sure it takes up the width of the parent so we don't have to clear its adjacent sibling.

#### HTML

htmlCopyPlay

```
<section>
  <div class="left">1</div>
  <div class="left">2</div>
  <div class="right">3</div>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tristique
    sapien ac erat tincidunt, sit amet dignissim lectus vulputate. Donec id
    iaculis velit. Aliquam vel malesuada erat. Praesent non magna ac massa
    aliquet tincidunt vel in massa. Phasellus feugiat est vel leo finibus
    congue.
  </p>
</section>

```

#### CSS

cssCopyPlay

```
section {
  box-sizing: border-box;
  border: 1px solid blue;
  width: 100%;
  float: left;
}

div {
  margin: 5px;
  width: 50px;
  height: 150px;
}

.left {
  float: left;
  background: pink;
}

.right {
  float: right;
  background: cyan;
}

```

#### Result

Play

### [Clearing floats](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#clearing_floats)

Sometimes you may want to force an item to move below any floated elements. For instance, you may want paragraphs to remain adjacent to floats, but force headings to be on their own line. See [`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) for examples.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#specifications)

| Specification |
| --- |
| [Cascading Style Sheets Level 2\<br>\# propdef-float](https://drafts.csswg.org/css2/#propdef-float) |
| [CSS Logical Properties and Values Level 1\<br>\# float-clear](https://drafts.csswg.org/css-logical/#float-clear) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/float# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/float.json "File: ⁨css/properties/float.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `float` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera7<br>Opera – Full support<br>Opera7 (Release date: ⁨2003-01-28⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android10.1<br>Opera Android – Full support<br>Opera Android10.1 (Release date: ⁨2010-11-09⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `inline-end` | Chrome – Full support<br>Chrome118<br>Chrome – Full support<br>Chrome118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge118<br>Edge – Full support<br>Edge118 (Release date: ⁨2023-10-13⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox55<br>Firefox – Full support<br>Firefox55 (Release date: ⁨2017-08-08⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera104<br>Opera – Full support<br>Opera104 (Release date: ⁨2023-10-23⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15<br>Safari – Full support<br>Safari15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android118<br>Chrome Android – Full support<br>Chrome Android118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android55<br>Firefox for Android – Full support<br>Firefox for Android55 (Release date: ⁨2017-08-08⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android79<br>Opera Android – Full support<br>Opera Android79 (Release date: ⁨2023-12-06⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15<br>Safari on iOS – Full support<br>Safari on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet25<br>Samsung Internet – Full support<br>Samsung Internet25 (Release date: ⁨2024-04-24⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android118<br>WebView Android – Full support<br>WebView Android118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15<br>WebView on iOS – Full support<br>WebView on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support |
| `inline-start` | Chrome – Full support<br>Chrome118<br>Chrome – Full support<br>Chrome118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge118<br>Edge – Full support<br>Edge118 (Release date: ⁨2023-10-13⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox55<br>Firefox – Full support<br>Firefox55 (Release date: ⁨2017-08-08⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera104<br>Opera – Full support<br>Opera104 (Release date: ⁨2023-10-23⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari15<br>Safari – Full support<br>Safari15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android118<br>Chrome Android – Full support<br>Chrome Android118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android55<br>Firefox for Android – Full support<br>Firefox for Android55 (Release date: ⁨2017-08-08⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android79<br>Opera Android – Full support<br>Opera Android79 (Release date: ⁨2023-12-06⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS15<br>Safari on iOS – Full support<br>Safari on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet25<br>Samsung Internet – Full support<br>Samsung Internet25 (Release date: ⁨2024-04-24⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android118<br>WebView Android – Full support<br>WebView Android118 (Release date: ⁨2023-10-10⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15<br>WebView on iOS – Full support<br>WebView on iOS15 (Release date: ⁨2021-09-20⁩)<br> <br>footnoteFull support |
| `left` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `none` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |
| `right` | Chrome – Full support<br>Chrome1<br>Chrome – Full support<br>Chrome1 (Release date: ⁨2008-12-11⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox1<br>Firefox – Full support<br>Firefox1 (Release date: ⁨2004-11-09⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari1<br>Safari – Full support<br>Safari1 (Release date: ⁨2003-06-23⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android18<br>Chrome Android – Full support<br>Chrome Android18 (Release date: ⁨2012-06-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android4<br>Firefox for Android – Full support<br>Firefox for Android4 (Release date: ⁨2011-03-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS1<br>Safari on iOS – Full support<br>Safari on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1<br>Samsung Internet – Full support<br>Samsung Internet1 (Release date: ⁨2013-04-27⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS1<br>WebView on iOS – Full support<br>WebView on iOS1 (Release date: ⁨2007-06-29⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/float\#see_also)

- [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context)
- Use [`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) to force an item to move below a floated element.

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/float/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/float/index.md?plain=1 "Folder: ⁨en-us/web/css/float⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffloat&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ffloat%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ffloat%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ffloat%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")