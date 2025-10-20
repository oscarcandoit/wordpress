---
url: https://api.jquery.com/deferred.done/
scraped_at: 2025-10-20T03:06:15.333Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.done( doneCallbacks \[, doneCallbacks \] )Returns: [Deferred](http://api.jquery.com/Types/\#Deferred)

**Description:** Add handlers to be called when the Deferred object is resolved.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.done( doneCallbacks \[, doneCallbacks \] )](https://api.jquery.com/deferred.done/\#deferred-done-doneCallbacks-doneCallbacks)

  - **doneCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     A function, or array of functions, that are called when the Deferred is resolved.


  - **doneCallbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)()


     Optional additional functions, or arrays of functions, that are called when the Deferred is resolved.

The `deferred.done()` method accepts one or more arguments, all of which can be either a single function or an array of functions. When the Deferred is resolved, the doneCallbacks are called. Callbacks are executed in the order they were added. Since `deferred.done()` returns the deferred object, other methods of the deferred object can be chained to this one, including additional `.done()` methods. When the Deferred is resolved, doneCallbacks are executed using the arguments provided to the [`resolve`](https://api.jquery.com/deferred.resolve/) or [`resolveWith`](https://api.jquery.com/deferred.resolveWith/) method call in the order they were added. For more information, see the documentation for [Deferred object](https://api.jquery.com/category/deferred-object/).

### Example 1

Since the [`jQuery.get`](https://api.jquery.com/jQuery.get/) method returns a jqXHR object, which is derived from a Deferred object, we can attach a success callback using the `.done()` method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Resolve a Deferred object when the user clicks a button, triggering a number of callback functions:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44 | ```<br>``` |

#### Demo: