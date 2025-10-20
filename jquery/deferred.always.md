---
url: https://api.jquery.com/deferred.always/
scraped_at: 2025-10-20T03:05:45.699Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.always( alwaysCallbacks \[, alwaysCallbacks \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Add handlers to be called when the Deferred object is either resolved or rejected.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [deferred.always( alwaysCallbacks \[, alwaysCallbacks \] )](https://api.jquery.com/deferred.always/\#deferred-always-alwaysCallbacks-alwaysCallbacks)

  - **alwaysCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, that is called when the Deferred is resolved or rejected.


  - **alwaysCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     Optional additional functions, or arrays of functions, that are called when the Deferred is resolved or rejected.

The argument can be either a single function or an array of functions. When the Deferred is resolved or rejected, the `alwaysCallbacks` are called. Since `deferred.always()` returns the Deferred object, other methods of the Deferred object can be chained to this one, including additional `.always()` methods. When the Deferred is resolved or rejected, callbacks are executed in the order they were added, using the arguments provided to the [`resolve`](https://api.jquery.com/deferred.resolve/), [`reject`](https://api.jquery.com/deferred.reject/), [`resolveWith`](https://api.jquery.com/deferred.resolveWith/) or [`rejectWith`](https://api.jquery.com/deferred.rejectWith/) method calls. For more information, see the documentation for [Deferred object](https://api.jquery.com/category/deferred-object/).

**Note:** The `deferred.always()` method receives the arguments that were used to `.resolve()` or `.reject()` the `Deferred` object, which are often very different. For this reason, it's best to use it only for actions that do not require inspecting the arguments. In all other cases, use explicit [`.done()`](https://api.jquery.com/deferred.done/) or [`.fail()`](https://api.jquery.com/deferred.fail/) handlers since the arguments will have well-known orders.

Since the [`jQuery.get()`](https://api.jquery.com/jQuery.get/) method returns a `jqXHR` object, which is derived from a Deferred object, we can attach a callback for both success and error using the `deferred.always()` method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |