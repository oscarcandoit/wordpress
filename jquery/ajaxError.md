---
url: https://api.jquery.com/ajaxError/
scraped_at: 2025-10-20T02:59:21.704Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxError", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Register a handler to be called when Ajax requests complete with an error. This is an [Ajax Event](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxError", handler )](https://api.jquery.com/ajaxError/\#on-%22ajaxError%22-handler)

  - **"ajaxError"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxError"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) event, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR, [PlainObject](http://api.jquery.com/Types/#PlainObject) ajaxSettings, [String](http://api.jquery.com/Types/#String) thrownError )

    The function to be invoked.

This page describes the `ajaxError` event. For the deprecated `.ajaxError()` method, see [`.ajaxError()`](https://api.jquery.com/ajaxError-shorthand/).

Whenever an Ajax request completes with an error, jQuery triggers the `ajaxError` event. Any and all registered `ajaxError` handlers are executed at this time. **Note:** _This handler is not called for cross-domain script and cross-domain JSONP requests._

To observe this method in action, set up a basic Ajax load request.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Attach the event handler to the document:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now, make an Ajax request using any jQuery method:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

When the user clicks the button and the Ajax request fails, because the requested file is missing, the log message is displayed.

All `ajaxError` handlers are invoked, regardless of what Ajax request was completed. To differentiate between the requests, use the parameters passed to the handler. Each time an `ajaxError` handler is executed, it is passed the event object, the `jqXHR` object (prior to jQuery 1.5, the `XHR` object), and the settings object that was used in the creation of the request. When an HTTP error occurs, the fourth argument ( `thrownError`) receives the textual portion of the HTTP status, such as "Not Found" or "Internal Server Error." For example, to restrict the error callback to only handling events dealing with a particular URL:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxError", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxError` event will not fire.


Show a message when an Ajax request fails.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |