---
url: https://api.jquery.com/Class-Selector/
scraped_at: 2025-10-20T03:19:59.627Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## class selector

**Description:** Selects all elements with the given class.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ".class" )


**class:** A class to search for. An element can have multiple classes; only one of them must match.


For class selectors, jQuery uses JavaScript's native `getElementsByClassName()` function if the browser supports it.

### Example 1

Finds the element with the class "myClass".

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

### Example 2

Finds the element with both "myclass" and "otherclass" classes.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo: