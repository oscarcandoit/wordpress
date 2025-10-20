---
url: https://api.jquery.com/deferred.notify/
scraped_at: 2025-10-20T03:06:37.806Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.notify( args )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Call the progressCallbacks on a Deferred object with the given `args`.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [deferred.notify( args )](https://api.jquery.com/deferred.notify/\#deferred-notify-args)

  - **args**

    Type: [Object](http://api.jquery.com/Types/#Object)


     Optional arguments that are passed to the progressCallbacks.

Normally, only the creator of a Deferred should call this method; you can prevent other code from changing the Deferred's state or reporting status by returning a restricted Promise object through deferred.promise().

When `deferred.notify` is called, any progressCallbacks added by [`deferred.then`](https://api.jquery.com/deferred.then/) or [`deferred.progress`](https://api.jquery.com/deferred.progress/) are called. Callbacks are executed in the order they were added. Each callback is passed the `args` from the `.notify()`. Any calls to `.notify()` after a Deferred is resolved or rejected (or any progressCallbacks added after that) are ignored. For more information, see the documentation for [Deferred object](https://api.jquery.com/category/deferred-object/).