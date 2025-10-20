---
url: https://api.jquery.com/ajaxSuccess/
scraped_at: 2025-10-20T02:59:34.891Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxSuccess", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Attach a function to be executed whenever an Ajax request completes successfully. This is an [Ajax Event](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxSuccess", handler )](https://api.jquery.com/ajaxSuccess/\#on-%22ajaxSuccess%22-handler)

  - **"ajaxSuccess"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxSuccess"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) event, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR, [PlainObject](http://api.jquery.com/Types/#PlainObject) ajaxOptions, [PlainObject](http://api.jquery.com/Types/#PlainObject) data )

    The function to be invoked.

This page describes the `ajaxSuccess` event. For the deprecated `.ajaxSuccess()` method, see [`.ajaxSuccess()`](https://api.jquery.com/ajaxSuccess-shorthand/).

Whenever an Ajax request completes successfully, jQuery triggers the `ajaxSuccess` event. Any and all registered `ajaxSuccess` handlers are executed at this time.

To observe this method in action, set up a basic Ajax load request:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Attach the event handler to any element:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now, make an Ajax request using any jQuery method:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

When the user clicks the element with class `trigger` and the Ajax request completes successfully, the log message is displayed.

All `ajaxSuccess` handlers are invoked, regardless of what Ajax request was completed. If you must differentiate between the requests, you can use the parameters passed to the handler. Each time an `ajaxSuccess` handler is executed, it is passed the event object, the `XMLHttpRequest` object, and the settings object that was used in the creation of the request. For example, you can restrict the callback to only handling events dealing with a particular URL:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

**Note:** You can get the returned Ajax contents by looking at `xhr.responseXML` or `xhr.responseText` for xml and html respectively.

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxSuccess", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxSuccess` event will not fire.


Show a message when an Ajax request completes successfully.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |