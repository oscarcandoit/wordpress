---
url: https://getbootstrap.com/docs/5.3/components/tooltips
scraped_at: 2025-10-20T02:28:16.214Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/components/tooltips/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/components/tooltips/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/components/tooltips.mdx "View and edit this file on GitHub")

# Tooltips

Documentation and examples for adding custom Bootstrap tooltips with CSS and JavaScript using CSS3 for animations and data-bs-attributes for local title storage.

On this page
**On this page**

* * *

## Overview [Link to this section: Overview](https://getbootstrap.com/docs/5.3/components/tooltips/\#overview)

Things to know when using the tooltip plugin:

- Tooltips rely on the third party library [Popper](https://popper.js.org/docs/v2/) for positioning. You must include [popper.min.js](https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js) before `bootstrap.js`, or use one `bootstrap.bundle.min.js` which contains Popper.
- Tooltips are opt-in for performance reasons, so **you must initialize them yourself**.
- Tooltips with zero-length titles are never displayed.
- Specify `container: 'body'` to avoid rendering problems in more complex components (like our input groups, button groups, etc).
- Triggering tooltips on hidden elements will not work.
- Tooltips for `.disabled` or `disabled` elements must be triggered on a wrapper element.
- When triggered from hyperlinks that span multiple lines, tooltips will be centered. Use `white-space: nowrap;` on your `<a>` s to avoid this behavior.
- Tooltips must be hidden before their corresponding elements have been removed from the DOM.
- Tooltips can be triggered thanks to an element inside a shadow DOM.

Got all that? Great, let’s see how they work with some examples.

By default, this component uses the built-in content sanitizer, which strips out any HTML elements that are not explicitly allowed. See the [sanitizer section in our JavaScript documentation](https://getbootstrap.com/docs/5.3/getting-started/javascript/#sanitizer) for more details.

The animation effect of this component is dependent on the `prefers-reduced-motion` media query. See the [reduced motion section of our accessibility documentation](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#reduced-motion).

## Examples [Link to this section: Examples](https://getbootstrap.com/docs/5.3/components/tooltips/\#examples)

### Enable tooltips [Link to this section: Enable tooltips](https://getbootstrap.com/docs/5.3/components/tooltips/\#enable-tooltips)

As mentioned above, you must initialize tooltips before they can be used. One way to initialize all tooltips on a page would be to select them by their `data-bs-toggle` attribute, like so:

```js
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]')
const tooltipList = [...tooltipTriggerList].map(tooltipTriggerEl => new bootstrap.Tooltip(tooltipTriggerEl))

```

### Tooltips on links [Link to this section: Tooltips on links](https://getbootstrap.com/docs/5.3/components/tooltips/\#tooltips-on-links)

Hover over the links below to see tooltips:

Placeholder text to demonstrate some [inline links](https://getbootstrap.com/docs/5.3/components/tooltips/#) with tooltips. This is now just filler, no killer. Content placed here just to mimic the presence of [real text](https://getbootstrap.com/docs/5.3/components/tooltips/#). And all that just to give you an idea of how tooltips would look when used in real-world situations. So hopefully you’ve now seen how [these tooltips on links](https://getbootstrap.com/docs/5.3/components/tooltips/#) can work in practice, once you use them on [your own](https://getbootstrap.com/docs/5.3/components/tooltips/#) site or project.

html

```html
<p class="muted">Placeholder text to demonstrate some <a href="#" data-bs-toggle="tooltip" data-bs-title="Default tooltip">inline links</a> with tooltips. This is now just filler, no killer. Content placed here just to mimic the presence of <a href="#" data-bs-toggle="tooltip" data-bs-title="Another tooltip">real text</a>. And all that just to give you an idea of how tooltips would look when used in real-world situations. So hopefully you’ve now seen how <a href="#" data-bs-toggle="tooltip" data-bs-title="Another one here too">these tooltips on links</a> can work in practice, once you use them on <a href="#" data-bs-toggle="tooltip" data-bs-title="The last tip!">your own</a> site or project.</p>
```

Feel free to use either `title` or `data-bs-title` in your HTML. When `title` is used, Popper will replace it automatically with `data-bs-title` when the element is rendered.

### Custom tooltips [Link to this section: Custom tooltips](https://getbootstrap.com/docs/5.3/components/tooltips/\#custom-tooltips)

Added in v5.2.0

You can customize the appearance of tooltips using [CSS variables](https://getbootstrap.com/docs/5.3/components/tooltips/#variables). We set a custom class with `data-bs-custom-class="custom-tooltip"` to scope our custom appearance and use it to override a local CSS variable.

[site/src/scss/\_component-examples.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/scss/_component-examples.scss)

```scss
.custom-tooltip {
  --bs-tooltip-bg: var(--bd-violet-bg);
  --bs-tooltip-color: var(--bs-white);
}

```

Custom tooltip

html

```html
<button type="button" class="btn btn-secondary"
        data-bs-toggle="tooltip" data-bs-placement="top"
        data-bs-custom-class="custom-tooltip"
        data-bs-title="This top tooltip is themed via CSS variables.">
  Custom tooltip
</button>
```

### Directions [Link to this section: Directions](https://getbootstrap.com/docs/5.3/components/tooltips/\#directions)

Hover over the buttons below to see the four tooltips directions: top, right, bottom, and left. Directions are mirrored when using Bootstrap in RTL.

Tooltip on topTooltip on rightTooltip on bottomTooltip on leftTooltip with HTML

```html
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="top" data-bs-title="Tooltip on top">
  Tooltip on top
</button>
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="right" data-bs-title="Tooltip on right">
  Tooltip on right
</button>
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Tooltip on bottom">
  Tooltip on bottom
</button>
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="left" data-bs-title="Tooltip on left">
  Tooltip on left
</button>

```

And with custom HTML added:

```html
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-html="true" data-bs-title="<em>Tooltip</em> <u>with</u> <b>HTML</b>">
  Tooltip with HTML
</button>

```

With an SVG:

[Hover or focus to see default tooltip](https://getbootstrap.com/docs/5.3/components/tooltips/#)

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/components/tooltips/\#css)

### Variables [Link to this section: Variables](https://getbootstrap.com/docs/5.3/components/tooltips/\#variables)

Added in v5.2.0

As part of Bootstrap’s evolving CSS variables approach, tooltips now use local CSS variables on `.tooltip` for enhanced real-time customization. Values for the CSS variables are set via Sass, so Sass customization is still supported, too.

[scss/\_tooltip.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_tooltip.scss)

```scss
--#{$prefix}tooltip-zindex: #{$zindex-tooltip};
--#{$prefix}tooltip-max-width: #{$tooltip-max-width};
--#{$prefix}tooltip-padding-x: #{$tooltip-padding-x};
--#{$prefix}tooltip-padding-y: #{$tooltip-padding-y};
--#{$prefix}tooltip-margin: #{$tooltip-margin};
@include rfs($tooltip-font-size, --#{$prefix}tooltip-font-size);
--#{$prefix}tooltip-color: #{$tooltip-color};
--#{$prefix}tooltip-bg: #{$tooltip-bg};
--#{$prefix}tooltip-border-radius: #{$tooltip-border-radius};
--#{$prefix}tooltip-opacity: #{$tooltip-opacity};
--#{$prefix}tooltip-arrow-width: #{$tooltip-arrow-width};
--#{$prefix}tooltip-arrow-height: #{$tooltip-arrow-height};

```

### Sass variables [Link to this section: Sass variables](https://getbootstrap.com/docs/5.3/components/tooltips/\#sass-variables)

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$tooltip-font-size:                 $font-size-sm;
$tooltip-max-width:                 200px;
$tooltip-color:                     var(--#{$prefix}body-bg);
$tooltip-bg:                        var(--#{$prefix}emphasis-color);
$tooltip-border-radius:             var(--#{$prefix}border-radius);
$tooltip-opacity:                   .9;
$tooltip-padding-y:                 $spacer * .25;
$tooltip-padding-x:                 $spacer * .5;
$tooltip-margin:                    null; // TODO: remove this in v6

$tooltip-arrow-width:               .8rem;
$tooltip-arrow-height:              .4rem;
// fusv-disable
$tooltip-arrow-color:               null; // Deprecated in Bootstrap 5.2.0 for CSS variables
// fusv-enable

```

## Usage [Link to this section: Usage](https://getbootstrap.com/docs/5.3/components/tooltips/\#usage)

The tooltip plugin generates content and markup on demand, and by default places tooltips after their trigger element. Trigger the tooltip via JavaScript:

```js
const exampleEl = document.getElementById('example')
const tooltip = new bootstrap.Tooltip(exampleEl, options)

```

Tooltips automatically attempt to change positions when a parent container has `overflow: auto` or `overflow: scroll`, but still keeps the original placement’s positioning. Set the [`boundary` option](https://popper.js.org/docs/v2/modifiers/flip/#boundary) (for the flip modifier using the `popperConfig` option) to any HTMLElement to override the default value, `'clippingParents'`, such as `document.body`:

```js
const tooltip = new bootstrap.Tooltip('#example', {
  boundary: document.body // or document.querySelector('#boundary')
})

```

### Markup [Link to this section: Markup](https://getbootstrap.com/docs/5.3/components/tooltips/\#markup)

The required markup for a tooltip is only a `data` attribute and `title` on the HTML element you wish to have a tooltip. The generated markup of a tooltip is rather simple, though it does require a position (by default, set to `top` by the plugin).

**Keep tooltips accessible to keyboard and assistive technology users** by only adding them to HTML elements that are traditionally keyboard-focusable and interactive (such as links or form controls). While other HTML elements can be made focusable by adding `tabindex="0"`, this can create annoying and confusing tab stops on non-interactive elements for keyboard users, and most assistive technologies currently do not announce tooltips in this situation. Additionally, do not rely solely on `hover` as the trigger for your tooltips as this will make them impossible to trigger for keyboard users.

```html
<!-- HTML to write -->
<a href="#" data-bs-toggle="tooltip" data-bs-title="Some tooltip text!">Hover over me</a>

<!-- Generated markup by the plugin -->
<div class="tooltip bs-tooltip-auto" role="tooltip">
  <div class="tooltip-arrow"></div>
  <div class="tooltip-inner">
    Some tooltip text!
  </div>
</div>

```

### Disabled elements [Link to this section: Disabled elements](https://getbootstrap.com/docs/5.3/components/tooltips/\#disabled-elements)

Elements with the `disabled` attribute aren’t interactive, meaning users cannot focus, hover, or click them to trigger a tooltip (or popover). As a workaround, you’ll want to trigger the tooltip from a wrapper `<div>` or `<span>`, ideally made keyboard-focusable using `tabindex="0"`.

Disabled button

html

```html
<span class="d-inline-block" tabindex="0" data-bs-toggle="tooltip" data-bs-title="Disabled tooltip">
  <button class="btn btn-primary" type="button" disabled>Disabled button</button>
</span>
```

### Options [Link to this section: Options](https://getbootstrap.com/docs/5.3/components/tooltips/\#options)

As options can be passed via data attributes or JavaScript, you can append an option name to `data-bs-`, as in `data-bs-animation="{value}"`. Make sure to change the case type of the option name from “ _camelCase_” to “ _kebab-case_” when passing the options via data attributes. For example, use `data-bs-custom-class="beautifier"` instead of `data-bs-customClass="beautifier"`.

As of Bootstrap 5.2.0, all components support an **experimental** reserved data attribute `data-bs-config` that can house simple component configuration as a JSON string. When an element has `data-bs-config='{"delay":0, "title":123}'` and `data-bs-title="456"` attributes, the final `title` value will be `456` and the separate data attributes will override values given on `data-bs-config`. In addition, existing data attributes are able to house JSON values like `data-bs-delay='{"show":0,"hide":150}'`.

The final configuration object is the merged result of `data-bs-config`, `data-bs-`, and `js object` where the latest given key-value overrides the others.

Note that for security reasons the `sanitize`, `sanitizeFn`, and `allowList` options cannot be supplied using data attributes.

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| `allowList` | object | [Default value](https://getbootstrap.com/docs/5.3/getting-started/javascript#sanitizer) | An object containing allowed tags and attributes. Those not explicitly allowed will be removed by [the content sanitizer](https://getbootstrap.com/docs/5.3/getting-started/javascript#sanitizer). <br>**Exercise caution when adding to this list.** Refer to [OWASP’s Cross Site Scripting Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) for more information. |
| `animation` | boolean | `true` | Apply a CSS fade transition to the tooltip. |
| `boundary` | string, element | `'clippingParents'` | Overflow constraint boundary of the tooltip (applies only to Popper’s preventOverflow modifier). By default, it’s `'clippingParents'` and can accept an HTMLElement reference (via JavaScript only). For more information refer to Popper’s [detectOverflow docs](https://popper.js.org/docs/v2/utils/detect-overflow/#boundary). |
| `container` | string, element, false | `false` | Appends the tooltip to a specific element. Example: `container: 'body'`. This option is particularly useful in that it allows you to position the tooltip in the flow of the document near the triggering element - which will prevent the tooltip from floating away from the triggering element during a window resize. |
| `customClass` | string, function | `''` | Add classes to the tooltip when it is shown. Note that these classes will be added in addition to any classes specified in the template. To add multiple classes, separate them with spaces: `'class-1 class-2'`. You can also pass a function that should return a single string containing additional class names. |
| `delay` | number, object | `0` | Delay showing and hiding the tooltip (ms)—doesn’t apply to manual trigger type. If a number is supplied, delay is applied to both hide/show. Object structure is: `delay: { "show": 500, "hide": 100 }`. |
| `fallbackPlacements` | array | `['top', 'right', 'bottom', 'left']` | Define fallback placements by providing a list of placements in array (in order of preference). For more information refer to Popper’s [behavior docs](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements). |
| `html` | boolean | `false` | Allow HTML in the tooltip. If true, HTML tags in the tooltip’s `title` will be rendered in the tooltip. If false, `innerText` property will be used to insert content into the DOM. Prefer text when dealing with user-generated input to [prevent XSS attacks](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html). |
| `offset` | array, string, function | `[0, 6]` | Offset of the tooltip relative to its target. You can pass a string in data attributes with comma separated values like: `data-bs-offset="10,20"`. When a function is used to determine the offset, it is called with an object containing the popper placement, the reference, and popper rects as its first argument. The triggering element DOM node is passed as the second argument. The function must return an array with two numbers: [skidding](https://popper.js.org/docs/v2/modifiers/offset/#skidding-1), [distance](https://popper.js.org/docs/v2/modifiers/offset/#distance-1). For more information refer to Popper’s [offset docs](https://popper.js.org/docs/v2/modifiers/offset/#options). |
| `placement` | string, function | `'top'` | How to position the tooltip: auto, top, bottom, left, right. When `auto` is specified, it will dynamically reorient the tooltip. When a function is used to determine the placement, it is called with the tooltip DOM node as its first argument and the triggering element DOM node as its second. The `this` context is set to the tooltip instance. |
| `popperConfig` | null, object, function | `null` | To change Bootstrap’s default Popper config, see [Popper’s configuration](https://popper.js.org/docs/v2/constructors/#options). When a function is used to create the Popper configuration, it’s called with an object that contains the Bootstrap’s default Popper configuration. It helps you use and merge the default with your own configuration. The function must return a configuration object for Popper. |
| `sanitize` | boolean | `true` | Enable [content sanitization](https://getbootstrap.com/docs/5.3/getting-started/javascript#sanitizer). If true, the `template`, `content` and `title` options will be sanitized. <br>**Exercise caution when disabling content sanitization.** Refer to [OWASP’s Cross Site Scripting Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) for more information. Vulnerabilities caused solely by disabling content sanitization are not considered within scope for Bootstrap’s security model. |
| `sanitizeFn` | null, function | `null` | Provide an alternative [content sanitization](https://getbootstrap.com/docs/5.3/getting-started/javascript#sanitizer) function. This can be useful if you prefer to use a dedicated library to perform sanitization. |
| `selector` | string, false | `false` | If a selector is provided, tooltip objects will be delegated to the specified targets. In practice, this is used to also apply tooltips to dynamically added DOM elements ( `jQuery.on` support). See [this issue](https://github.com/twbs/bootstrap/issues/4215) and [an informative example](https://codepen.io/Johann-S/pen/djJYPb). **Note**: `title` attribute must not be used as a selector. |
| `template` | string | `'<div class="tooltip" role="tooltip"><div class="tooltip-arrow"></div><div class="tooltip-inner"></div></div>'` | Base HTML to use when creating the tooltip. The tooltip’s `title` will be injected into the `.tooltip-inner`. `.tooltip-arrow` will become the tooltip’s arrow. The outermost wrapper element should have the `.tooltip` class and `role="tooltip"`. |
| `title` | string, element, function | `''` | The tooltip title. If a function is given, it will be called with its `this` reference set to the element that the popover is attached to. |
| `trigger` | string | `'hover focus'` | How tooltip is triggered: click, hover, focus, manual. You may pass multiple triggers; separate them with a space. `'manual'` indicates that the tooltip will be triggered programmatically via the `.tooltip('show')`, `.tooltip('hide')` and `.tooltip('toggle')` methods; this value cannot be combined with any other trigger. `'hover'` on its own will result in tooltips that cannot be triggered via the keyboard, and should only be used if alternative methods for conveying the same information for keyboard users is present. |

#### Data attributes for individual tooltips [Link to this section: Data attributes for individual tooltips](https://getbootstrap.com/docs/5.3/components/tooltips/\#data-attributes-for-individual-tooltips)

Options for individual tooltips can alternatively be specified through the use of data attributes, as explained above.

#### Using function with `popperConfig` [Link to this section: Using function with ](https://getbootstrap.com/docs/5.3/components/tooltips/\#using-function-with-popperconfig)

```js
const tooltip = new bootstrap.Tooltip(element, {
  popperConfig(defaultBsPopperConfig) {
    // const newPopperConfig = {...}
    // use defaultBsPopperConfig if needed...
    // return newPopperConfig
  }
})

```

### Methods [Link to this section: Methods](https://getbootstrap.com/docs/5.3/components/tooltips/\#methods)

**All API methods are asynchronous and start a transition.** They return to the caller as soon as the transition is started, but before it ends. In addition, a method call on a transitioning component will be ignored. [Learn more in our JavaScript docs.](https://getbootstrap.com/docs/5.3/getting-started/javascript/#asynchronous-functions-and-transitions)

| Method | Description |
| --- | --- |
| `disable` | Removes the ability for an element’s tooltip to be shown. The tooltip will only be able to be shown if it is re-enabled. |
| `dispose` | Hides and destroys an element’s tooltip (Removes stored data on the DOM element). Tooltips that use delegation (which are created using [the `selector` option](https://getbootstrap.com/docs/5.3/components/tooltips/#options)) cannot be individually destroyed on descendant trigger elements. |
| `enable` | Gives an element’s tooltip the ability to be shown. **Tooltips are enabled by default.** |
| `getInstance` | _Static_ method which allows you to get the tooltip instance associated with a DOM element. |
| `getOrCreateInstance` | _Static_ method which allows you to get the tooltip instance associated with a DOM element, or create a new one in case it wasn’t initialized. |
| `hide` | Hides an element’s tooltip. **Returns to the caller before the tooltip has actually been hidden** (i.e. before the `hidden.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip. |
| `setContent` | Gives a way to change the tooltip’s content after its initialization. |
| `show` | Reveals an element’s tooltip. **Returns to the caller before the tooltip has actually been shown** (i.e. before the `shown.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip. Tooltips with zero-length titles are never displayed. |
| `toggle` | Toggles an element’s tooltip. **Returns to the caller before the tooltip has actually been shown or hidden** (i.e. before the `shown.bs.tooltip` or `hidden.bs.tooltip` event occurs). This is considered a “manual” triggering of the tooltip. |
| `toggleEnabled` | Toggles the ability for an element’s tooltip to be shown or hidden. |
| `update` | Updates the position of an element’s tooltip. |

```js
const tooltip = bootstrap.Tooltip.getInstance('#example') // Returns a Bootstrap tooltip instance

// setContent example
tooltip.setContent({ '.tooltip-inner': 'another title' })

```

The `setContent` method accepts an `object` argument, where each property-key is a valid `string` selector within the tooltip template, and each related property-value can be `string` \| `element` \| `function` \| `null`

### Events [Link to this section: Events](https://getbootstrap.com/docs/5.3/components/tooltips/\#events)

| Event | Description |
| --- | --- |
| `hide.bs.tooltip` | This event is fired immediately when the `hide` instance method has been called. |
| `hidden.bs.tooltip` | This event is fired when the tooltip has finished being hidden from the user (will wait for CSS transitions to complete). |
| `inserted.bs.tooltip` | This event is fired after the `show.bs.tooltip` event when the tooltip template has been added to the DOM. |
| `show.bs.tooltip` | This event fires immediately when the `show` instance method is called. |
| `shown.bs.tooltip` | This event is fired when the tooltip has been made visible to the user (will wait for CSS transitions to complete). |

```js
const myTooltipEl = document.getElementById('myTooltip')
const tooltip = bootstrap.Tooltip.getOrCreateInstance(myTooltipEl)

myTooltipEl.addEventListener('hidden.bs.tooltip', () => {
  // do something...
})

tooltip.hide()

```