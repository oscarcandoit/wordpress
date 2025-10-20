---
url: https://api.jquery.com/one/
scraped_at: 2025-10-20T03:13:55.767Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .one( events \[, data \], handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Attach a handler to an event for the elements. The handler is executed at most once per element per event type.

- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [.one( events \[, data \], handler )](https://api.jquery.com/one/\#one-events-data-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing one or more JavaScript event types, such as "click" or "submit," or custom event names.

  - **data**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    Data to be passed to the handler in [`event.data`](https://api.jquery.com/event.data/) when an event is triggered.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.one( events \[, selector \] \[, data \], handler )](https://api.jquery.com/one/\#one-events-selector-data-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    One or more space-separated event types and optional namespaces, such as "click" or "keydown.myPlugin".

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector string to filter the descendants of the selected elements that trigger the event. If the selector is `null` or omitted, the event is always triggered when it reaches the selected element.

  - **data**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Data to be passed to the handler in [`event.data`](https://api.jquery.com/event.data/) when an event is triggered.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute when the event is triggered. The value `false` is also allowed as a shorthand for a function that simply does `return false`.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.one( events \[, selector \] \[, data \] )](https://api.jquery.com/one/\#one-events-selector-data)

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object in which the string keys represent one or more space-separated event types and optional namespaces, and the values represent a handler function to be called for the event(s).

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector string to filter the descendants of the selected elements that will call the handler. If the selector is null or omitted, the handler is always called when it reaches the selected element.

  - **data**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    Data to be passed to the handler in [`event.data`](https://api.jquery.com/event.data/) when an event occurs.

The `.one()` method is identical to `.on()`, except that the handler for a given element and event type is unbound after its first invocation. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

After the code is executed, a click on the element with ID `foo` will display the alert. Subsequent clicks will do nothing. This code is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

In other words, explicitly calling `.off()` from within a regularly-bound handler has exactly the same effect.

If the first argument contains more than one space-separated event types, the event handler is called _once for each event type_.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

In the example above the alert could be displayed twice due to the _two_ event types ( `click` and `mouseover`).

### Example 1

Tie a one-time click to each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47 | ```<br>``` |

#### Demo:

### Example 2

To display the text of all paragraphs in an alert box the first time each of them is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

Event handlers will trigger once per element per event type

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Demo: