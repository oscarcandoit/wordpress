---
url: https://api.jquery.com/position/
scraped_at: 2025-10-20T03:03:44.647Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .position()Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Get the current coordinates of the first element in the set of matched elements, relative to the offset parent.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.position()](https://api.jquery.com/position/\#position)

  - This method does not accept any arguments.

The `.position()` method allows us to retrieve the current position of an element (specifically its margin box) _relative to the offset parent_ (specifically its padding box, which excludes margins and borders). Contrast this with `[.offset()](https://api.jquery.com/offset/)`, which retrieves the current position _relative to the document_. When positioning a new element near another one and within the same containing DOM element, `.position()` is the more useful.

Returns an object containing the properties `top` and `left`.

**Note:** jQuery does not support getting the position coordinates of hidden elements or accounting for margins set on the `<html>` document element.

### Additional Notes:

- The number returned by dimensions-related APIs, including `.position()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.


Access the position of the second paragraph:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30 | ```<br>``` |

#### Demo: