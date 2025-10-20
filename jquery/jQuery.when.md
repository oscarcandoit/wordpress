---
url: https://api.jquery.com/jQuery.when/
scraped_at: 2025-10-20T03:07:25.384Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.when( deferreds )Returns: [Promise](http://api.jquery.com/Types/\#Promise)

**Description:** Provides a way to execute callback functions based on zero or more Thenable objects, usually [Deferred](https://api.jquery.com/category/deferred-object/) objects that represent asynchronous events.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.when( deferreds )](https://api.jquery.com/jQuery.when/\#jQuery-when-deferreds)

  - **deferreds**

    Type: [Deferred](http://api.jquery.com/Types/#Deferred) or [Promise](http://api.jquery.com/Types/#Promise) or [Thenable](http://api.jquery.com/Types/#Thenable)

    Zero or more Thenable objects.

If no arguments are passed to `jQuery.when()`, it will return a resolved Promise.

If a single Deferred is passed to `jQuery.when()`, its Promise object (a subset of the Deferred methods) is returned by the method. Additional methods of the Promise object can be called to attach callbacks, such as [`deferred.then`](https://api.jquery.com/deferred.then/). When the Deferred is resolved or rejected, usually by the code that created the Deferred originally, the appropriate callbacks will be called. For example, the jqXHR object returned by `jQuery.ajax()` is a Promise-compatible object and can be used this way:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

If a single argument is passed to `jQuery.when()` and it is not a Deferred or a Promise, it will be treated as a resolved Deferred and any doneCallbacks attached will be executed immediately. The doneCallbacks are passed the original argument. In this case any failCallbacks you might set are never called since the Deferred is never rejected. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

If you don't pass it any arguments at all, `jQuery.when()` will return a resolved promise.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

In the case where multiple Deferred objects are passed to `jQuery.when()`, the method returns the Promise from a new "master" Deferred object that tracks the aggregate state of all the Deferreds it has been passed. The method will resolve its master Deferred as soon as all the Deferreds resolve, or reject the master Deferred as soon as one of the Deferreds is rejected. If the master Deferred is resolved, the doneCallbacks for the master Deferred are executed. The arguments passed to the doneCallbacks provide the resolved values for each of the Deferreds, and matches the order the Deferreds were passed to `jQuery.when()`. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

In the event a Deferred was resolved with no value, the corresponding doneCallback argument will be undefined. If a Deferred resolved to a single value, the corresponding argument will hold that value. In the case where a Deferred resolved to multiple values, the corresponding argument will be an array of those values. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13 | ```<br>``` |

In the multiple-Deferreds case where one of the Deferreds is rejected, `jQuery.when()` immediately fires the failCallbacks for its master Deferred. Note that some of the Deferreds may still be unresolved at that point. The arguments passed to the failCallbacks match the signature of the failCallback for the Deferred that was rejected. If you need to perform additional processing for this case, such as canceling any unfinished Ajax requests, you can keep references to the underlying jqXHR objects in a closure and inspect/cancel them in the failCallback.

### Example 1

Execute a function after two Ajax requests are successful. (See the jQuery.ajax() documentation for a complete description of success and error cases for an ajax request).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### Example 2

Execute the function `myFunc` when both ajax requests are successful, or `myFailure` if either one has an error.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |