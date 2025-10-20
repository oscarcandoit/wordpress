---
url: https://api.jquery.com/first/
scraped_at: 2025-10-20T03:01:24.960Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .first()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Reduce the set of matched elements to the first in the set.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.first()](https://api.jquery.com/first/\#first)

  - This method does not accept any arguments.

Given a jQuery object that represents a set of DOM elements, the `.first()` method constructs a new jQuery object from the first element in that set.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can apply this method to the set of list items:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for the first item.

Highlight the first item in a list.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo: