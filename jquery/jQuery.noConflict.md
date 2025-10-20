---
url: https://api.jquery.com/jQuery.noConflict/
scraped_at: 2025-10-20T03:18:27.948Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.noConflict( \[removeAll \] )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Relinquish jQuery's control of the `$` variable.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.noConflict( \[removeAll \] )](https://api.jquery.com/jQuery.noConflict/\#jQuery-noConflict-removeAll)

  - **removeAll**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to remove all jQuery variables from the global scope (including jQuery itself).

Many JavaScript libraries use `$` as a function or variable name, just as jQuery does. In jQuery's case, `$` is just an alias for `jQuery`, so all functionality is available without using `$`. If you need to use another JavaScript library alongside jQuery, return control of `$` back to the other library with a call to `$.noConflict()`. Old references of `$` are saved during jQuery initialization; `noConflict()` simply restores them.

If for some reason two versions of jQuery are loaded (which is not recommended), calling `$.noConflict( true )` from the second version will return the globally scoped jQuery variables to those of the first version.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

This technique is especially effective in conjunction with the `.ready()` method's ability to alias the jQuery object, as within callback passed to `.ready()` you can use `$` if you wish without fear of conflicts later:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

If necessary, you can free up the `jQuery` name as well by passing `true` as an argument to the method. This is rarely necessary, and if you must do this (for example, if you need to use multiple versions of the jQuery library on the same page), you need to consider that most plug-ins rely on the presence of the `jQuery` variable and may not operate correctly in this situation.

### Example 1

Map the original object that was referenced by $ back to $.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Example 2

Revert the $ alias and then create and execute a function to provide the $ as a jQuery alias inside the function's scope. Inside the function the original $ object is not available. This works well for most plugins that don't rely on any other library.


|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### Example 3

Create a different alias instead of jQuery to use in the rest of the script.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

### Example 4

Completely move jQuery to a new namespace in another object.

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

#### Result:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### Example 5

Load two versions of jQuery (not recommended). Then, restore jQuery's globally scoped variables to the first loaded jQuery.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo: