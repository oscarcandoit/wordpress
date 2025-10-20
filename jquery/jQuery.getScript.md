---
url: https://api.jquery.com/jQuery.getScript/
scraped_at: 2025-10-20T02:59:11.924Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.getScript( url \[, success \] )Returns: [jqXHR](http://api.jquery.com/Types/\#jqXHR)

**Description:** Load a JavaScript file from the server using a GET HTTP request, then execute it.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.getScript( url \[, success \] )](https://api.jquery.com/jQuery.getScript/\#jQuery-getScript-url-success)

  - **url**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the URL to which the request is sent.

  - **success**

    Type: [Function](http://api.jquery.com/Types/#Function)( [String](http://api.jquery.com/Types/#String) script, [String](http://api.jquery.com/Types/#String) textStatus, [jqXHR](http://api.jquery.com/Types/#jqXHR) jqXHR )

    A callback function that is executed if the request succeeds.

This is a shorthand Ajax function, which is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

The script is executed in the global context, so it can refer to other variables and use jQuery functions. Included scripts can have some impact on the current page.

#### Success Callback

The callback is fired once the script has been loaded and executed.

Scripts are included and run by referencing the file name:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

#### Handling Errors

As of jQuery 1.5, you may use [`.fail()`](https://api.jquery.com/deferred.fail/) to account for errors:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

Prior to jQuery 1.5, the global `ajaxError` callback event had to be used in order to handle `$.getScript()` errors:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Prior to jQuery 3.5.0, unsuccessful HTTP responses with a script `Content-Type` were still executed.

#### Caching Responses

By default, `$.getScript()` sets the cache setting to `false`. This appends a timestamped query parameter to the request URL to ensure that the browser downloads the script each time it is requested. You can override this feature by setting the cache property globally using [`$.ajaxSetup()`](https://api.jquery.com/jquery.ajaxsetup/):

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Alternatively, you could define a new method that uses the more flexible `$.ajax()` method.

### Example 1

Define a $.cachedScript() method that allows fetching a cached script:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18 | ```<br>``` |

### Example 2

Load the [official jQuery Color Animation plugin](https://github.com/jquery/jquery-color) dynamically and bind some color animations to occur once the new functionality is loaded.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo: