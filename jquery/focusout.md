---
url: https://api.jquery.com/focusout/
scraped_at: 2025-10-20T03:12:46.740Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "focusout" event, or trigger that event on an element.

#### Contents:

- [.on( "focusout" \[, eventData \], handler )](https://api.jquery.com/focusout/#on1)  - [.on( "focusout" \[, eventData \], handler )](https://api.jquery.com/focusout/#on-%22focusout%22-eventData-handler)
- [.trigger( "focusout" )](https://api.jquery.com/focusout/#trigger2)  - [.trigger( "focusout" )](https://api.jquery.com/focusout/#trigger-%22focusout%22)

## .on( "focusout" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "focusout" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "focusout" \[, eventData \], handler )](https://api.jquery.com/focusout/\#on-%22focusout%22-eventData-handler)

  - **"focusout"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focusout"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `focusout` event. For the deprecated `.focusout()` method, see [`.focusout()`](https://api.jquery.com/focusout-shorthand/).

The `focusout` event is sent to an element when it, or any element inside of it, loses focus. This is distinct from the [blur](https://api.jquery.com/blur/) event in that it supports detecting the loss of focus on descendant elements (in other words, it supports event bubbling).

This event will likely be used together with the [focusin](https://api.jquery.com/focusin/) event.

Watch for a loss of focus to occur inside paragraphs and note the difference between the `focusout` count and the `blur` count. (The `blur` count does not change because those events do not bubble.)

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46 | ```<br>``` |

#### Demo:

## .trigger( "focusout" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "focuout" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "focusout" )](https://api.jquery.com/focusout/\#trigger-%22focusout%22)

  - **"focusout"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"focusout"`.

See the description for [`.on( "focusout", ... )`](https://api.jquery.com/focusout/#on1).