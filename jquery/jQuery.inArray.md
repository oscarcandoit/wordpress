---
url: https://api.jquery.com/jQuery.inArray/
scraped_at: 2025-10-20T03:14:43.991Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.inArray( value, array \[, fromIndex \] )Returns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** Search for a specified value within an array and return its index (or -1 if not found).

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [jQuery.inArray( value, array \[, fromIndex \] )](https://api.jquery.com/jQuery.inArray/\#jQuery-inArray-value-array-fromIndex)

  - **value**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    The value to search for.

  - **array**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array through which to search.

  - **fromIndex**

    Type: [Number](http://api.jquery.com/Types/#Number)

    The index of the array at which to begin the search. The default is 0, which will search the whole array.

The `$.inArray()` method is similar to JavaScript's native `.indexOf()` method in that it returns -1 when it doesn't find a match. If the first element within the array matches `value`, `$.inArray()` returns 0.

Because JavaScript treats 0 as loosely equal to false (i.e. 0 == false, but 0 !== false), to check for the presence of `value` within `array`, you need to check if it's not equal to (or greater than) -1.

The comparison between values is strict. The following will return `-1` (not found) because a number is being searched in an array of strings:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Report the index of some elements in the array.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo: