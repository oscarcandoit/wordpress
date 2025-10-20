---
url: https://api.jquery.com/deferred.pipe/
scraped_at: 2025-10-20T03:06:50.319Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.pipe( \[doneFilter \] \[, failFilter \] )Returns: [Promise](http://api.jquery.com/Types/\#Promise)version deprecated: [1.8](https://api.jquery.com/category/version/1.8/)

**Description:** Utility method to filter and/or chain Deferreds.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [deferred.pipe( \[doneFilter \] \[, failFilter \] )](https://api.jquery.com/deferred.pipe/\#deferred-pipe-doneFilter-failFilter)

  - **doneFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when the Deferred is resolved.


  - **failFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when the Deferred is rejected.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [deferred.pipe( \[doneFilter \] \[, failFilter \] \[, progressFilter \] )](https://api.jquery.com/deferred.pipe/\#deferred-pipe-doneFilter-failFilter-progressFilter)

  - **doneFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when the Deferred is resolved.


  - **failFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when the Deferred is rejected.


  - **progressFilter**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     An optional function that is called when progress notifications are sent to the Deferred.

**Deprecation Notice:** As of jQuery 1.8, the deferred.pipe() method is deprecated. The `deferred.then()` method, which replaces it, should be used instead.

The `deferred.pipe()` method returns a new promise that filters the status and values of a deferred through a function. The `doneFilter` and `failFilter` functions filter the original deferred's resolved / rejected status and values. **As of jQuery 1.7**, the method also accepts a `progressFilter` function to filter any calls to the original deferred's `notify` or `notifyWith` methods. These filter functions can return a new value to be passed along to the piped promise's `done()` or `fail()` callbacks, or they can return another observable object (Deferred, Promise, etc) which will pass its resolved / rejected status and values to the piped promise's callbacks. If the filter function used is `null`, or not specified, the piped promise will be resolved or rejected with the same values as the original.

### Example 1

Filter resolve value:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

### Example 2

Filter reject value:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

### Example 3

Chain tasks:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |