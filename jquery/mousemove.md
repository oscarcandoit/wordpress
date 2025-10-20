---
url: https://api.jquery.com/mousemove/
scraped_at: 2025-10-20T03:13:27.567Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "mousemove" event, or trigger that event on an element.

#### Contents:

- [.on( "mousemove" \[, eventData \], handler )](https://api.jquery.com/mousemove/#on1)  - [.on( "mousemove" \[, eventData \], handler )](https://api.jquery.com/mousemove/#on-%22mousemove%22-eventData-handler)
- [.trigger( "mousemove" )](https://api.jquery.com/mousemove/#trigger2)  - [.trigger( "mousemove" )](https://api.jquery.com/mousemove/#trigger-%22mousemove%22)

## .on( "mousemove" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "mousemove" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "mousemove" \[, eventData \], handler )](https://api.jquery.com/mousemove/\#on-%22mousemove%22-eventData-handler)

  - **"mousemove"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mousemove"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `mousemove` event. For the deprecated `.mousemove()` method, see [`.mousemove()`](https://api.jquery.com/mousemove-shorthand/).

The `mousemove` event is sent to an element when the mouse pointer moves inside the element. Any HTML element can receive this event.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The event handler can be bound to the target:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Now when the mouse pointer moves within the target button, the messages are appended to <div id="log">:

``Handler for `mousemove` called at (399, 48)``

``Handler for `mousemove` called at (398, 46)``

``Handler for `mousemove` called at (397, 44)``

``Handler for `mousemove` called at (396, 42)``

To trigger the event manually, use `.trigger( "mousemove" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on the Trigger button will also append the message:

``Handler for `mousemove` called at (undefined, undefined)``

When tracking mouse movement, you usually need to know the actual position of the mouse pointer. The event object that is passed to the handler contains some information about the mouse coordinates. Properties such as `.clientX`, `.offsetX`, and `.pageX` are available, but support for them differs between browsers. Fortunately, jQuery normalizes the `.pageX` and `.pageY` properties so that they can be used in all browsers. These properties provide the X and Y coordinates of the mouse pointer relative to the top-left corner of the document, as illustrated in the example output above.

Keep in mind that the `mousemove` event is triggered whenever the mouse pointer moves, even for a pixel. This means that hundreds of events can be generated over a very small amount of time. If the handler has to do any significant processing, or if multiple handlers for the event exist, this can be a serious performance drain on the browser. It is important, therefore, to optimize `mousemove ` handlers as much as possible, and to unbind them as soon as they are no longer needed.

A common pattern is to bind the `mousemove` handler from within a `mousedown` handler, and to unbind it from a corresponding `mouseup` handler. If implementing this sequence of events, remember that the `mouseup` event might be sent to a different HTML element than the `mousemove` event was. To account for this, the `mouseup` handler should typically be bound to an element high up in the DOM tree, such as `<body>`.

Show the mouse coordinates when the mouse is moved over the yellow div. Coordinates are relative to the window, which in this case is the iframe.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49 | ```<br>``` |

#### Demo:

## .trigger( "mousemove" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "mousemove" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "mousemove" )](https://api.jquery.com/mousemove/\#trigger-%22mousemove%22)

  - **"mousemove"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mousemove"`.

See the description for [`.on( "mousemove", ... )`](https://api.jquery.com/mousemove/#on1).