---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/progress
scraped_at: 2025-10-20T03:07:14.879Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#search)

# progress()

**Experimental:** **This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**

Check the [Browser compatibility table](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#browser_compatibility) carefully before using this in production.

The **`progress()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) returns a [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) value representing the position of one value (the progress value) relative to two other values (the progress start and end values).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#syntax)

cssCopy

```
/* With fixed progress value */
progress(300, 0, 1000)
progress(50px, 0px, 100px)
progress(50%, 30%, 80%)

/* With custom property */
progress(var(--container-width), 320, 1200)

/* Inside math function */
calc((progress(var(--container-width), 20%, 80%) / 2) + 0.5)

/* Inside non-math function */
rgb(
  calc(255 * progress(var(--container-width), 320px, 1200px))
  calc(255 * progress(var(--container-width), 320px, 1200px)) 255 / 0.5
);

/* Math function inside progress() */
progress(calc(20 + 30), 0, 100)

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#parameters)

The `progress()` function takes three comma-separated [`<calc-sum>`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-sum) expressions as parameters:

```
progress(<calc-sum>, <calc-sum>, <calc-sum>)

```

Respectively, these are:

[Progress](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#progress)

The value to calculate the position of relative to the other two values.

[Progress start](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#progress_start)

The lower progress bound.

[Progress end](https://developer.mozilla.org/en-US/docs/Web/CSS/progress#progress_end)

The upper progress bound.

### [Return value](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#return_value)

A [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) representing the position of the progress value relative to the other two values. This is calculated as follows:

```
(progress - progress start) / (progress end - progress start)

```

If the progress value is in between the progress start and progress end values, the return value will between `0` and `1`, representing a percentage. If the progress value is smaller than the progress start value, or larger than the progress end value, the function is still valid, but the return value is clamped to `0` or `1`, respectively.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#description)

The CSS `progress()` function provides a way to calculate a progress ratio, which is useful for creating use cases such as progress bar animations, or boxes that fade in as they become wider to reveal their contents.

The simplest possible use might look like this:

cssCopy

```
opacity: progress(5, 0, 10);

```

In this case, the computed value of [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity) would be `0.5`, as 5 is mid-way between `0` and `10`.

### [Permitted unit types](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#permitted_unit_types)

The parameters of a `progress()` function can be mathematical expressions or simple values. The values (or expression results) can be any [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number), [`<dimension>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension), or [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) value. They can have different units, but they must all be of the same type, or else the function is invalid.

The example we saw previously is valid — all of its parameters are unitless `<number>` values:

cssCopy

```
progress(5, 0, 10)

```

The next example is also valid — all of its parameters have [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) units. Behind the scenes, the computed values are used for the calculation. Provided the [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) is `16px` at the point of calculation, `3em` will resolve to `48px`, which is `48%` of the way between `0px` and `100px`, so the return value will be `0.48`.

cssCopy

```
progress(3em, 0px, 100px)

```

The final couple of examples in this section is not valid, however. The types do not match, so the resulting calculations do not make sense.

cssCopy

```
progress(3s, 0px, 100px)
progress(3em, 0, 100)

```

### [Creating unitless values](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#creating_unitless_values)

The `progress()` function outputs unitless values, therefore it can be used for the purpose of removing units from values in the same manner as the [`tan(atan2())` hack](https://dev.to/janeori/css-type-casting-to-numeric-tanatan2-scalars-582j). Note however that, due to the updates in behavior around [CSS typed arithmetic](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Using_CSS_typed_arithmetic), this can also be achieved via simple division.

### [Combining `progress()` with other functions and custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#combining_progress_with_other_functions_and_custom_properties)

Because `progress()` only ever returns a unitless value between `0` and `1`, it is common to combine it with another math function such as [`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc) to output the value and units you want. You can also use [CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) inside `progress()` functions — this makes sense, as you'll often want to set the same values in multiple places, and/or base them on custom properties set via JavaScript.

The following example calculates what percentage the viewport width is between a minimum width of `320px` and a maximum width of `1200px`. The `calc()` function is used to multiply the `progress()` return value by `600px` to convert it into a pixel value that will half of the viewport width's progress value between `320px` and `1200px`.

cssCopy

```
width: calc(progress(100vw, 320px, 1200px) * 600px);

```

For example, if the viewport width is `700px`, the progress value will be calculated as `((700 - 320) / (1200 - 320))` = `0.431818`. The width will then be calculated as `0.431818 * 600px`, which equals `259.1px`.

The next example is an update of the previous one, in which we've used custom properties for the progress, progress start, and progress end values.

cssCopy

```
width: calc(
  progress(
      var(--container-width),
      var(--custom-min-width),
      var(--custom-max-width)
    ) *
    var(--custom-max-width)
);

```

It is possible to use `progress()` functions to calculate individual values inside other functions and component values inside shorthand property values, provided your functions return valid types for those values.

This can result in some complex expressions. For example, here we are calculating the first two channels of an [`rgb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb) color proportionate to the same width proportion as before:

cssCopy

```
background-color: rgb(
  calc(
      255 *
        progress(
          var(--container-width),
          var(--custom-min-width),
          var(--custom-max-width)
        )
    )
    calc(
      255 *
        progress(
          var(--container-width),
          var(--custom-min-width),
          var(--custom-max-width)
        )
    )
    255 / 0.5
);

```

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#formal_syntax)

```
<progress()> =
  progress( <calc-sum> , <calc-sum> , <calc-sum> )

<calc-sum> =
  <calc-product>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '+' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") '-' [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <calc-product>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<calc-product> =
  <calc-value>  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") '*' [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present") / [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <calc-value>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times")

<calc-value> =
  [<number>](https://developer.mozilla.org/en-US/docs/Web/CSS/number)         [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<dimension>](https://developer.mozilla.org/en-US/docs/Web/CSS/dimension)      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)     [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <calc-keyword>   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  ( <calc-sum> )

<calc-keyword> =
  e           [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  pi          [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  infinity    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  -infinity   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  NaN

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#examples)

### [Basic `progress()` usage](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#basic_progress_usage)

In this example, we'll show basic usage of the `progress()` function to set a progress bar `width` as a percentage equal to the progress ratio of its parent's `width` between its `min-width` and `max-width`.

#### HTML

Our HTML features a [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/section) element representing our content, and a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/div) element representing the width progress bar.

htmlCopy

```
<section>
  <div class="progress"></div>
</section>

```

#### CSS

In our CSS, we first set some custom properties on our `<section>` element to represent its `min-width`, `max-width`, and `width`. We then set those properties to the appropriate custom property values, then give our `<section>` a solid [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) so it is visible.

cssCopy

```
section {
  --custom-min-width: 300px;
  --custom-max-width: 700px;
  --custom-width: 600px;

  min-width: var(--custom-min-width);
  max-width: var(--custom-max-width);
  width: var(--custom-width);

  background-color: cyan;
}

```

Now onto our `<div>` — we first give it a `height` and a dark `background-color` so it stands out against our `<section>` element. We then calculate its `width` by using a `progress()` function to calculate the progress ratio of the width between the minimum and maximum width, then using a `calc()` function to multiply the `progress()` return value by `100%` to return a percentage.

cssCopy

```
.progress {
  height: 4px;
  background-color: red;

  width: calc(
    progress(
        var(--custom-width),
        var(--custom-min-width),
        var(--custom-max-width)
      ) *
      100%
  );
}

```

#### Result

This demo will render as follows:

The width of the `<div>` is `75%` of the `<section>` width, as the `min-width` is `400px`, the `max-width` is `700px`, and the `width` is `600px`, which is `75%` of the distance between the previous two values.

### [Resize effects on a container](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#resize_effects_on_a_container)

This example shows off some more involved uses of the `progress()` function, resulting in some fun effects as the browser window is resized.

This example works much better when rendered full-size in a desktop browser tab. Therefore, we have not rendered it in an embedded live sample in this page. Instead, you can find it running live at [CSS `progress()` function demo](https://mdn.github.io/dom-examples/css-progress/) (also see the [source code](https://github.com/mdn/dom-examples/tree/main/css-progress)).

Open the live example in a separate tab, and try increasing and decreasing the browser window width to see the effect. Keep this open so you can refer back to it as you read the explanation below.

#### HTML

Our HTML features an [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/article) element that contains the rest of our content, and two [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/section) elements — one to hang a background image off, and the other one to contain our content. The `<section class="content">` also contains a `<div class="progress">` representing a width progress bar, the same as the one in our previous demo. We have omitted the rest of the content for brevity.

htmlCopy

```
<article>
  <section class="background"></section>
  <section class="content">
    <div class="progress"></div>
    <!-- Content here -->
  </section>
</article>

```

#### JavaScript

In our script, we first grab a reference to our `<article>` element. We then define a function called `setContainerWidth()`, which grabs the `<article>`'s client width via [`Element.getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect), and sets a custom property on it called `--container-width`, which is equal to the client width rounded down, with `px` appended to it.

We then set a [`resize`](https://developer.mozilla.org/en-US/docs/Web/API/Window/resize_event "resize") event listener on the `Window` object, which runs `setContainerWidth()` when the browser window is resized. We also run it once to set the `--container-width` custom property on the `<article>` element once the page loads.

jsCopy

```
const articleElem = document.querySelector("article");

function setContainerWidth() {
  const clientWidth = articleElem.getBoundingClientRect().width;
  articleElem.style.setProperty(
    "--container-width",
    `${Math.floor(clientWidth)}px`,
  );
}

window.addEventListener("resize", setContainerWidth);

setContainerWidth();

```

With this set up, we can now set some property values based on the `--container-width`, so that parts of our design will dynamically change as the window resizes.

#### CSS

The following section explains just the CSS relevant to how we've used the `progress()` function in the demo. For the full CSS, see the [CSS source](https://github.com/mdn/dom-examples/blob/main/css-progress/index.css).

We first center the `<article>` inside the `<body>` using [flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout), then set some custom properties on it to represent the `min-width` and `max-width` values we will use elsewhere. We then target the `<article>` element, giving it [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width) and [`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width) values equal to the custom properties we set earlier. We set its [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) to `relative` so we can position its content relative to it, then give it a percentage [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), fixed [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), and [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border).

cssCopy

```
body {
  height: inherit;
  display: flex;
  justify-content: center;
  align-items: center;
  --custom-min-width: 320px;
  --custom-max-width: 1200px;
}

article {
  min-width: var(--custom-min-width);
  max-width: var(--custom-max-width);
  position: relative;
  width: 70%;
  height: 600px;
  border: 3px solid black;
}

```

Now on to our `progress` `<div>`. We set its `width` equal to a percentage based on the progress ratio of the `--container-width` custom property set on the `<article>` element via JavaScript between its `min-width` and `max-width` (we use the same custom properties here for the second and third `progress()` parameters as we did for the `<article>` `min-width` and `max-width`).

We also give it a `height` and [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color), then absolutely position it at the top and left corner of the `<article>`.

cssCopy

```
.progress {
  width: calc(
    progress(
        var(--container-width),
        var(--custom-min-width),
        var(--custom-max-width)
      ) *
      100%
  );
  height: 4px;
  background-color: red;
  position: absolute;
  top: 0;
  left: 0;
}

```

Next, we'll look at our `background` `<section>`. We absolutely position it relative to our `<article>`, setting [`inset: 0`](https://developer.mozilla.org/en-US/docs/Web/CSS/inset) on it so that it adopts the same size and sits over the top of it. We then set a rather wide [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) on it, and position the background image by giving the [`background-position-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x) property the same value as we gave the progress bar's `width` property. This has the effect that, when you increase the browser window width, the background image is moved over to the left, creating a nice image scrolling effect.

cssCopy

```
.background {
  position: absolute;
  inset: 0;
  background-image: url("https://mdn.github.io/shared-assets/images/examples/wide-background.jpg");
  background-position-x: calc(
    progress(
        var(--container-width),
        var(--custom-min-width),
        var(--custom-max-width)
      ) *
      100%
  );
}

```

We position the `content` `<section>` absolutely so it sits over the top of the `background` `<section>`, then give it some [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding). We then vary two property values as the browser window is resized, using the same progress ratio as before:

- We vary the R and G components of the `background-color`, multiplying the progress ratio by 255 in each case to get a proportionate channel value. As the window gets wider, the background color gets less blue and more white, making the scene look as it is going from night to day (the color value has an opacity of `0.5`, so it acts like a tint for the underlying image).
- We vary the [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity) so that the content fades in a bit when the window gets wider.

cssCopy

```
.content {
  position: absolute;
  inset: 0;
  padding: 20px;
  background-color: rgb(
    calc(
        255 *
          progress(
            var(--container-width),
            var(--custom-min-width),
            var(--custom-max-width)
          )
      )
      calc(
        255 *
          progress(
            var(--container-width),
            var(--custom-min-width),
            var(--custom-max-width)
          )
      )
      255 / 0.5
  );
  opacity: calc(
    (
        progress(
            var(--container-width),
            var(--custom-min-width),
            var(--custom-max-width)
          ) /
          2
      ) +
      0.5
  );
}

```

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#specifications)

| Specification |
| --- |
| [CSS Values and Units Module Level 5\<br>\# progress](https://drafts.csswg.org/css-values-5/#progress) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/progress\#see_also)

- [CSS values and units module](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units)
- [Container style queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_size_and_style_queries#container_style_queries)
- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries)
- [Feature queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_conditional_rules/Using_feature_queries)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/progress/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/progress/index.md?plain=1 "Folder: ⁨en-us/web/css/progress⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fprogress&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fprogress%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fprogress%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fprogress%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F7615562a3689a3e23a2b6b623597f4391740a53e%0A*+Document+last+modified%3A+2025-10-13T01%3A34%3A32.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")