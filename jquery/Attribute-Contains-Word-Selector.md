---
url: https://api.jquery.com/attribute-contains-word-selector/
scraped_at: 2025-10-20T03:27:08.147Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## attributeContainsWord selector

**Description:** Selects elements that have the specified attribute with a value containing a given word, delimited by spaces.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\[attribute~='value'\]" )


**attribute:** An attribute name.

**value:** An attribute value. Can be either a [valid identifier](https://www.w3.org/TR/css3-selectors/#attribute-selectors) or a quoted string.


This selector matches the test string against each word in the attribute value, where a "word" is defined as a string delimited by whitespace. The selector matches if the test string is exactly equal to any of the words.

Finds all inputs with a name attribute that contains the word 'man' and sets the value with some text.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

#### Demo: