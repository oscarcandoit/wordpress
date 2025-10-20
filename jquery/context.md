---
url: https://api.jquery.com/context/
scraped_at: 2025-10-20T02:58:42.490Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## contextReturns: [Element](http://api.jquery.com/Types/\#Element)version deprecated: [1.10-and-2.0](https://api.jquery.com/category/version/1.10-and-2.0/), removed: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** The DOM node context originally passed to `jQuery()`; if none was passed then context will likely be the document.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/)context


Note: This API has been removed in jQuery 3.0.

The `.live()` method for binding event handlers uses this property to determine the root element to use for its event delegation needs.

The value of this property is typically equal to `document`, as this is the default context for jQuery objects if none is supplied. The context may differ if, for example, the object was created by searching within an `<iframe>` or XML document.

Note that the context property may only apply to the elements originally selected by `jQuery()`, as it is possible for the user to add elements to the collection via methods such as `.add()` and these may have a different context.

Determine the exact context used.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |