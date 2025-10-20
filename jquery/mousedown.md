---
url: https://api.jquery.com/mousedown/
scraped_at: 2025-10-20T03:13:17.208Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "mousedown" event, or trigger that event on an element.

#### Contents:

- [.on( "mousedown" \[, eventData \], handler )](https://api.jquery.com/mousedown/#on1)  - [.on( "mousedown" \[, eventData \], handler )](https://api.jquery.com/mousedown/#on-%22mousedown%22-eventData-handler)
- [.trigger( "mousedown" )](https://api.jquery.com/mousedown/#trigger2)  - [.trigger( "mousedown" )](https://api.jquery.com/mousedown/#trigger-%22mousedown%22)

## .on( "mousedown" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "mousedown" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "mousedown" \[, eventData \], handler )](https://api.jquery.com/mousedown/\#on-%22mousedown%22-eventData-handler)

  - **"mousedown"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mousedown"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `mousedown` event. For the deprecated `.mousedown()` method, see [`.mousedown()`](https://api.jquery.com/mousedown-shorthand/).

The `mousedown` event is sent to an element when the mouse pointer is over the element, and the mouse button is pressed. Any HTML element can receive this event.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_01.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any `<div>`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now if we click on this element, the alert is displayed:

``Handler for `mousedown` called.``

We can also trigger the event when a different element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message.

The `mousedown` event is sent when any mouse button is clicked. To act only on specific buttons, we can use the event object's `which` property. Not all browsers support this property (Internet Explorer uses button instead), but jQuery normalizes the property so that it is safe to use in any browser. The value of `which` will be 1 for the left button, 2 for the middle button, or 3 for the right button.

This event is primarily useful for ensuring that the primary button was used to begin a drag operation; if ignored, strange results can occur when the user attempts to use a context menu. While the middle and right buttons can be detected with these properties, this is not reliable. In Opera and Safari, for example, right mouse button clicks are not detectable by default.

If the user clicks on an element, drags away from it, and releases the button, this is still counted as a `mousedown` event. This sequence of actions is treated as a "canceling" of the button press in most user interfaces, so it is usually better to use the `click` event unless we know that the `mousedown` event is preferable for a particular situation.

Show texts when mouseup and mousedown event triggering.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo:

## .trigger( "mousedown" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "mousedown" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "mousedown" )](https://api.jquery.com/mousedown/\#trigger-%22mousedown%22)

  - **"mousedown"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mousedown"`.

See the description for [`.on( "mousedown", ... )`](https://api.jquery.com/mousedown/#on1).