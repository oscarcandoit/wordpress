---
url: https://api.jquery.com/closest/
scraped_at: 2025-10-20T03:00:49.859Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

#### Contents:

- [.closest( selector )](https://api.jquery.com/closest/#closest1)  - [.closest( selector )](https://api.jquery.com/closest/#closest-selector)
  - [.closest( selector \[, context \] )](https://api.jquery.com/closest/#closest-selector-context)
  - [.closest( selection )](https://api.jquery.com/closest/#closest-selection)
  - [.closest( element )](https://api.jquery.com/closest/#closest-element)
- [.closest( selectors \[, context \] )](https://api.jquery.com/closest/#closest2)  - [.closest( selectors \[, context \] )](https://api.jquery.com/closest/#closest-selectors-context)

## .closest( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** For each element in the set, get the first element that matches the selector by testing the element itself and traversing up through its ancestors in the DOM tree.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.closest( selector )](https://api.jquery.com/closest/\#closest-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.closest( selector \[, context \] )](https://api.jquery.com/closest/\#closest-selector-context)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

  - **context**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element within which a matching element may be found.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.closest( selection )](https://api.jquery.com/closest/\#closest-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    A jQuery object to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.closest( element )](https://api.jquery.com/closest/\#closest-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    An element to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.closest()` method searches through these elements and their ancestors in the DOM tree and constructs a new jQuery object from the matching elements. The [`.parents()`](https://api.jquery.com/parents/) and `.closest()` methods are similar in that they both traverse up the DOM tree. The differences between the two, though subtle, are significant:

| `.closest()` | [`.parents()`](https://api.jquery.com/parents/) |
| --- | --- |
| Begins with the current element | Begins with the parent element |
| Travels up the DOM tree until it finds a match for the supplied selector | Travels up the DOM tree to the document's root element, adding each ancestor element to a temporary collection; it then filters that collection based on a selector if one is supplied |
| The returned jQuery object contains zero or one element for each element in the original set, in document order | The returned jQuery object contains zero or more elements for each element in the original set, in reverse document order |

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

Suppose we perform a search for `<ul>` elements starting at item A:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This will change the color of the level-2 `<ul>`, since it is the first encountered when traveling up the DOM tree.

Suppose we search for an `<li>` element instead:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This will change the color of list item A. The `.closest()` method begins its search _with the element itself_ before progressing up the DOM tree, and stops when item A matches the selector.

We can pass in a DOM element as the context within which to search for the closest element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

This will change the color of the level-2 `<ul>`, because it is both the first `<ul>` ancestor of list item A and a descendant of list item II. It will not change the color of the level-1 `<ul>`, however, because it is not a descendant of list item II.

### Example 1

Show how event delegation can be done with closest. The closest list element toggles a yellow background when it or its descendent is clicked.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo:

### Example 2

Pass a jQuery object to closest. The closest list element toggles a yellow background when it or its descendent is clicked.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

## .closest( selectors \[, context \] )Returns: [Array](http://api.jquery.com/Types/\#Array)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.8](https://api.jquery.com/category/version/1.8/)

**Description:** Get an array of all the elements and selectors matched against the current element up through the DOM tree.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.closest( selectors \[, context \] )](https://api.jquery.com/closest/\#closest-selectors-context)

  - **selectors**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array or string containing a selector expression to match elements against (can also be a jQuery object).

  - **context**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element within which a matching element may be found.

**This signature (only!) is deprecated as of jQuery 1.7 and _removed_ in jQuery 1.8**. It was primarily meant to be used internally or by plugin authors.