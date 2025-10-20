---
url: https://api.jquery.com/event.which/
scraped_at: 2025-10-20T03:12:24.651Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.whichReturns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** For key or mouse events, this property indicates the specific key or button that was pressed.

- #### version added: [1.1.3](https://api.jquery.com/category/version/1.1.3/)event.which


The `event.which` property normalizes `event.keyCode` and `event.charCode`. It is recommended to watch `event.which` for keyboard key input. For more detail, read about [event.charCode on the MDN](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode#notes).

`event.which` also normalizes button presses ( `mousedown` and `mouseup` events), reporting `1` for left button, `2` for middle, and `3` for right. Use `event.which` instead of `event.button`.

### Example 1

Log which key was depressed.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo:

### Example 2

Log which mouse button was depressed.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: