---
url: https://api.jquery.com/contextmenu/
scraped_at: 2025-10-20T03:09:44.277Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "contextmenu" event, or trigger that event on an element.

#### Contents:

- [.on( handler )](https://api.jquery.com/contextmenu/#on1)  - [.on( handler )](https://api.jquery.com/contextmenu/#on-handler)
  - [.on( \[eventData \], handler )](https://api.jquery.com/contextmenu/#on-eventData-handler)
- [.trigger( "contextmenu" )](https://api.jquery.com/contextmenu/#trigger2)  - [.trigger( "contextmenu" )](https://api.jquery.com/contextmenu/#trigger-%22contextmenu%22)

## .on( handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "contextmenu" event.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.on( handler )](https://api.jquery.com/contextmenu/\#on-handler)

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.on( \[eventData \], handler )](https://api.jquery.com/contextmenu/\#on-eventData-handler)

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `contextmenu` event. For the deprecated `.contextmenu()` method, see [`.contextmenu()`](https://api.jquery.com/contextmenu-shorthand/).

The `contextmenu` event is sent to an element when the right button of the mouse is clicked on it, but before the context menu is displayed. In case the context menu key is pressed, the event is triggered on the `html` element or the currently focused element. Any HTML element can receive this event.
For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The event handler can be bound to the `<div>` as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now right-clicking on this element displays the alert:

``Handler for `contextmenu` called.``

To trigger the event manually, use `.trigger( "contextmenu" )`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 1

To show a "Hello World!" alert box when the contextmenu event is triggered on a paragraph on the page:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Right click to toggle background color.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

## .trigger( "contextmenu" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "contextmenu" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "contextmenu" )](https://api.jquery.com/contextmenu/\#trigger-%22contextmenu%22)

  - **"contextmenu"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"contextmenu"`.

See the description for [`.on( "contextmenu", ... )`](https://api.jquery.com/contextmenu/#on1).