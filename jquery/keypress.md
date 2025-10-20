---
url: https://api.jquery.com/keypress/
scraped_at: 2025-10-20T03:13:05.398Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "keypress" event, or trigger that event on an element.

#### Contents:

- [.on( "keypress" \[, eventData \], handler )](https://api.jquery.com/keypress/#on1)  - [.on( "keypress" \[, eventData \], handler )](https://api.jquery.com/keypress/#on-%22keypress%22-eventData-handler)
- [.trigger( "keypress" )](https://api.jquery.com/keypress/#trigger2)  - [.trigger( "keypress" )](https://api.jquery.com/keypress/#trigger-%22keypress%22)

## .on( "keypress" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "keypress" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "keypress" \[, eventData \], handler )](https://api.jquery.com/keypress/\#on-%22keypress%22-eventData-handler)

  - **"keypress"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"keypress"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `keypress` event. For the deprecated `.keypress()` method, see [`.keypress()`](https://api.jquery.com/keypress-shorthand/).

**Note:** as the `keypress` event isn't covered by any official specification, the actual behavior encountered when using it may differ across browsers, browser versions, and platforms.

The `keypress` event is sent to an element when the browser registers keyboard input. This is similar to the `keydown` event, except that modifier and non-printing keys such as `Shift`, `Esc`, and `delete` trigger `keydown` events but not `keypress` events. Other differences between the two events may arise depending on platform and browser.

A `keypress` event handler can be attached to any element, but the event is only sent to the element that has the focus. Focusable elements can vary between browsers, but form controls can always get focus so are reasonable candidates for this event type.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

The event handler can be bound to the input field:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now when the insertion point is inside the field, pressing a key displays the log:

``Handler for `keypress` called.``

To trigger the event manually, use `.trigger( "keypress" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on the `Trigger the handler` div will also log the message.

If key presses anywhere need to be caught (for example, to implement global shortcut keys on a page), it is useful to attach this behavior to the `document` object. Because of event bubbling, all key presses will make their way up the DOM to the `document` object unless explicitly stopped.

To determine which character was entered, examine the `event` object that is passed to the handler function. While browsers use differing properties to store this information, jQuery normalizes the `.which` property so you can reliably use it to retrieve the character code.

Note that `keydown` and `keyup` provide a code indicating which key is pressed, while `keypress` indicates which character was entered. For example, a lowercase "a" will be reported as 65 by `keydown` and `keyup`, but as 97 by `keypress`. An uppercase "A" is reported as 65 by all events. Because of this distinction, when catching special keystrokes such as arrow keys, `.keydown()` or `.keyup()` is a better choice.

Show the event object when a key is pressed in the input. Note: This demo relies on a simple $.print() plugin (https://api.jquery.com/resources/events.js) for the event object's output.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57 | ```<br>``` |

#### Demo:

## .trigger( "keypress" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "keypress" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "keypress" )](https://api.jquery.com/keypress/\#trigger-%22keypress%22)

  - **"keypress"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"keypress"`.

See the description for [`.on( "keypress", ... )`](https://api.jquery.com/keypress/#on1).