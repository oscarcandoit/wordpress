---
url: https://api.jquery.com/parent/
scraped_at: 2025-10-20T03:02:03.672Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .parent( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the parent of each element in the current set of matched elements, optionally filtered by a selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.parent( \[selector \] )](https://api.jquery.com/parent/\#parent-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `parent()` method traverses to the immediate parent of each of these elements in the DOM tree and constructs a new jQuery object from the matching elements.

This method is similar to [`.parents()`](https://api.jquery.com/parents/), except `.parent()` only travels a single level up the DOM tree. Also, `$( "html" ).parent()` method returns a set containing `document` whereas `$( "html" ).parents()` returns an empty set.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a basic nested list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

If we begin at item A, we can find its parents:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for the level-2 list. Since we do not supply a selector expression, the parent element is unequivocally included as part of the object. If we had supplied one, the element would be tested for a match before it was included.

### Example 1

Shows the parent of each element as (parent > child). Check the View Source to see the raw html.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44 | ```<br>``` |

#### Demo:

### Example 2

Find the parent element of each paragraph with a class "selected".

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18 | ```<br>``` |

#### Demo: