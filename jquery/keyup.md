---
url: https://api.jquery.com/keyup/
scraped_at: 2025-10-20T03:13:09.228Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "keyup" event, or trigger that event on an element.

#### Contents:

- [.on( "keyup" \[, eventData \], handler )](https://api.jquery.com/keyup/#on1)  - [.on( "keyup" \[, eventData \], handler )](https://api.jquery.com/keyup/#on-%22keyup%22-eventData-handler)
- [.trigger( "keyup" )](https://api.jquery.com/keyup/#trigger2)  - [.trigger( "keyup" )](https://api.jquery.com/keyup/#trigger-%22keyup%22)

## .on( "keyup" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "keyup" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "keyup" \[, eventData \], handler )](https://api.jquery.com/keyup/\#on-%22keyup%22-eventData-handler)

  - **"keyup"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"keyup"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `keyup` event. For the deprecated `.keyup()` method, see [`.keyup()`](https://api.jquery.com/keyup-shorthand/).

The `keyup` event is sent to an element when the user releases a key on the keyboard. It can be attached to any element, but the event is only sent to the element that has the focus. Focusable elements can vary between browsers, but form elements can always get focus so are reasonable candidates for this event type.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

The event handler can be bound to the input field:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now when the insertion point is inside the field and a key is pressed and released, the alert is displayed:

``Handler for `keyup` called.``

To trigger the event manually, use `.trigger( "keyup" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message.

If key presses anywhere need to be caught (for example, to implement global shortcut keys on a page), it is useful to attach this behavior to the `document` object. Because of event bubbling, all key presses will make their way up the DOM to the `document` object unless explicitly stopped.

To determine which key was pressed, examine the event object that is passed to the handler function. While browsers use differing properties to store this information, jQuery normalizes the `.which` property so you can reliably use it to retrieve the key code. This code corresponds to a key on the keyboard, including codes for special keys such as arrows. For catching actual text entry, `.keypress()` may be a better choice.

Show the event object for the keyup handler (using a simple $.print plugin) when a key is released in the input.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58 | ```<br>``` |

#### Demo:

## .trigger( "keyup" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "keyup" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "keyup" )](https://api.jquery.com/keyup/\#trigger-%22keyup%22)

  - **"keyup"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"keyup"`.

See the description for [`.on( "keyup", ... )`](https://api.jquery.com/keyup/#on1).