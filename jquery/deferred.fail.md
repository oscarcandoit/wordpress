---
url: https://api.jquery.com/deferred.fail/
scraped_at: 2025-10-20T03:06:18.858Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.fail( failCallbacks \[, failCallbacks \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Add handlers to be called when the Deferred object is rejected.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.fail( failCallbacks \[, failCallbacks \] )](https://api.jquery.com/deferred.fail/\#deferred-fail-failCallbacks-failCallbacks)

  - **failCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, that are called when the Deferred is rejected.


  - **failCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     Optional additional functions, or arrays of functions, that are called when the Deferred is rejected.

The `deferred.fail()` method accepts one or more arguments, all of which can be either a single function or an array of functions. When the Deferred is rejected, the failCallbacks are called. Callbacks are executed in the order they were added. Since `deferred.fail()` returns the deferred object, other methods of the deferred object can be chained to this one, including additional `deferred.fail()` methods. The failCallbacks are executed using the arguments provided to the [`deferred.reject()`](https://api.jquery.com/deferred.reject/) or [`deferred.rejectWith()`](https://api.jquery.com/deferred.rejectWith/) method call in the order they were added. For more information, see the documentation for [Deferred object](https://api.jquery.com/category/deferred-object/).

Since the [`jQuery.get`](https://api.jquery.com/jQuery.get/) method returns a jqXHR object, which is derived from a Deferred, you can attach a success and failure callback using the `deferred.done()` and `deferred.fail()` methods.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |