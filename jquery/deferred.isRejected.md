---
url: https://api.jquery.com/deferred.isRejected/
scraped_at: 2025-10-20T03:06:26.545Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.isRejected()Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.8](https://api.jquery.com/category/version/1.8/)

**Description:** Determine whether a Deferred object has been rejected.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.isRejected()](https://api.jquery.com/deferred.isRejected/\#deferred-isRejected)

  - This method does not accept any arguments.

Note: This API has been removed in jQuery 1.8; please use [`deferred.state()`](https://api.jquery.com/deferred.state/) instead.

Returns `true` if the Deferred object is in the rejected state, meaning that either [`deferred.reject()`](https://api.jquery.com/deferred.reject/) or [`deferred.rejectWith()`](https://api.jquery.com/deferred.rejectWith/) has been called for the object and the failCallbacks have been called (or are in the process of being called).

Note that a Deferred object can be in one of three states: pending, resolved, or rejected; use [`deferred.isResolved()`](https://api.jquery.com/deferred.isResolved/) to determine whether the Deferred object is in the resolved state. These methods are primarily useful for debugging, for example to determine whether a Deferred has already been resolved even though you are inside code that intended to reject it.