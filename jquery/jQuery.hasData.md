---
url: https://api.jquery.com/jQuery.hasData/
scraped_at: 2025-10-20T03:04:22.183Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.hasData( element )Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)

**Description:** Determine whether an element has any jQuery data associated with it.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [jQuery.hasData( element )](https://api.jquery.com/jQuery.hasData/\#jQuery-hasData-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element to be checked for data.

The `jQuery.hasData()` method provides a way to determine if an element currently has any values that were set using `[jQuery.data()](https://api.jquery.com/jQuery.data/)`. If there is no data object associated with an element, the method returns `false`; otherwise it returns `true`.

The primary advantage of `jQuery.hasData(element)` is that it does not create and associate a data object with the element if none currently exists. In contrast, `jQuery.data(element)` always returns a data object to the caller, creating one if no data object previously existed.

Note that jQuery's event system uses the jQuery data API to store event handlers. Therefore, binding an event to an element using `.on()`, `.bind()`, `.live()`, `.delegate()`, or one of the shorthand event methods also associates a data object with that element.

Set data on an element and see the results of hasData.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Demo: