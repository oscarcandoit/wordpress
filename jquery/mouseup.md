---
url: https://api.jquery.com/mouseup/
scraped_at: 2025-10-20T03:13:44.477Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "mouseup" event, or trigger that event on an element.

#### Contents:

- [.on( "mouseup" \[, eventData \], handler )](https://api.jquery.com/mouseup/#on1)  - [.on( "mouseup" \[, eventData \], handler )](https://api.jquery.com/mouseup/#on-%22mouseup%22-eventData-handler)
- [.trigger( "mouseup" )](https://api.jquery.com/mouseup/#trigger2)  - [.trigger( "mouseup" )](https://api.jquery.com/mouseup/#trigger-%22mouseup%22)

## .on( "mouseup" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "mouseup" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "mouseup" \[, eventData \], handler )](https://api.jquery.com/mouseup/\#on-%22mouseup%22-eventData-handler)

  - **"mouseup"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseup"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `mouseup` event. For the deprecated `.mouseup()` method, see [`.mouseup()`](https://api.jquery.com/mouseup-shorthand/).

The `mouseup` event is sent to an element when the mouse pointer is over the element, and the mouse button is released. Any HTML element can receive this event.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_02.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any `<div>`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now if we click on this element, the alert is displayed:

``Handler for `mouseup` called.``

We can also trigger the event when a different element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message.

If the user clicks outside an element, drags onto it, and releases the button, this is still counted as a `mouseup` event. This sequence of actions is not treated as a button press in most user interfaces, so it is usually better to use the `click` event unless we know that the `mouseup` event is preferable for a particular situation.

Show texts when mouseup and mousedown event triggering.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo:

## .trigger( "mouseup" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "mouseup" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "mouseup" )](https://api.jquery.com/mouseup/\#trigger-%22mouseup%22)

  - **"mouseup"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseup"`.

See the description for [`.on( "mouseup", ... )`](https://api.jquery.com/mouseup/#on1).