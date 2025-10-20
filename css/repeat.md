---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/repeat
scraped_at: 2025-10-20T02:59:50.106Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# repeat()


Baseline

Widely available


This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨July 2020⁩.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Frepeat&level=high)

The **`repeat()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) represents a repeated fragment of the [track list](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout), allowing a large number of columns or rows that exhibit a recurring pattern to be written in a more compact form.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#try_it)

- grid-template-columns: repeat(2, 60px);

- grid-template-columns: 1frrepeat(2, 60px);

- grid-template-columns: repeat(2, 20px 1fr);

- grid-template-columns: repeat(auto-fill, 40px);


cssCopy

```
grid-template-columns: repeat(2, 60px);

```

cssCopy

```
grid-template-columns: 1fr repeat(2, 60px);

```

cssCopy

```
grid-template-columns: repeat(2, 20px 1fr);

```

cssCopy

```
grid-template-columns: repeat(auto-fill, 40px);

```

htmlCopy

```
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
  </div>
</section>

```

cssCopy

```
#example-element {
  border: 1px solid #c5c5c5;
  display: grid;
  grid-auto-rows: 40px;
  grid-gap: 10px;
  width: 220px;
}

#example-element > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
}

```

This function can be used in the CSS grid properties [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns) and [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#syntax)

cssCopy

```
/* <track-repeat> values */
repeat(4, 1fr)
repeat(4, [col-start] 250px [col-end])
repeat(4, [col-start] 60% [col-end])
repeat(4, [col-start] 1fr [col-end])
repeat(4, [col-start] min-content [col-end])
repeat(4, [col-start] max-content [col-end])
repeat(4, [col-start] auto [col-end])
repeat(4, [col-start] minmax(100px, 1fr) [col-end])
repeat(4, [col-start] fit-content(200px) [col-end])
repeat(4, 10px [col-start] 30% [col-middle] auto [col-end])
repeat(4, [col-start] min-content [col-middle] max-content [col-end])

/* <auto-repeat> values */
repeat(auto-fill, 250px)
repeat(auto-fit, 250px)
repeat(auto-fill, [col-start] 250px [col-end])
repeat(auto-fit, [col-start] 250px [col-end])
repeat(auto-fill, [col-start] minmax(100px, 1fr) [col-end])
repeat(auto-fill, 10px [col-start] 30% [col-middle] 400px [col-end])

/* <fixed-repeat> values */
repeat(4, 250px)
repeat(4, [col-start] 250px [col-end])
repeat(4, [col-start] 60% [col-end])
repeat(4, [col-start] minmax(100px, 1fr) [col-end])
repeat(4, [col-start] fit-content(200px) [col-end])
repeat(4, 10px [col-start] 30% [col-middle] 400px [col-end])

```

The `repeat()` function takes two arguments:

- **repeat count**: the first argument specifies the number of times that the track list should be repeated. It is specified with an integer value of 1 or more, or with the keyword values [`auto-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fill) or [`auto-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fit). These keyword values repeat the set of tracks as many times as is needed to fill the grid container.
- **tracks**: the second argument specifies the set of tracks that will be repeated. Fundamentally this consists of one or more values, where each value represents the size of that track. Each size is specified using either a [`<track-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#track-size) value or a [`<fixed-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#fixed-size) value. You can also specify one or more [line names](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_named_grid_lines) before or after each track, by providing [`<line-names>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#line-names) values before and/or after the track size.

If you use [`auto-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fill) or [`auto-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fit) to set the repeat count, you may only specify track sizes using the [`<fixed-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#fixed-size) type, not the [`<track-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#track-size) type. This give us three main syntax forms for `repeat()`:

- `<track-repeat>`, which uses:

  - an integer to set the repeat count
  - [`<track-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#track-size) values to set track sizes.
- `<auto-repeat>`, which uses

  - [`auto-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fill) or [`auto-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fit) to set the repeat count
  - [`<fixed-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#fixed-size) to set track sizes.
- `<fixed-repeat>`, which uses:

  - an integer to set the repeat count
  - [`<fixed-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#fixed-size) values to set track sizes.

Then if a property declaration uses `<auto-repeat>`, it is only allowed to use `<fixed-repeat>` for any additional `repeat()` calls. For example, this is invalid, because it combines the `<auto-repeat>` form with the `<track-repeat>` form:

cssCopy

```
.wrapper {
  grid-template-columns:
    repeat(auto-fill, 10px)
    repeat(2, minmax(min-content, max-content));
}

```

There is a fourth form, `<name-repeat>`, which is used to add line names to subgrids. It only used with the [`subgrid`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid) keyword and only specifies line names, not track sizes.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#values)

[`<fixed-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#fixed-size)

One of the following forms:

- a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value
- a [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax) function with:

  - `min` given as a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value
  - `max` given as one of a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value, a [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value) value, or one of the following keywords: [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#min-content), [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#max-content), or [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)
- a [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax) function with:

  - `min` given as a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value or one of the following keywords: [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#min-content), [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#max-content), or [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)
  - `max` given as a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value.

[`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value)

A non-negative dimension with the unit `fr` specifying the track's flex factor. Each `<flex>`-sized track takes a share of the remaining space in proportion to its flex factor.

[`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length)

A positive integer length.

[`<line-names>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#line-names)

Zero or more [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident) values, space-separated and enclosed in square brackets, like this: `[first header-start]`.

[`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

A non-negative percentage relative to the inline size of the grid container in column grid tracks, and the block size of the grid container in row grid tracks. If the size of the grid container depends on the size of its tracks, then the `<percentage>` must be treated as `auto`. The user-agent may adjust the intrinsic size contributions of the track to the size of the grid container and increase the final size of the track by the minimum amount that would result in honoring the percentage.

[`<track-size>`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#track-size)

One of the following forms:

- a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value, a [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value) value, or one of the following keywords: [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#min-content), [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#max-content), or [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)
- a [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax) function with:

  - `min` given as a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value, or one of the following keywords: [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#min-content), [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#max-content), or [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)
  - `max` given as a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value, a [`<flex>`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value) value, or one of the following keywords: [`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#min-content), [`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#max-content), or [`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)
- a [`fit-content()`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content_function) function, passed a [`<length-percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length-percentage) value.

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto)

As a maximum, identical to `max-content`. As a minimum it represents the largest minimum size (as specified by [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width)/ [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height)) of the grid items occupying the grid track.

[`auto-fill`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fill)

If the grid container has a definite or maximal size in the relevant axis, then the number of repetitions is the largest possible positive integer that does not cause the grid to overflow its grid container. Treating each track as its maximal track sizing function (each independent value used to define `grid-template-rows` or `grid-template-columns`), if that is definite. Otherwise, as its minimum track sizing function, and taking grid-gap into account. If any number of repetitions would overflow, then the repetition is `1`. Otherwise, if the grid container has a definite minimal size in the relevant axis, the number of repetitions is the smallest possible positive integer that fulfills that minimum requirement. Otherwise, the specified track list repeats only once.

[`auto-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat#auto-fit)

Behaves the same as `auto-fill`, except that after placing the grid items any empty repeated tracks are collapsed. An empty track is one with no in-flow grid items placed into or spanning across it. (This can result in all tracks being collapsed, if they're all empty.)

A collapsed track is treated as having a single fixed track sizing function of `0px`, and the gutters on either side of it collapse.

For the purpose of finding the number of auto-repeated tracks, the user agent floors the track size to a user agent specified value (e.g., `1px`), to avoid division by zero.

[`max-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-content)

Represents the largest max-content contribution of the grid items occupying the grid track.

[`min-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-content)

Represents the largest min-content contribution of the grid items occupying the grid track.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#formal_syntax)

```
<track-repeat> =
  repeat(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<integer \[1,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") , [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <track-size>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [+](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#plus "Plus: the entity may occur one or several times")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<auto-repeat> =
  repeat(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  auto-fill  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  auto-fit  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") , [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <fixed-size>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [+](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#plus "Plus: the entity may occur one or several times")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<fixed-repeat> =
  repeat(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<integer \[1,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") , [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <fixed-size>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [+](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#plus "Plus: the entity may occur one or several times")  <line-names> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<name-repeat> =
  repeat(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [<integer \[1,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/integer)  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  auto-fill  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") , <line-names> [+](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#plus "Plus: the entity may occur one or several times") )

<line-names> =
  '[' [<custom-ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident) [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times") ']'

<track-size> =
  <track-breadth>                                    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  minmax( <inflexible-breadth> , <track-breadth> )   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  fit-content( <length-percentage [0,∞]> )

<fixed-size> =
  <fixed-breadth>                                    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  minmax( <fixed-breadth> , <track-breadth> )        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  minmax( <inflexible-breadth> , <fixed-breadth> )

<track-breadth> =
  <length-percentage [0,∞]>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<flex \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)                [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  min-content                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  max-content                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

<inflexible-breadth> =
  <length-percentage [0,∞]>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  min-content                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  max-content                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  auto

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

<fixed-breadth> =
  <length-percentage [0,∞]>

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#examples)

### [Specifying grid columns using repeat()](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#specifying_grid_columns_using_repeat)

#### HTML

htmlCopyPlay

```
<div id="container">
  <div>This item is 50 pixels wide.</div>
  <div>Item with flexible width.</div>
  <div>This item is 50 pixels wide.</div>
  <div>Item with flexible width.</div>
  <div>Inflexible item of 100 pixels width.</div>
</div>

```

#### CSS

cssCopyPlay

```
#container {
  display: grid;
  grid-template-columns: repeat(2, 50px 1fr) 100px;
  grid-gap: 5px;
  box-sizing: border-box;
  height: 200px;
  width: 100%;
  background-color: #8cffa0;
  padding: 10px;
}

#container > div {
  background-color: #8ca0ff;
  padding: 5px;
}

```

#### Result

Play

This item is 50 pixels wide.

Item with flexible width.

This item is 50 pixels wide.

Item with flexible width.

Inflexible item of 100 pixels width.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#specifications)

| Specification |
| --- |
| [CSS Grid Layout Module Level 2\<br>\# repeat-notation](https://drafts.csswg.org/css-grid/#repeat-notation) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/grid-template-columns.json "File: ⁨css/properties/grid-template-columns.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `repeat()` | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge16<br>Edge – Full support<br>Edge16 (Release date: ⁨2017-10-17⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox76<br>more<br>Firefox – Partial support<br>Firefox52 – 56 (Release date: ⁨2017-03-07⁩)<br> <br>footnotePartial supportfootnote[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) doesn't work in `repeat()` (see [bug 1350069](https://bugzil.la/1350069)).<br>Firefox – Partial support<br>Firefox57 – 75 (Release date: ⁨2017-11-14⁩)<br> <br>footnotePartial supportfootnote`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support one repeated column (see [bug 1341507](https://bugzil.la/1341507)).<br>Firefox – Full support<br>Firefox76 (Release date: ⁨2020-05-05⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10.1<br>Safari – Full support<br>Safari10.1 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android79<br>more<br>Firefox for Android – Partial support<br>Firefox for Android52 – 56 (Release date: ⁨2017-03-07⁩)<br> <br>footnotePartial supportfootnote[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) doesn't work in `repeat()` (see [bug 1350069](https://bugzil.la/1350069)).<br>Firefox for Android – Partial support<br>Firefox for Android57 – 68 (Release date: ⁨2017-11-28⁩)<br> <br>footnotePartial supportfootnote`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support one repeated column (see [bug 1341507](https://bugzil.la/1341507)).<br>Firefox for Android – Full support<br>Firefox for Android79 (Release date: ⁨2020-07-28⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS10.3<br>Safari on iOS – Full support<br>Safari on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet6<br>Samsung Internet – Full support<br>Samsung Internet6 (Release date: ⁨2017-08-23⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS10.3<br>WebView on iOS – Full support<br>WebView on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat\#see_also)

- [`grid-template`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template)
- [`grid-template-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
- [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- [`grid-template-areas`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
- [`grid-auto-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns)
- [`grid-auto-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows)
- [`grid-auto-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow)
- [Line-based placement with CSS grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_line-based_placement)
- [Grid template areas: grid definition shorthands](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_template_areas#grid_definition_shorthands)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/repeat/index.md?plain=1 "Folder: ⁨en-us/web/css/repeat⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Frepeat&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Frepeat%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Frepeat%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Frepeat%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")