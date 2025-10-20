---
url: https://api.jquery.com/siblings/
scraped_at: 2025-10-20T03:02:52.416Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .siblings( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the siblings of each element in the set of matched elements, optionally filtered by a selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.siblings( \[selector \] )](https://api.jquery.com/siblings/\#siblings-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.siblings()` method allows us to search through the siblings of these elements in the DOM tree and construct a new jQuery object from the matching elements.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

If we begin at the third item, we can find its siblings:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind items 1, 2, 4, and 5. Since we do not supply a selector expression, all of the siblings are part of the object. If we had supplied one, only the matching items among these four would be included.

The original element is not included among the siblings, which is important to remember when we wish to find all elements at a particular level of the DOM tree. However, if the original collection contains more than one element, they might be mutual siblings and will both be found. If you need an exclusive list of siblings, use `$collection.siblings().not($collection)`.

### Example 1

Find the unique siblings of all yellow li elements in the 3 lists (including other yellow li elements if appropriate).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58 | ```<br>``` |

#### Demo:

### Example 2

Find all siblings with a class "selected" of each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: