---
url: https://api.jquery.com/wrapInner/
scraped_at: 2025-10-20T03:17:36.610Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .wrapInner( wrappingElement )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Wrap an HTML structure around the content of each element in the set of matched elements.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.wrapInner( wrappingElement )](https://api.jquery.com/wrapInner/\#wrapInner-wrappingElement)

  - **wrappingElement**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Selector](http://api.jquery.com/Types/#Selector) or [jQuery](http://api.jquery.com/Types/#jQuery) or [Element](http://api.jquery.com/Types/#Element)

    An HTML snippet, selector expression, jQuery object, or DOM element specifying the structure to wrap around the content of the matched elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.wrapInner( function )](https://api.jquery.com/wrapInner/\#wrapInner-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index )
     =>
     [String](http://api.jquery.com/Types/#String)

    A callback function which generates a structure to wrap around the content of the matched elements. Receives the index position of the element in the set as an argument. Within the function, `this` refers to the current element in the set.

The `.wrapInner()` function can take any string or object that could be passed to the `$()` factory function to specify a DOM structure. This structure may be nested several levels deep, but should contain only one inmost element. The structure will be wrapped around the content of each of the elements in the set of matched elements.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Using `.wrapInner()`, we can insert an HTML structure around the content of each inner `<div>` elements like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The new `<div>` element is created on the fly and added to the DOM. The result is a new `<div>` wrapped around the content of each matched element:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

The second version of this method allows us to instead specify a callback function. This callback function will be called once for every matched element; it should return a DOM element, jQuery object, or HTML snippet in which to wrap the content of the corresponding element. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This will cause each `<div>` to have a class corresponding to the text it wraps:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

**Note:** When passing a selector string to the `.wrapInner()` function, the expected input is well formed HTML with correctly closed tags. Examples of valid input include:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Example 1

Selects all paragraphs and wraps a bold tag around each of its contents.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24 | ```<br>``` |

#### Demo:

### Example 2

Wraps a newly created tree of objects around the inside of the body.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

### Example 3

Selects all paragraphs and wraps a bold tag around each of its contents.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24 | ```<br>``` |

#### Demo:

### Example 4

Selects all paragraphs and wraps a jQuery object around each of its contents.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo: