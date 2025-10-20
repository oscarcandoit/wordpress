---
url: https://api.jquery.com/jQuery.dequeue/
scraped_at: 2025-10-20T03:04:17.618Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.dequeue( element \[, queueName \] )Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Execute the next function on the queue for the matched element.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [jQuery.dequeue( element \[, queueName \] )](https://api.jquery.com/jQuery.dequeue/\#jQuery-dequeue-element-queueName)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element from which to remove and execute a queued function.

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

**Note:** This is a low-level method, you should probably use `[.dequeue()](https://api.jquery.com/dequeue/)` instead.

When `jQuery.dequeue()` is called, the next function on the queue is removed from the queue, and then executed. This function should in turn (directly or indirectly) cause `jQuery.dequeue()` to be called, so that the sequence can continue.

Use jQuery.dequeue() to end a custom queue function which allows the queue to keep going.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41 | ```<br>``` |

#### Demo: