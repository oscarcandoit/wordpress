---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition
scraped_at: 2025-10-20T02:58:19.621Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

# animation-composition


Baseline

2023


Newly available

Since ⁨July 2023⁩, this feature works across the latest devices and browser versions. This feature might not work in older devices or browsers.


- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-composition&level=low)

The **`animation-composition`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the [composite operation](https://developer.mozilla.org/en-US/docs/Glossary/Composite_operation) to use when multiple animations affect the same property simultaneously.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#syntax)

cssCopy

```
/* Single animation */
animation-composition: replace;
animation-composition: add;
animation-composition: accumulate;

/* Multiple animations */
animation-composition: replace, add;
animation-composition: add, accumulate;
animation-composition: replace, add, accumulate;

/* Global values */
animation-composition: inherit;
animation-composition: initial;
animation-composition: revert;
animation-composition: revert-layer;
animation-composition: unset;

```

**Note:**
When you specify multiple comma-separated values on an `animation-*` property, they will be applied to the animations in the order in which the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) s appear. If the number of animations and compositions differ, the values listed in the `animation-composition` property will cycle from the first to the last `animation-name`, looping until all the animations have an assigned `animation-composition` value. For more information, see [Setting multiple animation property values](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations#setting_multiple_animation_property_values).

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#values)

[`replace`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#replace)

The effect value overrides the underlying value of the property. This is the default value.

[`add`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#add)

The effect value builds on the underlying value of the property. This operation produces an additive effect. For animation types where the addition operation is not commutative, the order of the operands is the underlying value followed by the effect value.

[`accumulate`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition#accumulate)

The effect and underlying values are combined. For animation types where the addition operation is not commutative, the order of the operands is the underlying value followed by the effect value.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#description)

Each property that is targeted by the [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) at-rule is associated with an effect stack. The value of the effect stack is calculated by combining the _underlying value_ of a property in a CSS style rule with the _effect value_ of that property in the keyframe. The `animation-composition` property helps to specify how to combine the underlying value with the effect value.

For example, in the CSS below, `blur(5px)` is the underlying value, and `blur(10px)` is the effect value. The `animation-composition` property specifies the operation to perform to produce the final effect value after compositing the effect of the underlying value and the effect value.

cssCopy

```
.icon:hover {
  filter: blur(5px);
  animation: 3s infinite pulse;
  animation-composition: add;
}

@keyframes pulse {
  0% {
    filter: blur(10px);
  }
  100% {
    filter: blur(20px);
  }
}

```

Consider different values for the `animation-composition` property in the above example. The final effect value in each of those cases will be calculated as explained below:

- With `replace`, `blur(10px)` will replace `blur(5px)` in the `0%` keyframe. This is the default behavior of the property.
- With `add`, the composite effect value in the `0%` keyframe will be `blur(5px) blur(10px)`.
- With `accumulate`, the composite effect value in `0%` keyframe will be `blur(15px)`.

**Note:**
A composite operation can also be specified in a keyframe. In that case, the specified composite operation is used for each property first within that keyframe and then on each property in the next keyframe.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `replace` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#formal_syntax)

```
animation-composition =
  <single-animation-composition> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma")

<single-animation-composition> =
  replace      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  add          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  accumulate

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#examples)

### [Understanding the animation-composition values](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#understanding_the_animation-composition_values)

The example below shows the effect of different `animation-composition` values side-by-side.

#### HTML

htmlCopyPlay

```
<div class="container">
  replace
  <div id="replace" class="target"></div>
</div>
<div class="container">
  add
  <div id="add" class="target"></div>
</div>
<div class="container">
  accumulate
  <div id="accumulate" class="target"></div>
</div>

```

#### CSS

Here the underlying value is `translateX(50px) rotate(45deg)`.

cssCopyPlay

```
.container {
  width: 230px;
  height: 200px;
  background: cyan;
  display: inline-block;
  text-align: center;
}

.target {
  width: 20px;
  height: 50px;
  background: green;
  border-radius: 10px;
  margin: 20px 0;
}

```

cssCopyPlay

```
@keyframes slide {
  20%,
  40% {
    transform: translateX(100px);
    background: yellow;
  }
  80%,
  100% {
    transform: translateX(150px);
    background: orange;
  }
}

.target {
  transform: translateX(30px) rotate(45deg);
  animation: slide 5s linear infinite;
}
.target:hover {
  animation-play-state: paused;
}
#replace {
  animation-composition: replace;
}
#add {
  animation-composition: add;
}
#accumulate {
  animation-composition: accumulate;
}

```

#### Result

Play

replace


add


accumulate


- With `replace`, the final effect value for the `transform` property in the `20%, 40%` keyframe is `translateX(100px)` (completely replacing the underlying value `translateX(30px) rotate(45deg)`). In this case, the element rotates from 45deg to 0deg as it animates from the default value set on the element itself to the non-rotated value set at the 20% mark. This is the default behavior.
- With `add`, the final effect value for the `transform` property in the `20%, 40%` keyframe is `translateX(30px) rotate(45deg) translateX(100px)`. So the element is first moved 100px to the right, rotated 45deg around the origin, then moved to the right by 30px.
- With `accumulate`, the final effect value in the `20%, 40%` keyframe is `translateX(130px) rotate(45deg)`. This means that the two X-axis translation values of `30px` and `100px` are combined or "accumulated".

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#specifications)

| Specification |
| --- |
| [CSS Animations Level 2\<br>\# animation-composition](https://drafts.csswg.org/css-animations-2/#animation-composition) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/animation-composition.json "File: ⁨css/properties/animation-composition.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `animation-composition` | Chrome – Full support<br>Chrome112<br>Chrome – Full support<br>Chrome112 (Release date: ⁨2023-04-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge112<br>Edge – Full support<br>Edge112 (Release date: ⁨2023-04-06⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox115<br>Firefox – Full support<br>Firefox115 (Release date: ⁨2023-07-04⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera98<br>Opera – Full support<br>Opera98 (Release date: ⁨2023-04-20⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari16<br>Safari – Full support<br>Safari16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android112<br>Chrome Android – Full support<br>Chrome Android112 (Release date: ⁨2023-04-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android115<br>Firefox for Android – Full support<br>Firefox for Android115 (Release date: ⁨2023-07-04⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android75<br>Opera Android – Full support<br>Opera Android75 (Release date: ⁨2023-05-17⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS16<br>Safari on iOS – Full support<br>Safari on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android112<br>WebView Android – Full support<br>WebView Android112 (Release date: ⁨2023-04-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS16<br>WebView on iOS – Full support<br>WebView on iOS16 (Release date: ⁨2022-09-12⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition\#see_also)

- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)
- [Composite property of KeyFrameEffect](https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/composite)
- Other related animation properties: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/animation-composition/index.md?plain=1 "Folder: ⁨en-us/web/css/animation-composition⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-composition&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fanimation-composition%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-composition%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fanimation-composition%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")