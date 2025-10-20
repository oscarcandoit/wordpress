---
url: https://api.jquery.com/jQuery.queue/
scraped_at: 2025-10-20T03:04:28.827Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Show or manipulate the queue of functions to be executed on the matched element.

#### Contents:

- [jQuery.queue( element \[, queueName \] )](https://api.jquery.com/jQuery.queue/#jQuery-queue1)   - [jQuery.queue( element \[, queueName \] )](https://api.jquery.com/jQuery.queue/#jQuery-queue-element-queueName)
- [jQuery.queue( element, queueName, newQueue )](https://api.jquery.com/jQuery.queue/#jQuery-queue2)  - [jQuery.queue( element, queueName, newQueue )](https://api.jquery.com/jQuery.queue/#jQuery-queue-element-queueName-newQueue)
  - [jQuery.queue( element, queueName, callback )](https://api.jquery.com/jQuery.queue/#jQuery-queue-element-queueName-callback)

## jQuery.queue( element \[, queueName \] )Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Show the queue of functions to be executed on the matched element.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [jQuery.queue( element \[, queueName \] )](https://api.jquery.com/jQuery.queue/\#jQuery-queue-element-queueName)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element to inspect for an attached queue.

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

**Note:** This is a low-level method, you should probably use `[.queue()](https://api.jquery.com/queue/)` instead.

Show the length of the queue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58 | ```<br>``` |

#### Demo:

## jQuery.queue( element, queueName, newQueue )Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Manipulate the queue of functions to be executed on the matched element.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [jQuery.queue( element, queueName, newQueue )](https://api.jquery.com/jQuery.queue/\#jQuery-queue-element-queueName-newQueue)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element where the array of queued functions is attached.

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

  - **newQueue**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of functions to replace the current queue contents.
- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [jQuery.queue( element, queueName, callback )](https://api.jquery.com/jQuery.queue/\#jQuery-queue-element-queueName-callback)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element on which to add a queued function.

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The new function to add to the queue.

**Note:** This is a low-level method, you should probably use `[.queue()](https://api.jquery.com/queue/)` instead.

Every element can have one or more queues of functions attached to it by jQuery. In most applications, only one queue (called `fx`) is used. Queues allow a sequence of actions to be called on an element asynchronously, without halting program execution.

The `jQuery.queue()` method allows us to directly manipulate this queue of functions. Calling `jQuery.queue()` with a callback is particularly useful; it allows us to place a new function at the end of the queue.

Note that when adding a function with `jQuery.queue()`, we should ensure that `jQuery.dequeue()` is eventually called so that the next function in line executes.

### Example 1

Queue a custom function.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47 | ```<br>``` |

#### Demo:

### Example 2

Set a queue array to delete the queue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52 | ```<br>``` |

#### Demo: