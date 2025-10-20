---
url: https://api.jquery.com/event.currentTarget/
scraped_at: 2025-10-20T03:10:03.842Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.currentTargetReturns: [Element](http://api.jquery.com/Types/\#Element)

**Description:** The current DOM element within the event bubbling phase.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/)event.currentTarget


This property will typically be equal to the `this` of the function.

_If you are using [jQuery.proxy](https://api.jquery.com/jQuery.proxy/) or another form of scope manipulation, `this` will be equal to whatever context you have provided, not `event.currentTarget`_

Alert that currentTarget matches the \`this\` keyword.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |