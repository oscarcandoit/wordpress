---
url: https://api.jquery.com/jQuery.grep/
scraped_at: 2025-10-20T03:14:37.378Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.grep( array, function \[, invert \] )Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Finds the elements of an array which satisfy a filter function. The original array is not affected.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.grep( array, function \[, invert \] )](https://api.jquery.com/jQuery.grep/\#jQuery-grep-array-function-invert)

  - **array**

    Type: [ArrayLikeObject](http://api.jquery.com/Types/#ArrayLikeObject)

    The array-like object to search through.

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Object](http://api.jquery.com/Types/#Object) elementOfArray, [Integer](http://api.jquery.com/Types/#Integer) indexInArray )
     =>
     [Boolean](http://api.jquery.com/Types/#Boolean)

    The function to process each item against. The first argument to the function is the item, and the second argument is the index. The function should return a Boolean value. `this` will be the global window object.

  - **invert**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    If "invert" is false, or not provided, then the function returns an array consisting of all elements for which "callback" returns true. If "invert" is true, then the function returns an array consisting of all elements for which "callback" returns false.

The `$.grep()` method removes items from an array as necessary so that all remaining items pass a provided test. The test is a function that is passed an array item and the index of the item within the array. Only if the test returns true will the item be in the result array.

The filter function will be passed two arguments: the current array item and its index. The filter function must return 'true' to include the item in the result array.

### Example 1

Filters the original array of numbers leaving that are not 5 and have an index greater than 4. Then it removes all 9s.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43 | ```<br>``` |

#### Demo:

### Example 2

Filter an array of numbers to include only numbers bigger then zero.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

#### Result:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Filter an array of numbers to include numbers that are not bigger than zero.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

#### Result:

|     |     |
| --- | --- |
| 1 | ```<br>``` |