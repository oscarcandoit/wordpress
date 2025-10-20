---
url: https://api.jquery.com/nextUntil/
scraped_at: 2025-10-20T03:01:53.510Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .nextUntil( \[selector \] \[, filter \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get all following siblings of each element up to but not including the element matched by the selector, DOM node, or jQuery object passed.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.nextUntil( \[selector \] \[, filter \] )](https://api.jquery.com/nextUntil/\#nextUntil-selector-filter)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to indicate where to stop matching following sibling elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.nextUntil( \[element \] \[, filter \] )](https://api.jquery.com/nextUntil/\#nextUntil-element-filter)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A DOM node or jQuery object indicating where to stop matching following sibling elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a selector expression that represents a set of DOM elements, the `.nextUntil()` method searches through the successors of these elements in the DOM tree, stopping when it reaches an element matched by the method's argument. The new jQuery object that is returned contains all following siblings up to but not including the one matched by the `.nextUntil()` argument.

If the selector is not matched or is not supplied, all following siblings will be selected; in these cases it selects the same elements as the `.nextAll()` method does when no filter selector is provided.

**As of jQuery 1.6**, A DOM node or jQuery object, instead of a selector, may be passed to the `.nextUntil()` method.

The method optionally accepts a selector expression for its second argument. If this argument is supplied, the elements will be filtered by testing whether they match it.

Find the siblings that follow <dt id="term-2"> up to the next <dt> and give them a red background color. Also, find <dd> siblings that follow <dt id="term-1"> up to <dt id="term-3"> and give them a green text color.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: