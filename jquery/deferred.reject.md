---
url: https://api.jquery.com/deferred.reject/
scraped_at: 2025-10-20T03:07:00.422Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.reject( \[args \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Reject a Deferred object and call any failCallbacks with the given `args`.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.reject( \[args \] )](https://api.jquery.com/deferred.reject/\#deferred-reject-args)

  - **args**

    Type: [Anything](http://api.jquery.com/Types/#Anything)


     Optional arguments that are passed to the failCallbacks.

Normally, only the creator of a Deferred should call this method; you can prevent other code from changing the Deferred's state by returning a restricted Promise object through [`deferred.promise()`](https://api.jquery.com/deferred.promise/).

When the Deferred is rejected, any failCallbacks added by [`deferred.then()`](https://api.jquery.com/deferred.then/) or [`deferred.fail()`](https://api.jquery.com/deferred.fail/) are called. Callbacks are executed in the order they were added. Each callback is passed the `args` from the `deferred.reject()` call. Any failCallbacks added after the Deferred enters the rejected state are executed immediately when they are added, using the arguments that were passed to the `deferred.reject()` call. For more information, see the documentation for [jQuery.Deferred()](https://api.jquery.com/jQuery.Deferred/).