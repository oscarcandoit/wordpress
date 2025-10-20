---
url: https://api.jquery.com/hover/
scraped_at: 2025-10-20T03:12:49.729Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind one or two handlers to the matched elements, to be executed when the mouse pointer enters and leaves the elements.

#### Contents:

- [.hover( handlerIn, handlerOut )](https://api.jquery.com/hover/#hover1)  - [.hover( handlerIn, handlerOut )](https://api.jquery.com/hover/#hover-handlerIn-handlerOut)
- [.hover( handlerInOut )](https://api.jquery.com/hover/#hover2)  - [.hover( handlerInOut )](https://api.jquery.com/hover/#hover-handlerInOut)

## .hover( handlerIn, handlerOut )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.3](https://api.jquery.com/category/version/3.3/)

**Description:** Bind two handlers to the matched elements, to be executed when the mouse pointer enters and leaves the elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.hover( handlerIn, handlerOut )](https://api.jquery.com/hover/\#hover-handlerIn-handlerOut)

  - **handlerIn**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute when the mouse pointer enters the element.

  - **handlerOut**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute when the mouse pointer leaves the element.

This API is deprecated. Use `.on( "mouseenter", handlerIn ).on( "mouseleave", handlerOut )` instead.

The `.hover()` method binds handlers for both `mouseenter` and `mouseleave` events. You can use it to simply apply behavior to an element during the time the mouse is within the element.

Calling `$( selector ).hover( handlerIn, handlerOut )` is shorthand for:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

See the discussions for `[mouseenter](https://api.jquery.com/mouseenter/)` and `[mouseleave](https://api.jquery.com/mouseleave/)` for more details.

### Example 1

To add a special style to list items that are being hovered over, try:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45 | ```<br>``` |

#### Demo:

### Example 2

To add a special style to table cells that are being hovered over, try:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

### Example 3

To unbind the above example use:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## .hover( handlerInOut )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.3](https://api.jquery.com/category/version/3.3/)

**Description:** Bind a single handler to the matched elements, to be executed when the mouse pointer enters or leaves the elements.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.hover( handlerInOut )](https://api.jquery.com/hover/\#hover-handlerInOut)

  - **handlerInOut**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute when the mouse pointer enters or leaves the element.

This API is deprecated. Use `.on( "mouseenter mouseleave", handlerInOut )` instead.

The `.hover()` method, when passed a single function, will execute that handler for both `mouseenter` and `mouseleave` events. This allows the user to use jQuery's various toggle methods within the handler or to respond differently within the handler depending on the `event.type`.

Calling `$(selector).hover(handlerInOut)` is shorthand for:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

See the discussions for `[mouseenter](https://api.jquery.com/mouseenter/)` and `[mouseleave](https://api.jquery.com/mouseleave/)` for more details.

Slide the next sibling LI up or down on hover, and toggle a class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51 | ```<br>``` |

#### Demo: