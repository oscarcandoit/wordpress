---
url: https://api.jquery.com/parents/
scraped_at: 2025-10-20T03:02:06.388Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .parents( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the ancestors of each element in the current set of matched elements, optionally filtered by a selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.parents( \[selector \] )](https://api.jquery.com/parents/\#parents-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.parents()` method allows us to search through the ancestors of these elements in the DOM tree and construct a new jQuery object from the matching elements ordered from immediate parent on up; the elements are returned in order from the closest parent to the outer ones. When multiple DOM elements are in the original set, the resulting set will be in _reverse_ order of the original elements as well, with duplicates removed.

The `.parents()` and `[.parent()](https://api.jquery.com/parent/)` methods are similar, except that the latter only travels a single level up the DOM tree. Also, `$( "html" ).parent()` method returns a set containing `document` whereas `$( "html" ).parents()` returns an empty set.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a basic nested list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

If we begin at item A, we can find its ancestors:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for the level-2 list, item II, and the level-1 list (and on up the DOM tree all the way to the `<html>` element). Since we do not supply a selector expression, all of the ancestors are part of the returned jQuery object. If we had supplied one, only the matching items among these would be included.

### Example 1

Find all parent elements of each b.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo:

### Example 2

Click to find all unique div parent elements of each span.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58 | ```<br>``` |

#### Demo: