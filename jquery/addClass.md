---
url: https://api.jquery.com/addClass/
scraped_at: 2025-10-20T03:17:41.970Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .addClass( className )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Adds the specified class(es) to each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.addClass( className )](https://api.jquery.com/addClass/\#addClass-className)

  - **className**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more space-separated classes to be added to the class attribute of each matched element.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.addClass( classNames )](https://api.jquery.com/addClass/\#addClass-classNames)

  - **classNames**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of classes to be added to the class attribute of each matched element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.addClass( function )](https://api.jquery.com/addClass/\#addClass-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) currentClassName )
     =>
     [String](http://api.jquery.com/Types/#String)

    A function returning one or more space-separated class names to be added to the existing class name(s). Receives the index position of the element in the set and the existing class name(s) as arguments. Within the function, `this` refers to the current element in the set.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.addClass( function )](https://api.jquery.com/addClass/\#addClass-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) currentClassName )
     =>
     [String](http://api.jquery.com/Types/#String) \| [Array](http://api.jquery.com/Types/#Array)

    A function returning one or more space-separated class names or an array of class names to be added to the existing class name(s). Receives the index position of the element in the set and the existing class name(s) as arguments. Within the function, `this` refers to the current element in the set.

It's important to note that this method does not replace a class. It simply adds the class, appending it to any which may already be assigned to the elements.

Before jQuery version 1.12/2.2, the `.addClass()` method manipulated the `className` _property_ of the selected elements, not the `class` _attribute_. Once the property was changed, it was the browser that updated the attribute accordingly. An implication of this behavior was that this method only worked for documents with HTML DOM semantics (e.g., not pure XML documents).

As of jQuery 1.12/2.2, this behavior is changed to improve the support for XML documents, including SVG. Starting from this version, the `class` _attribute_ is used instead. So, `.addClass()` can be used on XML or SVG documents.

More than one class may be added at a time, separated by a space, to the set of matched elements, like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This method is often used with `.removeClass()` to switch elements' classes from one to another, like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Here, the `myClass` and `noClass` classes are removed from all paragraphs, while `yourClass` is added.

As of jQuery 1.4, the `.addClass()` method's argument can receive a function.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Given an unordered list with two `<li>` elements, this example adds the class "item-0" to the first `<li>` and "item-1" to the second.

### Example 1

Add the class "selected" to the matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 2

Add the classes "selected" and "highlight" to the matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 3

Add the classes "selected" and "highlight" to the matched elements (3.3+ syntax).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 4

Pass in a function to `.addClass()` to add the "green" class to a div that already has a "red" class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo: