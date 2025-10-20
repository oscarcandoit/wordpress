---
url: https://api.jquery.com/next-adjacent-selector/
scraped_at: 2025-10-20T03:27:34.815Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## next adjacent selector

**Description:** Selects all next elements matching "next" that are immediately preceded by a sibling "prev".

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "prev + next" )


**prev:** Any valid selector.

**next:** A selector to match the element that is next to the first selector.


One important point to consider with both the next adjacent sibling selector ( `prev + next`) and the general sibling selector ( `prev ~ siblings`) is that the elements on either side of the combinator must share the same parent.

Finds all inputs that are next to a label.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo: