---
url: https://api.jquery.com/nth-of-type-selector/
scraped_at: 2025-10-20T03:29:27.300Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## nth-of-type selector

**Description:** Selects all elements that are the nth child of their parent in relation to siblings with the same element name.

- #### version added: [1.9](https://api.jquery.com/category/version/1.9/)jQuery( ":nth-of-type(index/even/odd/equation)" )


**index:** The index of each child to match, starting with `1`, the string `even` or `odd`, or an equation ( eg. `:nth-of-type(even)`, `:nth-of-type(4n)` )


Because jQuery's implementation of `:nth-` selectors is strictly derived from the CSS specification, the value of `n` is "1-indexed", meaning that the counting starts at 1. For other selector expressions such as [`.first()`](https://api.jquery.com/first/) or [`.eq()`](https://api.jquery.com/eq/) jQuery follows JavaScript's "0-indexed" counting.

Further discussion of this usage can be found in the [W3C CSS specification](https://www.w3.org/TR/css3-selectors/#nth-of-type-pseudo).

Find each span that is second in relation to its sibling spans.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: