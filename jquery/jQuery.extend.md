---
url: https://api.jquery.com/jQuery.extend/
scraped_at: 2025-10-20T03:14:27.333Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.extend( target, object1 \[, objectN \] )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Merge the contents of two or more objects together into the first object.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.extend( target, object1 \[, objectN \] )](https://api.jquery.com/jQuery.extend/\#jQuery-extend-target-object1-objectN)

  - **target**

    Type: [Object](http://api.jquery.com/Types/#Object)

     An object that will receive the new properties.

  - **object1**

    Type: [Object](http://api.jquery.com/Types/#Object)

    An object containing additional properties to merge in.

  - **objectN**

    Type: [Object](http://api.jquery.com/Types/#Object)

    Additional objects containing properties to merge in.
- #### version added: [1.1.4](https://api.jquery.com/category/version/1.1.4/) [jQuery.extend( \[deep \], target, object1 \[, objectN \] )](https://api.jquery.com/jQuery.extend/\#jQuery-extend-deep-target-object1-objectN)

  - **deep**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    If true, the merge becomes recursive (aka. deep copy). Passing `false` for this argument is not supported.

  - **target**

    Type: [Object](http://api.jquery.com/Types/#Object)

    The object to extend. It will receive the new properties.

  - **object1**

    Type: [Object](http://api.jquery.com/Types/#Object)

    An object containing additional properties to merge in.

  - **objectN**

    Type: [Object](http://api.jquery.com/Types/#Object)

    Additional objects containing properties to merge in.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.extend( object )](https://api.jquery.com/jQuery.extend/\#jQuery-extend-object)

  - **object**

    Type: [Object](http://api.jquery.com/Types/#Object)

     An object to merge onto the jQuery namespace.

When two or more object arguments are supplied to `$.extend()`, properties from all of the objects are added to the target object. Arguments that are `null` or `undefined` are ignored.

If only one argument is supplied to `$.extend()`, this means the target argument was omitted. In this case, the jQuery object itself is assumed to be the target. By doing this, you can add new functions to the jQuery namespace. This can be useful for plugin authors wishing to add new methods to JQuery.

Keep in mind that the target object (first argument) will be modified, and will also be returned from `$.extend()`. If, however, you want to preserve both of the original objects, you can do so by passing an empty object as the target:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The merge performed by `$.extend()` is not recursive by default; if a property of the first object is itself an object or array, it will be completely overwritten by a property with the same key in the second or subsequent object. The values are not merged. This can be seen in the example below by examining the value of banana. However, by passing `true` for the first function argument, objects will be recursively merged.

**Warning**: Versions prior to 3.4 had a security issue where calling `jQuery.extend(true, {}, object)` on an unsanitized object containing a `__proto__` property would extend `Object.prototype`.

**Warning**: Passing `false` for the first argument is not supported.

Undefined properties are not copied. However, properties inherited from the object's prototype _will_ be copied over. Properties that are an object constructed via `new MyCustomObject(args)`, or built-in JavaScript types such as Date or RegExp, are not re-constructed and will appear as plain Objects in the resulting object or array.

On a `deep` extend, Object and Array are extended, but object wrappers on primitive types such as String, Boolean, and Number are not. Deep-extending a cyclical data structure will result in an error.

For needs that fall outside of this behavior, write a custom extend method instead, or use a library like [lodash](https://lodash.com/).

### Example 1

Merge two objects, modifying the first.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 2

Merge two objects recursively, modifying the first.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 3

Merge defaults and options, without modifying the defaults. This is a common plugin development pattern.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo: