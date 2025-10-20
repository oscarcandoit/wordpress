---
url: https://api.jquery.com/jQuery.trim/
scraped_at: 2025-10-20T03:15:41.340Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.trim( str )Returns: [String](http://api.jquery.com/Types/\#String)version deprecated: [3.5](https://api.jquery.com/category/version/3.5/), removed: [4.0](https://api.jquery.com/category/version/4.0/)

**Description:** Remove the whitespace from the beginning and end of a string.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery.trim( str )](https://api.jquery.com/jQuery.trim/\#jQuery-trim-str)

  - **str**

    Type: [String](http://api.jquery.com/Types/#String)

    The string to trim.

Note: This API has been deprecated in jQuery 3.5; please use the native [`String.prototype.trim`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim) method instead. Unlike `jQuery.trim`, `String.prototype.trim` does not work with types other than strings ( `null`, `undefined`, `Number`). Make sure that your code is compatible when migrating.

The `$.trim()` function removes all newlines, spaces (including non-breaking spaces), and tabs from the beginning and end of the supplied string. If these whitespace characters occur in the middle of the string, they are preserved.

### Example 1

Remove the white spaces at the start and at the end of the string.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo:

### Example 2

Remove the white spaces at the start and at the end of the string.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

#### Result:

|     |     |
| --- | --- |
| 1 | ```<br>``` |