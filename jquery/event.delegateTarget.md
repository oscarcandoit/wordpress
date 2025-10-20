---
url: https://api.jquery.com/event.delegateTarget/
scraped_at: 2025-10-20T03:11:03.799Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.delegateTargetReturns: [Element](http://api.jquery.com/Types/\#Element)

**Description:** The element where the currently-called jQuery event handler was attached.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/)event.delegateTarget


This property is most often useful in delegated events attached by [`.delegate()`](https://api.jquery.com/delegate/) or [`.on()`](https://api.jquery.com/on/), where the event handler is attached at an ancestor of the element being processed. It can be used, for example, to identify and remove event handlers at the delegation point.

For non-delegated event handlers attached directly to an element, `event.delegateTarget` will always be equal to `event.currentTarget`.

When a button in any box class is clicked, change the box's background color to red.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |