---
url: https://api.jquery.com/callbacks.fire/
scraped_at: 2025-10-20T03:05:08.106Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## callbacks.fire( arguments )Returns: [Callbacks](http://api.jquery.com/Types/\#Callbacks)

**Description:** Call all of the callbacks with the given arguments.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [callbacks.fire( arguments )](https://api.jquery.com/callbacks.fire/\#callbacks-fire-arguments)

  - **arguments**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    The argument or list of arguments to pass back to the callback list.

This method returns the Callbacks object onto which it is attached ( `this`).

Use `callbacks.fire()` to invoke the callbacks in a list with any arguments that have been passed:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |