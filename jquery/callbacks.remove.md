---
url: https://api.jquery.com/callbacks.remove/
scraped_at: 2025-10-20T03:05:39.217Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## callbacks.remove( callbacks )Returns: [Callbacks](http://api.jquery.com/Types/\#Callbacks)

**Description:** Remove a callback or a collection of callbacks from a callback list.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [callbacks.remove( callbacks )](https://api.jquery.com/callbacks.remove/\#callbacks-remove-callbacks)

  - **callbacks**

    Type: [Function](http://api.jquery.com/Types/#Function)() or [Array](http://api.jquery.com/Types/#Array)

    A function, or array of functions, that are to be removed from the callback list.

This method returns the Callbacks object onto which it is attached ( `this`).

Use `callbacks.remove()` to remove callbacks from a callback list:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |