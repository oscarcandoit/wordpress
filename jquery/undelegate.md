---
url: https://api.jquery.com/undelegate/
scraped_at: 2025-10-20T03:14:07.131Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .undelegate()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** Remove a handler from the event for all elements which match the current selector, based upon a specific set of root elements.

- #### version added: [1.4.2](https://api.jquery.com/category/version/1.4.2/) [.undelegate()](https://api.jquery.com/undelegate/\#undelegate)

  - This signature does not accept any arguments.
- #### version added: [1.4.2](https://api.jquery.com/category/version/1.4.2/) [.undelegate( selector, eventType )](https://api.jquery.com/undelegate/\#undelegate-selector-eventType)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector which will be used to filter the event results.

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a JavaScript event type, such as "click" or "keydown"
- #### version added: [1.4.2](https://api.jquery.com/category/version/1.4.2/) [.undelegate( selector, eventType, handler )](https://api.jquery.com/undelegate/\#undelegate-selector-eventType-handler)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector which will be used to filter the event results.

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a JavaScript event type, such as "click" or "keydown"

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.undelegate( selector, events )](https://api.jquery.com/undelegate/\#undelegate-selector-events)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector which will be used to filter the event results.

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object of one or more event types and previously bound functions to unbind from them.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.undelegate( namespace )](https://api.jquery.com/undelegate/\#undelegate-namespace)

  - **namespace**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a namespace to unbind all events from.

As of jQuery 3.0, `.undelegate()` has been deprecated. It was superseded by the [`.off()`](https://api.jquery.com/off/) method since jQuery 1.7, so its use was already discouraged.

The `.undelegate()` method is a way of removing event handlers that have been bound using [`.delegate()`](https://api.jquery.com/delegate/).

### Example 1

Can bind and unbind events to the colored button.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo:

### Example 2

To unbind all delegated events from all paragraphs, write:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

To unbind all delegated click events from all paragraphs, write:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

To undelegate just one previously bound handler, pass the function in as the third argument:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

### Example 5

To unbind all delegated events by their namespace:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |