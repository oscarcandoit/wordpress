---
url: https://api.jquery.com/replaceWith/
scraped_at: 2025-10-20T03:17:14.048Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .replaceWith( newContent )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Replace each element in the set of matched elements with the provided new content and return the set of elements that was removed.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.replaceWith( newContent )](https://api.jquery.com/replaceWith/\#replaceWith-newContent)

  - **newContent**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    The content to insert. May be an HTML string, DOM element, array of DOM elements, or jQuery object.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.replaceWith( function )](https://api.jquery.com/replaceWith/\#replaceWith-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function that returns content with which to replace the set of matched elements.

The `.replaceWith()` method removes content from the DOM and inserts new content in its place with a single call. Consider this DOM structure:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

The second inner `<div>` could be replaced with the specified HTML:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This results in the structure:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

_All_ inner `<div>` elements could be targeted at once:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This causes all of them to be replaced:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

An element could also be selected as the replacement:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This results in the DOM structure:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

This example demonstrates that the selected element replaces the target by being moved from its old location, not by being cloned.

The `.replaceWith()` method, like most jQuery methods, returns the jQuery object so that other methods can be chained onto it. However, it must be noted that the _original_ jQuery object is returned. This object refers to the element that has been removed from the DOM, not the new element that has replaced it.

### Additional Notes:

- The `.replaceWith()` method removes all data and event handlers associated with the removed nodes.

- Prior to jQuery 1.9, `.replaceWith()` would attempt to add or change nodes in the current jQuery set if the first node in the set was not connected to a document, and in those cases return a new jQuery set rather than the original set. The method might or might not have returned a new result depending on the number or connectedness of its arguments! As of jQuery 1.9, `.after()`, `.before()`, and `.replaceWith()` always return the original unmodified set. Attempting to use these methods on a node without a parent has no effect—that is, neither the set nor the nodes it contains are changed.


### Example 1

On click, replace the button with a div containing the same word.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 2

Replace all paragraphs with bold words.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo:

### Example 3

On click, replace each paragraph with a div that is already in the DOM and selected with the `$()` function. Notice it doesn't clone the object but rather moves it to replace the paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 4

On button click, replace the containing div with its child divs and append the class name of the selected element to the paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo: