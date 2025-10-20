---
url: https://api.jquery.com/jQuery.ajaxTransport/
scraped_at: 2025-10-20T02:59:44.614Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.ajaxTransport( dataType, handler )Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Creates an object that handles the actual transmission of Ajax data.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.ajaxTransport( dataType, handler )](https://api.jquery.com/jQuery.ajaxTransport/\#jQuery-ajaxTransport-dataType-handler)

  - **dataType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string identifying the data type to use

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [PlainObject](http://api.jquery.com/Types/#PlainObject) options, [PlainObject](http://api.jquery.com/Types/#PlainObject) originalOptions, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A handler to return the new transport object to use with the data type provided in the first argument.

A transport is an object that provides two methods, `send` and `abort`, that are used internally by `$.ajax()` to issue requests. A transport is the most advanced way to enhance `$.ajax()` and should be used only as a last resort when prefilters and converters are insufficient.

Since each request requires its own transport object instance, transports cannot be registered directly. Therefore, you should provide a function that returns a transport instead.

Transports factories are registered using `$.ajaxTransport()`. A typical registration looks like this:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12 | ```<br>``` |

where:

- `options` are the request options
- `originalOptions` are the options as provided to the `$.ajax()` method, unmodified and, thus, without defaults from ajaxSettings
- `jqXHR` is the jqXHR object of the request
- `headers` is an object of (key-value) request headers that the transport can transmit if it supports it
- `completeCallback` is the callback used to notify Ajax of the completion of the request

`completeCallback` has the following signature:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

where:

- `status` is the HTTP status code of the response, like 200 for a typical success, or 404 for when the resource is not found.
- `statusText` is the statusText of the response.
- `responses` (Optional) is An object containing dataType/value that contains the response in all the formats the transport could provide (for instance, a native XMLHttpRequest object would set responses to `{ xml: XMLData, text: textData }` for a response that is an XML document)
- `headers` (Optional) is a string containing all the response headers if the transport has access to them (akin to what `XMLHttpRequest.getAllResponseHeaders()` would provide).

Just like prefilters, a transport's factory function can be attached to a specific dataType:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The following example shows how a minimal image transport could be implemented:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Handling Custom Data Types

The jQuery Ajax implementation comes with a set of standard dataTypes, such as text, json, xml, and html.

Use the `converters` option in `[$.ajaxSetup()](https://api.jquery.com/jQuery.ajaxSetup/)` to augment or modify the data type conversion strategies used by `$.ajax()`.

The unminified jQuery source itself includes a list of default converters, which effectively illustrates how they can be used:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14 | ```<br>``` |

When you specify a `converters` option globally in `$.ajaxSetup()` or per call in `$.ajax()`, the object will map onto the default converters, overwriting those you specify and leaving the others intact.

For example, the jQuery source uses `$.ajaxSetup()` to add a converter for "text script":

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |