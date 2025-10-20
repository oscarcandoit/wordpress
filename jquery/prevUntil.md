---
url: https://api.jquery.com/prevUntil/
scraped_at: 2025-10-20T03:02:49.318Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .prevUntil( \[selector \] \[, filter \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get all preceding siblings of each element up to but not including the element matched by the selector, DOM node, or jQuery object.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.prevUntil( \[selector \] \[, filter \] )](https://api.jquery.com/prevUntil/\#prevUntil-selector-filter)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to indicate where to stop matching preceding sibling elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.prevUntil( \[element \] \[, filter \] )](https://api.jquery.com/prevUntil/\#prevUntil-element-filter)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A DOM node or jQuery object indicating where to stop matching preceding sibling elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a selector expression that represents a set of DOM elements, the `.prevUntil()` method searches through the predecessors of these elements in the DOM tree, stopping when it reaches an element matched by the method's argument. The new jQuery object that is returned contains all previous siblings up to but not including the one matched by the `.prevUntil()` selector; the elements are returned in order from the closest sibling to the farthest.

If the selector is not matched or is not supplied, all previous siblings will be selected; in these cases it selects the same elements as the `[.prevAll()](https://api.jquery.com/prevAll/)` method does when no filter selector is provided.

**As of jQuery 1.6**, A DOM node or jQuery object, instead of a selector, may be used for the first **.prevUntil()** argument.

The method optionally accepts a selector expression for its second argument. If this argument is supplied, the elements will be filtered by testing whether they match it.

Find the siblings that precede <dt id="term-2"> up to the preceding <dt> and give them a red background color. Also, find previous <dd> siblings of <dt id="term-3"> up to <dt id="term-1"> and give them a green text color.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37 | ```<br>``` |

#### Demo: