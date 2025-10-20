---
url: https://api.jquery.com/removeData/
scraped_at: 2025-10-20T03:04:32.261Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .removeData( \[name \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove a previously-stored piece of data.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [.removeData( \[name \] )](https://api.jquery.com/removeData/\#removeData-name)

  - **name**

    Type: [String](http://api.jquery.com/Types/#String)

    A string naming the piece of data to delete.
- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [.removeData( \[list \] )](https://api.jquery.com/removeData/\#removeData-list)

  - **list**

    Type: [Array](http://api.jquery.com/Types/#Array) or [String](http://api.jquery.com/Types/#String)

    An array or space-separated string naming the pieces of data to delete.

The `.removeData()` method allows us to remove values that were previously set using `.data()`. When called with the name of a key, `.removeData()` deletes that particular value. When called with no arguments, `.removeData()` removes all values.

Note that `.removeData()` will only remove data from jQuery's internal `.data()` cache, and any corresponding `data-` attributes on the element will not be removed. A later call to `data()`
will therefore re-retrieve the value from the `data-` attribute. To prevent this, use `.removeAttr()` alongside `.removeData()` to remove the `data-` attribute as well. Prior to jQuery 1.4.3,
as `data()` did not use `data-` attributes, this was not an issue.


**As of jQuery 1.7**, when called with an array of keys or a string of space-separated keys, `.removeData()` deletes the value of each key in that array or string.

Set a data store for 2 names then remove one of them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo: