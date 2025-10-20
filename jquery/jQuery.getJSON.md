---
url: https://api.jquery.com/jQuery.getJSON/
scraped_at: 2025-10-20T02:59:08.530Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.getJSON( url \[, data \] \[, success \] )Returns: [jqXHR](http://api.jquery.com/Types/\#jqXHR)

**Description:** Load JSON-encoded data from the server using a GET HTTP request.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.getJSON( url \[, data \] \[, success \] )](https://api.jquery.com/jQuery.getJSON/\#jQuery-getJSON-url-data-success)

  - **url**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the URL to which the request is sent.

  - **data**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject) or [String](http://api.jquery.com/Types/#String)

    A plain object or string that is sent to the server with the request.

  - **success**

    Type: [Function](http://api.jquery.com/Types/#Function)( [PlainObject](http://api.jquery.com/Types/#PlainObject) data, [String](http://api.jquery.com/Types/#String) textStatus, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A callback function that is executed if the request succeeds.

This is a shorthand Ajax function, which is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

Data that is sent to the server is appended to the URL as a query string. If the value of the `data` parameter is a plain object, it is converted to a string and url-encoded before it is appended to the URL.

Most implementations will specify a success handler:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

This example, of course, relies on the structure of the JSON file:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Using this structure, the example loops through the requested data, builds an unordered list, and appends it to the body.

The `success` callback is passed the returned data, which is typically a JavaScript object or array as defined by the JSON structure and parsed using the `[$.parseJSON()](https://api.jquery.com/jQuery.parseJSON/)` method. It is also passed the text status of the response.

**As of jQuery 1.5**, the `success` callback function receives a ["jqXHR" object](https://api.jquery.com/jQuery.get/#jqxhr-object) (in **jQuery 1.4**, it received the `XMLHttpRequest` object). However, since JSONP and cross-domain GET requests do not use XHR, in those cases the `jqXHR` and `textStatus` parameters passed to the success callback are undefined.

**Important:** As of jQuery 1.4, if the JSON file contains a syntax error, the request will usually fail silently. Avoid frequent hand-editing of JSON data for this reason. JSON is a data-interchange format with syntax rules that are stricter than those of JavaScript's object literal notation. For example, all strings represented in JSON, whether they are properties or values, must be enclosed in double-quotes. For details on the JSON format, see [https://json.org/](https://json.org/).

#### JSONP

If the URL includes the string "callback=?" (or similar, as defined by the server-side API), the request is treated as JSONP instead. See the discussion of the `jsonp` data type in `[$.ajax()](https://api.jquery.com/jQuery.ajax/)` for more details.

#### The jqXHR Object

**As of jQuery 1.5**, all of jQuery's Ajax methods return a superset of the `XMLHTTPRequest` object. This jQuery XHR object, or "jqXHR," returned by `$.getJSON()` implements the Promise interface, giving it all the properties, methods, and behavior of a Promise (see [Deferred object](https://api.jquery.com/category/deferred-object/) for more information). The `jqXHR.done()` (for success), `jqXHR.fail()` (for error), and `jqXHR.always()` (for completion, whether success or error; added in jQuery 1.6) methods take a function argument that is called when the request terminates. For information about the arguments this function receives, see the [jqXHR Object](https://api.jquery.com/jQuery.ajax/#jqXHR) section of the `$.ajax()` documentation.

The Promise interface in jQuery 1.5 also allows jQuery's Ajax methods, including `$.getJSON()`, to chain multiple `.done()`, `.always()`, and `.fail()` callbacks on a single request, and even to assign these callbacks after the request may have completed. If the request is already complete, the callback is fired immediately.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Deprecation Notice

The `jqXHR.success()`, `jqXHR.error()`, and `jqXHR.complete()` callback methods are **removed as of jQuery 3.0**. You can use `jqXHR.done()`, `jqXHR.fail()`, and `jqXHR.always()` instead.

### Additional Notes:

- Due to browser security restrictions, most "Ajax" requests are subject to the [same origin policy](https://en.wikipedia.org/wiki/Same_origin_policy "Same Origin Policy on Wikipedia"); the request can not successfully retrieve data from a different domain, subdomain, port, or protocol.

- Script and JSONP requests are not subject to the same origin policy restrictions.


### Example 1

Loads the four most recent pictures of Mount Rainier from the Flickr JSONP API.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 2

Load the JSON data from test.js and access a name from the returned JSON data.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

Load the JSON data from test.js, passing along additional data, and access a name from the returned JSON data.
If an error occurs, log an error message instead.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |