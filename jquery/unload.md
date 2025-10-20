---
url: https://api.jquery.com/unload/
scraped_at: 2025-10-20T03:14:11.330Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "unload" event, or trigger that event on an element.

#### Contents:

- [.on( "unload" \[, eventData \], handler )](https://api.jquery.com/unload/#on1)  - [.on( "unload" \[, eventData \], handler )](https://api.jquery.com/unload/#on-%22unload%22-eventData-handler)
- [.trigger( "unload" )](https://api.jquery.com/unload/#trigger2)  - [.trigger( "unload" )](https://api.jquery.com/unload/#trigger-%22unload%22)

## .on( "unload" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "unload" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "unload" \[, eventData \], handler )](https://api.jquery.com/unload/\#on-%22unload%22-eventData-handler)

  - **"unload"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"unload"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    A plain object of data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `unload` event. For the `.unload()` method removed in jQuery 3.0, see [`.unload()`](https://api.jquery.com/unload-shorthand/).

The `unload` event is sent to the `window` element when the user navigates away from the page. This could mean one of many things. The user could have clicked on a link to leave the page, or typed in a new URL in the address bar. The forward and back buttons will trigger the event. Closing the browser window will cause the event to be triggered. Even a page reload will first create an `unload` event.

The exact handling of the `unload` event has varied from version to version of browsers. For example, some versions of Firefox trigger the event when a link is followed, but not when the window is closed. In practical usage, behavior should be tested on all supported browsers and contrasted with the similar `beforeunload` event.

Any `unload` event handler should be bound to the `window` object:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This event is available so that scripts can perform cleanup when the user leaves the page. Most browsers will ignore calls to `alert()`, `confirm()` and `prompt()` inside the event handler. The string you return may be used in a confirmation dialog, but not all browsers support this. It is not possible to cancel the `unload` event with `.preventDefault()`.

To display an alert when a page is unloaded:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

## .trigger( "unload" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "unload" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "unload" )](https://api.jquery.com/unload/\#trigger-%22unload%22)

  - **"unload"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"unload"`.

See the description for [`.on( "unload", ... )`](https://api.jquery.com/unload/#on1).