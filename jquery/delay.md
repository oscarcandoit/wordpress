---
url: https://api.jquery.com/delay/
scraped_at: 2025-10-20T03:07:37.220Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .delay( duration \[, queueName \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set a timer to delay execution of subsequent items in the queue.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.delay( duration \[, queueName \] )](https://api.jquery.com/delay/\#delay-duration-queueName)

  - **duration**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    An integer indicating the number of milliseconds to delay execution of the next item in the queue.

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

Added to jQuery in version 1.4, the `.delay()` method allows us to delay the execution of functions that follow it in the queue. It can be used with the standard effects queue or with a custom queue. Only subsequent events in a queue are delayed; for example this will _not_ delay the no-arguments forms of `.show()` or `.hide()` which do not use the effects queue.

Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings `'fast'` and `'slow'` can be supplied to indicate durations of 200 and 600 milliseconds, respectively.

Using the standard effects queue, we can, for example, set an 800-millisecond delay between the `.slideUp()` and `.fadeIn()` of `<div id="foo">`:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

When this statement is executed, the element slides up for 300 milliseconds and then pauses for 800 milliseconds before fading in for 400 milliseconds.

**The `.delay()` method is best for delaying between queued jQuery effects. Because it is limited—it doesn't, for example, offer a way to cancel the delay— `.delay()` is not a replacement for JavaScript's native [setTimeout](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout) function, which may be more appropriate for certain use cases.**

Animate the hiding and showing of two divs, delaying the first before showing it.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo: