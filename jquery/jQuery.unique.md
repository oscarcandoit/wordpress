---
url: https://api.jquery.com/jQuery.unique/
scraped_at: 2025-10-20T03:15:51.376Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.unique( array )Returns: [Array](http://api.jquery.com/Types/\#Array)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** Sorts an array of DOM elements, in place, with the duplicates removed. Note that this only works on arrays of DOM elements, not strings or numbers.

- #### version added: [1.1.3](https://api.jquery.com/category/version/1.1.3/) [jQuery.unique( array )](https://api.jquery.com/jQuery.unique/\#jQuery-unique-array)

  - **array**

    Type: [Array](http://api.jquery.com/Types/#Array)

    The Array of DOM elements.

As of jQuery 3.0, this method is deprecated and just an alias of `[jQuery.uniqueSort()](https://api.jquery.com/jQuery.uniqueSort/)`. Please use that method instead.

The `$.unique()` function searches through an array of objects, sorting the array, and removing any duplicate nodes. A node is considered a duplicate if it is the _exact same_ node as one already in the array; two different nodes with identical attributes are not considered to be duplicates. This function only works on plain JavaScript arrays of DOM elements, and is chiefly used internally by jQuery. You probably will never need to use it.

As of jQuery 1.4 the results will always be returned in document order.

Removes any duplicate elements from the array of divs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: