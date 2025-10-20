---
url: https://api.jquery.com/jQuery.removeData/
scraped_at: 2025-10-20T03:04:40.403Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.removeData( element \[, name \] )Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** Remove a previously-stored piece of data.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [jQuery.removeData( element \[, name \] )](https://api.jquery.com/jQuery.removeData/\#jQuery-removeData-element-name)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element from which to remove data.

  - **name**

    Type: [String](http://api.jquery.com/Types/#String)

    A string naming the piece of data to remove.

**Note:** This is a low-level method, you should probably use `[.removeData()](https://api.jquery.com/removeData/)` instead.

The `jQuery.removeData()` method allows us to remove values that were previously set using `[jQuery.data()](https://api.jquery.com/jQuery.data/)`. When called with the name of a key, `jQuery.removeData()` deletes that particular value; when called with no arguments, all values are removed.

Set a data store for 2 names then remove one of them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: