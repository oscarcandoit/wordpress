---
url: https://api.jquery.com/prev/
scraped_at: 2025-10-20T03:02:39.900Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .prev( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the immediately preceding sibling of each element in the set of matched elements. If a selector is provided, it retrieves the previous sibling only if it matches that selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.prev( \[selector \] )](https://api.jquery.com/prev/\#prev-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.prev()` method searches for the predecessor of each of these elements in the DOM tree and constructs a new jQuery object from the matching elements.

The method optionally accepts a selector expression of the same type that can be passed to the `$()` function. If the selector is supplied, the preceding element will be filtered by testing whether it match the selector.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

To select the element that comes immediately before item three:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind item 2. Since no selector expression is supplied, this preceding element is unequivocally included as part of the object. If one had been supplied, the element would be tested for a match before it was included.

If no previous sibling exists, or if the previous sibling element does not match a supplied selector, an empty jQuery object is returned.

To select _all_ preceding sibling elements, rather than just the preceding _adjacent_ sibling, use the [.prevAll()](https://api.jquery.com/prevAll/) method.

### Example 1

Find the very previous sibling of each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48 | ```<br>``` |

#### Demo:

### Example 2

For each paragraph, find the very previous sibling that has a class "selected".

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: