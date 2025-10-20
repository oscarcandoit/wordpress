---
url: https://api.jquery.com/parentsUntil/
scraped_at: 2025-10-20T03:02:34.240Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .parentsUntil( \[selector \] \[, filter \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the ancestors of each element in the current set of matched elements, up to but not including the element matched by the selector, DOM node, or jQuery object.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.parentsUntil( \[selector \] \[, filter \] )](https://api.jquery.com/parentsUntil/\#parentsUntil-selector-filter)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to indicate where to stop matching ancestor elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.parentsUntil( \[element \] \[, filter \] )](https://api.jquery.com/parentsUntil/\#parentsUntil-element-filter)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A DOM node or jQuery object indicating where to stop matching ancestor elements.

  - **filter**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a selector expression that represents a set of DOM elements, the `.parentsUntil()` method traverses through the ancestors of these elements until it reaches an element matched by the selector passed in the method's argument. The resulting jQuery object contains all of the ancestors up to but not including the one matched by the `.parentsUntil()` selector.

If the selector is not matched or is not supplied, all ancestors will be selected; in these cases it selects the same elements as the `.parents()` method does when no selector is provided.

**As of jQuery 1.6**, A DOM node or jQuery object, instead of a selector, may be used for the first **.parentsUntil()** argument.

The method optionally accepts a selector expression for its second argument. If this argument is supplied, the elements will be filtered by testing whether they match it.

Find the ancestors of <li class="item-a"> up to <ul class="level-1"> and give them a red background color. Also, find ancestors of <li class="item-2"> that have a class of "yes" up to <ul class="level-1"> and give them a green border.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39 | ```<br>``` |

#### Demo: