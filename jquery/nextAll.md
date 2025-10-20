---
url: https://api.jquery.com/nextAll/
scraped_at: 2025-10-20T03:01:50.018Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .nextAll( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get all following siblings of each element in the set of matched elements, optionally filtered by a selector.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.nextAll( \[selector \] )](https://api.jquery.com/nextAll/\#nextAll-selector)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.nextAll()` method allows us to search through the successors of these elements in the DOM tree and construct a new jQuery object from the matching elements.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the selector is supplied, the elements will be filtered by testing whether they match it.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

If we begin at the third item, we can find the elements which come after it:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind items 4 and 5. Since we do not supply a selector expression, these following elements are unequivocally included as part of the object. If we had supplied one, the elements would be tested for a match before they were included.

### Example 1

Locate all the divs after the first and give them a class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo:

### Example 2

Locate all the paragraphs after the second child in the body and give them a class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: