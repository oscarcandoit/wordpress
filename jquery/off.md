---
url: https://api.jquery.com/off/
scraped_at: 2025-10-20T03:13:47.371Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .off( events \[, selector \] \[, handler \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove an event handler.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.off( events \[, selector \] \[, handler \] )](https://api.jquery.com/off/\#off-events-selector-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more space-separated event types and optional namespaces, or just namespaces, such as "click", "keydown.myPlugin", or ".myPlugin".

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector which should match the one originally passed to `.on()` when attaching event handlers.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A handler function previously attached for the event(s), or the special value `false`.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.off( events \[, selector \] )](https://api.jquery.com/off/\#off-events-selector)

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object where the string keys represent one or more space-separated event types and optional namespaces, and the values represent handler functions previously attached for the event(s).

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector which should match the one originally passed to `.on()` when attaching event handlers.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.off( event )](https://api.jquery.com/off/\#off-event)

  - **event**

    Type: [Event](http://api.jquery.com/Types/#Event)

    A [`jQuery.Event`](https://api.jquery.com/category/events/event-object/) object.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.off()](https://api.jquery.com/off/\#off)

  - This signature does not accept any arguments.

The `.off()` method removes event handlers that were attached with [`.on()`](https://api.jquery.com/on/). See the discussion of delegated and directly bound events on that page for more information. Calling `.off()` with no arguments removes all handlers attached to the elements. Specific event handlers can be removed on elements by providing combinations of event names, namespaces, selectors, or handler function names. **When multiple filtering arguments are given, all of the arguments provided must match for the event handler to be removed.**

If a simple event name such as `"click"` is provided, _all_ events of that type (both direct and delegated) are removed from the elements in the jQuery set. When writing code that will be used as a plugin, or simply when working with a large code base, best practice is to attach and remove events using namespaces so that the code will not inadvertently remove event handlers attached by other code. All events of all types in a specific namespace can be removed from an element by providing just a namespace, such as `".myPlugin"`. At minimum, either a namespace or event name must be provided.

To remove specific delegated event handlers, provide a `selector` argument. The selector string must exactly match the one passed to `.on()` when the event handler was attached. To remove all delegated events from an element without removing non-delegated events, use the special value `"**"`.

A handler can also be removed by specifying the function name in the `handler` argument. When jQuery attaches an event handler, it assigns a unique id to the handler function. Handlers proxied by [`jQuery.proxy()`](https://api.jquery.com/jQuery.proxy/) or a similar mechanism will all have the same unique id (the proxy function), so passing proxied handlers to `.off` may remove more handlers than intended. In those situations it is better to attach and remove event handlers using namespaces.

As with `.on()`, you can pass `events` as an object instead of specifying an `events` string and `handler` function as separate arguments. The keys for the `events` object are events and/or namespaces; the values are handler functions or the special value `false`.

### Example 1

Add and remove event handlers on the colored button.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43 | ```<br>``` |

#### Demo:

### Example 2

Remove all event handlers from all paragraphs:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Remove all delegated click handlers from all paragraphs:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Remove just one previously bound handler by passing it as the third argument:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

### Example 5

Unbind all delegated event handlers by their namespace:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |