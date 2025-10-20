---
url: https://api.jquery.com/attribute-not-equal-selector/
scraped_at: 2025-10-20T03:27:17.355Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## attributeNotEqual selector

**Description:** Select elements that either don't have the specified attribute, or do have the specified attribute but not with a certain value.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\[attribute!='value'\]" )


**attribute:** An attribute name.

**value:** An attribute value. Can be either a [valid identifier](https://www.w3.org/TR/css3-selectors/#attribute-selectors) or a quoted string.


This selector is equivalent to `:not([attr='value'])`.

### Additional Notes:

- Because `[name!="value"]` is a jQuery extension and not part of the CSS specification, queries using `[name!="value"]` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `$( "your-pure-css-selector" ).not( "[name='value']" )` instead.


Finds all inputs that don't have the name 'newsletter' and appends text to the span next to it.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: