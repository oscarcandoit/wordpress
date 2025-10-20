---
url: https://api.jquery.com/removeProp/
scraped_at: 2025-10-20T03:18:13.916Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .removeProp( propertyName )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove a property for the set of matched elements.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.removeProp( propertyName )](https://api.jquery.com/removeProp/\#removeProp-propertyName)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the property to remove.

The `.removeProp()` method removes properties set by the `[.prop()](https://api.jquery.com/prop/)` method.

**Note:** This method should not be used to remove built-in (native) properties such as "checked", "disabled", "selected", or others. This can lead to unexpected behavior.

It's almost always better to use `[.prop()](https://api.jquery.com/prop/)` to set native properties to `false` instead of removing them.

### Additional Notes:

- In Internet Explorer prior to version 9, using `[.prop()](https://api.jquery.com/prop/)` to set a DOM element property to anything other than a simple primitive value (number, string, or boolean) can cause memory leaks if the property is not removed (using [`.removeProp()`](https://api.jquery.com/removeProp/)) before the DOM element is removed from the document. To safely set values on DOM objects without memory leaks, use [`.data()`](https://api.jquery.com/data/).


Set a numeric property on a paragraph and then remove it.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo: