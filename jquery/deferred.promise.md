---
url: https://api.jquery.com/deferred.promise/
scraped_at: 2025-10-20T03:06:57.193Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## deferred.promise( \[target \] )Returns: [Promise](http://api.jquery.com/Types/\#Promise)

**Description:** Return a Deferred's Promise object.

- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [deferred.promise( \[target \] )](https://api.jquery.com/deferred.promise/\#deferred-promise-target)

  - **target**

    Type: [Object](http://api.jquery.com/Types/#Object)

    Object onto which the promise methods have to be attached

The `deferred.promise()` method allows an asynchronous function to prevent other code from interfering with the progress or status of its internal request. The Promise exposes only the Deferred methods needed to attach additional handlers or determine the state ( `then`, `done`, `fail`, `always`, `pipe`, `progress`, `state` and `promise`), but not ones that change the state ( `resolve`, `reject`, `notify`, `resolveWith`, `rejectWith`, and `notifyWith`).

If `target` is provided, `deferred.promise()` will attach the methods onto it and then return this object rather than create a new one. This can be useful to attach the Promise behavior to an object that already exists.

If you are creating a Deferred, keep a reference to the Deferred so that it can be resolved or rejected at some point. Return _only_ the Promise object via `deferred.promise()` so other code can register callbacks or inspect the current state.

For more information, see the documentation for [Deferred object](https://api.jquery.com/category/deferred-object/).

### Example 1

Create a Deferred and set two timer-based functions to either resolve or reject the Deferred after a random interval. Whichever one fires first "wins" and will call one of the callbacks. The second timeout has no effect since the Deferred is already complete (in a resolved or rejected state) from the first timeout action. Also set a timer-based progress notification function, and call a progress handler that adds "working..." to the document body.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37 | ```<br>``` |

### Example 2

Use the target argument to promote an existing object to a Promise:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |