---
url: https://api.jquery.com/deferred.isResolved/
scraped_at: 2025-10-20T03:06:29.717Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.isResolved()Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.8](https://api.jquery.com/category/version/1.8/)

**Description:** Determine whether a Deferred object has been resolved.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.isResolved()](https://api.jquery.com/deferred.isResolved/\#deferred-isResolved)

  - This method does not accept any arguments.

Note: This API has been removed in jQuery 1.8; please use [`deferred.state()`](https://api.jquery.com/deferred.state/) instead.

Returns `true` if the Deferred object is in the resolved state, meaning that either [`deferred.resolve()`](https://api.jquery.com/deferred.resolve/) or [`deferred.resolveWith()`](https://api.jquery.com/deferred.resolveWith/) has been called for the object and the doneCallbacks have been called (or are in the process of being called).

Note that a Deferred object can be in one of three states: pending, resolved, or rejected; use [`deferred.isRejected()`](https://api.jquery.com/deferred.isRejected/) to determine whether the Deferred object is in the rejected state. These methods are primarily useful for debugging, for example to determine whether a Deferred has already been resolved even though you are inside code that intended to reject it.