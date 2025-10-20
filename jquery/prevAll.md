---
url: https://api.jquery.com/prevAll/
scraped_at: 2025-10-20T03:02:45.569Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .prevAll( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get all preceding siblings of each element in the set of matched elements, optionally filtered by a selector, in the reverse document order.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.prevAll( \[selector \] )](https://api.jquery.com/prevAll/\#prevAll-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.prevAll()` method searches through the predecessors of these elements in the DOM tree and construct a new jQuery object from the matching elements; the elements are returned in order beginning with the closest sibling.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

If we begin at the third item, we can find the elements which come before it:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind items 1 and 2. Since we do not supply a selector expression, these preceding elements are unequivocally included as part of the object. If we had supplied one, the elements would be tested for a match before they were included.

**Note:** Many APIs, like `[append](https://api.jquery.com/append/)` or `[wrapAll](https://api.jquery.com/wrapAll/)` process node in the order in which they appear in the jQuery object. This can pose issues with APIs like `.prevAll()` in which the reverse document order is used. Consider the following example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

The following call:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

would result in the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

because "Item 2" gets appended to the wrapper div first. To work around the issue, you may use `[.uniqueSort()](https://api.jquery.com/uniqueSort/)` on the `.prevAll()` output first:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Note that the `[.uniqueSort()](https://api.jquery.com/uniqueSort/)` method is only available in jQuery 3.7.0 or newer. In older versions, you will need to use `[$.uniqueSort()](https://api.jquery.com/jQuery.uniqueSort/)` to achieve a similar effect:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 1

Locate all the divs preceding the last div and give them a class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

### Example 2

Locate all the divs preceding the last item and wrap them with a div with class `wrapper` \- with or without `[.uniqueSort()](https://api.jquery.com/uniqueSort/)`.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69<br>70<br>71 | ```<br>``` |

#### Demo: