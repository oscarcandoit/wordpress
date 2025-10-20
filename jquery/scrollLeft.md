---
url: https://api.jquery.com/scrollLeft/
scraped_at: 2025-10-20T03:03:48.691Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current horizontal position of the scroll bar for the first element in the set of matched elements or set the horizontal position of the scroll bar for every matched element.

#### Contents:

- [.scrollLeft()](https://api.jquery.com/scrollLeft/#scrollLeft1)  - [.scrollLeft()](https://api.jquery.com/scrollLeft/#scrollLeft)
- [.scrollLeft( value )](https://api.jquery.com/scrollLeft/#scrollLeft2)  - [.scrollLeft( value )](https://api.jquery.com/scrollLeft/#scrollLeft-value)

## .scrollLeft()Returns: [Integer](http://api.jquery.com/Types/\#Integer)

**Description:** Get the current horizontal position of the scroll bar for the first element in the set of matched elements.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.scrollLeft()](https://api.jquery.com/scrollLeft/\#scrollLeft)

  - This method does not accept any arguments.

The horizontal scroll position is the same as the number of pixels that are hidden from view to the left of the scrollable area. If the scroll bar is at the very left, or if the element is not scrollable, this number will be `0`.

**Note:** `.scrollLeft()`, when called directly or animated as a property using `.animate()`, will not work if the element it is being applied to is hidden.

Get the scrollLeft of a paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

## .scrollLeft( value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the current horizontal position of the scroll bar for each of the set of matched elements.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.scrollLeft( value )](https://api.jquery.com/scrollLeft/\#scrollLeft-value)

  - **value**

    Type: [Number](http://api.jquery.com/Types/#Number)

    An integer indicating the new position to set the scroll bar to.

The horizontal scroll position is the same as the number of pixels that are hidden from view above the scrollable area. Setting the `scrollLeft` positions the horizontal scroll of each matched element.

Set the scrollLeft of a div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: