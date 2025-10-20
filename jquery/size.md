---
url: https://api.jquery.com/size/
scraped_at: 2025-10-20T03:16:18.912Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .size()Returns: [Integer](http://api.jquery.com/Types/\#Integer)version deprecated: [1.8](https://api.jquery.com/category/version/1.8/), removed: [3.0](https://api.jquery.com/category/version/3.0/)

**Description:** Return the number of elements in the jQuery object.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.size()](https://api.jquery.com/size/\#size)

  - This method does not accept any arguments.

Note: This method has been removed in jQuery 3.0. Use the `[.length](https://api.jquery.com/length/)` property instead.

The `.size()` method is functionally equivalent to the `[.length](https://api.jquery.com/length/)` property; however, **the `.length` property is preferred** because it does not have the overhead of a function call.

Given a simple unordered list on the page:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Both `.size()` and `.length` identify the number of items:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

This results in two alerts:

`Size: 2`

`Size: 2`

Count the divs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |