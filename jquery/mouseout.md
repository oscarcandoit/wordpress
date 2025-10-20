---
url: https://api.jquery.com/mouseout/
scraped_at: 2025-10-20T03:13:30.881Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "mouseout" event, or trigger that event on an element.

#### Contents:

- [.on( "mouseout" \[, eventData \], handler )](https://api.jquery.com/mouseout/#on1)  - [.on( "mouseout" \[, eventData \], handler )](https://api.jquery.com/mouseout/#on-%22mouseout%22-eventData-handler)
- [.trigger( "mouseout" )](https://api.jquery.com/mouseout/#trigger2)  - [.trigger( "mouseout" )](https://api.jquery.com/mouseout/#trigger-%22mouseout%22)

## .on( "mouseout" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "mouseout" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "mouseout" \[, eventData \], handler )](https://api.jquery.com/mouseout/\#on-%22mouseout%22-eventData-handler)

  - **"mouseout"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseout"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `mouseout` event. For the deprecated `.mouseout()` method, see [`.mouseout()`](https://api.jquery.com/mouseout-shorthand/).

The `mouseout` event is sent to an element when the mouse pointer leaves the element. Any HTML element can receive this event.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

![](https://api.jquery.com/resources/0042_05_07.png)Figure 1 - Illustration of the rendered HTML

The event handler can be bound to any element:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now when the mouse pointer moves out of the `Outer` `<div>`, the message is appended to `<div id="log">`. To trigger the event manually, use `.trigger( "mouseout" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also append the message.

This event type can cause many headaches due to event bubbling. For instance, when the mouse pointer moves out of the `Inner` element in this example, a `mouseout` event will be sent to that, then trickle up to `Outer`. This can trigger the bound `mouseout` handler at inopportune times. See the discussion for `. [mouseleave](https://api.jquery.com/mouseleave/)()` for a useful alternative.

Show the number of times mouseout and mouseleave events are triggered.
`mouseout` fires when the pointer moves out of the child element as well, while `mouseleave` fires only when the pointer moves out of the bound element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65 | ```<br>``` |

#### Demo:

## .trigger( "mouseout" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "mouseout" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "mouseout" )](https://api.jquery.com/mouseout/\#trigger-%22mouseout%22)

  - **"mouseout"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"mouseout"`.

See the description for [`.on( "mouseout", ... )`](https://api.jquery.com/mouseout/#on1).