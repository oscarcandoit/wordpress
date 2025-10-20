---
url: https://api.jquery.com/bind/
scraped_at: 2025-10-20T03:08:53.088Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .bind( eventType \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** Attach a handler to an event for the elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.bind( eventType \[, eventData \], handler )](https://api.jquery.com/bind/\#bind-eventType-eventData-handler)

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing one or more DOM event types, such as "click" or "submit," or custom event names.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.bind( eventType \[, eventData \] \[, preventBubble \] )](https://api.jquery.com/bind/\#bind-eventType-eventData-preventBubble)

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing one or more DOM event types, such as "click" or "submit," or custom event names.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **preventBubble**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    Setting the third argument to false will attach a function that prevents the default action from occurring and stops the event from bubbling. The default is true.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.bind( events )](https://api.jquery.com/bind/\#bind-events)

  - **events**

    Type: [Object](http://api.jquery.com/Types/#Object)

    An object containing one or more DOM event types and functions to execute for them.

As of jQuery 3.0, `.bind()` has been deprecated. It was superseded by the [`.on()`](https://api.jquery.com/on/) method for attaching event handlers to a document since jQuery 1.7, so its use was already discouraged. For earlier versions, the `.bind()` method is used for attaching an event handler directly to elements. Handlers are attached to the currently selected elements in the jQuery object, so those elements _must exist_ at the point the call to `.bind()` occurs. For more flexible event binding, see the discussion of event delegation in [`.on()`](https://api.jquery.com/on/).

Any string is legal for `eventType`; if the string is not the name of a native DOM event, then the handler is bound to a custom event. These events are never called by the browser, but may be triggered manually from other JavaScript code using `.trigger()` or `.triggerHandler()`.

If the `eventType` string contains a period ( `.`) character, then the event is namespaced. The period character separates the event from its namespace. For example, in the call `.bind( "click.name", handler )`, the string `click` is the event type, and the string `name` is the namespace. Namespacing allows us to unbind or trigger some events of a type without affecting others. See the discussion of `.unbind()` for more information.

Some events have dedicated pages, describing specifics of their usage. For a complete list of those events, see the [events category](https://api.jquery.com/category/events/).

When an event reaches an element, all handlers bound to that event type for the element are fired. If there are multiple handlers registered, they will always execute in the order in which they were bound. After all handlers have executed, the event continues along the normal event propagation path.

A basic usage of `.bind()` is:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This code will cause the element with an ID of `foo` to respond to the `click` event. When a user clicks inside this element thereafter, the alert will be shown.

#### Multiple Events

Multiple event types can be bound at once by including each one separated by a space:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The effect of this on `<div id="foo">` (when it does not initially have the "entered" class) is to add the "entered" class when the mouse enters the `<div>` and remove the class when the mouse leaves.

As of jQuery 1.4 we can bind multiple event handlers simultaneously by passing an object of event type/handler pairs:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

#### Event Handlers

The `handler` parameter takes a callback function, as shown above. Within the handler, the keyword `this` refers to the DOM element to which the handler is bound. To make use of the element in jQuery, it can be passed to the normal `$()` function. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code is executed, when the user clicks inside the element with an ID of `foo`, its text contents will be shown as an alert.


As of jQuery 1.4.2 duplicate event handlers can be bound to an element instead of being discarded. This is useful when the event data feature is being used, or when other unique data resides in a closure around the event handler function.

In jQuery 1.4.3 you can now pass in `false` in place of an event handler. This will bind an event handler equivalent to: `function(){ return false; }`. This function can be removed at a later time by calling: `.unbind( eventName, false )`.

#### [The Event object](https://api.jquery.com/category/events/event-object/)

The `handler` callback function can also take parameters. When the function is called, the event object will be passed to the first parameter.

The event object is often unnecessary and the parameter omitted, as sufficient context is usually available when the handler is bound to know exactly what needs to be done when the handler is triggered. However, at times it becomes necessary to gather more information about the user's environment at the time the event was initiated. [View the full Event Object](https://api.jquery.com/category/events/event-object/).

Returning `false` from a handler is equivalent to calling both `.preventDefault()` and `.stopPropagation()` on the event object.

Using the event object in a handler looks like this:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

Note the parameter added to the anonymous function. This code will cause a click on the element with ID `foo` to report the page coordinates of the mouse cursor at the time of the click.

#### Passing Event Data

The optional `eventData` parameter is not commonly used. When provided, this argument allows us to pass additional information to the handler. One handy use of this parameter is to work around issues caused by closures. For example, suppose we have two event handlers that both refer to the same external variable:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

Because the handlers are closures that both have `message` in their environment, both will display the message `Not in the face!` when triggered. The variable's value has changed. To sidestep this, we can pass the message in using `eventData`:


|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12 | ```<br>``` |

This time the variable is not referred to directly within the handlers; instead, the variable is passed in _by value_ through `eventData`, which fixes the value at the time the event is bound. The first handler will now display `Spoon!` while the second will alert `Not in the face!`

Note that objects are passed to functions _by reference_, which further complicates this scenario.

If `eventData` is present, it is the second argument to the `.bind()` method; if no additional data needs to be sent to the handler, then the callback is passed as the second and final argument.

See the `.trigger()` method reference for a way to pass data to a handler at the time the event happens rather than when the handler is bound.

As of jQuery 1.4 we can no longer attach data (and thus, events) to object, embed, or applet elements because critical errors occur when attaching data to Java applets.

**Note:** Although demonstrated in the next example, it is inadvisable to bind handlers to both the `click` and `dblclick` events for the same element. The sequence of events triggered varies from browser to browser, with some receiving two click events before the `dblclick` and others only one. Double-click sensitivity (maximum time between clicks that is detected as a double click) can vary by operating system and browser, and is often user-configurable.

### Example 1

Handle click and double-click for the paragraph. Note: the coordinates are window relative, so in this case relative to the demo iframe.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo:

### Example 2

To display each paragraph's text in an alert box whenever it is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

You can pass some extra data before the event handler:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

### Example 4

Cancel a default action and prevent it from bubbling up by returning `false`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 5

Cancel only the default action by using the .preventDefault() method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 6

Stop an event from bubbling without preventing the default action by using the .stopPropagation() method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 7

Bind custom events.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 8

Bind multiple events simultaneously.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |