---
url: https://api.jquery.com/change/
scraped_at: 2025-10-20T03:09:04.949Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Bind an event handler to the "change" event, or trigger that event on an element.

#### Contents:

- [.on( "change" \[, eventData \], handler )](https://api.jquery.com/change/#on1)  - [.on( "change" \[, eventData \], handler )](https://api.jquery.com/change/#on-%22change%22-eventData-handler)
- [.trigger( "change" )](https://api.jquery.com/change/#trigger2)  - [.trigger( "change" )](https://api.jquery.com/change/#trigger-%22change%22)

## .on( "change" \[, eventData \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Bind an event handler to the "change" event.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.on( "change" \[, eventData \], handler )](https://api.jquery.com/change/\#on-%22change%22-eventData-handler)

  - **"change"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"change"`.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute each time the event is triggered.

This page describes the `change` event. For the deprecated `.change()` method, see [`.change()`](https://api.jquery.com/change-shorthand/).

The `change` event is sent to an element when its value changes. This event is limited to `<input>` elements, `<textarea>` boxes and `<select>` elements. For select boxes, checkboxes, and radio buttons, the event is fired immediately when the user makes a selection with the mouse, but for the other element types the event is deferred until the element loses focus.

For example, consider the HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

The event handler can be bound to the text input and the select box:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Now when the second option is selected from the dropdown, the alert is displayed. It is also displayed if you change the text in the field and then click away. If the field loses focus without the contents having changed, though, the event is not triggered. To trigger the event manually, use `.trigger( "change" )`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After this code executes, clicks on `Trigger the handler` will also alert the message. The message will display twice, because the handler has been bound to the `change` event on both of the form elements.

As of jQuery 1.4, the `change` event bubbles in Internet Explorer, behaving consistently with the event in other modern browsers.

**Note:** Changing the value of an input element using JavaScript, using [`.val()`](https://api.jquery.com/val) for example, won't fire the event.

### Example 1

Attaches a change event to the select that gets the text for each selected option and writes them in the div. It then triggers the event for the initial text draw.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo:

### Example 2

To add a validity test to all text input elements:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

## .trigger( "change" )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Trigger the "change" event on an element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.trigger( "change" )](https://api.jquery.com/change/\#trigger-%22change%22)

  - **"change"**

    Type: [string](http://api.jquery.com/Types/#string)

    The string `"change"`.

See the description for [`.on( "change", ... )`](https://api.jquery.com/change/#on1).