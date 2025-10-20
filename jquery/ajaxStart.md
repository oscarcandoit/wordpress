---
url: https://api.jquery.com/ajaxStart/
scraped_at: 2025-10-20T02:59:28.540Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .on( "ajaxStart", handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Register a handler to be called when the first Ajax request begins. This is an [Ajax Event](https://api.jquery.com/Ajax_Events/).

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "ajaxStart", handler )](https://api.jquery.com/ajaxStart/\#on-%22ajaxStart%22-handler)

  - **"ajaxStart"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"ajaxStart"`.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The function to be invoked.

This page describes the `ajaxStart` event. For the deprecated `.ajaxStart()` method, see [`.ajaxStart()`](https://api.jquery.com/ajaxStart-shorthand/).

Whenever an Ajax request is about to be sent, jQuery checks whether there are any other outstanding Ajax requests. If none are in progress, jQuery triggers the `ajaxStart` event. Any and all handlers that have been registered with `.on( "ajaxStart", ... )` are executed at this time.

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

When the user clicks the element with class `trigger` and the Ajax request is sent, the log message is displayed.

### Additional Notes:

- As of jQuery 1.9, all the handlers for the [jQuery global Ajax events](https://api.jquery.com/category/ajax/global-ajax-event-handlers/), including those added with `.on( "ajaxStart", ... )`, _must_ be attached to `document`.

- If `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` or `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` is called with the `global` option set to `false`, the `ajaxStart` event will not fire.


Show a loading message whenever an Ajax request starts (and none is already active).

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |