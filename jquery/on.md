---
url: https://api.jquery.com/on/
scraped_at: 2025-10-20T03:13:51.365Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( events \[, selector \] \[, data \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Attach an event handler function for one or more events to the selected elements.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( events \[, selector \] \[, data \], handler )](https://api.jquery.com/on/\#on-events-selector-data-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more space-separated event types and optional namespaces, such as "click" or "keydown.myPlugin".

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector string to filter the descendants of the selected elements that trigger the event. If the selector is `null` or omitted, the event is always triggered when it reaches the selected element.

  - **data**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Data to be passed to the handler in [`event.data`](https://api.jquery.com/event.data/) when an event is triggered.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject \[, [Anything](http://api.jquery.com/Types/#Anything) extraParameter \] \[, ... \] )

    A function to execute when the event is triggered. The value `false` is also allowed as a shorthand for a function that simply does `return false`.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( events \[, selector \] \[, data \] )](https://api.jquery.com/on/\#on-events-selector-data)

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object in which the string keys represent one or more space-separated event types and optional namespaces, and the values represent a handler function to be called for the event(s).

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector string to filter the descendants of the selected elements that will call the handler. If the selector is null or omitted, the handler is always called when it reaches the selected element.

  - **data**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Data to be passed to the handler in [`event.data`](https://api.jquery.com/event.data/) when an event occurs.

The `.on()` method attaches event handlers to the currently selected set of elements in the jQuery object. As of jQuery 1.7, the `.on()` method provides all functionality required for attaching event handlers. For help in converting from older jQuery event methods, see [`.bind()`](https://api.jquery.com/bind/), [`.delegate()`](https://api.jquery.com/delegate/), and [`.live()`](https://api.jquery.com/live/). To remove events bound with `.on()`, see [`.off()`](https://api.jquery.com/off/). To attach an event that runs only once and then removes itself, see [`.one()`](https://api.jquery.com/one/)

## Event names and namespaces

Any event names can be used for the `events` argument. jQuery will pass through the browser's standard JavaScript event types, calling the `handler` function when the browser generates events due to user actions such as `click`. In addition, the [`.trigger()`](https://api.jquery.com/trigger/) method can trigger both standard browser event names and custom event names to call attached handlers. Event names should only contain alphanumerics, underscore, and colon characters.

An event name can be qualified by _event namespaces_ that simplify removing or triggering the event. For example, `"click.myPlugin.simple"` defines both the myPlugin and simple namespaces for this particular click event. A click event handler attached via that string could be removed with `.off("click.myPlugin")` or `.off("click.simple")` without disturbing other click handlers attached to the elements. Namespaces are similar to CSS classes in that they are not hierarchical; only one name needs to match. Namespaces should contain upper/lowercase letters and digits only.

In the second form of `.on()`, the `events` argument is a plain object. The keys are strings in the same form as the `events` argument with space-separated event type names and optional namespaces. The value for each key is a function (or `false` value) that is used as the `handler` instead of the final argument to the method. In other respects, the two forms are identical in their behavior as described below.

## Direct and delegated event handlers

The majority of browser events _bubble_, or _propagate_, from the deepest, innermost element (the **event target**) in the document where they occur all the way up to the body and the `document` element. In Internet Explorer 8 and lower, a few events such as `change` and `submit` do not natively bubble but jQuery patches these to bubble and create consistent cross-browser behavior.

If `selector` is omitted or is null, the event handler is referred to as _direct_ or _directly-bound_. The handler is called every time an event occurs on the selected elements, whether it occurs directly on the element or bubbles from a descendant (inner) element.

When a `selector` is provided, the event handler is referred to as _delegated_. The handler is not called when the event occurs directly on the bound element, but only for descendants (inner elements) that match the selector. jQuery bubbles the event from the event target up to the element where the handler is attached (i.e., innermost to outermost element) and runs the handler for any elements along that path matching the selector.

**Event handlers are bound only to the currently selected elements; they must exist at the time your code makes the call to `.on()`**. To ensure the elements are present and can be selected, place scripts after the elements in the HTML markup or perform event binding inside a document ready handler. Alternatively, use delegated event handlers to attach event handlers.

**Delegated event handlers** have the advantage that they can process events from _descendant elements_ that are added to the document at a later time. By picking an element that is guaranteed to be present at the time the delegated event handler is attached, you can use delegated event handlers to avoid the need to frequently attach and remove event handlers. This element could be the container element of a view in a Model-View-Controller design, for example, or `document` if the event handler wants to monitor all bubbling events in the document. The `document` element is available in the `head` of the document before loading any other HTML, so it is safe to attach events there without waiting for the document to be ready.

In addition to their ability to handle events on descendant elements not yet created, another advantage of delegated event handlers is their potential for much lower overhead when many elements must be monitored. On a data table with 1,000 rows in its `tbody`, this example attaches a handler to 1,000 elements:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

An event-delegation approach attaches an event handler to only one element, the tbody, and the event only needs to bubble up one level (from the clicked `tr` to `tbody`):

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

**Note:** Delegated event handlers do not work for SVG.

## The event handler and its environment

The `handler` argument is a function (or the value `false`, see below), and is required unless you pass an object for the `events` argument. You can provide an anonymous handler function at the point of the `.on()` call, as the examples have done above, or declare a named function and pass its name:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

When the browser triggers an event or other JavaScript calls jQuery's `.trigger()` method, jQuery passes the handler an [`Event`](https://api.jquery.com/category/events/event-object/) object it can use to analyze and change the status of the event. This object is a _normalized subset_ of data provided by the browser; the browser's unmodified native event object is available in `event.originalEvent`. For example, [`event.type`](https://api.jquery.com/event.type/) contains the event name (e.g., "resize") and [`event.target`](https://api.jquery.com/event.target/) indicates the deepest (innermost) element where the event occurred.

By default, most events bubble up from the original event target to the `document` element. At each element along the way, jQuery calls any matching event handlers that have been attached. A handler can prevent the event from bubbling further up the document tree (and thus prevent handlers on those elements from running) by calling `event.stopPropagation()`. Any other handlers attached on the current element _will_ run however. To prevent that, call `event.stopImmediatePropagation()`. (Event handlers bound to an element are called in the same order that they were bound.)

Similarly, a handler can call `event.preventDefault()` to cancel any default action that the browser may have for this event; for example, the default action on a `click` event is to follow the link. Not all browser events have default actions, and not all default actions can be canceled. See the [W3C Events Specification](https://www.w3.org/TR/DOM-Level-3-Events/#event-types-list) for details.

Returning `false` from an event handler will automatically call `event.stopPropagation()` and `event.preventDefault()`. A `false` value can also be passed for the `handler` as a shorthand for `function(){ return false; }`. So, `$( "a.disabled" ).on( "click", false );` attaches an event handler to all links with class "disabled" that prevents them from being followed when they are clicked and also stops the event from bubbling.

When jQuery calls a handler, the `this` keyword is a reference to the element where the event is being delivered; for directly bound events this is the element where the event was attached and for delegated events this is an element matching `selector`. (Note that `this` may not be equal to `event.target` if the event has bubbled from a descendant element.) To create a jQuery object from the element so that it can be used with jQuery methods, use `$( this )`.

## Passing data to the handler

If a `data` argument is provided to `.on()` and is not `null` or `undefined`, it is passed to the handler in the [`event.data`](https://api.jquery.com/event.data/) property each time an event is triggered. The `data` argument can be any type, but if a string is used the `selector` must either be provided or explicitly passed as `null` so that the data is not mistaken for a selector. Best practice is to use a plain object so that multiple values can be passed as properties.

As of jQuery 1.4, the same event handler can be bound to an element multiple times. This is especially useful when the `event.data` feature is being used, or when other unique data resides in a closure around the event handler function. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

The above code will generate two different alerts when the button is clicked.

As an alternative or in addition to the `data` argument provided to the `.on()` method, you can also pass data to an event handler using a second argument to [`.trigger()`](https://api.jquery.com/trigger/) or [`.triggerHandler()`](https://api.jquery.com/triggerHandler/). Data provided this way is passed to the event handler as further parameters after the `Event` object. If an array was passed to the second argument of `.trigger()` or `.triggerHandler()`, each element in the array will be presented to the event handler as an individual parameter.

## Event performance

In most cases, an event such as `click` occurs infrequently and performance is not a significant concern. However, high frequency events such as `mousemove` or `scroll` can fire dozens of times per second, and in those cases it becomes more important to use events judiciously. Performance can be increased by reducing the amount of work done in the handler itself, caching information needed by the handler rather than recalculating it, or by rate-limiting the number of actual page updates using `setTimeout`.

Attaching many delegated event handlers near the top of the document tree can degrade performance. Each time the event occurs, jQuery must compare all selectors of all attached events of that type to every element in the path from the event target up to the top of the document. For best performance, attach delegated events at a document location as close as possible to the target elements. Avoid excessive use of `document` or `document.body` for delegated events on large documents.

jQuery can process simple selectors of the form `tag#id.class` very quickly when they are used to filter delegated events. So, `"#myForm"`, `"a.external"`, and `"button"` are all fast selectors. Delegated events that use more complex selectors, particularly hierarchical ones, can be several times slower--although they are still fast enough for most applications. Hierarchical selectors can often be avoided simply by attaching the handler to a more appropriate point in the document. For example, instead of `$( "body" ).on( "click", "#commentForm .addNew", addComment )` use `$( "#commentForm" ).on( "click", ".addNew", addComment )`.

## Additional notes

Some events have dedicated pages, describing specifics of their usage. For a complete list of those events, see the [events category](https://api.jquery.com/category/events/).

_Deprecated in jQuery 1.8, removed in 1.9:_ The name `"hover"` used as a shorthand for the string `"mouseenter mouseleave"`. It attaches a _single event handler_ for those two events, and the handler must examine `event.type` to determine whether the event is `mouseenter` or `mouseleave`. Do not confuse the "hover" pseudo-event-name with the [`.hover()`](https://api.jquery.com/hover/) method, which accepts _one or two_ functions.

jQuery's event system requires that a DOM element allow attaching data via a property on the element, so that events can be tracked and delivered. The `object`, `embed`, and `applet` elements cannot attach data, and therefore cannot have jQuery events bound to them.

The `focus` and `blur` events are specified by the W3C to not bubble, but jQuery defines cross-browser `focusin` and `focusout` events that do bubble. When `focus` and `blur` are used to attach delegated event handlers, jQuery maps the names and delivers them as `focusin` and `focusout` respectively. For consistency and clarity, use the bubbling event type names.

In all browsers, the `load`, `scroll`, and `error` events (e.g., on an `<img>` element) do not bubble. In Internet Explorer 8 and lower, the `paste` and `reset` events do not bubble. Such events are not supported for use with delegation, but they _can_ be used when the event handler is directly attached to the element generating the event.

The `error` event on the `window` object uses nonstandard arguments and return value conventions, so it is not supported by jQuery. Instead, assign a handler function directly to the `window.onerror` property.

The handler list for an element is set when the event is first delivered. Adding or removing event handlers on the current element won't take effect until the next time the event is handled. To prevent any further event handlers from executing on an element within an event handler, call `event.stopImmediatePropagation()`. This behavior goes against the [W3C events specification](https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-EventTarget-removeEventListener). To better understand this case, consider the following code:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13 | ```<br>``` |

In the code above, `handler2` will be executed anyway the first time even if it's removed using [`.off()`](https://api.jquery.com/off/). However, the handler will not be executed the following times the `click` event is triggered.

### Example 1

Display a paragraph's text in an alert when it is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Pass data to the event handler, which is specified here by name:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Example 3

Cancel a form submit action and prevent the event from bubbling up by returning `false`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Cancel only the default action by using `.preventDefault()`.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 5

Stop submit events from bubbling without preventing form submit, using `.stopPropagation()`.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 6

Pass data to the event handler using the second argument to `.trigger()`

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Example 7

Use the second argument of `.trigger()` to pass an array of data to the event handler

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Example 8

Attach and trigger custom (non-browser) events.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 9

Attach multiple event handlers simultaneously using a plain object.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 10

Click any paragraph to add another after it. Note that `.on()` allows a click event on any paragraph--even new ones--since the event is handled by the ever-present body element after it bubbles to there.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 11

Display each paragraph's text in an alert box whenever it is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 12

Cancel a link's default action using the `.preventDefault()` method:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 13

Attach multiple events—one on `mouseenter` and one on `mouseleave` to the same element:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |