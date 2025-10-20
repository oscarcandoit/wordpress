---
url: https://api.jquery.com/has/
scraped_at: 2025-10-20T03:01:32.811Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .has( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Reduce the set of matched elements to those that have a descendant that matches the selector or DOM element.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.has( selector )](https://api.jquery.com/has/\#has-selector)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a selector expression to match elements against.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.has( contained )](https://api.jquery.com/has/\#has-contained)

  - **contained**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.has()` method constructs a new jQuery object from a subset of the matching elements. The supplied selector is tested against the descendants of the matching elements; the element will be included in the result if any of its descendant elements matches the selector.

Consider a page with a nested list as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

We can apply this method to the set of list items as follows:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for item 2, as it is the only `<li>` that has a `<ul>` among its descendants.

Check if an element is inside another.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo: