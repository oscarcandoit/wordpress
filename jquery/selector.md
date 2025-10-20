---
url: https://api.jquery.com/selector/
scraped_at: 2025-10-20T02:58:38.444Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## selectorReturns: [String](http://api.jquery.com/Types/\#String)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** A selector representing selector passed to jQuery(), if any, when creating the original set.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/)selector


Note: This API has been removed in jQuery 3.0. The property was never a reliable indicator of the selector that could be used to obtain the set of elements currently contained in the jQuery set where it was a property, since subsequent traversal methods may have changed the set. Plugins that need to use a selector string within their plugin can require it as a parameter of the method. For example, a "foo" plugin could be written as `$.fn.foo = function( selector, options ) { /* plugin code goes here */ };`, and the person using the plugin would write `$( "div.bar" ).foo( "div.bar", {dog: "bark"} );` with the `"div.bar"` selector repeated as the first argument of `.foo()`.