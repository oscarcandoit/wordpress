---
url: https://api.jquery.com/offsetParent/
scraped_at: 2025-10-20T03:02:00.757Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .offsetParent()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the closest ancestor element that is positioned.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.offsetParent()](https://api.jquery.com/offsetParent/\#offsetParent)

  - This method does not accept any arguments.

Given a jQuery object that represents a set of DOM elements, the `.offsetParent()` method allows us to search through the ancestors of these elements in the DOM tree and construct a new jQuery object wrapped around the closest positioned ancestor. An element is said to be positioned if it has a CSS position attribute of `relative`, `absolute`, or `fixed`. This information is useful for calculating offsets for performing animations and placing objects on the page.

Consider a page with a basic nested list on it, with a positioned element:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

If we begin at item A, we can find its positioned ancestor:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This will change the color of list item II, which is positioned.

Find the offsetParent of item "A."

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo: