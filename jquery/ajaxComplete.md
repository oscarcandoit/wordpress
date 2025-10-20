---
url: https://api.jquery.com/ajaxComplete/
scraped_at: 2025-10-20T02:59:18.550Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxComplete", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Register a handler to be called when Ajax requests complete. This is an [AjaxEvent](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxComplete", handler )](https://api.jquery.com/ajaxComplete/\#on-%22ajaxComplete%22-handler)

  - **"ajaxComplete"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxComplete"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) event, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR, [PlainObject](http://api.jquery.com/Types/#PlainObject) ajaxOptions )

    The function to be invoked.

This page describes the `ajaxComplete` event. For the deprecated `.ajaxComplete()` method, see [`.ajaxComplete()`](https://api.jquery.com/ajaxComplete-shorthand/).

Whenever an Ajax request completes, jQuery triggers the `ajaxComplete` event. Any and all registered `ajaxComplete` handlers are executed at this time.

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

When the user clicks the element with class `trigger` and the Ajax request completes, the log message is displayed.

All `ajaxComplete` handlers are invoked, regardless of what Ajax request was completed. If you must differentiate between the requests, use the parameters passed to the handler. Each time an `ajaxComplete` handler is executed, it is passed the event object, the `XMLHttpRequest` object, and the settings object that was used in the creation of the request. For example, you can restrict the callback to only handling events dealing with a particular URL:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

**Note:** You can get the returned Ajax contents by looking at `xhr.responseText`.

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxComplete", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxComplete` event will not fire.


Show a message when an Ajax request completes.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |