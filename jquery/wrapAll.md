---
url: https://api.jquery.com/wrapAll/
scraped_at: 2025-10-20T03:17:32.242Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .wrapAll( wrappingElement )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Wrap an HTML structure around all elements in the set of matched elements.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.wrapAll( wrappingElement )](https://api.jquery.com/wrapAll/\#wrapAll-wrappingElement)

  - **wrappingElement**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A selector, element, HTML string, or jQuery object specifying the structure to wrap around the matched elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.wrapAll( function )](https://api.jquery.com/wrapAll/\#wrapAll-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)()
     =>
     [String](http://api.jquery.com/Types/#String) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A callback function returning the HTML content or jQuery object to wrap around all the matched elements. Within the function, `this` refers to the first element in the set. **Prior to jQuery 3.0**, the callback was incorrectly called for every element in the set and received the index position of the element in the set as an argument.

The `.wrapAll()` function can take any string or object that could be passed to the `$()` function to specify a DOM structure. This structure may be nested several levels deep, but should contain only one inmost element. The structure will be wrapped around all of the elements in the set of matched elements, as a single group.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Using `.wrapAll()`, we can insert an HTML structure around the inner `<div>` elements like so:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The new `<div>` element is created on the fly and added to the DOM. The result is a new `<div>` wrapped around all matched elements:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

### Example 1

Wrap a new div around all of the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Wraps a newly created tree of objects around the spans. Notice anything in between the spans gets left out like the <strong> (red text) in this example. Even the white space between spans is left out. Click View Source to see the original html.

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