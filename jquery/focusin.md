---
url: https://api.jquery.com/focusin/
scraped_at: 2025-10-20T03:12:34.283Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "focusin" event, or trigger that event on an element.

#### Contents:

- [.on( "focusin" \[, eventData \], handler )](https://api.jquery.com/focusin/#on1)  - [.on( "focusin" \[, eventData \], handler )](https://api.jquery.com/focusin/#on-%22focusin%22-eventData-handler)
- [.trigger( "focusin" )](https://api.jquery.com/focusin/#trigger2)  - [.trigger( "focusin" )](https://api.jquery.com/focusin/#trigger-%22focusin%22)

## .on( "focusin" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "focusin" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "focusin" \[, eventData \], handler )](https://api.jquery.com/focusin/\#on-%22focusin%22-eventData-handler)

  - **"focusin"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focusin"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `focusin` event. For the deprecated `.focusin()` method, see [`.focusin()`](https://api.jquery.com/focusin-shorthand/).

The `focusin` event is sent to an element when it, or any element inside of it, gains focus. This is distinct from the [focus](https://api.jquery.com/focus/) event in that it supports detecting the focus event on parent elements (in other words, it supports event bubbling).

This event will likely be used together with the [focusout](https://api.jquery.com/focusout/) event.

Watch for a focus to occur within the paragraphs on the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

## .trigger( "focusin" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "focusin" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "focusin" )](https://api.jquery.com/focusin/\#trigger-%22focusin%22)

  - **"focusin"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focusin"`.

See the description for [`.on( "focusin", ... )`](https://api.jquery.com/focusin/#on1).