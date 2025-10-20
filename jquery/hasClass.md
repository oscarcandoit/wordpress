---
url: https://api.jquery.com/hasClass/
scraped_at: 2025-10-20T03:17:53.913Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .hasClass( className )Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)

**Description:** Determine whether any of the matched elements are assigned the given class.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.hasClass( className )](https://api.jquery.com/hasClass/\#hasClass-className)

  - **className**

    Type: [String](http://api.jquery.com/Types/#String)

    The class name to search for.

Elements may have more than one class assigned to them. In HTML, this is represented by separating the class names with a space:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The `.hasClass()` method will return `true` if the class is assigned to an element, even if other classes also are. For example, given the HTML above, the following will return `true`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

As would:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

While this would return `false`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

As of jQuery 1.12/2.2, this method supports XML documents, including SVG.

Looks for the paragraph that contains 'selected' as a class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo: