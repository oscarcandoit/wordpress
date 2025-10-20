---
url: https://api.jquery.com/event.preventDefault/
scraped_at: 2025-10-20T03:11:41.015Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.preventDefault()Returns: [undefined](http://api.jquery.com/Types/\#undefined)

**Description:** If this method is called, the default action of the event will not be triggered.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [event.preventDefault()](https://api.jquery.com/event.preventDefault/\#event-preventDefault)

  - This method does not accept any arguments.

For example, clicked anchors will not take the browser to a new URL. We can use [`event.isDefaultPrevented()`](https://api.jquery.com/event.isDefaultPrevented/) to determine if this method has been called by an event handler that was triggered by this event.

Cancel the default action (navigation) of the click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: