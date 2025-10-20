---
url: https://api.jquery.com/jQuery.support/
scraped_at: 2025-10-20T03:24:47.631Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.supportReturns: [Object](http://api.jquery.com/Types/\#Object)version deprecated: [1.9](https://api.jquery.com/category/version/1.9/)

**Description:** A collection of properties that represent the presence of different browser features or bugs; intended for jQuery's internal use.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/)jQuery.support


A collection of properties that represent the presence of different browser features or bugs. Intended for jQuery's internal use; specific properties may be removed when they are no longer needed internally to improve page startup performance. For your own project's feature-detection needs, we strongly recommend the use of an external library such as [Modernizr](https://modernizr.com/) instead of dependency on properties in `jQuery.support`.

As of jQuery 1.11 or 1.12, `jQuery.support` is no longer JSON-serializable; some properties point to functions that return the support test result when called. This was necessary to support lazy execution of support tests.