---
url: https://api.jquery.com/wrap/
scraped_at: 2025-10-20T03:17:28.564Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .wrap( wrappingElement )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Wrap an HTML structure around each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.wrap( wrappingElement )](https://api.jquery.com/wrap/\#wrap-wrappingElement)

  - **wrappingElement**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A selector, element, HTML string, or jQuery object specifying the structure to wrap around the matched elements. When you pass a jQuery collection containing more than one element, or a selector matching more than one element, the first element will be used.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.wrap( function )](https://api.jquery.com/wrap/\#wrap-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index )
     =>
     [String](http://api.jquery.com/Types/#String) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A callback function returning the HTML content or jQuery object to wrap around the matched elements. Receives the index position of the element in the set as an argument. Within the function, `this` refers to the current element in the set.

The `.wrap()` function can take any string or object that could be passed to the `$()` factory function to specify a DOM structure. This structure may be nested several levels deep, but should contain only one inmost element. A copy of this structure will be wrapped around each of the elements in the set of matched elements. This method returns the original set of elements for chaining purposes.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Using `.wrap()`, we can insert an HTML structure around the inner `<div>` elements like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The new `<div>` element is created on the fly and added to the DOM. The result is a new `<div>` wrapped around each matched element:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

The second version of this method allows us to instead specify a callback function. This callback function will be called once for every matched element; it should return a DOM element, jQuery object, or HTML snippet in which to wrap the corresponding element. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This will cause each `<div>` to have a class corresponding to the text it wraps:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### Example 1

Wrap a new div around all of the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Wraps a newly created tree of objects around the spans. Notice anything in between the spans gets left out like the <strong> (red text) in this example. Even the white space between spans is left out. Click View Source to see the original html.>

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo:

### Example 3

Wrap a new div around all of the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 4

Wrap a jQuery object double depth div around all of the paragraphs. Notice it doesn't move the object but just clones it to wrap around its target.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo: