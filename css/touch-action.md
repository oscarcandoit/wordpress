---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action
scraped_at: 2025-10-20T03:15:13.793Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#search)

# touch-action


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨September 2019⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftouch-action&level=high)

The **`touch-action`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how an element's region can be manipulated by a touchscreen user (for example, by zooming features built into the browser).

By default, panning (scrolling) and pinching gestures are handled exclusively by the browser. An application using [Pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events "Pointer events") will receive a [`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointercancel_event "pointercancel") event when the browser starts handling a touch gesture. By explicitly specifying which gestures should be handled by the browser, an application can supply its own behavior in [`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointermove_event "pointermove") and [`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointerup_event "pointerup") listeners for the remaining gestures. Applications using [Touch events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events "Touch events") disable the browser handling of gestures by calling [`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault "preventDefault()"), but should also use `touch-action` to ensure the browser knows the intent of the application before any event listeners have been invoked.

When a gesture is started, the browser intersects the `touch-action` values of the touched element and its ancestors, up to the one that implements the gesture (in other words, the first containing scrolling element). This means that in practice, `touch-action` is typically applied only to top-level elements which have some custom behavior, without needing to specify `touch-action` explicitly on any of that element's descendants.

**Note:**
After a gesture starts, changes to `touch-action` will not have any impact on the behavior of the current gesture.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#syntax)

cssCopy

```
/* Keyword values */
touch-action: auto;
touch-action: none;
touch-action: pan-x;
touch-action: pan-left;
touch-action: pan-right;
touch-action: pan-y;
touch-action: pan-up;
touch-action: pan-down;
touch-action: pinch-zoom;
touch-action: manipulation;

/* Global values */
touch-action: inherit;
touch-action: initial;
touch-action: revert;
touch-action: revert-layer;
touch-action: unset;

```

The `touch-action` property may be specified as either:

- One of the keywords `auto`, `none`, [`manipulation`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#manipulation), _or_
- One of the keywords `pan-x`, `pan-left`, `pan-right`, and/or one of the keywords `pan-y`, `pan-up`, `pan-down`, plus optionally the keyword `pinch-zoom`.

### [Values](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#values)

[`auto`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#auto)

Enable browser handling of all panning and zooming gestures.

[`none`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#none)

Disable browser handling of all panning and zooming gestures.

[`pan-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#pan-x)

Enable single-finger horizontal panning gestures. May be combined with **pan-y**, **pan-up**, **pan-down** and/or **pinch-zoom**.

[`pan-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#pan-y)

Enable single-finger vertical panning gestures. May be combined with **pan-x**, **pan-left**, **pan-right** and/or **pinch-zoom**.

[`manipulation`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#manipulation)

Enable panning and pinch zoom gestures, but disable additional non-standard gestures such as double-tap to zoom. Disabling double-tap to zoom removes the need for browsers to delay the generation of **click** events when the user taps the screen. This is an alias for " **pan-x pan-y pinch-zoom**" (which, for compatibility, is itself still valid).

[`pan-left`, `pan-right`, `pan-up`, `pan-down`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#pan-left)

Enable single-finger gestures that begin by scrolling in the given direction(s). Once scrolling has started, the direction may still be reversed. Note that scrolling "up" ( **pan-up**) means that the user is dragging their finger downward on the screen surface, and likewise **pan-left** means the user is dragging their finger to the right. Multiple directions may be combined except when there is a simpler representation (for example, **"pan-left pan-right**" is invalid since " **pan-x**" is simpler, but " **pan-left pan-down**" is valid).

[`pinch-zoom`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action#pinch-zoom)

Enable multi-finger panning and zooming of the page. This may be combined with any of the **pan-** values.

## [Accessibility](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#accessibility)

A declaration of `touch-action: none;` may inhibit operating a browser's zooming capabilities. This will prevent people experiencing low vision conditions from being able to read and understand page content.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## [Formal definition](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#formal_definition)

| [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) | `auto` |
| Applies to | all elements except: non-replaced inline elements, table rows, row groups, table columns, and column groups |
| [Inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) | no |
| [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value) | as specified |
| [Animation type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | Not animatable |

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#formal_syntax)

```
touch-action =
  auto                                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  none                                                 [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  pan-x  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  pan-left  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  pan-right  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  [\[](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  pan-y  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  pan-up  [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")  pan-down  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")  [\|\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#double_bar "Double bar: one or several of the entities must be present, in any order")  pinch-zoom  [\]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#brackets "Brackets: enclose several entities, combinators, and multipliers to transform them as a single component")   [\|](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#single_bar "Single bar: exactly one of the entities must be present")
  manipulation

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#examples)

### [Disabling all gestures](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#disabling_all_gestures)

The most common usage is to disable all gestures on an element (and its non-scrollable descendants) that provides its own dragging and zooming behavior – such as a map or game surface.

#### HTML

htmlCopy

```
<div id="map"></div>

```

#### CSS

cssCopy

```
#map {
  height: 150vh;
  width: 70vw;
  background: linear-gradient(blue, green);
  touch-action: none;
}

```

#### Result

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#specifications)

| Specification |
| --- |
| [Compatibility\<br>\# touch-action](https://compat.spec.whatwg.org/#touch-action) |
| [Pointer Events\<br>\# the-touch-action-css-property](https://w3c.github.io/pointerevents/#the-touch-action-css-property) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#browser_compatibility)

Loading…

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action\#see_also)

- [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
- [Pointer Events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)
- WebKit Blog [More Responsive Tapping on iOS](https://webkit.org/blog/5610/more-responsive-tapping-on-ios/)
- Google Developers Blog [Making touch scrolling fast by default](https://developer.chrome.com/blog/scrolling-intervention/)
- [Scroll Snap](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Jul 14, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/touch-action/index.md?plain=1 "Folder: ⁨en-us/web/css/touch-action⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftouch-action&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Ftouch-action%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Ftouch-action%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Ftouch-action%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cc9980e3b21c83d1800a428bc402ae1865326b2%0A*+Document+last+modified%3A+2025-07-14T14%3A43%3A58.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")