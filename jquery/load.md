---
url: https://api.jquery.com/load/
scraped_at: 2025-10-20T02:59:04.757Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .load( url \[, data \] \[, complete \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Load data from the server and place the returned HTML into the matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.load( url \[, data \] \[, complete \] )](https://api.jquery.com/load/\#load-url-data-complete)

  - **url**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the URL to which the request is sent.

  - **data**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject) or [String](http://api.jquery.com/Types/#String)

    A plain object or string that is sent to the server with the request.

  - **complete**

    Type: [Function](http://api.jquery.com/Types/#Function)( [String](http://api.jquery.com/Types/#String) responseText, [String](http://api.jquery.com/Types/#String) textStatus, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A callback function that is executed when the request completes.

Note: Prior to jQuery 3.0, the event handling suite also had a method named `[.load()](https://api.jquery.com/load-event/)`. Older versions of jQuery determined which method to fire based on the set of arguments passed to it.

This method is the simplest way to fetch data from the server. It is roughly equivalent to `$.get(url, data, success)` except that it is a method rather than global function and it has an implicit callback function. When a successful response is detected (i.e. when `textStatus` is "success" or "notmodified"), `.load()` sets the HTML contents of the matched elements to the returned data. This means that most uses of the method can be quite simple:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If no element is matched by the selector — in this case, if the document does not contain an element with id="result" — the Ajax request will _not_ be sent.

#### Callback Function

If a "complete" callback is provided, it is executed after post-processing and HTML insertion has been performed. The callback is fired once for each element in the jQuery collection, and `this` is set to each DOM element in turn.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

In the two examples above, if the current document does not contain an element with an ID of "result," the `.load()` method is not executed.

#### Request Method

The POST method is used if data is provided as an object; otherwise, GET is assumed.

#### Loading Page Fragments

The `.load()` method, unlike `[$.get()](https://api.jquery.com/jQuery.get/)`, allows us to specify a portion of the remote document to be inserted. This is achieved with a special syntax for the `url` parameter. If one or more space characters are included in the string, the portion of the string following the first space is assumed to be a jQuery selector that determines the content to be loaded.

We could modify the example above to use only part of the document that is fetched:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

When this method executes, it retrieves the content of `ajax/test.html`, but then jQuery parses the returned document to find the element with an ID of `container`. This element, along with its contents, is inserted into the element with an ID of `result`, and the rest of the retrieved document is discarded.

jQuery uses the browser's `.innerHTML` property to parse the retrieved document and insert it into the current document. During this process, browsers often filter elements from the document such as `<html>`, `<title>`, or `<head>` elements. As a result, the elements retrieved by `.load()` may not be exactly the same as if the document were retrieved directly by the browser.

#### Script Execution

When calling `.load()` using a URL without a suffixed selector expression, the content is passed to `.html()` prior to scripts being removed. This executes the script blocks before they are discarded. If `.load()` is called with a selector expression appended to the URL, however, the scripts are stripped out prior to the DOM being updated, and thus are _not_ executed. An example of both cases can be seen below:

Here, any JavaScript loaded into `#a` as a part of the document will successfully execute.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

However, in the following case, script blocks in the document being loaded into `#b` are stripped out and not executed:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Additional Notes:

- Due to browser security restrictions, most "Ajax" requests are subject to the [same origin policy](https://en.wikipedia.org/wiki/Same_origin_policy "Same Origin Policy on Wikipedia"); the request can not successfully retrieve data from a different domain, subdomain, port, or protocol.


### Example 1

Load another page's list items into an ordered list.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24 | ```<br>``` |

#### Demo:

### Example 2

Display a notice if the Ajax request encounters an error.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 3

Load the feeds.html file into the div with the ID of feeds.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

#### Result:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

pass arrays of data to the server.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 5

Same as above, but will POST the additional parameters to the server and a callback that is executed when the server is finished responding.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |