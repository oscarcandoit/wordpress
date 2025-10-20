---
url: https://api.jquery.com/removeClass/
scraped_at: 2025-10-20T03:18:08.684Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Remove a single class, multiple classes, or all classes from each element in the set of matched elements.

#### Contents:

- [.removeClass( className )](https://api.jquery.com/removeClass/#removeClass1)  - [.removeClass( className )](https://api.jquery.com/removeClass/#removeClass-className)
  - [.removeClass( classNames )](https://api.jquery.com/removeClass/#removeClass-classNames)
  - [.removeClass( function )](https://api.jquery.com/removeClass/#removeClass-function)
  - [.removeClass( function )](https://api.jquery.com/removeClass/#removeClass-function)
- [.removeClass()](https://api.jquery.com/removeClass/#removeClass2)  - [.removeClass()](https://api.jquery.com/removeClass/#removeClass)

## .removeClass( className )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove a single class or multiple classes from each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.removeClass( className )](https://api.jquery.com/removeClass/\#removeClass-className)

  - **className**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more space-separated classes to be removed from the class attribute of each matched element.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.removeClass( classNames )](https://api.jquery.com/removeClass/\#removeClass-classNames)

  - **classNames**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of classes to be removed from the class attribute of each matched element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.removeClass( function )](https://api.jquery.com/removeClass/\#removeClass-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) className )
     =>
     [String](http://api.jquery.com/Types/#String)

    A function returning one or more space-separated class names to be removed. Receives the index position of the element in the set and the old class value as arguments.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.removeClass( function )](https://api.jquery.com/removeClass/\#removeClass-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) className )
     =>
     [String](http://api.jquery.com/Types/#String) \| [Array](http://api.jquery.com/Types/#Array)

    A function returning one or more space-separated class names or an array of class names to be removed. Receives the index position of the element in the set and the old class value as arguments.

Before jQuery version 1.12/2.2, the `.removeClass()` method manipulated the `className` _property_ of the selected elements, not the `class` _attribute_. Once the property was changed, it was the browser that updated the attribute accordingly. This means that when the `class` attribute was updated and the last class name was removed, the browser might have set the attribute's value to an empty string instead of removing the attribute completely. An implication of this behavior was that this method only worked for documents with HTML DOM semantics (e.g., not pure XML documents).

As of jQuery 1.12/2.2, this behavior is changed to improve the support for XML documents, including SVG. Starting from this version, the `class` _attribute_ is used instead. So, `.removeClass()` can be used on XML or SVG documents.

More than one class may be removed at a time, separated by a space, from the set of matched elements, like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This method is often used with `.addClass()` to switch elements' classes from one to another, like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Here, the `myClass` and `noClass` classes are removed from all paragraphs, while `yourClass` is added.

To replace all existing classes with another class, we can use `.attr( "class", "newClass" )` instead.

As of jQuery 1.4, the `.removeClass()` method allows us to indicate the class to be removed by passing in a function.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This example removes the class name of the penultimate `<li>` from the last `<li>`.

### Example 1

Remove the class 'blue' from the matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 2

Remove the class 'blue' and 'under' from the matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 3

Remove the class 'blue' and 'under' from the matched elements (3.3+ syntax).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

## .removeClass()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove all classes from each matched element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.removeClass()](https://api.jquery.com/removeClass/\#removeClass)

  - This method does not accept any arguments.

Before jQuery version 1.12/2.2, the `.removeClass()` method manipulated the `className` _property_ of the selected elements, not the `class` _attribute_. Once the property was changed, it was the browser that updated the attribute accordingly. This means that when the `class` attribute was updated and the last class name was removed, the browser might have set the attribute's value to an empty string instead of removing the attribute completely. An implication of this behavior was that this method only worked for documents with HTML DOM semantics (e.g., not pure XML documents).

As of jQuery 1.12/2.2, this behavior is changed to improve the support for XML documents, including SVG. Starting from this version, the `class` _attribute_ is used instead. So, `.removeClass()` can be used on XML or SVG documents.

Remove all the classes from the matched elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: