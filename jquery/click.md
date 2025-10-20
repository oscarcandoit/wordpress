---
url: https://api.jquery.com/click/
scraped_at: 2025-10-20T03:09:41.076Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "click" event, or trigger that event on an element.

#### Contents:

- [.on( "click" \[, eventData \], handler )](https://api.jquery.com/click/#on1)  - [.on( "click" \[, eventData \], handler )](https://api.jquery.com/click/#on-%22click%22-eventData-handler)
- [.trigger( "click" )](https://api.jquery.com/click/#trigger2)  - [.trigger( "click" )](https://api.jquery.com/click/#trigger-%22click%22)

## .on( "click" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "click" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "click" \[, eventData \], handler )](https://api.jquery.com/click/\#on-%22click%22-eventData-handler)

  - **"click"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"click"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `click` event. For the deprecated `.click()` method, see [`.click()`](https://api.jquery.com/click-shorthand/).

The `click` event is sent to an element when the mouse pointer is over the element, and the mouse button is pressed and released. Any HTML element can receive this event.
For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_03.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any `<div>`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now if we click on this element, the alert is displayed:

``Handler for `click` called.``

We can also trigger the event when a different element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicking on `Trigger the handler` will also alert the message.

The `click` event is only triggered after this exact series of events:

- The mouse button is depressed while the pointer is inside the element.
- The mouse button is released while the pointer is inside the element.

This is usually the desired sequence before taking an action. If this is not required, the `mousedown` or `mouseup` event may be more suitable.

### Example 1

Hide paragraphs on a page when they are clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 2

Trigger the click event on all the paragraphs on the page:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## .trigger( "click" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "click" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "click" )](https://api.jquery.com/click/\#trigger-%22click%22)

  - **"click"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"click"`.

See the description for [`.on( "click", ... )`](https://api.jquery.com/click/#on1).