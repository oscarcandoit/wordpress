---
url: https://api.jquery.com/All-Selector/
scraped_at: 2025-10-20T03:19:14.355Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## all selector

**Description:** Selects all elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\*" )


Caution: The all, or universal, selector is extremely slow, except when used by itself.

### Example 1

Find every element (including head, body, etc) in the document. Note that if your browser has an extension/add-on enabled that inserts a `<script>` or `<link>` element into the DOM, that element will be counted as well.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

### Example 2

Find all elements within document.body so elements like head, script, etc. are excluded.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: