---
url: https://api.jquery.com/event.stopPropagation/
scraped_at: 2025-10-20T03:12:02.730Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.stopPropagation()Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Prevents the event from bubbling up the DOM tree, preventing any parent handlers from being notified of the event.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [event.stopPropagation()](https://api.jquery.com/event.stopPropagation/\#event-stopPropagation)

  - This method does not accept any arguments.

We can use `[event.isPropagationStopped()](https://api.jquery.com/event.isPropagationStopped/)` to determine if this method was ever called (on that event object).

This method works for custom events triggered with [trigger()](https://api.jquery.com/trigger/) as well.

Note that this will not prevent other handlers _on the same element_ from running.

### Additional Notes:

- Since the [`.live()`](https://api.jquery.com/live/) method handles events once they have propagated to the top of the document, it is not possible to stop propagation of live events. Similarly, events handled by `[.delegate()](https://api.jquery.com/delegate/)` will propagate to the elements to which they are delegated; event handlers bound on any elements below it in the DOM tree will already have been executed by the time the delegated event handler is called. These handlers, therefore, may prevent the delegated handler from triggering by calling `[event.stopPropagation()](https://api.jquery.com/event.stopPropagation/)` or returning `false`.


Kill the bubbling on the click event.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |