---
url: https://api.jquery.com/delegate/
scraped_at: 2025-10-20T03:09:51.056Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .delegate( selector, eventType, handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** Attach a handler to one or more events for all elements that match the selector, now or in the future, based on a specific set of root elements.

- #### version added: [1.4.2](https://api.jquery.com/category/version/1.4.2/) [.delegate( selector, eventType, handler )](https://api.jquery.com/delegate/\#delegate-selector-eventType-handler)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector to filter the elements that trigger the event.

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing one or more space-separated JavaScript event types, such as "click" or "keydown," or custom event names.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.4.2](https://api.jquery.com/category/version/1.4.2/) [.delegate( selector, eventType, eventData, handler )](https://api.jquery.com/delegate/\#delegate-selector-eventType-eventData-handler)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector to filter the elements that trigger the event.

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing one or more space-separated JavaScript event types, such as "click" or "keydown," or custom event names.

  - **eventData**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.delegate( selector, events )](https://api.jquery.com/delegate/\#delegate-selector-events)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector to filter the elements that trigger the event.

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A plain object of one or more event types and functions to execute for them.

As of jQuery 3.0, `.delegate()` has been deprecated. It was superseded by the [`.on()`](https://api.jquery.com/on/) method since jQuery 1.7, so its use was already discouraged. For earlier versions, however, it remains the most effective means to use event delegation. More information on event binding and delegation is in the [`.on()`](https://api.jquery.com/on/) method. In general, these are the equivalent templates for the two methods:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

For example, the following `.delegate()` code:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

is equivalent to the following code written using `.on()`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

To remove events attached with `delegate()`, see the [.undelegate()](https://api.jquery.com/undelegate/) method.

Passing and handling event data works the same way as it does for `.on()`.

### Additional Notes:

- Since the [`.live()`](https://api.jquery.com/live/) method handles events once they have propagated to the top of the document, it is not possible to stop propagation of live events. Similarly, events handled by `[.delegate()](https://api.jquery.com/delegate/)` will propagate to the elements to which they are delegated; event handlers bound on any elements below it in the DOM tree will already have been executed by the time the delegated event handler is called. These handlers, therefore, may prevent the delegated handler from triggering by calling `[event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)` or returning `false`.


### Example 1

Click a paragraph to add another. Note that .delegate() attaches a click event handler to all paragraphs - even new ones.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 2

To display each paragraph's text in an alert box whenever it is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

To cancel a default action and prevent it from bubbling up, return false:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 4

To cancel only the default action by using the preventDefault method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 5

Can bind custom events too.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo: