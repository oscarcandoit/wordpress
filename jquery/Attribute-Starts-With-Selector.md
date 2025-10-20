---
url: https://api.jquery.com/attribute-starts-with-selector/
scraped_at: 2025-10-20T03:27:20.177Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## attributeStartsWith selector

**Description:** Selects elements that have the specified attribute with a value beginning exactly with a given string.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\[attribute^='value'\]" )


**attribute:** An attribute name.

**value:** An attribute value. Can be either a [valid identifier](https://www.w3.org/TR/css3-selectors/#attribute-selectors) or a quoted string.


This selector can be useful for identifying elements in pages produced by server-side frameworks that produce HTML with systematic element IDs. However it will be slower than using a class selector so leverage classes, if you can, to group like elements.

Finds all inputs with an attribute name that starts with 'news' and puts text in them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: