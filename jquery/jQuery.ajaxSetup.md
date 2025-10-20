---
url: https://api.jquery.com/jQuery.ajaxSetup/
scraped_at: 2025-10-20T02:59:41.202Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.ajaxSetup( options )Returns: [PlainObject](http://api.jquery.com/Types/\#PlainObject)

**Description:** Set default values for future Ajax requests. Its use is not recommended.

- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [jQuery.ajaxSetup( options )](https://api.jquery.com/jQuery.ajaxSetup/\#jQuery-ajaxSetup-options)

  - **options**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A set of key/value pairs that configure the default Ajax request. All options are optional.

For details on the settings available for `$.ajaxSetup()`, see `[$.ajax()](https://api.jquery.com/jQuery.ajax/)`.

All subsequent Ajax calls using any function will use the new settings, unless overridden by the individual calls, until the next invocation of `$.ajaxSetup()`.

**Note:** The settings specified here will affect _all_ calls to `$.ajax` or Ajax-based derivatives such as `$.get()`. This can cause undesirable behavior since other callers (for example, plugins) may be expecting the normal default settings. For that reason we _strongly recommend against using this API_. Instead, set the options explicitly in the call or define a simple plugin to do so.

For example, the following sets a default for the `url` parameter before pinging the server repeatedly:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now each time an Ajax request is made, the "ping.php" URL will be used automatically:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Note: Global callback functions should be set via `.on()` with their respective global Ajax events— `[ajaxStart](https://api.jquery.com/ajaxStart/)`, `[ajaxStop](https://api.jquery.com/ajaxStop/)`, `[ajaxComplete](https://api.jquery.com/ajaxComplete/)`, `[ajaxError](https://api.jquery.com/ajaxError/)`, `[ajaxSuccess](https://api.jquery.com/ajaxSuccess/)`, `[ajaxSend](https://api.jquery.com/ajaxSend/)`—rather than within the `options` object for `$.ajaxSetup()`.

Sets the defaults for Ajax requests to the url "/xmlhttp/", disables global handlers and uses POST instead of GET. The following Ajax requests then sends some data without having to set anything else.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |