---
url: https://api.jquery.com/removeAttr/
scraped_at: 2025-10-20T03:18:03.061Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .removeAttr( attributeName )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove an attribute from each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.removeAttr( attributeName )](https://api.jquery.com/removeAttr/\#removeAttr-attributeName)

  - **attributeName**

    Type: [String](http://api.jquery.com/Types/#String)

    An attribute to remove; as of version 1.7, it can be a space-separated list of attributes.

The `.removeAttr()` method uses the JavaScript `removeAttribute()` function, but it has the advantage of being able to be called directly on a jQuery object and it accounts for different attribute naming across browsers.

**Note:** Removing an inline `onclick` event handler using `.removeAttr()` doesn't achieve the desired effect in Internet Explorer 8, 9 and 11. To avoid potential problems, use `.prop()` instead:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

Clicking the button changes the title of the input next to it. Move the mouse pointer over the text input to see the effect of adding and removing the title attribute.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo: