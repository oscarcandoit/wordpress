---
url: https://developer.mozilla.org/en-US/docs/Web/CSS/env
scraped_at: 2025-10-20T02:59:13.204Z
---

- [Skip to main content](https://developer.mozilla.org/en-US/docs/Web/CSS/env#content)
- [Skip to search](https://developer.mozilla.org/en-US/docs/Web/CSS/env#search)

Learn front-end development with high quality, interactive courses
from
[Scrimba](https://scrimba.com/learn/frontend?via=mdn)

[We’d love for you to take 10 minutes to share your feedback.](https://survey.alchemer.com/s3/8409929/MDN-Developer-Survey?referrer=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fenv "Take survey (Opens in a new tab)")

# env()


Baseline

Widely available

\*



This feature is well established and works across many devices and browser versions. It’s been available across browsers since ⁨January 2020⁩.


\\* Some parts of this feature may have varying levels of support.

- [Learn more](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility)
- [See full compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/env#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fenv&level=high)

The **`env()`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/CSS_value_functions) can be used to insert the value of a user-agent defined [environment variable](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables) into your CSS.

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#syntax)

cssCopy

```
/* Without a fallback value */
env(safe-area-inset-top);
env(titlebar-area-width);
env(viewport-segment-right 0 0);

/* With a fallback value */
env(safe-area-inset-right, 1em);
env(titlebar-area-y, 40px);
env(viewport-segment-width 0 0, 40%);

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#parameters)

The `env( <environment-variable>, <fallback> )` function accepts the following parameters:

[`<environment-variable>`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables#browser-defined_environment_variables)

A [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident) specifying the name of the environment variable to be inserted. If the name provided represents an array-like environment variable, the name is followed by [`<integer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/integer) values identifying the specific instance the name is referencing. The case-sensitive environment variable name can be one of the following:

[`safe-area-inset-top`, `safe-area-inset-right`, `safe-area-inset-bottom`, `safe-area-inset-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/env#safe-area-inset-top)

The safe distance from the top, right, bottom, or left inset edge of the viewport, defining where it is safe to place content into without risking it being cut off by the shape of a non‑rectangular display. The four values form a rectangle, inside which all content is visible. The values are `0` if the viewport is a rectangle and no features — such as toolbars or dynamic keyboards — are occupying viewport space; otherwise, it is a `px` value greater than `0`.

[`safe-area-max-inset-top`, `safe-area-max-inset-right`, `safe-area-max-inset-bottom`, `safe-area-max-inset-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/env#safe-area-max-inset-top)

The static maximum values of their dynamic `safe-area-inset-*` variable counterparts when all dynamic user interface features are retracted. While the `safe-area-inset-*` values change as the currently-visible content area changes, the `safe-area-max-inset-*` values are constants.

[`titlebar-area-x`, `titlebar-area-y`, `titlebar-area-width`, `titlebar-area-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/env#titlebar-area-x)

The dimensions of a visible `titlebar-area-*` area. These variables are available when using the `window-controls-overlay` [`display_override`](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest/Reference/display_override) manifest field. The variables' values can be used to ensure content doesn't overlap window control buttons (that is, minimize, maximize, and close) with progressive web apps (PWA) installed on desktop devices.

[`keyboard-inset-top`, `keyboard-inset-right`, `keyboard-inset-bottom`, `keyboard-inset-left`, `keyboard-inset-width`, `keyboard-inset-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/env#keyboard-inset-top)

The insets from the edge of the viewport and dimensions of the device's on-screen virtual keyboard. Defined in the [VirtualKeyboard API](https://developer.mozilla.org/en-US/docs/Web/API/VirtualKeyboard_API "VirtualKeyboard API").

[`viewport-segment-width`, `viewport-segment-height`, `viewport-segment-top`, `viewport-segment-right`, `viewport-segment-bottom`, `viewport-segment-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/env#viewport-segment-width)

The dimensions and offset positions of specific viewport segments. The `viewport-segment-*` keyword is followed by two space-separated [`<integer>`](https://developer.mozilla.org/en-US/docs/Web/CSS/integer) values that indicate the segment's horizontal and vertical position, or indices. The viewport-segment keywords are only defined when the viewport is made up of two or more segments, as with foldable or hinged devices.

[`<fallback>` Optional](https://developer.mozilla.org/en-US/docs/Web/CSS/env#fallback)

A fallback value to be inserted if the environment variable referenced in the first argument does not exist. Everything after the first comma is deemed to be the fallback value. This can be a single value, another `env()` function, or a comma-separated list of values.

## [Description](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#description)

The `env()` function is used to insert the value of a globally-scoped, [user-agent-defined environment variable](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables#browser-defined_environment_variables) into your CSS. The `env()` function can be used as a property value or in place of any part of a property value or descriptor (for example, in [Media query rules](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)).

The function accepts an `<environment-variable>` as its first argument. This is a case-sensitive [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident) equal to the [name of the environment variable](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables#browser-defined_environment_variables) to be substituted, but it can also include additional space-separated values if required. For example, `env(viewport-segment-width 0 0)` would return the width of the top or left segment in the case of a device with multiple viewport segments.

The second argument, if provided, is the fallback value, which is used if the environment variable referenced in the first argument is not supported or doesn't exist. The fallback can be another environment variable, even with its own fallback.

The syntax of the fallback is similar to the fallback syntax of the [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var) function used to insert [CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) in that it allows for multiple commas. Anything between the first comma and the end of the function is considered the fallback value. However, if the `env()` function is used within a property value or descriptor that doesn't include commas, a fallback value that includes commas will not be valid.

A property or descriptor containing a syntactically valid `env()` function is assumed to be valid at parse time, when the browser first reads and interprets the downloaded CSS text. It is only syntax-checked at compute time, after each `env()` function has been substituted with its browser-provided value (or the fallback value if the environment variable passed as the first parameter is not a recognized environment variable name). If the value is invalid and no fallback is provided, the property or descriptor containing the `env()` function is [invalid at computed-value time](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_syntax/Error_handling#invalid_custom_properties).

When an `env()` substitution is invalid, and an invalid fallback is included, or the fallback is omitted, the declaration is not ignored. Instead, the [initial](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value) or [inherited](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance) value of the property is used. The property is set to a new value, but it may not be the expected one.

### [Use cases](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#use_cases)

Originally provided by the iOS browser to allow developers to place their content in a safe area of the viewport, and not be obscured by device notches or rounded corners, the `safe-area-inset-*` values can be used to help ensure content is visible to viewers. This feature was later expanded beyond its initial purpose to enable use cases such as [stopping device notifications from covering up some of the app user interface](https://developer.mozilla.org/en-US/docs/Web/CSS/env#using_env_to_ensure_buttons_are_not_obscured_by_device_ui).

Another use case for `env()` variables is for desktop [Progressive web apps](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps) (PWAs) that use the [Window Controls Overlay](https://developer.mozilla.org/en-US/docs/Web/API/Window_Controls_Overlay_API) feature to take advantage of the full application window surface area. Using the [`titlebar-area-*` values](https://developer.mozilla.org/en-US/docs/Web/CSS/env#titlebar-area-x) values, developers can position elements where the title bar would have been and [ensure content is not obscured by window control buttons](https://developer.mozilla.org/en-US/docs/Web/CSS/env#using_env_to_ensure_content_is_not_obscured_by_window_control_buttons_in_desktop_pwas).

The `viewport-segment-*` variable names can be used to set your containers to fit neatly into the available segments of a multi-viewport-segment device such as a hinged or foldable device. The integers following the `viewport-segment-*` name indicate which segment of the multiple segments the environment variable is referencing.

### [Names followed by integers](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#names_followed_by_integers)

When the environment variable is array-like, meaning the name may reference more than once value, such as is the case with devices with multiple viewport segments, the `<environment-variable>` parameter includes both the name of the variable and the indices of the specific instance of the variable the function is referencing. For example, in the case of the `viewport-segment-*` variables, the variable names are passed to the `env()` function along with two integers indicating the indices of the segment to return the value for. These values are both integers of `0` or greater. The first integer represents the horizontal index of the segment, with `0` being the left-most segment, and the second value represents the vertical index of the segment, with `0` representing the bottom-most segment:

![Two device segment layouts; in a horizontal layout, 0 0 is the first segment and 1 0 is the second segment. In a vertical layout, the indices are 0 0 and 0 1](https://developer.mozilla.org/en-US/docs/Web/CSS/env/env-var-indices.png)

- In a horizontal side-by-side layout, the left segment is represented by `0 0`, and the right segment is represented by `1 0`.
- In a vertical top-to-bottom layout, the top segment is represented by `0 0`, and the bottom segment is represented by `0 1`.
- In devices with more than two segments, the numbers may be greater. For example, a device with three horizontal segments may have the center segment represented by `1 0`, and the right-hand segment represented by `2 0`.

For example, the following returns the width of the right-hand segment on a two-segment foldable device where the segments are oriented horizontally:

cssCopy

```
env(viewport-segment-width 1 0)

```

See the [Viewport segment API demo](https://mdn.github.io/dom-examples/viewport-segments-api/) for a full working demo ( [source code](https://github.com/mdn/dom-examples/tree/main/viewport-segments-api)). Also check out [Using the Viewport Segments API](https://developer.mozilla.org/en-US/docs/Web/API/Viewport_segments_API/Using) for a full demo explanation.

## [Formal syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#formal_syntax)

```
<env()> =
  env(  [<custom-ident>](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident)  [<integer \[0,∞\]>](https://developer.mozilla.org/en-US/docs/Web/CSS/integer) [\*](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#asterisk "Asterisk: the entity may occur zero, one or several times") , <declaration-value> [?](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_values_and_units/Value_definition_syntax#question_mark "Question mark: the entity is optional") )

```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#examples)

### [Using env() to ensure buttons are not obscured by device UI](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#using_env_to_ensure_buttons_are_not_obscured_by_device_ui)

In the following example, `env()` is used to ensure that fixed app toolbar buttons are not obscured by device notifications appearing at the bottom of the screen. On the desktop `safe-area-inset-bottom` is `0`. However, in devices that display notifications at the bottom of the screen, such as iOS, it contains a value that leaves space for the notification to display. This can then be used in the value for [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom) to create a gap that appears natural on that device.

#### HTML

We have a [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/main) section containing a fake application and a [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/footer) containing two [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/button) elements:

htmlCopyPlay

```
<main>Main content of app here</main>
<footer>
  <button>Go here</button>
  <button>Or here</button>
</footer>

```

#### CSS

Using [CSS flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout), we create a footer that is only as tall as it needs to be, while the main section containing the application fills up the rest of the viewport:

cssCopyPlay

```
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font: 1em system-ui;
}

main {
  flex: 1;
  background-color: #eeeeee;
  padding: 1em;
}

footer {
  flex: none;
  display: flex;
  gap: 1em;
  justify-content: space-evenly;
  background: black;
}

button {
  padding: 1em;
  background: white;
  color: black;
  margin: 0;
  width: 100%;
  border: none;
  font: 1em system-ui;
}

```

We set [`position: sticky`](https://developer.mozilla.org/en-US/docs/Web/CSS/position#sticky) to stick the footer to the bottom of the viewport. We then use the [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) shorthand to add padding to the footer. We include the value of the `safe-area-inset-bottom` environment value to an initial `1em` of bottom padding. A larger black area will display on devices that have a positive value for this variable, ensuring the buttons in the footer are never obscured.

cssCopyPlay

```
footer {
  position: sticky;
  bottom: 0;

  padding: 1em 1em calc(1em + env(safe-area-inset-bottom));
}

```

#### Results

Play

Main content of app here

### [Using a fallback value](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#using_a_fallback_value)

This example makes use of the optional second parameter of `env()`, which provides a fallback value in case the environment variable is not available.

#### HTML

We include a paragraph of text:

htmlCopyPlay

```
<p>
  If the <code>env()</code> function is supported in your browser, this
  paragraph's text will have 50px of padding between it and the left border —
  but not the top, right and bottom. This is because the accompanying CSS is the
  equivalent of <code>padding: 0 0 0 50px</code>, because, unlike other CSS
  properties, user agent property names are case-sensitive.
</p>

```

#### CSS

We set a [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) of `300px` and a [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border). We then add [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding), using the `env()` function with a fallback for the size of the padding on each side. We intentionally set an invalid value for the left padding (remember, environment variable names are case-sensitive), to demonstrate the use of the fallback value.

cssCopyPlay

```
p {
  width: 300px;
  border: 2px solid red;
  padding: env(safe-area-inset-top, 50px) env(safe-area-inset-right, 50px)
    env(safe-area-inset-bottom, 50px) env(SAFE-AREA-INSET-LEFT, 50px);
}

```

#### Results

Play

If the `env()` function is supported in your browser, this
paragraph's text will have 50px of padding between it and the left border —
but not the top, right and bottom. This is because the accompanying CSS is the
equivalent of `padding: 0 0 0 50px`, because, unlike other CSS
properties, user agent property names are case-sensitive.

### [Using env() to ensure content is not obscured by window control buttons in desktop PWAs](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#using_env_to_ensure_content_is_not_obscured_by_window_control_buttons_in_desktop_pwas)

In the following example, `env()` ensures that content displayed in a desktop Progressive Web App that uses the [Window Controls Overlay API](https://developer.mozilla.org/en-US/docs/Web/API/Window_Controls_Overlay_API) is not obscured by the operating system's window control buttons. The `titlebar-area-*` values define a rectangle where the title bar would normally have been displayed. On devices that do not support the Window Controls Overlay feature, such as mobile devices, the fallback values are used.

Here is what a PWA installed on a desktop device normally looks like:

![Illustration of what a PWA installed on desktop normally looks like, with window control buttons, a title bar, and web content below that](https://developer.mozilla.org/en-US/docs/Web/CSS/env/desktop-pwa-window.png)

With the Window Controls Overlay feature, the web content covers the whole app window surface area, with the window controls and PWA buttons displayed as overlays:

![Illustration of what a PWA installed on desktop looks like with the Window Controls Overlay feature, with window control buttons, no title bar, and web content spanning the whole window](https://developer.mozilla.org/en-US/docs/Web/CSS/env/desktop-pwa-window-wco.png)

htmlCopy

```
<header>Title of the app here</header>
<main>Main content of app here</main>

```

cssCopy

```
header {
  position: fixed;
  left: env(titlebar-area-x);
  top: env(titlebar-area-y);
  width: env(titlebar-area-width);
  height: env(titlebar-area-height);
}

main {
  margin-top: env(titlebar-area-height);
}

```

**Note:**
Using `position:fixed` makes sure the header does not scroll with the rest of the content, and instead stays aligned with the window control buttons, even on device/browsers that support elastic overscroll (also known as rubber banding).

### [Viewport segments](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#viewport_segments)

The [Viewport segment API demo](https://mdn.github.io/dom-examples/viewport-segments-api/) and [Using the Viewport Segments API](https://developer.mozilla.org/en-US/docs/Web/API/Viewport_segments_API/Using) guide provides a demonstration and explanation of using the `env()` function with the `viewport-segments-*` environment variables.

## [Specifications](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#specifications)

| Specification |
| --- |
| [CSS Environment Variables Module Level 1\<br>\# env-function](https://drafts.csswg.org/css-env/#env-function) |

## [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#browser_compatibility)

[Report problems with this compatibility data](https://developer.mozilla.org/en-US/docs/Web/CSS/env# "Report an issue with this compatibility data") •
[View data on GitHub](https://github.com/mdn/browser-compat-data/tree/main/css/types/env.json "File: ⁨css/types/env.json⁩")

|  | desktop | mobile |
| --- | --- | --- |
|  | Chrome | Edge | Firefox | Opera | Safari | Chrome Android | Firefox for Android | Opera Android | Safari on iOS | Samsung Internet | WebView Android | WebView on iOS |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `env()` | Chrome – Full support<br>Chrome69<br>Chrome – Full support<br>Chrome69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox65<br>Firefox – Full support<br>Firefox65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera56<br>Opera – Full support<br>Opera56 (Release date: ⁨2018-09-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11.1<br>more<br>Safari – No support<br>Safari11 – 11 (Release date: ⁨2017-09-19⁩)<br> <br>altname<br>altnameAlternate name: ⁨constant⁩<br>Safari – Full support<br>Safari11.1 (Release date: ⁨2018-04-12⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android69<br>Chrome Android – Full support<br>Chrome Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android65<br>Firefox for Android – Full support<br>Firefox for Android65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11.3<br>more<br>Safari on iOS – No support<br>Safari on iOS11 – 11 (Release date: ⁨2017-09-19⁩)<br> <br>altname<br>altnameAlternate name: ⁨constant⁩<br>Safari on iOS – Full support<br>Safari on iOS11.3 (Release date: ⁨2018-03-29⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android69<br>WebView Android – Full support<br>WebView Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11.3<br>more<br>WebView on iOS – No support<br>WebView on iOS11 – 11 (Release date: ⁨2017-09-19⁩)<br> <br>altname<br>altnameAlternate name: ⁨constant⁩<br>WebView on iOS – Full support<br>WebView on iOS11.3 (Release date: ⁨2018-03-29⁩)<br> <br>footnoteFull support |
| [Safe area inset variable `safe-area-inset-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome69<br>Chrome – Full support<br>Chrome69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox65<br>Firefox – Full support<br>Firefox65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera56<br>Opera – Full support<br>Opera56 (Release date: ⁨2018-09-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android69<br>Chrome Android – Full support<br>Chrome Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android65<br>Firefox for Android – Full support<br>Firefox for Android65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android69<br>WebView Android – Full support<br>WebView Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| [Safe area inset variable `safe-area-inset-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome69<br>Chrome – Full support<br>Chrome69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox65<br>Firefox – Full support<br>Firefox65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera56<br>Opera – Full support<br>Opera56 (Release date: ⁨2018-09-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android69<br>Chrome Android – Full support<br>Chrome Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android65<br>Firefox for Android – Full support<br>Firefox for Android65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android69<br>WebView Android – Full support<br>WebView Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| [Safe area inset variable `safe-area-inset-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome69<br>Chrome – Full support<br>Chrome69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox65<br>Firefox – Full support<br>Firefox65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera56<br>Opera – Full support<br>Opera56 (Release date: ⁨2018-09-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android69<br>Chrome Android – Full support<br>Chrome Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android65<br>Firefox for Android – Full support<br>Firefox for Android65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android69<br>WebView Android – Full support<br>WebView Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| [Safe area inset variable `safe-area-inset-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome69<br>Chrome – Full support<br>Chrome69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge79<br>Edge – Full support<br>Edge79 (Release date: ⁨2020-01-15⁩)<br> <br>footnoteFull support | Firefox – Full support<br>Firefox65<br>Firefox – Full support<br>Firefox65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera – Full support<br>Opera56<br>Opera – Full support<br>Opera56 (Release date: ⁨2018-09-25⁩)<br> <br>footnoteFull support | Safari – Full support<br>Safari11<br>Safari – Full support<br>Safari11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Chrome Android – Full support<br>Chrome Android69<br>Chrome Android – Full support<br>Chrome Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | Firefox for Android – Full support<br>Firefox for Android65<br>Firefox for Android – Full support<br>Firefox for Android65 (Release date: ⁨2019-01-29⁩)<br> <br>footnoteFull support | Opera Android – Full support<br>Opera Android48<br>Opera Android – Full support<br>Opera Android48 (Release date: ⁨2018-11-08⁩)<br> <br>footnoteFull support | Safari on iOS – Full support<br>Safari on iOS11<br>Safari on iOS – Full support<br>Safari on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support | Samsung Internet – Full support<br>Samsung Internet10<br>Samsung Internet – Full support<br>Samsung Internet10 (Release date: ⁨2019-08-22⁩)<br> <br>footnoteFull support | WebView Android – Full support<br>WebView Android69<br>WebView Android – Full support<br>WebView Android69 (Release date: ⁨2018-09-04⁩)<br> <br>footnoteFull support | WebView on iOS – Full support<br>WebView on iOS11<br>WebView on iOS – Full support<br>WebView on iOS11 (Release date: ⁨2017-09-19⁩)<br> <br>footnoteFull support |
| [Window Controls Overlay variable `titlebar-area-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome93<br>more<br>Chrome – Partial support<br>Chrome92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome – Full support<br>Chrome93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge93<br>more<br>Edge – Partial support<br>Edge92 – 92 (Release date: ⁨2021-07-22⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Edge – Full support<br>Edge93 (Release date: ⁨2021-09-02⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera78<br>Opera – Full support<br>Opera78 (Release date: ⁨2021-08-03⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android93<br>more<br>Chrome Android – Partial support<br>Chrome Android92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome Android – Full support<br>Chrome Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android65<br>Opera Android – Full support<br>Opera Android65 (Release date: ⁨2021-10-20⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet17<br>Samsung Internet – Full support<br>Samsung Internet17 (Release date: ⁨2022-05-04⁩)<br> <br>footnoteFull support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| [Window Controls Overlay variable `titlebar-area-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome93<br>more<br>Chrome – Partial support<br>Chrome92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome – Full support<br>Chrome93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge93<br>more<br>Edge – Partial support<br>Edge92 – 92 (Release date: ⁨2021-07-22⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Edge – Full support<br>Edge93 (Release date: ⁨2021-09-02⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera78<br>Opera – Full support<br>Opera78 (Release date: ⁨2021-08-03⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android93<br>more<br>Chrome Android – Partial support<br>Chrome Android92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome Android – Full support<br>Chrome Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android65<br>Opera Android – Full support<br>Opera Android65 (Release date: ⁨2021-10-20⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet17<br>Samsung Internet – Full support<br>Samsung Internet17 (Release date: ⁨2022-05-04⁩)<br> <br>footnoteFull support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| [Window Controls Overlay variable `titlebar-area-x`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome93<br>more<br>Chrome – Partial support<br>Chrome92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome – Full support<br>Chrome93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge93<br>more<br>Edge – Partial support<br>Edge92 – 92 (Release date: ⁨2021-07-22⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Edge – Full support<br>Edge93 (Release date: ⁨2021-09-02⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera78<br>Opera – Full support<br>Opera78 (Release date: ⁨2021-08-03⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android93<br>more<br>Chrome Android – Partial support<br>Chrome Android92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome Android – Full support<br>Chrome Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android65<br>Opera Android – Full support<br>Opera Android65 (Release date: ⁨2021-10-20⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet17<br>Samsung Internet – Full support<br>Samsung Internet17 (Release date: ⁨2022-05-04⁩)<br> <br>footnoteFull support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| [Window Controls Overlay variable `titlebar-area-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/env) | Chrome – Full support<br>Chrome93<br>more<br>Chrome – Partial support<br>Chrome92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome – Full support<br>Chrome93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge93<br>more<br>Edge – Partial support<br>Edge92 – 92 (Release date: ⁨2021-07-22⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Edge – Full support<br>Edge93 (Release date: ⁨2021-09-02⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera78<br>Opera – Full support<br>Opera78 (Release date: ⁨2021-08-03⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android93<br>more<br>Chrome Android – Partial support<br>Chrome Android92 – 92 (Release date: ⁨2021-07-20⁩)<br> <br>footnotePartial supportfootnoteBefore version 93, Linux is unsupported.<br>Chrome Android – Full support<br>Chrome Android93 (Release date: ⁨2021-08-31⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android65<br>Opera Android – Full support<br>Opera Android65 (Release date: ⁨2021-10-20⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – Full support<br>Samsung Internet17<br>Samsung Internet – Full support<br>Samsung Internet17 (Release date: ⁨2022-05-04⁩)<br> <br>footnoteFull support | WebView Android – No support<br>WebView AndroidNo<br> <br>WebView Android – No support<br>WebView Android<br>footnoteNo support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-bottom`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-height`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-left`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-right`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-top`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |
| Viewport segment variable `viewport-segment-width`<br>Experimental | Chrome – Full support<br>Chrome138<br>Chrome – Full support<br>Chrome138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Edge – Full support<br>Edge138<br>Edge – Full support<br>Edge138 (Release date: ⁨2025-06-26⁩)<br> <br>footnoteFull support | Firefox – No support<br>FirefoxNo<br> <br>Firefox – No support<br>Firefox<br>footnoteNo support | Opera – Full support<br>Opera122<br>Opera – Full support<br>Opera122 (Release date: ⁨2025-09-11⁩)<br> <br>footnoteFull support | Safari – No support<br>SafariNo<br> <br>Safari – No support<br>Safari<br>footnoteNo support | Chrome Android – Full support<br>Chrome Android138<br>Chrome Android – Full support<br>Chrome Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | Firefox for Android – No support<br>Firefox for AndroidNo<br> <br>Firefox for Android – No support<br>Firefox for Android<br>footnoteNo support | Opera Android – Full support<br>Opera Android91<br>Opera Android – Full support<br>Opera Android91 (Release date: ⁨2025-08-19⁩)<br> <br>footnoteFull support | Safari on iOS – No support<br>Safari on iOSNo<br> <br>Safari on iOS – No support<br>Safari on iOS<br>footnoteNo support | Samsung Internet – No support<br>Samsung InternetNo<br> <br>Samsung Internet – No support<br>Samsung Internet<br>footnoteNo support | WebView Android – Full support<br>WebView Android138<br>WebView Android – Full support<br>WebView Android138 (Release date: ⁨2025-06-24⁩)<br> <br>footnoteFull support | WebView on iOS – No support<br>WebView on iOSNo<br> <br>WebView on iOS – No support<br>WebView on iOS<br>footnoteNo support |

### Legend

Tip: you can click/tap on a cell for more information.


Full supportFull support

Partial supportPartial support

No supportNo support

⁨Experimental⁩. Expect behavior to change in the future.

Uses a non-standard name.

Has more compatibility info.

## [See also](https://developer.mozilla.org/en-US/docs/Web/CSS/env\#see_also)

- [Using environment variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables/Using_environment_variables)
- [CSS environment variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_environment_variables) module
- [`var()`](https://developer.mozilla.org/en-US/docs/Web/CSS/var)
- [CSS custom properties for cascading variables](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables) module
- [Custom properties ( `--*`): CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
- [Using CSS custom properties (variables)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties)
- [Viewport Segments API](https://developer.mozilla.org/en-US/docs/Web/API/Viewport_segments_API)
- [Customize the window controls overlay of your PWA's title bar](https://web.dev/articles/window-controls-overlay)
- [Display content in the title bar](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps/how-to/window-controls-overlay)
- [Breaking Out of the Box](https://alistapart.com/article/breaking-out-of-the-box/)

## Help improve MDN

Was this page helpful to you?

YesNo

[Learn how to contribute](https://developer.mozilla.org/en-US/docs/MDN/Community/Getting_started)

This page was last modified on ⁨Oct 10, 2025⁩ by [MDN contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/env/contributors.txt).


[View this page on GitHub](https://github.com/mdn/content/blob/main/files/en-us/web/css/env/index.md?plain=1 "Folder: ⁨en-us/web/css/env⁩ (Opens in a new tab)") • [Report a problem with this content](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fenv&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fcss%2Fenv%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2Fenv%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fcss%2Fenv%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F70285e396b5c97675e90b85d573be42078e0168e%0A*+Document+last+modified%3A+2025-10-10T12%3A00%3A42.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue.")