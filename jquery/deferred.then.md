---
url: https://api.jquery.com/deferred.then/
scraped_at: 2025-10-20T03:07:21.430Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.then( doneFilter \[, failFilter \] \[, progressFilter \] )Returns: [Promise](http://api.jquery.com/Types/\#Promise)

**Description:** Add handlers to be called when the Deferred object is resolved, rejected, or still in progress.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [deferred.then( doneFilter \[, failFilter \] \[, progressFilter \] )](https://api.jquery.com/deferred.then/\#deferred-then-doneFilter-failFilter-progressFilter)

  - **doneFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function that is called when the Deferred is resolved.


  - **failFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when the Deferred is rejected.


  - **progressFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when progress notifications are sent to the Deferred.
- #### version added: [1.5](https://api.jquery.com/category/version/1.5/), removed: [1.8](https://api.jquery.com/category/version/1.8/) [deferred.then( doneCallbacks, failCallbacks )](https://api.jquery.com/deferred.then/\#deferred-then-doneCallbacks-failCallbacks)

  - **doneCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, called when the Deferred is resolved.


  - **failCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, called when the Deferred is rejected.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.8](https://api.jquery.com/category/version/1.8/) [deferred.then( doneCallbacks, failCallbacks \[, progressCallbacks \] )](https://api.jquery.com/deferred.then/\#deferred-then-doneCallbacks-failCallbacks-progressCallbacks)

  - **doneCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, called when the Deferred is resolved.


  - **failCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, called when the Deferred is rejected.


  - **progressCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, called when the Deferred notifies progress.

**Prior to jQuery 1.8**, the arguments could be a function or an array of functions.

For all signatures, the arguments can be `null` if no callback of that type is desired. Alternatively, use `.done()`, `.fail()` or `.progress()` to set only one type of callback without filtering status or values.

**As of jQuery 1.8**, the `deferred.then()` method returns a new promise that can filter the status and values of a deferred through a function, replacing the now-deprecated `deferred.pipe()` method. The `doneFilter` and `failFilter` functions filter the original deferred's resolved / rejected status and values. The `progressFilter` function filters any calls to the original deferred's `notify` or `notifyWith` methods. These filter functions can return a new value to be passed along to the promise's `.done()` or `.fail()` callbacks, or they can return another observable object (Deferred, Promise, etc) which will pass its resolved / rejected status and values to the promise's callbacks. If the filter function used is `null`, or not specified, the promise will be resolved or rejected with the same values as the original.

Callbacks are executed in the order they were added. Since
`deferred.then` returns a Promise, other methods of the
Promise object can be chained to this one, including additional
`.then()` methods.


### Example 1

Since the [`jQuery.get`](https://api.jquery.com/jQuery.get/) method returns a jqXHR object, which is derived from a Deferred object, we can attach handlers using the `.then` method.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

### Example 2

Filter the resolve value:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Demo:

### Example 3

Filter reject value:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

### Example 4

Chain tasks:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |