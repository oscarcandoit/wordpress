---
url: https://api.jquery.com/scrollTop/
scraped_at: 2025-10-20T03:03:51.643Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

#### Contents:

- [.scrollTop()](https://api.jquery.com/scrollTop/#scrollTop1)  - [.scrollTop()](https://api.jquery.com/scrollTop/#scrollTop)
- [.scrollTop( value )](https://api.jquery.com/scrollTop/#scrollTop2)  - [.scrollTop( value )](https://api.jquery.com/scrollTop/#scrollTop-value)

## .scrollTop()Returns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** Get the current vertical position of the scroll bar for the first element in the set of matched elements or set the vertical position of the scroll bar for every matched element.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.scrollTop()](https://api.jquery.com/scrollTop/\#scrollTop)

  - This method does not accept any arguments.

The vertical scroll position is the same as the number of pixels that are hidden from view above the scrollable area. If the scroll bar is at the very top, or if the element is not scrollable, this number will be `0`.

Get the scrollTop of a paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

## .scrollTop( value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the current vertical position of the scroll bar for each of the set of matched elements.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.scrollTop( value )](https://api.jquery.com/scrollTop/\#scrollTop-value)

  - **value**

    Type: [Number](http://api.jquery.com/Types/#Number)

    A number indicating the new position to set the scroll bar to.

The vertical scroll position is the same as the number of pixels that are hidden from view above the scrollable area. Setting the `scrollTop` positions the vertical scroll of each matched element.

Set the scrollTop of a div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: