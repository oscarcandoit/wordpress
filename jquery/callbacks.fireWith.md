---
url: https://api.jquery.com/callbacks.fireWith/
scraped_at: 2025-10-20T03:05:22.052Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## callbacks.fireWith( \[context \] \[, args \] )Returns: [Callbacks](http://api.jquery.com/Types/\#Callbacks)

**Description:** Call all callbacks in a list with the given context and arguments.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [callbacks.fireWith( \[context \] \[, args \] )](https://api.jquery.com/callbacks.fireWith/\#callbacks-fireWith-context-args)

  - **context**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    A reference to the context in which the callbacks in the list should be fired.

  - **args**

    Type: [ArrayLikeObject](http://api.jquery.com/Types/#ArrayLikeObject)

    An array or array-like object of arguments to pass to the callbacks in the list. If omitted or undefined, no arguments will be passed.

This method returns the Callbacks object onto which it is attached ( `this`).

Use `callbacks.fireWith()` to fire a list of callbacks with a specific context and an array of arguments:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15 | ```<br>``` |