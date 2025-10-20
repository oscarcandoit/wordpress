---
url: https://api.jquery.com/pushStack/
scraped_at: 2025-10-20T03:15:59.362Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .pushStack( elements )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Add a collection of DOM elements onto the jQuery stack.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.pushStack( elements )](https://api.jquery.com/pushStack/\#pushStack-elements)

  - **elements**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of elements to push onto the stack and make into a new jQuery object.
- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.pushStack( elements, name, arguments )](https://api.jquery.com/pushStack/\#pushStack-elements-name-arguments)

  - **elements**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of elements to push onto the stack and make into a new jQuery object.

  - **name**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of a jQuery method that generated the array of elements.

  - **arguments**

    Type: [Array](http://api.jquery.com/Types/#Array)

    The arguments that were passed in to the jQuery method (for serialization).

Add some elements onto the jQuery stack, then pop back off again.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |