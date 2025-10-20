---
url: https://api.jquery.com/blur/
scraped_at: 2025-10-20T03:09:00.253Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "blur" event, or trigger that event on an element.

#### Contents:

- [.on( "blur" \[, eventData \], handler )](https://api.jquery.com/blur/#on1)  - [.on( "blur" \[, eventData \], handler )](https://api.jquery.com/blur/#on-%22blur%22-eventData-handler)
- [.trigger( "blur" )](https://api.jquery.com/blur/#trigger2)  - [.trigger( "blur" )](https://api.jquery.com/blur/#trigger-%22blur%22)

## .on( "blur" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "blur" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "blur" \[, eventData \], handler )](https://api.jquery.com/blur/\#on-%22blur%22-eventData-handler)

  - **"blur"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"blur"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `blur` event. For the deprecated `.blur()` method, see [`.blur()`](https://api.jquery.com/blur-shorthand/).

The `blur` event is sent to an element when it loses focus. Originally, this event was only applicable to form elements, such as `<input>`. In recent browsers, the domain of the event has been extended to include all element types. An element can lose focus via keyboard commands, such as the Tab key, or by mouse clicks elsewhere on the page.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The event handler can be bound to the first input field:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now if the first field has the focus, clicking elsewhere or tabbing away from it displays the alert:

``Handler for `blur` called.``

To trigger the event programmatically, call `.trigger( "blur" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message.

The `blur` event does not bubble. As of version 1.4.2, jQuery works around this limitation by mapping `blur` to the `focusout` event in its event delegation methods.

The native `blur` event is asynchronous in all versions of IE, contrary to other browsers. To avoid issues related to this discrepancy, as of jQuery 3.7.0, jQuery uses `focusout` as the native backing event for `blur` in IE.

To trigger the blur event on all paragraphs:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## .trigger( "blur" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "blur" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "blur" )](https://api.jquery.com/blur/\#trigger-%22blur%22)

  - **"blur"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"blur"`.

See the description for [`.on( "blur", ... )`](https://api.jquery.com/blur/#on1).