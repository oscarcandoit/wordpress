---
url: https://api.jquery.com/toArray/
scraped_at: 2025-10-20T03:16:03.158Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .toArray()Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Retrieve all the elements contained in the jQuery set, as an array.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.toArray()](https://api.jquery.com/toArray/\#toArray)

  - This method does not accept any arguments.

`.toArray()` returns all of the elements in the jQuery set:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

All of the matched DOM nodes are returned by this call, contained in a standard array:

\[<li id="foo">, <li id="bar">\]

Select all divs in the document and return the DOM Elements as an Array; then use the built-in reverse() method to reverse that array.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo: