---
url: https://api.jquery.com/add/
scraped_at: 2025-10-20T02:59:56.054Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .add( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Create a new jQuery object with elements added to the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.add( selector )](https://api.jquery.com/add/\#add-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string representing a selector expression to find additional elements to add to the set of matched elements.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.add( elements )](https://api.jquery.com/add/\#add-elements)

  - **elements**

    Type: [Element](http://api.jquery.com/Types/#Element)

    One or more elements to add to the set of matched elements.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.add( html )](https://api.jquery.com/add/\#add-html)

  - **html**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString)

    An HTML fragment to add to the set of matched elements.
- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [.add( selection )](https://api.jquery.com/add/\#add-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    An existing jQuery object to add to the set of matched elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.add( selector, context )](https://api.jquery.com/add/\#add-selector-context)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string representing a selector expression to find additional elements to add to the set of matched elements.

  - **context**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The point in the document at which the selector should begin matching; similar to the context argument of the `$(selector, context)` method.

Given a jQuery object that represents a set of DOM elements, the `.add()` method constructs a new jQuery object from the union of those elements and the ones passed into the method. The argument to `.add()` can be pretty much anything that `$()` accepts, including a jQuery selector expression, references to DOM elements, or an HTML snippet.

Do not assume that this method appends the elements to the existing collection in the order they are passed to the `.add()` method. When all elements are members of the same document, the resulting collection from `.add()` will be sorted in document order; that is, in order of each element's appearance in the document. If the collection consists of elements from different documents or ones not in any document, the sort order is undefined. To create a jQuery object with elements in a well-defined order and without sorting overhead, use the `$(array_of_DOM_elements)` signature.

The updated set of elements can be used in a following (chained) method, or assigned to a variable for later use. For example:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The following will _not_ save the added elements, because the `.add()` method creates a new set and leaves the original set in pdiv unchanged:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Consider a page with a simple list and a paragraph following it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

We can select the list items and then the paragraph by using either a selector or a reference to the DOM element itself as the `.add()` method's argument:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Or:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The result of this call is a red background behind all four elements.
Using an HTML snippet as the `.add()` method's argument (as in the third version), we can create additional elements on the fly and add those elements to the matched set of elements. Let's say, for example, that we want to alter the background of the list items along with a newly created paragraph:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Although the new paragraph has been created and its background color changed, it still does not appear on the page. To place it on the page, we could add one of the insertion methods to the chain.

As of jQuery 1.4 the results from .add() will always be returned in document order (rather than a simple concatenation).

**Note:** To reverse the `.add()` you can use [`.not( elements | selector )`](https://api.jquery.com/not/) to remove elements from the jQuery results, or [`.end()`](https://api.jquery.com/end/) to return to the selection before you added.

### Example 1

Finds all divs and makes a border. Then adds all paragraphs to the jQuery object to set their backgrounds yellow.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo:

### Example 2

Adds more elements, matched by the given expression, to the set of matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18 | ```<br>``` |

#### Demo:

### Example 3

Adds more elements, created on the fly, to the set of matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

#### Demo:

### Example 4

Adds one or more Elements to the set of matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18 | ```<br>``` |

#### Demo:

### Example 5

Demonstrates how to add (or push) elements to an existing collection

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Demo: