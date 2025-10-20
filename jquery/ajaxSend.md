---
url: https://api.jquery.com/ajaxSend/
scraped_at: 2025-10-20T02:59:25.053Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxSend", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Attach a function to be executed before an Ajax request is sent. This is an [Ajax Event](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxSend", handler )](https://api.jquery.com/ajaxSend/\#on-%22ajaxSend%22-handler)

  - **"ajaxSend"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxSend"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) event, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR, [PlainObject](http://api.jquery.com/Types/#PlainObject) ajaxOptions )

    The function to be invoked.

This page describes the `ajaxSend` event. For the deprecated `.ajaxSend()` method, see [`.ajaxSend()`](https://api.jquery.com/ajaxSend-shorthand/).

Whenever an Ajax request is about to be sent, jQuery triggers the `ajaxSend` event. Any and all registerd `ajaxSend` handlers are executed at this time.

To observe this method in action, set up a basic Ajax load request:

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

When the user clicks the element with class `trigger` and the Ajax request is about to begin, the log message is displayed.

All `ajaxSend` handlers are invoked, regardless of what Ajax request is to be sent. If you must differentiate between the requests, use the parameters passed to the handler. Each time an `ajaxSend` handler is executed, it is passed the event object, the `jqXHR` object (in version 1.4, `XMLHttpRequest` object), and the [settings object](https://api.jquery.com/jQuery.ajax/) that was used in the creation of the Ajax request. For example, you can restrict the callback to only handling events dealing with a particular URL:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxSend", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxSend` event will not fire.


Show a message before an Ajax request is sent.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |