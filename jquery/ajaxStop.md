---
url: https://api.jquery.com/ajaxStop/
scraped_at: 2025-10-20T02:59:31.714Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxStop", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Register a handler to be called when all Ajax requests have completed. This is an [Ajax Event](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxStop", handler )](https://api.jquery.com/ajaxStop/\#on-%22ajaxStop%22-handler)

  - **"ajaxStop"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxStop"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The function to be invoked.

This page describes the `ajaxStop` event. For the deprecated `.ajaxStop()` method, see [`.ajaxStop()`](https://api.jquery.com/ajaxStop-shorthand/).

Whenever an Ajax request completes, jQuery checks whether there are any other outstanding Ajax requests. If none remain, jQuery triggers the `ajaxStop` event. Any and all registered `ajaxStop` handlers are executed at this time. The `ajaxStop` event is also triggered if the last outstanding Ajax request is cancelled by returning false within the `beforeSend` callback function.

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

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxStop", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxStop` event will not fire.


Hide a loading message after all the Ajax requests have stopped.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |