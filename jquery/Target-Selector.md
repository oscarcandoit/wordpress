---
url: https://api.jquery.com/target-selector/
scraped_at: 2025-10-20T03:30:05.063Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## target selector

**Description:** Selects the target element indicated by the fragment identifier of the document's URI.

- #### version added: [1.9](https://api.jquery.com/category/version/1.9/)jQuery( ":target" )


If the document's URI contains a fragment identifier, or hash, then the `:target` selector will match the element with an ID that matches the identifier. For example, given a document with a URI of https://example.com/#foo, `$( "p:target" )` will select the `<p id="foo">` element.

Further discussion of this usage can be found in the [W3C CSS specification](https://www.w3.org/TR/css3-selectors/#target-pseudo).