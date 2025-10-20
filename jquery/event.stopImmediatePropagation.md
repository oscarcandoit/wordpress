---
url: https://api.jquery.com/event.stopImmediatePropagation/
scraped_at: 2025-10-20T03:11:58.743Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.stopImmediatePropagation()Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Keeps the rest of the handlers from being executed and prevents the event from bubbling up the DOM tree.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [event.stopImmediatePropagation()](https://api.jquery.com/event.stopImmediatePropagation/\#event-stopImmediatePropagation)

  - This method does not accept any arguments.

In addition to keeping any additional handlers on an element from being executed, this method also stops the bubbling by implicitly calling `event.stopPropagation()`. To simply prevent the event from bubbling to ancestor elements but allow other event handlers to execute on the same element, we can use `[event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)` instead.

Use `[event.isImmediatePropagationStopped()](https://api.jquery.com/event.isImmediatePropagationStopped/)` to know whether this method was ever called (on that event object).

### Additional Notes:

- Since the [`.live()`](https://api.jquery.com/live/) method handles events once they have propagated to the top of the document, it is not possible to stop propagation of live events. Similarly, events handled by `[.delegate()](https://api.jquery.com/delegate/)` will propagate to the elements to which they are delegated; event handlers bound on any elements below it in the DOM tree will already have been executed by the time the delegated event handler is called. These handlers, therefore, may prevent the delegated handler from triggering by calling `[event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)` or returning `false`.


Prevents other event handlers from being called.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: