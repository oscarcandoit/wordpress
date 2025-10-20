---
url: https://api.jquery.com/mouseleave/
scraped_at: 2025-10-20T03:13:24.043Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to be fired when the mouse leaves an element, or trigger that handler on an element.

#### Contents:

- [.on( "mouseleave" \[, eventData \], handler )](https://api.jquery.com/mouseleave/#on1)  - [.on( "mouseleave" \[, eventData \], handler )](https://api.jquery.com/mouseleave/#on-%22mouseleave%22-eventData-handler)
- [.trigger( "mouseleave" )](https://api.jquery.com/mouseleave/#trigger2)  - [.trigger( "mouseleave" )](https://api.jquery.com/mouseleave/#trigger-%22mouseleave%22)

## .on( "mouseleave" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to be fired when the mouse leaves an element.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "mouseleave" \[, eventData \], handler )](https://api.jquery.com/mouseleave/\#on-%22mouseleave%22-eventData-handler)

  - **"mouseleave"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseleave"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `mouseleave` event. For the deprecated `.mouseleave()` method, see [`.mouseleave()`](https://api.jquery.com/mouseleave-shorthand/).

The `mouseleave` JavaScript event is proprietary to Internet Explorer. Because of the event's general utility, jQuery simulates this event so that it can be used regardless of browser. This event is sent to an element when the mouse pointer leaves the element. Any HTML element can receive this event.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_09.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any element:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now when the mouse pointer moves out of the `Outer` `<div>`, the message is appended to `<div id="log">`. You can also trigger the event when another element is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also append the message.

The `mouseleave` event differs from `mouseout` in the way it handles event bubbling. If `mouseout` were used in this example, then when the mouse pointer moved out of the `Inner` element, the handler would be triggered. This is usually undesirable behavior. The `mouseleave` event, on the other hand, only triggers its handler when the mouse leaves the element it is bound to, not a descendant. So in this example, the handler is triggered when the mouse leaves the `Outer` element, but not the `Inner` element.

Show number of times mouseout and mouseleave events are triggered. `mouseout` fires when the pointer moves out of child element as well, while `mouseleave` fires only when the pointer moves out of the bound element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64 | ```<br>``` |

#### Demo:

## .trigger( "mouseleave" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "mouseleave" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "mouseleave" )](https://api.jquery.com/mouseleave/\#trigger-%22mouseleave%22)

  - **"mouseleave"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseleave"`.

See the description for [`.on( "mouseleave", ... )`](https://api.jquery.com/mouseleave/#on1).