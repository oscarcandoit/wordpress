---
url: https://api.jquery.com/event.timeStamp/
scraped_at: 2025-10-20T03:12:12.602Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.timeStampReturns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** The difference in milliseconds between the time the browser created the event and January 1, 1970.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/)event.timeStamp


This property can be useful for profiling event performance by getting the `event.timeStamp` value at two points in the code and noting the difference. To simply determine the current time inside an event handler, use `(new Date).getTime()` instead.

Note: Due to a [bug open since 2004](https://bugzilla.mozilla.org/show_bug.cgi?id=238041), this value is not populated correctly in Firefox and it is not possible to know the time the event was created in that browser.

Display the time since the click handler last executed.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo: