---
url: https://api.jquery.com/filter/
scraped_at: 2025-10-20T03:01:16.083Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .filter( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Reduce the set of matched elements to those that match the selector or pass the function's test.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.filter( selector )](https://api.jquery.com/filter/\#filter-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match the current set of elements against.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.filter( function )](https://api.jquery.com/filter/\#filter-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Element](http://api.jquery.com/Types/#Element) element )
     =>
     [Boolean](http://api.jquery.com/Types/#Boolean)

    A function used as a test for each element in the set. `this` is the current DOM element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.filter( elements )](https://api.jquery.com/filter/\#filter-elements)

  - **elements**

    Type: [Element](http://api.jquery.com/Types/#Element)

    One or more DOM elements to match the current set of elements against.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.filter( selection )](https://api.jquery.com/filter/\#filter-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    An existing jQuery object to match the current set of elements against.

Given a jQuery object that represents a set of DOM elements, the `.filter()` method constructs a new jQuery object from a subset of the matching elements. The supplied selector is tested against each element; all elements matching the selector will be included in the result.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

We can apply this method to the set of list items:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for items 2, 4, and 6, as they match the selector.

#### Using a Filter Function

The second form of this method allows us to filter elements against a function rather than a selector. For each element, if the function returns `true` (or a "truthy" value), the element will be included in the filtered set; otherwise, it will be excluded. Suppose we have a somewhat more involved HTML snippet:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

We can select the list items, then filter them based on their contents:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

This code will alter the first list item only, as it contains exactly one `<strong>` tag. Within the filter function, `this` refers to each DOM element in turn. The parameter passed to the function tells us the index of that DOM element within the set matched by the jQuery object.

We can also take advantage of the `index` passed through the function, which indicates the 0-based position of the element within the unfiltered set of matched elements:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

This alteration to the code will cause the third and sixth list items to be highlighted, as it uses the modulus operator ( `%`) to select every item with an `index` value that, when divided by 3, has a remainder of `2`.

**Note:** When a CSS selector string is passed to `.filter()`, text and comment nodes will always be removed from the resulting jQuery object during the filtering process. When a specific node or array of nodes are provided, a text or comment node will be included in the resulting jQuery object only if it matches one of the nodes in the filtering array.

### Example 1

Change the color of all divs; then add a border to those with a "middle" class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo:

### Example 2

Change the color of all divs; then add a border to the second one (index == 1) and the div with an id of "fourth."

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 3

Select all divs and filter the selection with a DOM element, keeping only the one with an id of "unique".

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Select all divs and filter the selection with a jQuery object, keeping only the one with an id of "unique".

|     |     |
| --- | --- |
| 1 | ```<br>``` |