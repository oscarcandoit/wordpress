---
url: https://getbootstrap.com/docs/4.6/components/tooltips
scraped_at: 2025-10-20T02:40:40.276Z
---

[Skip to main content](https://getbootstrap.com/docs/4.6/components/tooltips/#content) [Skip to docs navigation](https://getbootstrap.com/docs/4.6/components/tooltips/#bd-docs-nav)

Bootstrap 4 has reached end of life.
[Upgrade to the latest](https://getbootstrap.com/migration/)
or consider
[Never-Ending Support](https://www.herodevs.com/support/nes-bootstrap?utm_source=Bootstrap_site&utm_medium=Banner&utm_campaign=v4_eol)
for your project.

```

```

Menu

[View on GitHub](https://github.com/twbs/bootstrap/blob/v4.6.2/site/content/docs/4.6/components/tooltips.md "View and edit this file on GitHub")

# Tooltips

Documentation and examples for adding custom Bootstrap tooltips with CSS and JavaScript using CSS3 for animations and data-attributes for local title storage.

## Overview [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#overview)

Things to know when using the tooltip plugin:

- Tooltips rely on the 3rd party library [Popper](https://popper.js.org/) for positioning. You must include [popper.min.js](https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js) before bootstrap.js or use `bootstrap.bundle.min.js` / `bootstrap.bundle.js` which contains Popper in order for tooltips to work!
- If you’re building our JavaScript from source, it [requires `util.js`](https://getbootstrap.com/docs/4.6/getting-started/javascript/#util).
- Tooltips are opt-in for performance reasons, so **you must initialize them yourself**.
- Tooltips with zero-length titles are never displayed.
- Specify `container: 'body'` to avoid rendering problems in more complex components (like our input groups, button groups, etc).
- Triggering tooltips on hidden elements will not work.
- Tooltips for `.disabled` or `disabled` elements must be triggered on a wrapper element.
- When triggered from hyperlinks that span multiple lines, tooltips will be centered. Use `white-space: nowrap;` on your `<a>` s to avoid this behavior.
- Tooltips must be hidden before their corresponding elements have been removed from the DOM.
- Tooltips can be triggered thanks to an element inside a shadow DOM.

By default, this component uses the built-in content sanitizer, which strips out any HTML elements that are not explicitly allowed. See the [sanitizer section in our JavaScript documentation](https://getbootstrap.com/docs/4.6/getting-started/javascript/#sanitizer) for more details.

The animation effect of this component is dependent on the `prefers-reduced-motion` media query. See the [reduced motion section of our accessibility documentation](https://getbootstrap.com/docs/4.6/getting-started/accessibility/#reduced-motion).

Got all that? Great, let’s see how they work with some examples.

## Example: Enable tooltips everywhere [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#example-enable-tooltips-everywhere)

One way to initialize all tooltips on a page would be to select them by their `data-toggle` attribute:

Copy

```js
$(function () {
  $('[data-toggle="tooltip"]').tooltip()
})

```

## Examples [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#examples)

Hover over the links below to see tooltips:

Placeholder text to demonstrate some [inline links](https://getbootstrap.com/docs/4.6/components/tooltips/# "Default tooltip") with tooltips. This is now just filler, no killer. Content placed here just to mimic the presence of [real text](https://getbootstrap.com/docs/4.6/components/tooltips/# "Another tooltip"). And all that just to give you an idea of how tooltips would look when used in real-world situations. So hopefully you've now seen how [these tooltips on links](https://getbootstrap.com/docs/4.6/components/tooltips/# "Another one here too") can work in practice, once you use them on [your own](https://getbootstrap.com/docs/4.6/components/tooltips/# "The last tip!") site or project.


Hover over the buttons below to see the four tooltips directions: top, right, bottom, and left.

Tooltip on topTooltip on rightTooltip on bottomTooltip on leftTooltip with HTML

Copy

```html
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="top" title="Tooltip on top">
  Tooltip on top
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="right" title="Tooltip on right">
  Tooltip on right
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="bottom" title="Tooltip on bottom">
  Tooltip on bottom
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="left" title="Tooltip on left">
  Tooltip on left
</button>

```

And with custom HTML added:

Copy

```html
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-html="true" title="<em>Tooltip</em> <u>with</u> <b>HTML</b>">
  Tooltip with HTML
</button>

```

## Usage [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#usage)

The tooltip plugin generates content and markup on demand, and by default places tooltips after their trigger element.

Trigger the tooltip via JavaScript:

Copy

```js
$('#example').tooltip(options)

```

##### Overflow `auto` and `scroll`

Tooltip position attempts to automatically change when a parent container has `overflow: auto` or `overflow: scroll` like our `.table-responsive`, but still keeps the original placement’s positioning. To resolve, set the `boundary` option to anything other than default value, `'scrollParent'`, such as `'window'`:

Copy

```js
$('#example').tooltip({ boundary: 'window' })

```

### Markup [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#markup)

The required markup for a tooltip is only a `data` attribute and `title` on the HTML element you wish to have a tooltip. The generated markup of a tooltip is rather simple, though it does require a position (by default, set to `top` by the plugin).

##### Making tooltips work for keyboard and assistive technology users

You should only add tooltips to HTML elements that are traditionally keyboard-focusable and interactive (such as links or form controls). Although arbitrary HTML elements (such as `<span>` s) can be made focusable by adding the `tabindex="0"` attribute, this will add potentially annoying and confusing tab stops on non-interactive elements for keyboard users, and most assistive technologies currently do not announce the tooltip in this situation. Additionally, do not rely solely on `hover` as the trigger for your tooltip, as this will make your tooltips impossible to trigger for keyboard users.

Copy

```html
<!-- HTML to write -->
<a href="#" data-toggle="tooltip" title="Some tooltip text!">Hover over me</a>

<!-- Generated markup by the plugin -->
<div class="tooltip bs-tooltip-top" role="tooltip">
  <div class="arrow"></div>
  <div class="tooltip-inner">
    Some tooltip text!
  </div>
</div>

```

### Disabled elements [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#disabled-elements)

Elements with the `disabled` attribute aren’t interactive, meaning users cannot focus, hover, or click them to trigger a tooltip (or popover). As a workaround, you’ll want to trigger the tooltip from a wrapper `<div>` or `<span>`, ideally made keyboard-focusable using `tabindex="0"`, and override the `pointer-events` on the disabled element.

Disabled button

Copy

```html
<span class="d-inline-block" tabindex="0" data-toggle="tooltip" title="Disabled tooltip">
  <button class="btn btn-primary" style="pointer-events: none;" type="button" disabled>Disabled button</button>
</span>
```

### Options [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#options)

Options can be passed via data attributes or JavaScript. For data attributes, append the option name to `data-`, as in `data-animation=""`.

Note that for security reasons the `sanitize`, `sanitizeFn` and `whiteList` options cannot be supplied using data attributes.

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| animation | boolean | true | Apply a CSS fade transition to the tooltip |
| container | string \| element \| false | false | Appends the tooltip to a specific element. Example: `container: 'body'`. This option is particularly useful in that it allows you to position the tooltip in the flow of the document near the triggering element - which will prevent the tooltip from floating away from the triggering element during a window resize. |
| delay | number \| object | 0 | Delay showing and hiding the tooltip (ms) - does not apply to manual trigger type<br>If a number is supplied, delay is applied to both hide/show<br>Object structure is: `delay: { "show": 500, "hide": 100 }` |
| html | boolean | false | Allow HTML in the tooltip.<br>If true, HTML tags in the tooltip's `title` will be rendered in the tooltip. If false, jQuery's `text` method will be used to insert content into the DOM.<br>Use text if you're worried about XSS attacks. |
| placement | string \| function | 'top' | How to position the tooltip - auto \| top \| bottom \| left \| right.<br>When `auto` is specified, it will dynamically reorient the tooltip.<br>When a function is used to determine the placement, it is called with the tooltip DOM node as its first argument and the triggering element DOM node as its second. The `this` context is set to the tooltip instance. |
| selector | string \| false | false | If a selector is provided, tooltip objects will be delegated to the specified targets. In practice, this is used to also apply tooltips to dynamically added DOM elements ( `jQuery.on` support). See [this](https://github.com/twbs/bootstrap/issues/4215) and [an informative example](https://codepen.io/team/bootstrap/pen/qBNGbYK). |
| template | string | `'<div class="tooltip" role="tooltip"><div class="arrow"></div><div class="tooltip-inner"></div></div>'` | Base HTML to use when creating the tooltip.<br>The tooltip's `title` will be injected into the `.tooltip-inner`.<br>`.arrow` will become the tooltip's arrow.<br>The outermost wrapper element should have the `.tooltip` class and `role="tooltip"`. |
| title | string \| element \| function | '' | Default title value if `title` attribute isn't present.<br>If a function is given, it will be called with its `this` reference set to the element that the tooltip is attached to. |
| trigger | string | 'hover focus' | How tooltip is triggered - click \| hover \| focus \| manual. You may pass multiple triggers; separate them with a space.<br>`'manual'` indicates that the tooltip will be triggered programmatically via the `.tooltip('show')`, `.tooltip('hide')` and `.tooltip('toggle')` methods; this value cannot be combined with any other trigger.<br>`'hover'` on its own will result in tooltips that cannot be triggered via the keyboard, and should only be used if alternative methods for conveying the same information for keyboard users is present. |
| offset | number \| string \| function | 0 | Offset of the tooltip relative to its target.<br>When a function is used to determine the offset, it is called with an object containing the offset data as its first argument. The function must return an object with the same structure. The triggering element DOM node is passed as the second argument.<br>For more information refer to Popper's [offset docs](https://popper.js.org/docs/v1/#modifiers..offset.offset). |
| fallbackPlacement | string \| array | 'flip' | Allow to specify which position Popper will use on fallback. For more information refer to<br> Popper's [behavior docs](https://popper.js.org/docs/v1/#modifiers..flip.behavior) |
| customClass | string \| function | '' | Add classes to the tooltip when it is shown. Note that these classes will be added in addition to any classes specified in the template. To add multiple classes, separate them with spaces: `'a b'`.<br>You can also pass a function that should return a single string containing additional class names. |
| boundary | string \| element | 'scrollParent' | Overflow constraint boundary of the tooltip. Accepts the values of `'viewport'`, `'window'`, `'scrollParent'`, or an HTMLElement reference (JavaScript only). For more information refer to Popper's [preventOverflow docs](https://popper.js.org/docs/v1/#modifiers..preventOverflow.boundariesElement). |
| sanitize | boolean | true | Enable or disable the sanitization. If activated `'template'` and `'title'` options will be sanitized. See the [sanitizer section in our JavaScript documentation](https://getbootstrap.com/docs/4.6/getting-started/javascript/#sanitizer). |
| whiteList | object | [Default value](https://getbootstrap.com/docs/4.6/getting-started/javascript/#sanitizer) | Object which contains allowed attributes and tags |
| sanitizeFn | null \| function | null | Here you can supply your own sanitize function. This can be useful if you prefer to use a dedicated library to perform sanitization. |
| popperConfig | null \| object | null | To change Bootstrap's default Popper config, see [Popper's configuration](https://popper.js.org/docs/v1/#Popper.Defaults) |

#### Data attributes for individual tooltips

Options for individual tooltips can alternatively be specified through the use of data attributes, as explained above.

### Methods [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#methods)

#### Asynchronous methods and transitions

All API methods are **asynchronous** and start a **transition**. They return to the caller as soon as the transition is started but **before it ends**. In addition, a method call on a **transitioning component will be ignored**.

[See our JavaScript documentation for more information](https://getbootstrap.com/docs/4.6/getting-started/javascript/#asynchronous-functions-and-transitions).

#### `$().tooltip(options)` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipoptions)

Attaches a tooltip handler to an element collection.

#### `.tooltip('show')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipshow)

Reveals an element’s tooltip. **Returns to the caller before the tooltip has actually been shown** (i.e. before the `shown.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip. Tooltips with zero-length titles are never displayed.

Copy

```js
$('#element').tooltip('show')

```

#### `.tooltip('hide')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltiphide)

Hides an element’s tooltip. **Returns to the caller before the tooltip has actually been hidden** (i.e. before the `hidden.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip.

Copy

```js
$('#element').tooltip('hide')

```

#### `.tooltip('toggle')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltiptoggle)

Toggles an element’s tooltip. **Returns to the caller before the tooltip has actually been shown or hidden** (i.e. before the `shown.bs.tooltip` or `hidden.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip.

Copy

```js
$('#element').tooltip('toggle')

```

#### `.tooltip('dispose')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipdispose)

Hides and destroys an element’s tooltip. Tooltips that use delegation (which are created using [the `selector` option](https://getbootstrap.com/docs/4.6/components/tooltips/#options)) cannot be individually destroyed on descendant trigger elements.

Copy

```js
$('#element').tooltip('dispose')

```

#### `.tooltip('enable')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipenable)

Gives an element’s tooltip the ability to be shown. **Tooltips are enabled by default.**

Copy

```js
$('#element').tooltip('enable')

```

#### `.tooltip('disable')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipdisable)

Removes the ability for an element’s tooltip to be shown. The tooltip will only be able to be shown if it is re-enabled.

Copy

```js
$('#element').tooltip('disable')

```

#### `.tooltip('toggleEnabled')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltiptoggleenabled)

Toggles the ability for an element’s tooltip to be shown or hidden.

Copy

```js
$('#element').tooltip('toggleEnabled')

```

#### `.tooltip('update')` [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#tooltipupdate)

Updates the position of an element’s tooltip.

Copy

```js
$('#element').tooltip('update')

```

### Events [Anchor](https://getbootstrap.com/docs/4.6/components/tooltips/\#events)

| Event Type | Description |
| --- | --- |
| show.bs.tooltip | This event fires immediately when the `show` instance method is called. |
| shown.bs.tooltip | This event is fired when the tooltip has been made visible to the user (will wait for CSS transitions to complete). |
| hide.bs.tooltip | This event is fired immediately when the `hide` instance method has been called. |
| hidden.bs.tooltip | This event is fired when the tooltip has finished being hidden from the user (will wait for CSS transitions to complete). |
| inserted.bs.tooltip | This event is fired after the `show.bs.tooltip` event when the tooltip template has been added to the DOM. |

Copy

```js
$('#myTooltip').on('hidden.bs.tooltip', function () {
  // do something...
})

```