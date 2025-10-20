---
url: https://api.jquery.com/attribute-contains-selector/
scraped_at: 2025-10-20T03:27:04.739Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## attributeContains selector

**Description:** Selects elements that have the specified attribute with a value containing a given substring.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\[attribute\*='value'\]" )


**attribute:** An attribute name.

**value:** An attribute value. Can be either a [valid identifier](https://www.w3.org/TR/css3-selectors/#attribute-selectors) or a quoted string.


This is the most generous of the jQuery attribute selectors that match against a value. It will select an element if the selector's string appears anywhere within the element's attribute value. Compare this selector with the Attribute Contains Word selector (e.g. \[attr~="word"\]), which is more appropriate in many cases.

Finds all inputs with a name attribute that contains 'man' and sets the value with some text.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: