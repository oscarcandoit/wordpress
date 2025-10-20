---
url: https://api.jquery.com/deferred.resolve/
scraped_at: 2025-10-20T03:07:09.552Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.resolve( \[args \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Resolve a Deferred object and call any doneCallbacks with the given `args`.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.resolve( \[args \] )](https://api.jquery.com/deferred.resolve/\#deferred-resolve-args)

  - **args**

    Type: [Anything](http://api.jquery.com/Types/#Anything)


     Optional arguments that are passed to the doneCallbacks.

Normally, only the creator of a Deferred should call this method; you can prevent other code from changing the Deferred's state by returning a restricted Promise object through [`deferred.promise()`](https://api.jquery.com/deferred.promise/).

When the Deferred is resolved, any doneCallbacks added by [`deferred.then()`](https://api.jquery.com/deferred.then/) or [`deferred.done()`](https://api.jquery.com/deferred.done/) are called. Callbacks are executed in the order they were added. Each callback is passed the `args` from the `deferred.resolve()`. Any doneCallbacks added after the Deferred enters the resolved state are executed immediately when they are added, using the arguments that were passed to the `deferred.resolve()` call. For more information, see the documentation for [jQuery.Deferred()](https://api.jquery.com/jQuery.Deferred/).