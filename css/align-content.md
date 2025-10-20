---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/align-content
scraped_at: 2025-10-20T03:09:00.694Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# align-content


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨September 2015⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Falign-content&level=high)

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **`align-content`** property sets the distribution of space between and around content items along a [flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout)'s [cross axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis), or a [grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout) or [block-level](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content) element's block axis.

The interactive example below uses grid layout to demonstrate some of the values of this property.

## [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#try_it)

- align-content: start;

- align-content: center;

- align-content: space-between;

- align-content: space-around;


This property has no effect on single line flex containers (i.e., ones with `flex-wrap: nowrap`).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#syntax)

cssCopy

```
/* Normal alignment */
align-content: normal;

/* Basic positional alignment */
/* align-content does not take left and right values */
align-content: start;
align-content: center;
align-content: end;
align-content: flex-start;
align-content: flex-end;

/* Baseline alignment */
align-content: baseline;
align-content: first baseline;
align-content: last baseline;

/* Distributed alignment */
align-content: space-between;
align-content: space-around;
align-content: space-evenly;
align-content: stretch;

/* Overflow alignment */
align-content: safe center;
align-content: unsafe center;

/* Global values */
align-content: inherit;
align-content: initial;
align-content: revert;
align-content: revert-layer;
align-content: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#values)

[`normal`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#normal)

The items are packed in their default position as if no `align-content` value was set.

[`start`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#start)

The items are packed flush to each other against the start edge of the alignment container in the cross axis.

[`center`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#center)

The items are packed flush to each other in the center of the alignment container along the cross axis.

[`end`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#end)

The items are packed flush to each other against the end edge of the alignment container in the cross axis.

[`flex-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#flex-start)

The items are packed flush to each other against the edge of the alignment container depending on the flex container's cross-start side.
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `start`.

[`flex-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#flex-end)

The items are packed flush to each other against the edge of the alignment container depending on the flex container's cross-end side.
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `end`.

[`baseline`, `first baseline`, `last baseline`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#baseline)

Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box's first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.

![the baseline is the line upon which most letters "sit" and below which descenders extend.](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content/410px-typography_line_terms.svg.png)

The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

[`space-between`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#space-between)

The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items is the same. The first item is flush with the start edge of the alignment container in the cross axis, and the last item is flush with the end edge of the alignment container in the cross axis.

[`space-around`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#space-around)

The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items is the same. The empty space before the first and after the last item equals half of the space between each pair of adjacent items.

[`space-evenly`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#space-evenly)

The items are evenly distributed within the alignment container along the cross axis. The spacing between each pair of adjacent items, the start edge and the first item, and the end edge and the last item, are all exactly the same.

[`stretch`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#stretch)

If the combined size of the items along the cross axis is less than the size of the alignment container, any `auto`-sized items have their size increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)/ [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width) (or equivalent functionality), so that the combined size exactly fills the alignment container along the cross axis.

[`safe`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#safe)

Used alongside an alignment keyword. If the chosen keyword means that the item overflows the alignment container causing data loss, the item is instead aligned as if the alignment mode were `start`.

[`unsafe`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#unsafe)

Used alongside an alignment keyword. Regardless of the relative sizes of the item and alignment container and whether overflow which causes data loss might happen, the given alignment value is honored.

**Note:**
The `<content-distribution>` values ( `space-between`, `space-around`, `space-evenly`, and `stretch`) have no effect in [block layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_block_abspos_tables#align-content_and_justify-content) as all the content in that block is treated as a single [alignment-subject](https://developer.mozilla.org/en-US/docs/Glossary/Alignment_Subject).

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `normal` |
| Applies to | Block-containers, multi-column containers, flex containers |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | discrete |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#formal_syntax)

```
align-content =
  normal                                    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <baseline-position>                       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <content-distribution>                    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <overflow-position> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")  <content-position>

<baseline-position> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  first  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  last  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional")   [&&](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_ampersand "Double ampersand: all of the entities must be present, in any order")
  baseline

<content-distribution> =
  space-between   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  space-around    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  space-evenly    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  stretch

<overflow-position> =
  unsafe   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  safe

<content-position> =
  center       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  start        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  end          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  flex-start   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  flex-end

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#examples)

### [Effects of different align-content values](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#effects_of_different_align-content_values)

In this example, you can switch between three different [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property values, including `flex`, `grid`, and `block`. You can also switch between the different values for `align-content`.

#### HTML

htmlCopyPlay

```
<section>
  <div class="olive">Olive</div>
  <div class="coral">Coral</div>
  <div class="deepskyblue">Deep<br />sky<br />blue</div>
  <div class="orchid">Orchid</div>
  <div class="slateblue">Slateblue</div>
  <div class="maroon">Maroon</div>
</section>

```

#### CSS

cssCopyPlay

```
section {
  border: solid 1.5px tomato;
  height: 300px;
  width: 300px;
  flex-wrap: wrap; /* used by flex only */
  gap: 0.2rem; /* not used by block */
}
.olive {
  background-color: olive;
}
.coral {
  background-color: coral;
}
.deepskyblue {
  background-color: deepskyblue;
}
.orchid {
  background-color: orchid;
}
.slateblue {
  background-color: slateblue;
  color: white;
}
.maroon {
  background-color: maroon;
  color: white;
}

```

#### Result

Try changing the `display` value and the `align-content` value.

Play

In [block layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_block_abspos_tables#align-content_and_justify-content), child elements are treated as a single element, meaning `space-between`, `space-around`, and `space-evenly` behave differently.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#specifications)

| Specification |
| --- |
| [CSS Box Alignment Module Level 3\<br>\# align-justify-content](https://drafts.csswg.org/css-align/#align-justify-content) |
| [CSS Flexible Box Layout Module Level 1\<br>\# align-content-property](https://drafts.csswg.org/css-flexbox/#align-content-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/align-content.json "File: ⁨css/properties/align-content.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `align-content` | Chrome – Full support<br>Chrome29<br>more<br>Chrome – Full support<br>Chrome21 (Release date: ⁨2012-07-31⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome – Full support<br>Chrome29 (Release date: ⁨2013-08-20⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>more<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox28<br>more<br>Firefox – Full support<br>Firefox49 (Release date: ⁨2016-09-20⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Firefox – Full support<br>Firefox28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera16<br>more<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera – Full support<br>Opera16 (Release date: ⁨2013-08-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>more<br>Safari – Full support<br>Safari7 (Release date: ⁨2013-10-22⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android29<br>more<br>Chrome Android – Full support<br>Chrome Android25 (Release date: ⁨2013-02-27⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Chrome Android – Full support<br>Chrome Android29 (Release date: ⁨2013-08-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android28<br>more<br>Firefox for Android – Full support<br>Firefox for Android49 (Release date: ⁨2016-09-20⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Firefox for Android – Full support<br>Firefox for Android28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android16<br>more<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Opera Android – Full support<br>Opera Android16 (Release date: ⁨2013-09-18⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>more<br>Safari on iOS – Full support<br>Safari on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet2<br>more<br>Samsung Internet – Full support<br>Samsung Internet1.5 (Release date: ⁨2013-09-25⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>Samsung Internet – Full support<br>Samsung Internet2 (Release date: ⁨2014-10-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>more<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>more<br>WebView on iOS – Full support<br>WebView on iOS7 (Release date: ⁨2013-09-18⁩)<br> <br>prefix<br>prefixImplemented with the vendor prefix: ⁨-webkit-⁩<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| Supported in Block Layout | Chrome – Full support<br>Chrome123<br>Chrome – Full support<br>Chrome123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge123<br>Edge – Full support<br>Edge123 (Release date: ⁨2024-03-22⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox125<br>Firefox – Full support<br>Firefox125 (Release date: ⁨2024-04-16⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera109<br>Opera – Full support<br>Opera109 (Release date: ⁨2024-03-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari17.4<br>Safari – Full support<br>Safari17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android123<br>Chrome Android – Full support<br>Chrome Android123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android125<br>Firefox for Android – Full support<br>Firefox for Android125 (Release date: ⁨2024-04-16⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android82<br>Opera Android – Full support<br>Opera Android82 (Release date: ⁨2024-05-02⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS17.4<br>Safari on iOS – Full support<br>Safari on iOS17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet27<br>Samsung Internet – Full support<br>Samsung Internet27 (Release date: ⁨2024-11-06⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android123<br>WebView Android – Full support<br>WebView Android123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS17.4<br>WebView on iOS – Full support<br>WebView on iOS17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support |
| Supported in Flex Layout | Chrome – Full support<br>Chrome21<br>Chrome – Full support<br>Chrome21 (Release date: ⁨2012-07-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox28<br>Firefox – Full support<br>Firefox28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera15<br>Opera – Full support<br>Opera15 (Release date: ⁨2013-07-02⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android25<br>Chrome Android – Full support<br>Chrome Android25 (Release date: ⁨2013-02-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android28<br>Firefox for Android – Full support<br>Firefox for Android28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android14<br>Opera Android – Full support<br>Opera Android14 (Release date: ⁨2013-05-21⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet1.5<br>Samsung Internet – Full support<br>Samsung Internet1.5 (Release date: ⁨2013-09-25⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| `flex_context.baseline` | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox45<br>Firefox – Full support<br>Firefox45 (Release date: ⁨2016-03-08⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android45<br>Firefox for Android – Full support<br>Firefox for Android45 (Release date: ⁨2016-03-08⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet7<br>Samsung Internet – Full support<br>Samsung Internet7 (Release date: ⁨2018-03-16⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| `first baseline` | Chrome – Full support<br>Chrome59<br>Chrome – Full support<br>Chrome59 (Release date: ⁨2017-06-05⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera46<br>Opera – Full support<br>Opera46 (Release date: ⁨2017-06-22⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android59<br>Chrome Android – Full support<br>Chrome Android59 (Release date: ⁨2017-06-06⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet7<br>Samsung Internet – Full support<br>Samsung Internet7 (Release date: ⁨2018-03-16⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android59<br>WebView Android – Full support<br>WebView Android59 (Release date: ⁨2017-06-06⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| `last baseline` | Chrome – No support<br>ChromeNo<br> <br>footnote<br>Chrome – No support<br>Chrome<br>footnote<br>footnoteSee [⁨bug 41344054⁩](https://crbug.com/41344054) | Edge – No support<br>EdgeNo<br> <br>footnote<br>Edge – No support<br>Edge<br>footnote<br>footnoteSee [⁨bug 41344054⁩](https://crbug.com/41344054) | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – No support<br>OperaNo<br> <br>Opera – No support<br>Opera<br>footnoteNo support | Safari – Partial support<br>Safari11<br>Safari – Partial support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnotePartial supportfootnoteThis value is recognized, but has no effect. See [bug 235005](https://webkit.org/b/235005). | Chrome Android – No support<br>Chrome AndroidNo<br> <br>footnote<br>Chrome Android – No support<br>Chrome Android<br>footnote<br>footnoteSee [⁨bug 41344054⁩](https://crbug.com/41344054) | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>Opera Android – No support<br>Opera Android<br>footnoteNo support | Safari on iOS – Partial support<br>Safari on iOS11<br>Safari on iOS – Partial support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnotePartial supportfootnoteThis value is recognized, but has no effect. See [bug 235005](https://webkit.org/b/235005). | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – Partial support<br>WebView on iOS11<br>WebView on iOS – Partial support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnotePartial supportfootnoteThis value is recognized, but has no effect. See [bug 235005](https://webkit.org/b/235005). |
| `safe` and `unsafe` | Chrome – Full support<br>Chrome115<br>footnote<br>Chrome – Full support<br>Chrome115 (Release date: ⁨2023-07-18⁩)<br> <br>footnote<br>footnoteBefore version 115, this value is recognized, but has no effect. | Edge – Full support<br>Edge115<br>footnote<br>Edge – Full support<br>Edge115 (Release date: ⁨2023-07-21⁩)<br> <br>footnote<br>footnoteBefore version 115, this value is recognized, but has no effect. | Firefox – Full support<br>Firefox63<br>Firefox – Full support<br>Firefox63 (Release date: ⁨2018-10-23⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera101<br>footnote<br>Opera – Full support<br>Opera101 (Release date: ⁨2023-07-26⁩)<br> <br>footnote<br>footnoteBefore version 101, this value is recognized, but has no effect. | Safari – Full support<br>Safari17.6<br>Safari – Full support<br>Safari17.6 (Release date: ⁨2024-07-29⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android115<br>footnote<br>Chrome Android – Full support<br>Chrome Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnote<br>footnoteBefore version 115, this value is recognized, but has no effect. | Firefox for Android – Full support<br>Firefox for Android63<br>Firefox for Android – Full support<br>Firefox for Android63 (Release date: ⁨2018-10-23⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android77<br>footnote<br>Opera Android – Full support<br>Opera Android77 (Release date: ⁨2023-08-31⁩)<br> <br>footnote<br>footnoteBefore version 77, this value is recognized, but has no effect. | Safari on iOS – Full support<br>Safari on iOS17.6<br>Safari on iOS – Full support<br>Safari on iOS17.6 (Release date: ⁨2024-07-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>footnote<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnote<br>footnoteBefore version 23.0, this value is recognized, but has no effect. | WebView Android – Full support<br>WebView Android115<br>footnote<br>WebView Android – Full support<br>WebView Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnote<br>footnoteBefore version 115, this value is recognized, but has no effect. | WebView on iOS – Full support<br>WebView on iOS17.6<br>WebView on iOS – Full support<br>WebView on iOS17.6 (Release date: ⁨2024-07-29⁩)<br> <br>footnoteFull support |
| `flex_context.space-evenly` | Chrome – Full support<br>Chrome60<br>Chrome – Full support<br>Chrome60 (Release date: ⁨2017-07-25⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera47<br>Opera – Full support<br>Opera47 (Release date: ⁨2017-08-09⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android60<br>Chrome Android – Full support<br>Chrome Android60 (Release date: ⁨2017-08-01⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android44<br>Opera Android – Full support<br>Opera Android44 (Release date: ⁨2017-12-11⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet8<br>Samsung Internet – Full support<br>Samsung Internet8 (Release date: ⁨2018-07-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android60<br>WebView Android – Full support<br>WebView Android60 (Release date: ⁨2017-08-01⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| `start` and `end` | Chrome – Full support<br>Chrome93<br>Chrome – Full support<br>Chrome93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge93<br>Edge – Full support<br>Edge93 (Release date: ⁨2021-09-02⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox45<br>Firefox – Full support<br>Firefox45 (Release date: ⁨2016-03-08⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera79<br>footnote<br>Opera – Full support<br>Opera79 (Release date: ⁨2021-09-14⁩)<br> <br>footnote<br>footnoteBefore version 79, this value is recognized, but has no effect. | Safari – Full support<br>Safari15.6<br>Safari – Full support<br>Safari15.6 (Release date: ⁨2022-07-20⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android93<br>Chrome Android – Full support<br>Chrome Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android45<br>Firefox for Android – Full support<br>Firefox for Android45 (Release date: ⁨2016-03-08⁩)<br> <br>footnoteFull support | Opera Android – No support<br>Opera AndroidNo<br> <br>footnote<br>Opera Android – No support<br>Opera Android<br>footnote<br>footnoteThis value is recognized, but has no effect. | Safari on iOS – Full support<br>Safari on iOS15.6<br>Safari on iOS – Full support<br>Safari on iOS15.6 (Release date: ⁨2022-07-20⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet17<br>Samsung Internet – Full support<br>Samsung Internet17 (Release date: ⁨2022-05-04⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android93<br>WebView Android – Full support<br>WebView Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS15.6<br>WebView on iOS – Full support<br>WebView on iOS15.6 (Release date: ⁨2022-07-20⁩)<br> <br>footnoteFull support |
| `flex_context.stretch` | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android57<br>Chrome Android – Full support<br>Chrome Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet7<br>Samsung Internet – Full support<br>Samsung Internet7 (Release date: ⁨2018-03-16⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |
| Supported in Grid Layout | Chrome – Full support<br>Chrome57<br>Chrome – Full support<br>Chrome57 (Release date: ⁨2017-03-09⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge16<br>Edge – Full support<br>Edge16 (Release date: ⁨2017-10-17⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox52<br>Firefox – Full support<br>Firefox52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera44<br>Opera – Full support<br>Opera44 (Release date: ⁨2017-03-21⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari10.1<br>Safari – Full support<br>Safari10.1 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android52<br>Chrome Android – Full support<br>Chrome Android52 (Release date: ⁨2016-07-27⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android52<br>Firefox for Android – Full support<br>Firefox for Android52 (Release date: ⁨2017-03-07⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android43<br>Opera Android – Full support<br>Opera Android43 (Release date: ⁨2017-09-27⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS10.3<br>Safari on iOS – Full support<br>Safari on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet6.2<br>Samsung Internet – Full support<br>Samsung Internet6.2 (Release date: ⁨2017-10-26⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android57<br>WebView Android – Full support<br>WebView Android57 (Release date: ⁨2017-03-16⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS10.3<br>WebView on iOS – Full support<br>WebView on iOS10.3 (Release date: ⁨2017-03-27⁩)<br> <br>footnoteFull support |
| Supported in Multi-column Layout | Chrome – Full support<br>Chrome123<br>Chrome – Full support<br>Chrome123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge123<br>Edge – Full support<br>Edge123 (Release date: ⁨2024-03-22⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera109<br>Opera – Full support<br>Opera109 (Release date: ⁨2024-03-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari17.4<br>Safari – Full support<br>Safari17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android123<br>Chrome Android – Full support<br>Chrome Android123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android82<br>Opera Android – Full support<br>Opera Android82 (Release date: ⁨2024-05-02⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS17.4<br>Safari on iOS – Full support<br>Safari on iOS17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet27<br>Samsung Internet – Full support<br>Samsung Internet27 (Release date: ⁨2024-11-06⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android123<br>WebView Android – Full support<br>WebView Android123 (Release date: ⁨2024-03-19⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS17.4<br>WebView on iOS – Full support<br>WebView on iOS17.4 (Release date: ⁨2024-03-05⁩)<br> <br>footnoteFull support |
| `normal` | Chrome – Full support<br>Chrome29<br>Chrome – Full support<br>Chrome29 (Release date: ⁨2013-08-20⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge12<br>Edge – Full support<br>Edge12 (Release date: ⁨2015-07-29⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox28<br>Firefox – Full support<br>Firefox28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera16<br>Opera – Full support<br>Opera16 (Release date: ⁨2013-08-27⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari9<br>Safari – Full support<br>Safari9 (Release date: ⁨2015-09-30⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android29<br>Chrome Android – Full support<br>Chrome Android29 (Release date: ⁨2013-08-21⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android28<br>Firefox for Android – Full support<br>Firefox for Android28 (Release date: ⁨2014-03-18⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android16<br>Opera Android – Full support<br>Opera Android16 (Release date: ⁨2013-09-18⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS9<br>Safari on iOS – Full support<br>Safari on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet2<br>Samsung Internet – Full support<br>Samsung Internet2 (Release date: ⁨2014-10-17⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android4.4<br>WebView Android – Full support<br>WebView Android4.4 (Release date: ⁨2013-12-09⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS9<br>WebView on iOS – Full support<br>WebView on iOS9 (Release date: ⁨2015-09-16⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

No supportNo support

See implementation notes.

Requires a vendor prefix or different name for use.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content\#see_also)

- [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [Aligning items in a flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container)
- [Box alignment in grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_grid_layout)
- [CSS box alignment](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment)
- [Block and inline layout in normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_and_inline_layout_in_normal_flow)
- [Block-level content](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)
- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Sep 21, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/align-content/index.md?plain=1 "Folder: ⁨en-us/web/css/align-content⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Falign-content&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Falign-content%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Falign-content%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Falign-content%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0ea88f719ad95045993f8a54d5bbaee857617380%0A*+Document+last+modified%3A+2025-09-21T14%3A46%3A57.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")