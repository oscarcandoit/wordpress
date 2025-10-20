---
url: https://api.jquery.com/jQuery.get/
scraped_at: 2025-10-20T02:59:01.584Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.get( url \[, data \] \[, success \] \[, dataType \] )Returns: [jqXHR](http://api.jquery.com/Types/\#jqXHR)

**Description:** Load data from the server using a HTTP GET request.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.get( url \[, data \] \[, success \] \[, dataType \] )](https://api.jquery.com/jQuery.get/\#jQuery-get-url-data-success-dataType)

  - **url**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the URL to which the request is sent.

  - **data**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject) or [String](http://api.jquery.com/Types/#String)

    A plain object or string that is sent to the server with the request.

  - **success**

    Type: [Function](http://api.jquery.com/Types/#Function)( [PlainObject](http://api.jquery.com/Types/#PlainObject) data, [String](http://api.jquery.com/Types/#String) textStatus, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A callback function that is executed if the request succeeds. Required if `dataType` is provided, but you can use `null` or [`jQuery.noop`](https://api.jquery.com/jQuery.noop/) as a placeholder. **NOTE:** In jQuery 3.x and older, when providing a `null` value for `success` you also have to provide the `data` parameter; you can set it to `null` or `undefined`.

  - **dataType**

    Type: [String](http://api.jquery.com/Types/#String)

    The type of data expected from the server. Default: Intelligent Guess (xml, json, script, text, html).
- #### version added: [1.12-and-2.2](https://api.jquery.com/category/version/1.12-and-2.2/) [jQuery.get( \[settings \] )](https://api.jquery.com/jQuery.get/\#jQuery-get-settings)

  - **settings**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A set of key/value pairs that configure the Ajax request. All properties except for `url` are optional. A default can be set for any option with [$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/). See [jQuery.ajax( settings )](https://api.jquery.com/jQuery.ajax/#jQuery-ajax-settings) for a complete list of all settings. The type option will automatically be set to `GET`.

This is a shorthand Ajax function, which is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

The `success` callback function is passed the returned data, which will be an XML root element, text string, JavaScript file, or JSON object, depending on the MIME type of the response. It is also passed the text status of the response.

**As of jQuery 1.5**, the `success` callback function is also passed a ["jqXHR" object](https://api.jquery.com/jQuery.get/#jqxhr-object) (in **jQuery 1.4**, it was passed the `XMLHttpRequest` object). However, since JSONP and cross-domain GET requests do not use XHR, in those cases the `jqXHR` and `textStatus` parameters passed to the success callback are undefined.

Most implementations will specify a success handler:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

This example fetches the requested HTML snippet and inserts it on the page.

#### The jqXHR Object

**As of jQuery 1.5**, all of jQuery's Ajax methods return a superset of the `XMLHTTPRequest` object. This jQuery XHR object, or "jqXHR," returned by `$.get()` implements the Promise interface, giving it all the properties, methods, and behavior of a Promise (see [Deferred object](https://api.jquery.com/category/deferred-object/) for more information). The `jqXHR.done()` (for success), `jqXHR.fail()` (for error), and `jqXHR.always()` (for completion, whether success or error; added in jQuery 1.6) methods take a function argument that is called when the request terminates. For information about the arguments this function receives, see the [jqXHR Object](https://api.jquery.com/jQuery.ajax/#jqXHR) section of the `$.ajax()` documentation.

The Promise interface also allows jQuery's Ajax methods, including `$.get()`, to chain multiple `.done()`, `.fail()`, and `.always()` callbacks on a single request, and even to assign these callbacks after the request may have completed. If the request is already complete, the callback is fired immediately.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Deprecation Notice

The `jqXHR.success()`, `jqXHR.error()`, and `jqXHR.complete()` callback methods are **removed as of jQuery 3.0**. You can use `jqXHR.done()`, `jqXHR.fail()`, and `jqXHR.always()` instead.

### Additional Notes:

- Due to browser security restrictions, most "Ajax" requests are subject to the [same origin policy](https://en.wikipedia.org/wiki/Same_origin_policy "Same Origin Policy on Wikipedia"); the request can not successfully retrieve data from a different domain, subdomain, port, or protocol.

- If a request with jQuery.get() returns an error code, it will fail silently unless the script has also called the global [`ajaxError`](https://api.jquery.com/ajaxError/) event. Alternatively, as of jQuery 1.5, the `.error()` method of the `jqXHR` object returned by jQuery.get() is also available for error handling.

- Script and JSONP requests are not subject to the same origin policy restrictions.


### Example 1

Request the test.php page, but ignore the return results.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 2

Request the test.php page and send some additional data along (while still ignoring the return results).

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Pass arrays of data to the server (while still ignoring the return results).

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Alert the results from requesting test.php (HTML or XML, depending on what was returned).

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 5

Alert the results from requesting test.cgi with an additional payload of data (HTML or XML, depending on what was returned).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Example 6

Get the test.php page contents, which has been returned in json format (<?php echo json\_encode( array( "name"=>"John","time"=>"2pm" ) ); ?>), and add it to the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Example 7

Get another page on the same domain. Outputs to console both the data returned and the type of data returned.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |