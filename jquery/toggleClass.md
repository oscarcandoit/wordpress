---
url: https://api.jquery.com/toggleClass/
scraped_at: 2025-10-20T03:18:17.298Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

#### Contents:

- [.toggleClass( className )](https://api.jquery.com/toggleClass/#toggleClass1)  - [.toggleClass( className )](https://api.jquery.com/toggleClass/#toggleClass-className)
  - [.toggleClass( className, state )](https://api.jquery.com/toggleClass/#toggleClass-className-state)
  - [.toggleClass( classNames )](https://api.jquery.com/toggleClass/#toggleClass-classNames)
  - [.toggleClass( classNames, state )](https://api.jquery.com/toggleClass/#toggleClass-classNames-state)
  - [.toggleClass( function \[, state \] )](https://api.jquery.com/toggleClass/#toggleClass-function-state)
  - [.toggleClass( function \[, state \] )](https://api.jquery.com/toggleClass/#toggleClass-function-state)
- [.toggleClass( \[state \] )](https://api.jquery.com/toggleClass/#toggleClass2)  - [.toggleClass( \[state \] )](https://api.jquery.com/toggleClass/#toggleClass-state)

## .toggleClass( className )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Add or remove one or more classes from each element in the set of matched elements, depending on either the class's presence or the value of the state argument.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.toggleClass( className )](https://api.jquery.com/toggleClass/\#toggleClass-className)

  - **className**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more classes (separated by spaces) to be toggled for each element in the matched set.
- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.toggleClass( className, state )](https://api.jquery.com/toggleClass/\#toggleClass-className-state)

  - **className**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more classes (separated by spaces) to be toggled for each element in the matched set.

  - **state**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A boolean (not just truthy/falsy) value to determine whether the class should be added or removed.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.toggleClass( classNames )](https://api.jquery.com/toggleClass/\#toggleClass-classNames)

  - **classNames**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of classes to be toggled for each element in the matched set.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.toggleClass( classNames, state )](https://api.jquery.com/toggleClass/\#toggleClass-classNames-state)

  - **classNames**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of classes to be toggled for each element in the matched set.

  - **state**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A boolean (not just truthy/falsy) value to determine whether the class should be added or removed.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.toggleClass( function \[, state \] )](https://api.jquery.com/toggleClass/\#toggleClass-function-state)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) className, [Boolean](http://api.jquery.com/Types/#Boolean) state )
     =>
     [String](http://api.jquery.com/Types/#String)

    A function returning one or more space-separated class names to be toggled in the class attribute of each element in the matched set. Receives the index position of the element in the set, the old class value, and the state as arguments.

  - **state**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A boolean value to determine whether the class should be added or removed.
- #### version added: [3.3](https://api.jquery.com/category/version/3.3/) [.toggleClass( function \[, state \] )](https://api.jquery.com/toggleClass/\#toggleClass-function-state)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) className, [Boolean](http://api.jquery.com/Types/#Boolean) state )
     =>
     [String](http://api.jquery.com/Types/#String) \| [Array](http://api.jquery.com/Types/#Array)

    A function returning one or more space-separated class names or an array of class names to be toggled in the class attribute of each element in the matched set. Receives the index position of the element in the set, the old class value, and the state as arguments.

  - **state**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A boolean value to determine whether the class should be added or removed.

This method takes one or more classes as its parameter. In the first version, if an element in the matched set of elements already has the class, then it is removed; if an element does not have the class, then it is added. For example, we can apply `.toggleClass()` to a simple `<div>`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The first time we apply `$( "div.tumble" ).toggleClass( "bounce" )`, we get the following:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The second time we apply `$( "div.tumble" ).toggleClass( "bounce" )`, the `<div>` class is returned to the single `tumble` value:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Applying `.toggleClass( "bounce spin" )` to the same `<div>` alternates between `<div class="tumble bounce spin">` and `<div class="tumble">`.

The second version of `.toggleClass()` uses the second parameter for determining whether the class should be added or removed. If this parameter's value is `true`, then the class is added; if `false`, the class is removed. In essence, the statement:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

**As of jQuery 1.4**, if no arguments are passed to `.toggleClass()`, all classes on the element the first time `.toggleClass()` is called will be toggled. Also as of jQuery 1.4, the class name to be toggled can be determined by passing in a function.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

This example will toggle the `happy` class for `<div class="foo">` elements if their parent element has a class of `bar`; otherwise, it will toggle the `sad` class.

### Example 1

Toggle the class 'highlight' when a paragraph is clicked.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 2

Add the "highlight" class to the clicked paragraph on every third click of that paragraph, remove it every first and second click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43 | ```<br>``` |

#### Demo:

### Example 3

Toggle the class name(s) indicated on the buttons for each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69 | ```<br>``` |

#### Demo:

## .toggleClass( \[state \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/), removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:**

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.toggleClass( \[state \] )](https://api.jquery.com/toggleClass/\#toggleClass-state)

  - **state**

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A boolean value to determine whether the class should be added or removed.

**This signature (only!) is deprecated as of jQuery 3.0**.