---
url: https://api.jquery.com/queue/
scraped_at: 2025-10-20T03:08:19.384Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Show or manipulate the queue of functions to be executed on the matched elements.

#### Contents:

- [.queue( \[queueName \] )](https://api.jquery.com/queue/#queue1)  - [.queue( \[queueName \] )](https://api.jquery.com/queue/#queue-queueName)
- [.queue( \[queueName \], newQueue )](https://api.jquery.com/queue/#queue2)  - [.queue( \[queueName \], newQueue )](https://api.jquery.com/queue/#queue-queueName-newQueue)
  - [.queue( \[queueName \], callback )](https://api.jquery.com/queue/#queue-queueName-callback)

## .queue( \[queueName \] )Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Show the queue of functions to be executed on the matched elements.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.queue( \[queueName \] )](https://api.jquery.com/queue/\#queue-queueName)

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

Show the length of the queue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57 | ```<br>``` |

#### Demo:

## .queue( \[queueName \], newQueue )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Manipulate the queue of functions to be executed, once for each matched element.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.queue( \[queueName \], newQueue )](https://api.jquery.com/queue/\#queue-queueName-newQueue)

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

  - **newQueue**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of functions to replace the current queue contents.
- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.queue( \[queueName \], callback )](https://api.jquery.com/queue/\#queue-queueName-callback)

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Function](http://api.jquery.com/Types/#Function) next() )

    The new function to add to the queue, with a function to call that will dequeue the next item.

Every element can have one to many queues of functions attached to it by jQuery. In most applications, only one queue (called `fx`) is used. Queues allow a sequence of actions to be called on an element asynchronously, without halting program execution. The typical example of this is calling multiple animation methods on an element. For example:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

When this statement is executed, the element begins its sliding animation immediately, but the fading transition is placed on the `fx` queue to be called only once the sliding transition is complete.

The `.queue()` method allows us to directly manipulate this queue of functions. Calling `.queue()` with a callback is particularly useful; it allows us to place a new function at the end of the queue. The callback function is executed once for each element in the jQuery set.

This feature is similar to providing a callback function with an animation method, but does not require the callback to be given at the time the animation is performed.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

This is equivalent to:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Note that when adding a function with `.queue()`, we should ensure that `.dequeue()` is eventually called so that the next function in line executes.

**As of jQuery 1.4**, the function that's called is passed another function as the first argument. When called, this automatically dequeues the next item and keeps the queue moving. We use it as follows:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

### Example 1

Queue a custom function.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45 | ```<br>``` |

#### Demo:

### Example 2

Set a queue array to delete the queue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51 | ```<br>``` |

#### Demo: