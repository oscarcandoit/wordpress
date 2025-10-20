---
url: https://api.jquery.com/jQuery.ajaxPrefilter/
scraped_at: 2025-10-20T02:59:37.856Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.ajaxPrefilter( \[dataTypes \], handler )Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Handle custom Ajax options or modify existing options before each request is sent and before they are processed by `$.ajax()`.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.ajaxPrefilter( \[dataTypes \], handler )](https://api.jquery.com/jQuery.ajaxPrefilter/\#jQuery-ajaxPrefilter-dataTypes-handler)

  - **dataTypes**

    Type: [String](http://api.jquery.com/Types/#String)

    An optional string containing one or more space-separated dataTypes

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [PlainObject](http://api.jquery.com/Types/#PlainObject) options, [PlainObject](http://api.jquery.com/Types/#PlainObject) originalOptions, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A handler to set default values for future Ajax requests.

A typical prefilter registration using `$.ajaxPrefilter()` looks like this:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

where:

- `options` are the request options
- `originalOptions` are the options as provided to the `$.ajax()` method, unmodified and, thus, without defaults from `ajaxSettings`
- `jqXHR` is the jqXHR object of the request

Prefilters are a perfect fit when custom options need to be handled. Given the following code, for example, a call to `$.ajax()` would automatically abort a request to the same URL if the custom `abortOnRetry` option is set to `true`:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

Prefilters can also be used to modify existing options. For example, the following proxies cross-domain requests through https://mydomain.net/proxy/:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

If the optional `dataTypes` argument is supplied, the prefilter will be only be applied to requests with the indicated dataTypes. For example, the following only applies the given prefilter to JSON and script requests:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The `$.ajaxPrefilter()` method can also redirect a request to another dataType by returning that dataType. For example, the following sets a request as "script" if the URL has some specific properties defined in a custom `isActuallyScript()` function:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

This would ensure not only that the request is considered "script" but also that all the prefilters specifically attached to the script dataType would be applied to it.