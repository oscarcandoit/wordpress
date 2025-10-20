---
url: https://api.jquery.com/deferred.state/
scraped_at: 2025-10-20T03:07:17.523Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.state()Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Determine the current state of a Deferred object.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [deferred.state()](https://api.jquery.com/deferred.state/\#deferred-state)

  - This method does not accept any arguments.

The deferred.state() method returns a string representing the current state of the Deferred object. The Deferred object can be in one of three states:

- **"pending"**: The Deferred object is not yet in a completed state (neither "rejected" nor "resolved").
- **"resolved"**: The Deferred object is in the resolved state, meaning that either [`deferred.resolve()`](https://api.jquery.com/deferred.resolve/) or [`deferred.resolveWith()`](https://api.jquery.com/deferred.resolveWith/) has been called for the object and the doneCallbacks have been called (or are in the process of being called).
- **"rejected"**: The Deferred object is in the rejected state, meaning that either [`deferred.reject()`](https://api.jquery.com/deferred.reject/) or [`deferred.rejectWith()`](https://api.jquery.com/deferred.rejectWith/) has been called for the object and the failCallbacks have been called (or are in the process of being called).

This method is primarily useful for debugging to determine, for example, whether a Deferred has already been resolved even though you are inside code that intended to reject it.