---
url: https://api.jquery.com/val/
scraped_at: 2025-10-20T03:18:23.267Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current value of the first element in the set of matched elements or set the value of every matched element.

#### Contents:

- [.val()](https://api.jquery.com/val/#val1)  - [.val()](https://api.jquery.com/val/#val)
- [.val( value )](https://api.jquery.com/val/#val2)  - [.val( value )](https://api.jquery.com/val/#val-value)
  - [.val( function )](https://api.jquery.com/val/#val-function)

## .val()Returns: [String](http://api.jquery.com/Types/\#String) or [Number](http://api.jquery.com/Types/\#Number) or [Array](http://api.jquery.com/Types/\#Array)

**Description:** Get the current value of the first element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.val()](https://api.jquery.com/val/\#val)

  - This method does not accept any arguments.

The `.val()` method is primarily used to get the values of form elements such as `input`, `select` and `textarea`. When called on an empty collection, it returns `undefined`.

When the first element in the collection is a `select-multiple` (i.e., a `select` element with the `multiple` attribute set), `.val()` returns an array containing the value of each selected option. **As of jQuery 3.0**, if no options are selected, it returns an empty array; **prior to jQuery 3.0**, it returns `null`.

For selects, checkboxes and radio buttons, you can use [:checked](https://api.jquery.com/checked-selector/) to select the right elements. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

**Note:** At present, using `.val()` on `<textarea>` elements strips carriage return characters from the browser-reported value. When this value is sent to the server via XHR, however, carriage returns are preserved (or added by browsers which do not include them in the raw value). A workaround for this issue can be achieved using a valHook as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

### Example 1

Get the single value from a single select and an array of values from a multiple select and display their values.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47 | ```<br>``` |

#### Demo:

### Example 2

Find the value of an input box.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

## .val( value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the value of each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.val( value )](https://api.jquery.com/val/\#val-value)

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number) or [Array](http://api.jquery.com/Types/#Array)

    A string of text, a number, or an array of strings corresponding to the value of each matched element to set as selected/checked.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.val( function )](https://api.jquery.com/val/\#val-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) value )
     =>
     [String](http://api.jquery.com/Types/#String)

    A function returning the value to set. `this` is the current element. Receives the index position of the element in the set and the old value as arguments.

This method is typically used to set the values of form fields.

`val()` allows you to pass an array of element values. This is useful when working on a jQuery object containing elements like `<input type="checkbox">`, `<input type="radio">`, and `<option>` s inside of a `<select>`. In this case, the `input` s and the `option` s having a `value` that matches one of the elements of the array will be checked or selected while those having a `value` that doesn't match one of the elements of the array will be unchecked or unselected, depending on the type. In the case of `<input type="radio">` s that are part of a radio group and `<select>` s, any previously selected element will be deselected.

Setting values using this method (or using the native `value` property) does not cause the dispatch of the `change` event. For this reason, the relevant event handlers will not be executed. If you want to execute them, you should call `.trigger( "change" )` after setting the value.

The `.val()` method allows setting the value by passing in a function. As of jQuery 1.4, the function is passed two arguments, the current element's index and its current value:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This example removes leading and trailing whitespace from the values of text inputs with a "tags" class.

### Example 1

Set the value of an input box.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 2

Use the function argument to modify the value of an input box.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 3

Set a single select, a multiple select, checkboxes and a radio button .

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39 | ```<br>``` |

#### Demo: