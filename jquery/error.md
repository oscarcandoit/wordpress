---
url: https://api.jquery.com/error/
scraped_at: 2025-10-20T03:09:57.527Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "error" event, or trigger that event on an element.

#### Contents:

- [.on( "error" \[, eventData \], handler )](https://api.jquery.com/error/#on1)  - [.on( "error" \[, eventData \], handler )](https://api.jquery.com/error/#on-%22error%22-eventData-handler)
- [.trigger( "error" )](https://api.jquery.com/error/#trigger2)  - [.trigger( "error" )](https://api.jquery.com/error/#trigger-%22error%22)

## .on( "error" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "error" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "error" \[, eventData \], handler )](https://api.jquery.com/error/\#on-%22error%22-eventData-handler)

  - **"error"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"error"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `error` event. For the `.error()` method removed in jQuery 3.0, see [`.error()`](https://api.jquery.com/error-shorthand/).

The `error` event is sent to elements, such as images, that are referenced by a document and loaded by the browser. It is called if the element was not loaded correctly.

For example, consider a page with a simple image element:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The event handler can be bound to the image:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

If the image cannot be loaded (for example, because it is not present at the supplied URL), the alert is displayed:

``Handler for `error` called.``

The event handler _must_ be attached before the browser fires the `error` event, which is why the example sets the `src` attribute after attaching the handler. Also, the `error` event may not be correctly fired when the page is served locally; `error` relies on HTTP status codes and will generally not be triggered if the URL uses the `file:` protocol.

Note: A jQuery `error` event handler should not be attached to the `window` object. The browser fires the `window`'s `error` event when a script error occurs. However, the window `error` event receives different arguments and has different return value requirements than conventional event handlers. Use `window.onerror` instead.

To replace all the missing images with another, you can update the `src` attribute inside the `error` handler. Be sure that the replacement image exists; otherwise the `error` event will be triggered indefinitely.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

## .trigger( "error" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "error" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "error" )](https://api.jquery.com/error/\#trigger-%22error%22)

  - **"error"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"error"`.

See the description for [`.on( "error", ... )`](https://api.jquery.com/error/#on1).