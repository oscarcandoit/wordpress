---
url: https://api.jquery.com/promise/
scraped_at: 2025-10-20T03:04:43.884Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .promise( \[type \] \[, target \] )Returns: [Promise](http://api.jquery.com/Types/\#Promise)

**Description:** Return a Promise object to observe when all actions of a certain type bound to the collection, queued or not, have finished.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.promise( \[type \] \[, target \] )](https://api.jquery.com/promise/\#promise-type-target)

  - **type** (default: `fx`)

    Type: [String](http://api.jquery.com/Types/#String)

     The type of queue that needs to be observed.

  - **target**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    Object onto which the promise methods have to be attached

The `.promise()` method returns a dynamically generated Promise that is resolved once all actions of a certain type bound to the collection, queued or not, have ended.

By default, `type` is `"fx"`, which means the returned Promise is resolved when all animations of the selected elements have completed.

Resolve context and sole argument is the collection onto which `.promise()` has been called.

If `target` is provided, `.promise()` will attach the methods onto it and then return this object rather than create a new one. This can be useful to attach the Promise behavior to an object that already exists.

**Note:** The returned Promise is linked to a Deferred object stored on the `.data()` for an element. Since the `.remove()` method removes the element's data as well as the element itself, it will prevent any of the element's unresolved Promises from resolving. If it is necessary to remove an element from the DOM before its Promise is resolved, use `.detach()` instead and follow with `.removeData()` after resolution.

### Example 1

Using `.promise()` on a collection with no active animation returns a resolved Promise:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

### Example 2

Resolve the returned Promise when all animations have ended (including those initiated in the animation callback or added later on):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo:

### Example 3

Resolve the returned Promise using a `$.when()` statement (the `.promise()` method makes it possible to do this with jQuery collections):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo: