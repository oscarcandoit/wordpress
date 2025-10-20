---
url: https://api.jquery.com/jQuery.contains/
scraped_at: 2025-10-20T03:14:14.371Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.contains( container, contained )Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)

**Description:** Check to see if a DOM element is a descendant of another DOM element.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery.contains( container, contained )](https://api.jquery.com/jQuery.contains/\#jQuery-contains-container-contained)

  - **container**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The DOM element that may contain the other element.

  - **contained**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The DOM element that may be contained by (a descendant of) the other element.

The `$.contains()` method returns `true` if the DOM element provided by the second argument is a descendant of the DOM element provided by the first argument, whether it is a direct child or nested more deeply. Otherwise, it returns `false`. Only _element_ nodes are supported; if the second argument is a text or comment node, `$.contains()` will return `false`.

**Note:** The first argument _must_ be a DOM element, not a jQuery object or plain JavaScript object.

Check if an element is a descendant of another.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |