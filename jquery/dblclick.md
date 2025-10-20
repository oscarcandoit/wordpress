---
url: https://api.jquery.com/dblclick/
scraped_at: 2025-10-20T03:09:47.602Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "dblclick" event, or trigger that event on an element.

#### Contents:

- [.on( "dblclick" \[, eventData \], handler )](https://api.jquery.com/dblclick/#on1)  - [.on( "dblclick" \[, eventData \], handler )](https://api.jquery.com/dblclick/#on-%22dblclick%22-eventData-handler)
- [.trigger( "dblclick" )](https://api.jquery.com/dblclick/#trigger2)  - [.trigger( "dblclick" )](https://api.jquery.com/dblclick/#trigger-%22dblclick%22)

## .on( "dblclick" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "dblclick" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "dblclick" \[, eventData \], handler )](https://api.jquery.com/dblclick/\#on-%22dblclick%22-eventData-handler)

  - **"dblclick"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"dblclick"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `dblclick` event. For the deprecated `.dblclick()` method, see [`.dblclick()`](https://api.jquery.com/dblclick-shorthand/).

The `dblclick` event is sent to an element when the element is double-clicked. Any HTML element can receive this event.
For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_04.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any `<div>`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now double-clicking on this element displays the alert:

``Handler for `dblclick` called.``

To trigger the event manually, call `.trigger( "dblclick" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, (single) clicks on `Trigger the handler` will also alert the message.

The `dblclick` event is only triggered after this exact series of events:

- The mouse button is depressed while the pointer is inside the element.
- The mouse button is released while the pointer is inside the element.
- The mouse button is depressed again while the pointer is inside the element, within a time window that is system-dependent.
- The mouse button is released while the pointer is inside the element.

It is inadvisable to bind handlers to both the `click` and `dblclick` events for the same element. The sequence of events triggered varies from browser to browser, with some receiving two `click` events before the `dblclick` and others only one. Double-click sensitivity (maximum time between clicks that is detected as a double click) can vary by operating system and browser, and is often user-configurable.


### Example 1

To bind a "Hello World!" alert box to the dblclick event on every paragraph on the page:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Double click to toggle background color.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

## .trigger( "dblclick" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "dblclick" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "dblclick" )](https://api.jquery.com/dblclick/\#trigger-%22dblclick%22)

  - **"dblclick"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"dblclick"`.

See the description for [`.on( "dblclick", ... )`](https://api.jquery.com/dblclick/#on1).