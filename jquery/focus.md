---
url: https://api.jquery.com/focus/
scraped_at: 2025-10-20T03:12:27.971Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "focus" event, or trigger that event on an element.

#### Contents:

- [.on( "focus" \[, eventData \], handler )](https://api.jquery.com/focus/#on1)  - [.on( "focus" \[, eventData \], handler )](https://api.jquery.com/focus/#on-%22focus%22-eventData-handler)
- [.trigger( "focus" )](https://api.jquery.com/focus/#trigger2)  - [.trigger( "focus" )](https://api.jquery.com/focus/#trigger-%22focus%22)

## .on( "focus" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "focus" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "focus" \[, eventData \], handler )](https://api.jquery.com/focus/\#on-%22focus%22-eventData-handler)

  - **"focus"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focus"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `focus` event. For the deprecated `.focus()` method, see [`.focus()`](https://api.jquery.com/focus-shorthand/).

- The `focus` event is sent to an element when it gains focus. This event is implicitly applicable to a limited set of elements, such as form elements ( `<input>`, `<select>`, etc.) and links ( `<a href>`). In recent browser versions, the event can be extended to include all element types by explicitly setting the element's `tabindex` property. An element can gain focus via keyboard commands, such as the Tab key, or by mouse clicks on the element.
- Elements with focus are usually highlighted in some way by the browser, for example with a dotted line surrounding the element. The focus is used to determine which element is the first to receive keyboard-related events.

Attempting to set focus to a hidden element causes an error in Internet Explorer. Take care to only use `.trigger( "focus" )` on elements that are visible. To run an element's focus event handlers without setting focus to the element, use `.triggerHandler( "focus" )` instead of `.trigger( "focus" )`.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The event handler can be bound to the first input field:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now clicking on the first field, or tabbing to it from another field, displays the alert:

``Handler for `focus` called.``

We can trigger the event when another element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message.

The `focus` event does not bubble. As of version 1.4.2, jQuery works around this limitation by mapping `focus` to the `focusin` event in its event delegation methods.

The native `focus` event is asynchronous in all versions of IE, contrary to other browsers. To avoid issues related to this discrepancy, as of jQuery 3.7.0, jQuery uses `focusin` as the native backing event for `focus` in IE.

### Example 1

Fire focus.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

### Example 2

To stop people from writing in text input boxes, try:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

To focus on a login input box with id 'login' on page startup, try:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

## .trigger( "focus" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "focus" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "focus" )](https://api.jquery.com/focus/\#trigger-%22focus%22)

  - **"focus"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focus"`.

See the description for [`.on( "focus", ... )`](https://api.jquery.com/focus/#on1).