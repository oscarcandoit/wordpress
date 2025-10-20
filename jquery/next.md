---
url: https://api.jquery.com/next/
scraped_at: 2025-10-20T03:01:47.258Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .next( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the immediately following sibling of each element in the set of matched elements. If a selector is provided, it retrieves the next sibling only if it matches that selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.next( \[selector \] )](https://api.jquery.com/next/\#next-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.next()` method allows us to search through the immediately following sibling of these elements in the DOM tree and construct a new jQuery object from the matching elements.

The method optionally accepts a selector expression of the same type that we can pass to the `$()` function. If the immediately following sibling matches the selector, it remains in the newly constructed jQuery object; otherwise, it is excluded.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

If we begin at the third item, we can find the element which comes just after it:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background behind item 4. Since we do not supply a selector expression, this following element is unequivocally included as part of the object. If we had supplied one, the element would be tested for a match before it was included.

### Example 1

Find the very next sibling of each disabled button and change its text "this button is disabled".

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Find the very next sibling of each paragraph. Keep only the ones with a class "selected".

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: