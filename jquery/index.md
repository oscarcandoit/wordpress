---
url: https://api.jquery.com/index/
scraped_at: 2025-10-20T03:16:11.036Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .index()Returns: [Integer](http://api.jquery.com/Types/\#Integer)

**Description:** Search for a given element from among the matched elements.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.index()](https://api.jquery.com/index/\#index)

  - This signature does not accept any arguments.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.index( selector )](https://api.jquery.com/index/\#index-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A selector representing a jQuery collection in which to look for an element.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.index( element )](https://api.jquery.com/index/\#index-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    The DOM element or first element within the jQuery object to look for.

#### Return Values

If no argument is passed to the `.index()` method, the return value is an integer indicating the position of the first element within the jQuery object relative to its sibling elements.

If `.index()` is called on a collection of elements and a DOM element or jQuery object is passed in, `.index()` returns an integer indicating the position of the passed element relative to the original collection.

If a selector string is passed as an argument, `.index()` returns an integer indicating the position of the first element within the jQuery object relative to the elements matched by the selector. If the element is not found, `.index()` will return -1.

#### Detail

The complementary operation to `.get()`, which accepts an index and returns a DOM node, `.index()` can take a DOM node and returns an index. Suppose we have a simple unordered list on the page:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

If we retrieve one of the three list items (for example, through a DOM function or as the context to an event handler), `.index()` can search for this list item within the set of matched elements:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

We get back the zero-based position of the list item:

`Index: 1`

Similarly, if we retrieve a jQuery object consisting of one of the three list items, `.index()` will search for that list item:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

We get back the zero-based position of the list item:

`Index: 1`

Note that if the jQuery collection used as the `.index()` method's argument contains more than one element, the first element within the matched set of elements will be used.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

We get back the zero-based position of the first list item within the matched set:

`Index: 1`

If we use a string as the `.index()` method's argument, it is interpreted as a jQuery selector string. The first element among the object's matched elements which also matches this selector is located.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

We get back the zero-based position of the list item:

`Index: 1`

If we omit the argument, `.index()` will return the position of the first element within the set of matched elements in relation to its siblings:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Again, we get back the zero-based position of the list item:

`Index: 1`

### Example 1

On click, returns the index (zero-based) of that div in the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

### Example 2

Returns the index for the element with ID bar.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

### Example 3

Returns the index for the first item in the jQuery collection.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

### Example 4

Returns the index for the element with ID bar in relation to all <li> elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 5

Returns the index for the element with ID bar in relation to its siblings.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

### Example 6

Returns -1, as there is no element with ID foobar.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo: