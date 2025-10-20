---
url: https://api.jquery.com/jQuery.each/
scraped_at: 2025-10-20T03:14:20.649Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.each( array, callback )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** A generic iterator function, which can be used to seamlessly iterate over both objects and arrays. Arrays and array-like objects with a length property (such as a function's arguments object) are iterated by numeric index, from 0 to length-1. Other objects are iterated via their named properties.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.each( array, callback )](https://api.jquery.com/jQuery.each/\#jQuery-each-array-callback)

  - **array**

    Type: [ArrayLikeObject](http://api.jquery.com/Types/#ArrayLikeObject)

    The array or array-like object to iterate over.

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) indexInArray, [Object](http://api.jquery.com/Types/#Object) value )

    The function that will be executed on every value.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.each( object, callback )](https://api.jquery.com/jQuery.each/\#jQuery-each-object-callback)

  - **object**

    Type: [Object](http://api.jquery.com/Types/#Object)

    The object to iterate over.

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)( [String](http://api.jquery.com/Types/#String) propertyName, [Object](http://api.jquery.com/Types/#Object) valueOfProperty )

    The function that will be executed on every value.

The `$.each()` function is not the same as [$(selector).each()](https://api.jquery.com/each/), which is used to iterate, exclusively, over a jQuery object. The `$.each()` function can be used to iterate over any collection, whether it is an object or an array. In the case of an array, the callback is passed an array index and a corresponding array value each time. (The value can also be accessed through the `this` keyword, but Javascript will always wrap the `this` value as an `Object` even if it is a simple string or number value.) The method returns its first argument, the object that was iterated.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This produces two messages:

`0: 52`

`1: 97`

If an object is used as the collection, the callback is passed a key-value pair each time:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

Once again, this produces two messages:

`flammable: inflammable`

`duh: no duh`

We can break the `$.each()` loop at a particular iteration by making the callback function return `false`. Returning _non-false_ is the same as a `continue` statement in a for loop; it will skip immediately to the next iteration.

### Example 1

Iterates through the array displaying each number as both a word and numeral

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo:

### Example 2

Iterates over items in an array, accessing both the current item and its index.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

Iterates over the properties in an object, accessing both the current item and its key.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |