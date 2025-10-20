---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline
scraped_at: 2025-10-20T02:58:21.675Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-timeline "Take survey (Opens in a new tab)")

# animation-timeline

Limited availability

This feature is not Baseline because it does not work in some of the most widely-used browsers.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-timeline&level=not)

The **`animation-timeline`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the timeline that is used to control the progress of a CSS animation.

The following types of timelines can be set via `animation-timeline`:

- The default document timeline, which is progressed through by the passing of time since the document was first loaded in the browser. This is the timeline traditionally associated with CSS animations and is selected with a value of `auto`, or by not specifying an `animation-timeline` value at all.
- A _scroll progress timeline_, which is progressed through by scrolling a scrollable element ( _scroller_) between top and bottom (or left and right). The position in the scroll range is converted into a percentage of progress — 0% at the start and 100% at the end. The element that provides the scroll progress timeline can be specified in two ways:

  - A _named scroll progress timeline_ is one where the scroller providing the scroll progress timeline is explicitly named using the [`scroll-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name) property (or the [`scroll-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline) shorthand property). The name is then linked to the element to animate by specifying it as the value of that element's `animation-timeline` property.
  - An _anonymous scroll progress timeline_ is one where the element to animate is given a [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/scroll) function as an `animation-timeline` value, which selects the scroller providing the scroll progress timeline and the scroll axis to be used based on the arguments you pass to it.
- A _view progress timeline_, which is progressed through based on the change in visibility of an element (known as the _subject_) inside a scroller. The visibility of the subject inside the scroller is tracked — by default, the timeline is at 0% when the subject is first visible at one edge of the scroller, and 100% when it reaches the opposite edge. Unlike with scroll progress timelines, you can't specify the scroller — the subject's visibility is always tracked within its nearest ancestor scroller. The subject that provides the view progress timeline can be specified in two ways:

  - A _named view progress timeline_ is one where the subject is explicitly named using the [`view-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name) property (or the [`view-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline) shorthand property). The name is then linked to the element to animate by specifying it as the value of that element's `animation-timeline` property. This is a key point — with named view progress timelines, the element to animate does not have to be the same as the subject.
  - An _anonymous view progress timeline_ is one where the subject is given a [`view()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/view) function as an `animation-timeline` value, causing it to be animated based on its position inside its nearest parent scroller.

**Note:** `animation-timeline` is included in the [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) shorthand as a reset-only value. This means that including `animation` resets a previously-declared `animation-timeline` value to `auto`, but a specific value cannot be set via `animation`. When creating [CSS scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations), you need to declare `animation-timeline` after declaring any `animation` shorthand for it to take effect.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#syntax)

cssCopy

```
/* Keyword */
animation-timeline: none;
animation-timeline: auto;

/* Single animation named timeline */
animation-timeline: --timeline_name;

/* Single animation anonymous scroll progress timeline */
animation-timeline: scroll();
animation-timeline: scroll(scroller axis);

/* Single animation anonymous view progress timeline */
animation-timeline: view();
animation-timeline: view(axis inset);

/* Multiple animations */
animation-timeline: --progress-bar-timeline, --carousel-timeline;
animation-timeline: none, --sliding-timeline;

/* Global values */
animation-timeline: inherit;
animation-timeline: initial;
animation-timeline: revert;
animation-timeline: revert-layer;
animation-timeline: unset;

```

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#values)

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#none)

The animation is not associated with a timeline.

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#auto)

The animation's timeline is the document's default [DocumentTimeline](https://developer.mozilla.org/en-US/docs/Web/API/DocumentTimeline).

[`scroll()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#scroll)

An anonymous scroll progress timeline is provided by some ancestor scroller of the current element. The function parameters allow you to select the scroller, and the scrolling axis the timeline will be measured along.

See [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/scroll) for more information.

[`view()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#view)

An anonymous view progress timeline is provided by the subject that `animation-timeline: view();` is set on. The function parameters allow you to select the scrollbar axis along which timeline progress will be tracked and an inset that adjusts the position of the box in which the subject is deemed to be visible.

See [`view()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/view) for more information.

[`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline#dashed-ident)

A [`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident) identifying a named timeline previously declared with the [`scroll-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name) or [`view-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name) property (or the [`scroll-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline) or [`view-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline) shorthand property).

**Note:**
If two or more timelines share the same name, the last declared within the cascade will be used. Also, if no timeline is found that matches the given name, the animation is not associated with a timeline.

**Note:**
The [`<dashed-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident) values must start with `--`. This helps avoid name clashes with standard CSS keywords.

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | all elements |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | a list, each item either a case-sensitive CSS identifier or the keywords `none`, `auto` |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#formal_syntax)

```
animation-timeline =
  <single-animation-timeline> [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma")

<single-animation-timeline> =
  auto             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none             [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<dashed-ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident)   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <scroll()>       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  <view()>

<scroll()> =
  scroll(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <scroller>  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  <axis>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<view()> =
  view(  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  <axis>  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  [<'view-timeline-inset'>](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-inset)  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

<scroller> =
  root      [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  nearest   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  self

<axis> =
  block    [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  inline   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  x        [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  y

<view-timeline-inset> =
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  auto  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  <length-percentage>  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [{1,2}](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#curly_braces "Curly braces: encloses two integers defining the minimal and maximal numbers of occurrences of the entity, or a single integer defining the exact number required")  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component") [#](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#hash_mark "Hash mark: the entity is repeated one or several times, each occurrence separated by a comma")

<length-percentage> =
  [<length>](https://developer.mozilla.org/en-US/docs/Web/CSS/length)       [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#examples)

### [Setting a named scroll progress timeline](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#setting_a_named_scroll_progress_timeline)

A scroll progress timeline named `--square-timeline` is defined using the `scroll-timeline-name` property on an element with an `id` of `container`.
This is then set as the timeline for the animation on the `#square` element using `animation-timeline: --square-timeline`.

#### HTML

The HTML for the example is shown below.

htmlCopyPlay

```
<div id="container">
  <div id="square"></div>
  <div id="stretcher"></div>
</div>

```

#### CSS

The CSS for the container sets it as the source of a scroll progress timeline named `--square-timeline` using the `scroll-timeline-name` property (we could explicitly set which scrollbar axis to use with [`scroll-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-axis), but there is only a block direction scrollbar here, and it will be used by default).

The height of the container is set to 300px and we also set the container to create a vertical scrollbar if it overflows (below we will use CSS on the "stretcher" element to ensure that it does overflow).

cssCopyPlay

```
#container {
  height: 300px;
  overflow-y: scroll;
  scroll-timeline-name: --square-timeline;
  position: relative;
}

```

The CSS below defines a square that rotates in alternate directions according to the timeline provided by the `animation-timeline` property, which is set to the `--square-timeline` timeline named above.

cssCopyPlay

```
#square {
  background-color: deeppink;
  width: 100px;
  height: 100px;
  margin-top: 100px;
  animation-name: rotateAnimation;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
  animation-direction: alternate;
  animation-timeline: --square-timeline;

  position: absolute;
  bottom: 0;
}

@keyframes rotateAnimation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

```

The "stretcher" CSS sets the block height to 600px, which forces the container element to overflow and create scroll bars.
Without this element there would be no scrollbar, and hence no scroll progress timeline to associate with the animation timeline.

cssCopyPlay

```
#stretcher {
  height: 600px;
}

```

#### Result

Scroll to see the square element being animated.

Play

### [Setting an anonymous scroll progress timeline](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#setting_an_anonymous_scroll_progress_timeline)

In this example, the `#square` element is animated using an anonymous scroll progress timeline, which is applied to the element to be animated using the `scroll()` function.
The timeline in this particular example is provided by the nearest parent element that has (any) scrollbar, from the scrollbar in the block direction.

#### HTML

The HTML for the example is shown below.

htmlCopyPlay

```
<div id="container">
  <div id="square"></div>
  <div id="stretcher"></div>
</div>

```

#### CSS

The CSS below defines a square that rotates in alternate directions according to the timeline provided by the `animation-timeline` property.
In this case, the timeline is provided by `scroll(block nearest)`, which means that it will select the scrollbar in the block direction of the nearest ancestor element that has scrollbars; in this case the vertical scrollbar of the "container" element.

**Note:** `block` and `nearest` are actually the default parameter values, so we could have used just `scroll()`.

cssCopyPlay

```
#square {
  background-color: deeppink;
  width: 100px;
  height: 100px;
  margin-top: 100px;
  position: absolute;
  bottom: 0;

  animation-name: rotateAnimation;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
  animation-direction: alternate;
  animation-timeline: scroll(block nearest);
}

@keyframes rotateAnimation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

```

The CSS for the container sets its height to 300px and we also set the container to create a vertical scrollbar if it overflows.
The "stretcher" CSS sets the block height to 600px, which forces the container element to overflow.
These two together ensure that the container has a vertical scrollbar, which allows it to be used as the source of the anonymous scroll progress timeline.

cssCopyPlay

```
#container {
  height: 300px;
  overflow-y: scroll;
  position: relative;
}

#stretcher {
  height: 600px;
}

```

#### Result

Scroll to see the square element being animated.

Play

### [Setting a named view progress timeline](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#setting_a_named_view_progress_timeline)

A view progress timeline named `--subject-reveal` is defined using the `view-timeline-name` property on a subject element with a `class` of `animation`.
This is then set as the timeline for the same element using `animation-timeline: --subject-reveal;`. The result is that the subject element animates as it moves upwards through the document as it is scrolled.

#### HTML

The HTML for the example is shown below.

htmlCopyPlay

```
<div class="content">
  <h1>Content</h1>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Risus quis varius quam
    quisque id. Et ligula ullamcorper malesuada proin libero nunc consequat
    interdum varius. Elit ullamcorper dignissim cras tincidunt lobortis feugiat
    vivamus at augue.
  </p>

  <p>
    Dolor sed viverra ipsum nunc aliquet. Sed sed risus pretium quam vulputate
    dignissim. Tortor aliquam nulla facilisi cras. A erat nam at lectus urna
    duis convallis convallis. Nibh ipsum consequat nisl vel pretium lectus.
    Sagittis aliquam malesuada bibendum arcu vitae elementum. Malesuada bibendum
    arcu vitae elementum curabitur vitae nunc sed velit.
  </p>

  <div class="subject animation"></div>

  <p>
    Adipiscing enim eu turpis egestas pretium aenean pharetra magna ac. Arcu
    cursus vitae congue mauris rhoncus aenean vel. Sit amet cursus sit amet
    dictum. Augue neque gravida in fermentum et. Gravida rutrum quisque non
    tellus orci ac auctor augue mauris. Risus quis varius quam quisque id diam
    vel quam elementum. Nibh praesent tristique magna sit amet purus gravida
    quis. Duis ultricies lacus sed turpis tincidunt id aliquet. In egestas erat
    imperdiet sed euismod nisi. Eget egestas purus viverra accumsan in nisl nisi
    scelerisque. Netus et malesuada fames ac.
  </p>
</div>

```

#### CSS

The `subject` element and its containing `content` element are styled minimally, and the text content is given some basic font settings:

cssCopyPlay

```
.subject {
  width: 300px;
  height: 200px;
  margin: 0 auto;
  background-color: deeppink;
}

.content {
  width: 75%;
  max-width: 800px;
  margin: 0 auto;
}

p,
h1 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h1 {
  font-size: 3rem;
}

p {
  font-size: 1.5rem;
  line-height: 1.5;
}

```

The `<div>` with the class of `subject` is also given a class of `animation` — this is where the [`view-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name) is set to define a named view progress timeline. It is also given an `animation-timeline` name with the same value to declare that this will be the element animated as the view progress timeline is progressed.

Lastly, an animation is specified on the element that animates its opacity and scale, causing it to fade in and size up as it moves up the scroller.

cssCopyPlay

```
.animation {
  view-timeline-name: --subject-reveal;
  animation-timeline: --subject-reveal;

  animation-name: appear;
  animation-fill-mode: both;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
}

@keyframes appear {
  from {
    opacity: 0;
    transform: scaleX(0);
  }

  to {
    opacity: 1;
    transform: scaleX(1);
  }
}

```

#### Result

Scroll to see the subject element being animated.

Play

# Content

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Risus quis varius quam
quisque id. Et ligula ullamcorper malesuada proin libero nunc consequat
interdum varius. Elit ullamcorper dignissim cras tincidunt lobortis feugiat
vivamus at augue.


Dolor sed viverra ipsum nunc aliquet. Sed sed risus pretium quam vulputate
dignissim. Tortor aliquam nulla facilisi cras. A erat nam at lectus urna
duis convallis convallis. Nibh ipsum consequat nisl vel pretium lectus.
Sagittis aliquam malesuada bibendum arcu vitae elementum. Malesuada bibendum
arcu vitae elementum curabitur vitae nunc sed velit.


Adipiscing enim eu turpis egestas pretium aenean pharetra magna ac. Arcu
cursus vitae congue mauris rhoncus aenean vel. Sit amet cursus sit amet
dictum. Augue neque gravida in fermentum et. Gravida rutrum quisque non
tellus orci ac auctor augue mauris. Risus quis varius quam quisque id diam
vel quam elementum. Nibh praesent tristique magna sit amet purus gravida
quis. Duis ultricies lacus sed turpis tincidunt id aliquet. In egestas erat
imperdiet sed euismod nisi. Eget egestas purus viverra accumsan in nisl nisi
scelerisque. Netus et malesuada fames ac.


### [Setting an anonymous view progress timeline](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#setting_an_anonymous_view_progress_timeline)

An anonymous view progress timeline is set on an element with class `subject` using `animation-timeline: view()`. The result is that the `subject` element animates as it moves upwards through the document as it is scrolled.

#### HTML

The HTML for the example is shown below.

htmlCopyPlay

```
<div class="content">
  <h1>Content</h1>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Risus quis varius quam
    quisque id. Et ligula ullamcorper malesuada proin libero nunc consequat
    interdum varius. Elit ullamcorper dignissim cras tincidunt lobortis feugiat
    vivamus at augue.
  </p>

  <p>
    Dolor sed viverra ipsum nunc aliquet. Sed sed risus pretium quam vulputate
    dignissim. Tortor aliquam nulla facilisi cras. A erat nam at lectus urna
    duis convallis convallis. Nibh ipsum consequat nisl vel pretium lectus.
    Sagittis aliquam malesuada bibendum arcu vitae elementum. Malesuada bibendum
    arcu vitae elementum curabitur vitae nunc sed velit.
  </p>

  <div class="subject animation"></div>

  <p>
    Adipiscing enim eu turpis egestas pretium aenean pharetra magna ac. Arcu
    cursus vitae congue mauris rhoncus aenean vel. Sit amet cursus sit amet
    dictum. Augue neque gravida in fermentum et. Gravida rutrum quisque non
    tellus orci ac auctor augue mauris. Risus quis varius quam quisque id diam
    vel quam elementum. Nibh praesent tristique magna sit amet purus gravida
    quis. Duis ultricies lacus sed turpis tincidunt id aliquet. In egestas erat
    imperdiet sed euismod nisi. Eget egestas purus viverra accumsan in nisl nisi
    scelerisque. Netus et malesuada fames ac.
  </p>
</div>

```

#### CSS

The `subject` element and its containing `content` element are styled minimally, and the text content is given some basic font settings:

cssCopyPlay

```
.subject {
  width: 300px;
  height: 200px;
  margin: 0 auto;
  background-color: deeppink;
}

.content {
  width: 75%;
  max-width: 800px;
  margin: 0 auto;
}

p,
h1 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h1 {
  font-size: 3rem;
}

p {
  font-size: 1.5rem;
  line-height: 1.5;
}

```

The `<div>` with the class of `subject` is also given a class of `animation` — this is where `animation-timeline: view()` is set to declare that it will be animated as it progresses through the view progress timeline provided by its scrolling ancestor (in this case the document's root element).

Last, an animation is specified on the element that animates its opacity and scale, causing it to fade in and size up as it moves up the scroller.

cssCopyPlay

```
.animation {
  animation-timeline: view();

  animation-name: appear;
  animation-fill-mode: both;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
}

@keyframes appear {
  from {
    opacity: 0;
    transform: scaleX(0);
  }

  to {
    opacity: 1;
    transform: scaleX(1);
  }
}

```

#### Result

Scroll to see the subject element being animated.

Play

# Content

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Risus quis varius quam
quisque id. Et ligula ullamcorper malesuada proin libero nunc consequat
interdum varius. Elit ullamcorper dignissim cras tincidunt lobortis feugiat
vivamus at augue.


Dolor sed viverra ipsum nunc aliquet. Sed sed risus pretium quam vulputate
dignissim. Tortor aliquam nulla facilisi cras. A erat nam at lectus urna
duis convallis convallis. Nibh ipsum consequat nisl vel pretium lectus.
Sagittis aliquam malesuada bibendum arcu vitae elementum. Malesuada bibendum
arcu vitae elementum curabitur vitae nunc sed velit.


Adipiscing enim eu turpis egestas pretium aenean pharetra magna ac. Arcu
cursus vitae congue mauris rhoncus aenean vel. Sit amet cursus sit amet
dictum. Augue neque gravida in fermentum et. Gravida rutrum quisque non
tellus orci ac auctor augue mauris. Risus quis varius quam quisque id diam
vel quam elementum. Nibh praesent tristique magna sit amet purus gravida
quis. Duis ultricies lacus sed turpis tincidunt id aliquet. In egestas erat
imperdiet sed euismod nisi. Eget egestas purus viverra accumsan in nisl nisi
scelerisque. Netus et malesuada fames ac.


## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#specifications)

| Specification |
| --- |
| [CSS Animations Level 2\<br>\# animation-timeline](https://drafts.csswg.org/css-animations-2/#animation-timeline) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/properties/animation-timeline.json "File: ⁨css/properties/animation-timeline.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `animation-timeline` | Chrome – Full support<br>Chrome115<br>Chrome – Full support<br>Chrome115 (Release date: ⁨2023-07-18⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge115<br>Edge – Full support<br>Edge115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox – No support<br>Firefox110<br>disabled<br>Firefox – No support<br>Firefox110 (Release date: ⁨2023-02-14⁩)<br> <br>disabled<br>disabled⁨From version ⁨110⁩⁩⁨⁨ ⁩users⁩<br>⁨ ⁩must explicitly set the `⁨layout.css.scroll-driven-animations.enabled⁩` ⁨ ⁩<br>⁨preference⁩⁨⁨ ⁩to `⁨true⁩` ⁩⁨.⁩<br>⁨To change preferences in ⁨Firefox⁩, visit ⁨about:config⁩.⁩ | Opera – Full support<br>Opera101<br>Opera – Full support<br>Opera101 (Release date: ⁨2023-07-26⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari26<br>Safari – Full support<br>Safari26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android115<br>Chrome Android – Full support<br>Chrome Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android77<br>Opera Android – Full support<br>Opera Android77 (Release date: ⁨2023-08-31⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS26<br>Safari on iOS – Full support<br>Safari on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android115<br>WebView Android – Full support<br>WebView Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS26<br>WebView on iOS – Full support<br>WebView on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support |
| [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/scroll) | Chrome – Full support<br>Chrome115<br>Chrome – Full support<br>Chrome115 (Release date: ⁨2023-07-18⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge115<br>Edge – Full support<br>Edge115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox – No support<br>Firefox110<br>footnotedisabled<br>Firefox – No support<br>Firefox110 (Release date: ⁨2023-02-14⁩)<br> <br>footnotedisabled<br>disabled⁨From version ⁨110⁩⁩⁨⁨ ⁩users⁩<br>⁨ ⁩must explicitly set the `⁨layout.css.scroll-driven-animations.enabled⁩` ⁨ ⁩<br>⁨preference⁩⁨⁨ ⁩to `⁨true⁩` ⁩⁨.⁩<br>⁨To change preferences in ⁨Firefox⁩, visit ⁨about:config⁩.⁩<br>footnoteZero scroll range is treated as 100% but should be 0% (see [bug 1780865](https://bugzil.la/1780865)).footnoteSupports the deprecated `horizontal` and `vertical` axis values, and not the `x` and `y` values. | Opera – Full support<br>Opera101<br>Opera – Full support<br>Opera101 (Release date: ⁨2023-07-26⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari26<br>Safari – Full support<br>Safari26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android115<br>Chrome Android – Full support<br>Chrome Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android77<br>Opera Android – Full support<br>Opera Android77 (Release date: ⁨2023-08-31⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS26<br>Safari on iOS – Full support<br>Safari on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android115<br>WebView Android – Full support<br>WebView Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS26<br>WebView on iOS – Full support<br>WebView on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support |
| [`view()`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/view) | Chrome – Full support<br>Chrome115<br>Chrome – Full support<br>Chrome115 (Release date: ⁨2023-07-18⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge115<br>Edge – Full support<br>Edge115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox – No support<br>Firefox114<br>disabled<br>Firefox – No support<br>Firefox114 (Release date: ⁨2023-06-06⁩)<br> <br>disabled<br>disabled⁨From version ⁨114⁩⁩⁨⁨ ⁩users⁩<br>⁨ ⁩must explicitly set the `⁨layout.css.scroll-driven-animations.enabled⁩` ⁨ ⁩<br>⁨preference⁩⁨⁨ ⁩to `⁨true⁩` ⁩⁨.⁩<br>⁨To change preferences in ⁨Firefox⁩, visit ⁨about:config⁩.⁩ | Opera – Full support<br>Opera101<br>Opera – Full support<br>Opera101 (Release date: ⁨2023-07-26⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari26<br>Safari – Full support<br>Safari26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android115<br>Chrome Android – Full support<br>Chrome Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android77<br>Opera Android – Full support<br>Opera Android77 (Release date: ⁨2023-08-31⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS26<br>Safari on iOS – Full support<br>Safari on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet23<br>Samsung Internet – Full support<br>Samsung Internet23 (Release date: ⁨2023-10-18⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android115<br>WebView Android – Full support<br>WebView Android115 (Release date: ⁨2023-07-21⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS26<br>WebView on iOS – Full support<br>WebView on iOS26 (Release date: ⁨2025-09-15⁩)<br> <br>footnoteFull support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

No supportNo support

See implementation notes.

User must explicitly enable this feature.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline\#see_also)

- [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-composition`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
- [`scroll-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name), [`scroll-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-axis), [`scroll-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline)
- [`timeline-scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/timeline-scope)
- [`view-timeline-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-name), [`view-timeline-axis`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-axis), [`view-timeline`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline), [`view-timeline-inset`](https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-inset)
- The JavaScript equivalent: The `timeline` property available in [`Element.animate()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animate) calls
- [CSS scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations)
- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 13, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/animation-timeline/index.md?plain=1 "Folder: ⁨en-us/web/css/animation-timeline⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-timeline&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fanimation-timeline%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fanimation-timeline%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fanimation-timeline%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fbb52c01c1534149f1e3e4755e2576ef7828ecc0f%0A*+Document+last+modified%3A+2025-10-13T00%3A08%3A12.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")