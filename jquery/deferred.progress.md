---
url: https://api.jquery.com/deferred.progress/
scraped_at: 2025-10-20T03:06:53.280Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.progress( progressCallbacks \[, progressCallbacks \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Add handlers to be called when the Deferred object generates progress notifications.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [deferred.progress( progressCallbacks \[, progressCallbacks \] )](https://api.jquery.com/deferred.progress/\#deferred-progress-progressCallbacks-progressCallbacks)

  - **progressCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)() or [Array](http://api.jquery.com/Types/#Array)


     A function, or array of functions, to be called when the Deferred generates progress notifications.


  - **progressCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)() or [Array](http://api.jquery.com/Types/#Array)


     Optional additional functions, or arrays of functions, to be called when the Deferred generates progress notifications.

The `deferred.progress()` method accepts one or more arguments, all of which can be either a single function or an array of functions. When the Deferred generates progress notifications by calling `notify` or `notifyWith`, the `progressCallbacks` are called. Since `deferred.progress()` returns the Deferred object, other methods of the Deferred object can be chained to this one. When the Deferred is resolved or rejected, progress callbacks will no longer be called, with the exception that any `progressCallbacks` added after the Deferred enters the resolved or rejected state are executed immediately when they are added, using the arguments that were passed to the `.notify()` or `notifyWith()` call. For more information, see the documentation for [jQuery.Deferred()](https://api.jquery.com/jQuery.Deferred/).