---
url: https://api.jquery.com/not/
scraped_at: 2025-10-20T03:01:57.059Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .not( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove elements from the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.not( selector )](https://api.jquery.com/not/\#not-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [Element](http://api.jquery.com/Types/#Element) or [Array](http://api.jquery.com/Types/#Array)

    A string containing a selector expression, a DOM element, or an array of elements to match against the set.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.not( function )](https://api.jquery.com/not/\#not-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Element](http://api.jquery.com/Types/#Element) element )
     =>
     [Boolean](http://api.jquery.com/Types/#Boolean)

    A function used as a test for each element in the set. It accepts two arguments, `index`, which is the element's index in the jQuery collection, and `element`, which is the DOM element. Within the function, `this` refers to the current DOM element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.not( selection )](https://api.jquery.com/not/\#not-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    An existing jQuery object to match the current set of elements against.

Given a jQuery object that represents a set of DOM elements, the `.not()` method constructs a new jQuery object from a subset of the matching elements. The supplied selector is tested against each element; the elements that don't match the selector will be included in the result.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can apply this method to the set of list items:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for items 1, 3 and 5, as they do not match the selector.

#### Removing Specific Elements

The second version of the `.not()` method allows us to remove elements from the matched set, assuming we have found those elements previously by some other means. For example, suppose our list had an id applied to one of its items:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can fetch the third list item using the native JavaScript `getElementById()` function, then remove it from a jQuery object:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

This statement changes the color of items 1, 2, 4, and 5. We could have accomplished the same thing with a simpler jQuery expression, but this technique can be useful when, for example, other libraries provide references to plain DOM nodes.

As of jQuery 1.4, the `.not()` method can take a function as its argument in the same way that `.filter()` does. Elements for which the function returns `true` are excluded from the filtered set; all other elements are included.

**Note:** When a CSS selector string is passed to `.not()`, text and comment nodes will always be removed from the resulting jQuery object during the filtering process. When a specific node or array of nodes are provided, text or comment nodes will only be removed from the jQuery object if they match one of the nodes in the filtering array.

### Example 1

Adds a border to divs that are not green or blue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43 | ```<br>``` |

#### Demo:

### Example 2

Removes the element with the ID "selected" from the set of all paragraphs.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Removes the element with the ID "selected" from the set of all paragraphs.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Removes all elements that match "div p.selected" from the total set of all paragraphs.

|     |     |
| --- | --- |
| 1 | ```<br>``` |